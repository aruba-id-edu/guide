# CPPM-Azure

## SSID

![image](https://github.com/aruba-id-edu/guide/assets/137608707/917dd7de-ed0e-41af-9a5b-d6b7fe25da0a)

Group -> Devices -> Config -> Add SSID

n= no kelompok

SSID: cloud-n

![image](https://github.com/aruba-id-edu/guide/assets/137608707/b17cf7fd-1d3b-4ef5-92bc-fd674bbae42c)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/531f3776-bdf6-4571-8d7a-388323d8a04c)

Add Captive Portal

Hostname: demo.aruba-id-edu.com

URL: /guest/cloud-n.php

![image](https://github.com/aruba-id-edu/guide/assets/137608707/a14a0127-f485-4f8a-83c8-e33788fca38f)

Add Primary Server

IP: 10.234.23.41

Shared Secret: aruba123

![image](https://github.com/aruba-id-edu/guide/assets/137608707/89b1bc69-5784-44d5-a1a0-e8cd570d9b53)

Key Management: Open

Access: Role Based

Create Microsoft Portal Role

Whitelist:

login.microsoftonline.com

*.aadcdn.microsoftonline-p.com

*.msauth.com

*.windowsazure.com

![image](https://github.com/aruba-id-edu/guide/assets/137608707/fd2f5bfc-b7b0-4e72-863c-725dfd9bb0bc)

Assign Pre-Authentication Role

![image](https://github.com/aruba-id-edu/guide/assets/137608707/1ab2caee-77c2-4dfc-83ec-382d052f8464)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/127f919e-0a3b-4655-b50e-a1e7e4d5e767)

## Login Page

Menu -> Guest -> Configuration -> Pages -> Web Login -> Create New

![image](https://github.com/aruba-id-edu/guide/assets/137608707/c12dcadc-f713-4629-936c-b65367ad9a2b)

n= no kelompok

Name: cloud-n

Page Name: cloud-n

Vendor: Aruba

Address: securelogin.hpe.com

Custom Form: yes

Pre-Auth Check: none

Prevent CNA: Yes

Cloud Identity: Enabled

Log Debugging Data: Yes

Add New Authentication Provider

![image](https://github.com/aruba-id-edu/guide/assets/137608707/0c3601d0-4928-451f-8063-dadef1e74ec1)

Show Advanced: yes

Auto Redirect: yes

Endpoint Attributes: Create additional Endpoint attributes converting any arrays to JSON

Group Membership: yes

![image](https://github.com/aruba-id-edu/guide/assets/137608707/c3af5a6d-c078-44a3-aa36-07e08b58fd9a)

## Captive Portal Service

Menu -> Policy Manager -> Configuration -> Service Templates & Wizard -> Cloud Identity / Social Media Authentication

![image](https://github.com/aruba-id-edu/guide/assets/137608707/2857ab47-9d86-4c32-a914-5d2b14fd99ec)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/b60cc6ed-85cb-4230-87f8-1ccd597dde81)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/0de2fcc8-eb6d-41f2-80b7-c6b1d1054ff5)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/8862c464-dfd5-49df-816f-3575f5dc88ed)

Menu -> Policy Manager -> Configuration -> Service -> cloud-n

![image](https://github.com/aruba-id-edu/guide/assets/137608707/66a6c9db-4e91-49f0-a5d7-5b2f289b4085)

Service Tab

![image](https://github.com/aruba-id-edu/guide/assets/137608707/206331d1-3e60-4c08-9b08-61bdc2b97c8c)

Add this condition:

Type: Radius:Aruba

Name: Aruba-Essid-Name

Operator: EQUALS

Value: cloud-n

Roles Tab

![image](https://github.com/aruba-id-edu/guide/assets/137608707/db334127-17cb-4776-ae9a-624f9c200880)

Role Mapping Policy: --Select--

Enforcement Tab

![image](https://github.com/aruba-id-edu/guide/assets/137608707/59bfdb0e-2ca4-4a83-b062-ff9c47fda5a9)

Modify Enforcement Policy

![image](https://github.com/aruba-id-edu/guide/assets/137608707/b8bd5e40-c1d4-4437-b4a3-36ff9dcb02c5)

Rules Tab

Edit 1st condition

![image](https://github.com/aruba-id-edu/guide/assets/137608707/c00e4d3c-c2f2-40cb-a830-398f454dd4b3)

Change google to azure

save

## Connect to SSID

![image](https://github.com/aruba-id-edu/guide/assets/137608707/20dd82b5-cd72-4b7b-8f81-c4896da31e8f)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/2db20937-5046-4b1a-b8f4-911799aefe41)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/67dd46cd-88f3-4063-b6f0-82b4f668d719)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/3ad4ff9b-89df-428a-a82d-0634171b4ac5)
