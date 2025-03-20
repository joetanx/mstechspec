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

### 4.2. CEF via AMA

![image](https://github.com/user-attachments/assets/12c2fc83-7385-4fb6-b5c7-c4a46752948c)

![image](https://github.com/user-attachments/assets/3c5b1289-d411-4988-aada-9194c1f9dd16)

#### 4.1.1. Install AMA on Linux machines

```sh
curl -sLO https://github.com/Azure/Azure-Sentinel/raw/refs/heads/master/DataConnectors/Syslog/Forwarder_AMA_installer.py
python Forwarder_AMA_installer.py
```

![image](https://github.com/user-attachments/assets/cefc409a-be2f-4065-a14e-bc871b0c598d)

![image](https://github.com/user-attachments/assets/efc53f7c-2c5e-4167-958f-96d723d1482d)

![image](https://github.com/user-attachments/assets/adfa069b-435d-4c45-b458-d284eb5e464d)

#### 4.1.2. Create data collection rule

![image](https://github.com/user-attachments/assets/7178cef4-c00b-42d1-8e05-facb93c5b09d)

![image](https://github.com/user-attachments/assets/c100487a-c8c0-4cdc-814e-1ce049f941e7)

![image](https://github.com/user-attachments/assets/c7ab7f94-868d-49e5-b8c9-530b2de4ffd7)

![image](https://github.com/user-attachments/assets/192c4aec-5438-4a47-ba74-02d815ad6e3d)

![image](https://github.com/user-attachments/assets/af19e8a5-18fe-45b5-b858-57524fb6d116)

#### 4.1.3. Results

![image](https://github.com/user-attachments/assets/40b88e24-71c6-44a0-a6db-ed0839a0fff0)

![image](https://github.com/user-attachments/assets/c535b12e-6c4b-430d-8d01-9d89da894aa7)

![image](https://github.com/user-attachments/assets/38936108-6805-4421-9484-d4e17f449293)

![image](https://github.com/user-attachments/assets/74a656be-859f-40fb-8dae-d482dd85aa5c)
