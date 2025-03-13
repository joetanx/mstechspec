## 4. Deploy [Users App](https://github.com/joetanx/usersapp) on Azure VM

Adapted from [manual install](https://github.com/joetanx/usersapp#4-deployment-via-manual-install) of [Users App](https://github.com/joetanx/usersapp) to install on Ubuntu

### 4.1. Preparation

Install necessary packages:

```sh
apt update
apt -y install mysql-server postgresql nodejs npm jq
```

### 4.2. Setup Databases

#### 4.2.1. MySQL

Set MySQL to listen on `0.0.0.0`

```sh
sed -i '/bind-address/s/127.0.0.1/0.0.0.0/' /etc/mysql/mysql.conf.d/mysqld.cnf
systemctl restart mysql
```

```console
root@ubuntu-vm:~# grep bind-address /etc/mysql/mysql.conf.d/mysqld.cnf
bind-address            = 0.0.0.0
mysqlx-bind-address     = 0.0.0.0
root@ubuntu-vm:~# ss -plntu | grep mysqld
tcp   LISTEN 0      151          0.0.0.0:3306       0.0.0.0:*    users:(("mysqld",pid=10198,fd=23))
tcp   LISTEN 0      70           0.0.0.0:33060      0.0.0.0:*    users:(("mysqld",pid=10198,fd=21))
```

Populate MySQL database:

```sh
curl -sLo /tmp/users-my.sql https://github.com/joetanx/usersapp/raw/main/users-my.sql
mysql -u root < /tmp/users-my.sql
```

Create `node` database user:

```sh
mysql -u root -e "CREATE USER 'node'@'%' IDENTIFIED BY 'password';"
mysql -u root -e "GRANT ALL PRIVILEGES ON users.* TO 'node'@'%';"
```

<details><summary>MySQL Test Queries:</summary>

Retrieve a random row:

```sh
mysql -u root -e "SELECT id,firstName,lastName,username,email,mobile,password FROM users.users ORDER BY RAND() LIMIT 0,1;"
```

Search for a user:

```sh
mysql -u root -e "SELECT id,firstName,lastName,username,email,mobile,password FROM users.users WHERE firstName LIKE '%jack%';"
```

</details>

#### 4.2.2. PostgreSQL

Populate PostgreSQL database:

```sh
curl -sLo /tmp/users-pg.sql https://github.com/joetanx/users-app/raw/main/users-pg.sql
sudo -u postgres psql -d postgres -f /tmp/users-pg.sql
```

Configure `/etc/postgresql/16/main/pg_hba.conf` to listen on all addresses:

```sh
sed -i '0,/127.0.0.1\/32/s//0.0.0.0\/0   /' /etc/postgresql/16/main/pg_hba.conf
```

```console
root@ubuntu-vm:~# grep -A1 'IPv4 local connections' /etc/postgresql/16/main/pg_hba.conf
# IPv4 local connections:
host    all             all             0.0.0.0/0               scram-sha-256
```

Configure `/etc/postgresql/16/main/postgresql.conf` to listen on all addresses and enable `scram-sha-256` hashing:

```sh
sed -i '/listen_addresses/s/^#//' /etc/postgresql/16/main/postgresql.conf
sed -i '/password_encryption/s/^#//' /etc/postgresql/16/main/postgresql.conf
```

```console
root@ubuntu-vm:~# grep listen_addresses /etc/postgresql/16/main/postgresql.conf
listen_addresses = 'localhost'          # what IP address(es) to listen on;
root@ubuntu-vm:~# grep password_encryption /etc/postgresql/16/main/postgresql.conf
password_encryption = scram-sha-256     # scram-sha-256 or md5
```

Restart PostgreSQL:

```sh
systemctl restart postgresql
```

Create `node` database user:

```
sudo -u postgres psql -c "CREATE ROLE node WITH LOGIN PASSWORD 'password';"
sudo -u postgres psql -d users -c "GRANT ALL ON users TO node;"
sudo -u postgres psql -d users -c "GRANT USAGE ON SEQUENCE users_id_seq TO node;"
```

Reset user password (if needed):

```
sudo -u postgres psql -c "ALTER USER node WITH PASSWORD 'password';"
```

<details><summary>PostgreSQL Test Queries:</summary>

Retrieve a random row:

```sh
sudo -u postgres psql -d users -c "SELECT id,firstName,lastName,username,email,mobile,password FROM users ORDER BY RANDOM() LIMIT 1 OFFSET 0;"
```

Search for a user:

```sh
sudo -u postgres psql -d users -c "SELECT id,firstName,lastName,username,email,mobile,password FROM users WHERE LOWER(firstName) LIKE '%jack%';"
```

</details>

#### 4.2.3. Clean-up

```sh
rm -f /tmp/users-my.sql /tmp/users-pg.sql
```

### 4.3. Deploy Node.js Application

Install NPM modules, create `.env` file and download keys, application code and view templates:

> [!Note]
>
> Below commands uses keys from [lab-cert](https://github.com/joetanx/lab-certs) for JWT authentication and set connection details such as hostname and credentials on the `.env` file
>
> Change these as needed
>
> `DB_TYPE` can also be changed to `postgresql` to use PostgreSQL

```sh
mkdir -p /etc/usersapp/views /etc/usersapp/pki
npm install express express-session mysql2 pg path dotenv bcrypt hbs jsonwebtoken cookie-parser
cat << EOF > /etc/usersapp/.env
DB_TYPE = mysql
DB_HOST = $(hostname)
DB_NAME = users
DB_USER = node
DB_PASSWORD = password
JWT_PRIVATE_KEY = /etc/usersapp/pki/jwt.key
JWT_PUBLIC_KEY = /etc/usersapp/pki/jwt.pem
EOF
curl -sLo /etc/usersapp/pki/jwt.key https://github.com/joetanx/lab-certs/raw/main/ca/lab_issuer.key
curl -sLo /etc/usersapp/pki/jwt.pem https://github.com/joetanx/lab-certs/raw/main/ca/lab_issuer.pem
curl -sLo /etc/usersapp/app.js https://github.com/joetanx/usersapp/raw/main/app.js
curl -sLo /etc/usersapp/views/index.hbs https://github.com/joetanx/usersapp/raw/main/index.html
curl -sLo /etc/usersapp/views/login.hbs https://github.com/joetanx/usersapp/raw/main/login.html
curl -sLo /etc/usersapp/views/register.hbs https://github.com/joetanx/usersapp/raw/main/register.html
curl -sLo /etc/usersapp/views/home.hbs https://github.com/joetanx/usersapp/raw/main/home.html
curl -sLo /etc/usersapp/views/message.hbs https://github.com/joetanx/usersapp/raw/main/message.html
```

Create `systemd` unit file for the application:

```sh
cat << EOF > /lib/systemd/system/usersapp.service
[Unit]
Description=Run node.js usersapp
After=network.target

[Service]
Type=simple
ExecStart=/usr/bin/node /etc/usersapp/app.js
WorkingDirectory=/etc/usersapp

[Install]
WantedBy=multi-user.target
EOF
```

Enable and start the application:

```console
root@ubuntu-vm:~# systemctl enable --now usersapp
Created symlink /etc/systemd/system/multi-user.target.wants/usersapp.service → /usr/lib/systemd/system/usersapp.service.
root@ubuntu-vm:~# systemctl status usersapp
● usersapp.service - Run node.js usersapp
     Loaded: loaded (/usr/lib/systemd/system/usersapp.service; enabled; preset: enabled)
     Active: active (running) since Thu 2025-03-13 20:48:00 +08; 7s ago
   Main PID: 10489 (node)
      Tasks: 14 (limit: 4610)
     Memory: 35.2M (peak: 35.7M)
        CPU: 257ms
     CGroup: /system.slice/usersapp.service
             └─10489 /usr/bin/node /etc/usersapp/app.js

Mar 13 20:48:00 ubuntu-vm systemd[1]: Started usersapp.service - Run node.js usersapp.
Mar 13 20:48:01 ubuntu-vm node[10489]: Verification service listening at http://azcm-ubuntu:3000
```

![image](https://github.com/user-attachments/assets/34d0a0ca-5baa-4901-a631-99d1f9d3d0aa)
