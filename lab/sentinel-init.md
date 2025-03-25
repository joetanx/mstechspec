## 1. Create log analytics workspace

![image](https://github.com/user-attachments/assets/b7141a21-9e1b-472e-b8ae-7b828a94c9f0)

![image](https://github.com/user-attachments/assets/9d74a56e-4f40-4713-9c96-073b906e7be1)

![image](https://github.com/user-attachments/assets/5462a12b-ac67-4970-a580-1075b2431d23)

![image](https://github.com/user-attachments/assets/66453802-162a-4715-a88b-f7139184b0ff)

![image](https://github.com/user-attachments/assets/cf9af924-6301-4fcb-a077-c1ec4d966d4c)

## 2. Create Sentinel workspace

![image](https://github.com/user-attachments/assets/fd663bb9-8da7-4719-a997-a7f4f7f95d98)

![image](https://github.com/user-attachments/assets/2df8c244-7693-4365-b4b6-47b4fa9a518b)

![image](https://github.com/user-attachments/assets/65d73e39-8597-4915-956b-e55dd46cfef1)

![image](https://github.com/user-attachments/assets/0c83a6d6-a59c-4c30-98f7-df4a7c7f778a)

## 3. Essential Sentinel solutions

Install Sentinel solutions: left pane → Content management → Content hub

![image](https://github.com/user-attachments/assets/edb5804d-80bc-46c6-b2d7-a881c0e56661)

|Solution||
|---|---|
|Azure Activity|![image](https://github.com/user-attachments/assets/6faae0ac-f746-43e3-9839-2ee0ecd82d8a)|
|Defender for Cloud|![image](https://github.com/user-attachments/assets/6c55ca54-9b5f-47f4-ba51-8d64d27fc73b)|
|Windows Security Events|![image](https://github.com/user-attachments/assets/99e19ad4-d811-438b-8b9f-72edd8f0e79e)|
|Windows Forwarded Events|![image](https://github.com/user-attachments/assets/1047fe4e-f402-439e-b2a4-d8c4c5d0ae70)|
|Common Event Format|![image](https://github.com/user-attachments/assets/da9da109-c3ed-4cfc-9c35-182b6ad67024)|
|Syslog|![image](https://github.com/user-attachments/assets/5468f1dd-6d0b-43f6-81d6-890a44aed7c0)|
|Sentinel SOAR Essentials|![image](https://github.com/user-attachments/assets/91672ea7-ed56-4085-a06f-f1e092686434)|
|Threat Intelligence|![image](https://github.com/user-attachments/assets/2b4bcfa5-3ad1-4076-a3fa-c9b3e53906c8)|

Data connectors available after installation:

![image](https://github.com/user-attachments/assets/b4df07c8-6496-4757-94b3-8627eeb8f57b)

## 4. Ingestion

### 4.1. Windows Security Events via AMA

Ref: https://learn.microsoft.com/en-us/azure/sentinel/connect-services-windows-based

![image](https://github.com/user-attachments/assets/b43b9062-09f6-43d8-9772-378fd9d9448f)

![image](https://github.com/user-attachments/assets/6ce7047d-b0e0-4b3b-9b5d-3b00f2c75369)

#### 4.1.1. Create data collection rule

![image](https://github.com/user-attachments/assets/624d6246-2cdf-41ff-91dc-8a1151abfeda)

Select the resources that the DCR will cover:

> [!Note]
>
> At the end of this process, the Azure Monitor Agent will be installed on any selected machines that don't already have it installed.

![image](https://github.com/user-attachments/assets/31d33f09-c475-4867-b238-f3d3ddf4a79b)

![image](https://github.com/user-attachments/assets/46d256ad-be37-4425-b215-94d19e3af3f5)

![image](https://github.com/user-attachments/assets/89c20321-2e82-49a4-8c50-e59ed8d1613e)

![image](https://github.com/user-attachments/assets/235cac21-4d0e-4c14-8dfe-d5eeecf66cbe)

#### 4.1.2. Results

![image](https://github.com/user-attachments/assets/9dd40d4c-414b-4572-b1bc-d950280602f7)

![image](https://github.com/user-attachments/assets/7788843e-2f00-433f-ad78-8b450b304ad6)

![image](https://github.com/user-attachments/assets/1baf6220-5d03-4aa8-bf20-3fb4f4d4a95d)

![image](https://github.com/user-attachments/assets/97fdb096-1118-4050-a9a7-a99218e4f707)

### 4.2. Windows Forwarded Events

![image](https://github.com/user-attachments/assets/9f216be8-e03e-43db-8efb-25f895154f84)

![image](https://github.com/user-attachments/assets/42cd0c88-968d-41dd-9ea1-a812547bdfaa)

#### 4.2.1. Create data collection rule

![image](https://github.com/user-attachments/assets/8d57affc-91c0-45d5-85f2-d2f5b1335407)

Select the Windows events collector:

![image](https://github.com/user-attachments/assets/40c76178-ab34-4557-ac6a-4be25938fa42)

![image](https://github.com/user-attachments/assets/1da74e00-73b2-471f-8285-5aa215d115a8)

![image](https://github.com/user-attachments/assets/e4bc6935-cadf-4566-b0b6-139f1dca49bc)

![image](https://github.com/user-attachments/assets/e9087b81-4999-470b-ba46-38d7eba3f203)

#### 4.2.2. Results

![image](https://github.com/user-attachments/assets/fabcc5b5-e077-4079-9c96-e18a32724e6b)

### 4.3. Syslog via AMA

![image](https://github.com/user-attachments/assets/45698c20-9b7f-4969-83d1-e08922a20039)

![image](https://github.com/user-attachments/assets/b47c16bf-8e1f-4759-a8b8-aac007f089d9)

#### 4.3.1. Install AMA on Linux machines

```sh
curl -sLO https://github.com/Azure/Azure-Sentinel/raw/refs/heads/master/DataConnectors/Syslog/Forwarder_AMA_installer.py
python Forwarder_AMA_installer.py
```

![image](https://github.com/user-attachments/assets/cefc409a-be2f-4065-a14e-bc871b0c598d)

![image](https://github.com/user-attachments/assets/efc53f7c-2c5e-4167-958f-96d723d1482d)

![image](https://github.com/user-attachments/assets/adfa069b-435d-4c45-b458-d284eb5e464d)

#### 4.3.2. Create data collection rule

![image](https://github.com/user-attachments/assets/e5671eda-c7c6-43eb-8a40-4b8ce1f44c32)

![image](https://github.com/user-attachments/assets/d4cbd91f-4365-4bc3-9b09-1656187551b2)

![image](https://github.com/user-attachments/assets/c100487a-c8c0-4cdc-814e-1ce049f941e7)

![image](https://github.com/user-attachments/assets/8b1da32c-32d6-479b-b7c1-efa3f2eee565)

![image](https://github.com/user-attachments/assets/af19e8a5-18fe-45b5-b858-57524fb6d116)

#### 4.3.3. Results

![image](https://github.com/user-attachments/assets/40b88e24-71c6-44a0-a6db-ed0839a0fff0)

![image](https://github.com/user-attachments/assets/c535b12e-6c4b-430d-8d01-9d89da894aa7)

![image](https://github.com/user-attachments/assets/38936108-6805-4421-9484-d4e17f449293)

Check AMA status `systemctl status azuremonitor*`:

![image](https://github.com/user-attachments/assets/9e9a851f-3ef3-4695-b437-b4ace22b9360)

![image](https://github.com/user-attachments/assets/14d24b5f-d67c-4592-99c8-b09e859d23df)
