# SAML CPPM Guide

## Login Page

Menu -> Guest -> Configuration -> Pages -> Web Login -> Create New

![image](https://github.com/aruba-id-edu/guide/assets/137608707/669122c6-373c-4e42-bf12-56b027e35b18)

n= no kelompok

Name: kelompok-n

Page Name: kelompok-n

Vendor: Single Sign-on - SAML Identity Provider

![image](https://github.com/aruba-id-edu/guide/assets/137608707/8fe90e1b-532d-4c13-896c-8c3307542eb6)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/90c54fdf-d81e-4f97-a4e7-c060ee18c976)

## SAML Cert

Menu -> Policy Manager -> Administration -> Certificates -> Certificate Store -> Create Sefl-Signed Certificate

![image](https://github.com/aruba-id-edu/guide/assets/137608707/08e17a6b-5fbd-48ba-b765-a2af08fdaab5)

Certificate Type: SAML Certificate

CN: kelompok-n

Private Key Password: *

![image](https://github.com/aruba-id-edu/guide/assets/137608707/e7c5620c-f6d5-4828-8ede-ef9ebfbd7e2c)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/5e941fb3-b3c3-4988-a788-ab3aff94fddc)

## SAML IdP

Menu -> Policy Manager -> Configuration -> Identyty -> Single Sign-On -> SAML IdP Configuration -> Add Web Login Configuration

![image](https://github.com/aruba-id-edu/guide/assets/137608707/96c510e1-96c3-40ea-8f91-9d36f32fe3bc)

Page Name: kelompok-n

Identity Provider (IdP) Signing Certificate: kelompok-n

![image](https://github.com/aruba-id-edu/guide/assets/137608707/64d0383d-b474-4178-a3b5-1224a2aa16d2)

## SAML Metadata

https://sptest.iamshowcase.com/

![image](https://github.com/aruba-id-edu/guide/assets/137608707/a8651c6b-63fd-4b7b-a986-0e5bb05fbb75)

https://sptest.iamshowcase.com/instructions#start

download SP metadata

![image](https://github.com/aruba-id-edu/guide/assets/137608707/ee664fc2-fc90-4906-a3df-943914016b85)

https://sptest.iamshowcase.com/testsp_metadata.xml

Menu -> Policy Manager -> Configuration -> Identity -> Single Sign-On -> SAML IdP Configuration -> Add SP Metadata

Upload SP Metadata

![image](https://github.com/aruba-id-edu/guide/assets/137608707/8953d613-1c7e-4618-b26f-d75002c600d6)

Download IdP Metadata

![image](https://github.com/aruba-id-edu/guide/assets/137608707/a7fe7cb4-6fff-4e91-945e-72c4f5d9b685)

Edit IdP Metadata

Replace aruba-id-edu -> demo.aruba-id-edu.com

![image](https://github.com/aruba-id-edu/guide/assets/137608707/3f1202fb-41e2-4c9d-8778-2c8f36efe74d)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/0e6e6059-7b47-453d-bd40-08cec8a12b65)

Upload IdP Metadata to https://sptest.iamshowcase.com/instructions#start

![image](https://github.com/aruba-id-edu/guide/assets/137608707/d660f8f6-0b15-46da-a254-6e2bf7a89125)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/d68734ff-0560-4284-b70b-86623c93e7ef)

Copy link to somewhere = SP Link

## SAML Services

Menu -> Policy Manager -> Configuration -> Service Templates & Wizard -> ClearPass Identity Provider (SAML IdP Service)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/264439cd-b486-4a8a-ba64-1cafa558a406)

Name: kelompok-n

![image](https://github.com/aruba-id-edu/guide/assets/137608707/eaff520c-de79-4f08-84c7-a80fc78301a9)

Authentication Source: AD or LDAP

![image](https://github.com/aruba-id-edu/guide/assets/137608707/01ecc57f-c92a-4d04-b417-a6b094118d23)

Attribute Name: lastname

Attribute Value: User or DN

![image](https://github.com/aruba-id-edu/guide/assets/137608707/fb9eceb3-47f6-4a54-9954-d7015b35d9fa)

Menu -> Policy Manager -> Configuration -> Service -> saml-kelompok-n

Service Tab

Add this condition:

Type: Application:ClearPass	

Name: IdpUrl	

Operator: EQUALS	

Value: https://demo.aruba-id-edu.com/guest/kelompok-n.php

![image](https://github.com/aruba-id-edu/guide/assets/137608707/88609f1e-5e29-4e76-8fe4-c3d53c061386)

Authentication Tab

Add another Authentication Source

![image](https://github.com/aruba-id-edu/guide/assets/137608707/f35e81d9-99c8-420b-a182-9e32a9678e56)

## SAML Test

Open SP Link and login

![image](https://github.com/aruba-id-edu/guide/assets/137608707/5f5dc4df-8b6f-46f7-9c82-3868fb4170d7)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/f5fe933d-1544-413c-a01a-54445fa38ab2)

![image](https://github.com/aruba-id-edu/guide/assets/137608707/cee2c3ad-89f7-425f-a068-73225953e0af)
