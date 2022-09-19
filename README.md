## Base URL :

    https://jumia-samir-hussein.vercel.app/apis

## Company Admin Account

    email: nziemann@example.net
    password: 12345678

## Contents

-   [Company Account APIs](#Company-Account-APIs)
-   [Customer Account APIs](#Customer-Account-APIs)

## **Company Account APIs**

### Company Account login

<b>POST :</b>

    /company/login

<b>Headers :</b>

    Accept : Application/json

<b>Parameters :</b>

    email (required)
    password (required)

### Company Account register

#### (only admin account can create new account)

<b>POST :</b>

    /company/register

<b>Headers :</b>

    Accept : Application/json
    Authorization : "Bearer {company_token}"

<b>Parameters :</b>

    name (required)
    email (required)
    role (required | [admin , customer service , seller service])

### Company Account verify

<b>POST :</b>

    /company/verify

<b>Headers :</b>

    Accept : Application/json

<b>Parameters :</b>

    token (required)
    email (required)
    password (required | min:8)
    password_confirmation (required)

### Company Account logout

<b>GET :</b>

    /company/logout

<b>Headers :</b>

    Accept : Application/json
    Authorization : "Bearer {company_token}"

### Company Account Update Information

#### (only admin account can change the role of any account)

<b>PUT :</b>

    /company/account/{account_id}/update

<b>Headers :</b>

    Accept : Application/json
    Authorization : "Bearer {company_token}"

<b>Parameters :</b>

    name (optional)
    img (optional | mimes:jpeg,jpg,png,webp | max:10MB)
    password (optional | min:8)
    password_confirmation (required with password)
    old_password (required with password)
    role (optional)

### Company Account Delete

#### (only admin account can delete any account)

<b>DELETE :</b>

    /company/account/{account_id}/delete

<b>Headers :</b>

    Accept : Application/json
    Authorization : "Bearer {company_token}"

## Customer Account APIs

### Customer Account login

<b>POST :</b>

    /customer/login

<b>Headers :</b>

    Accept : Application/json

<b>Parameters :</b>

    email (required)
    password (required)

### Customer Account register

<b>POST :</b>

    /customer/register

<b>Headers :</b>

    Accept : Application/json

<b>Parameters :</b>

    name (required)
    email (required)
    phone (required)
    password (required | min:8)
    password_confirmation (required)

### Customer Account logout

<b>GET :</b>

    /customer/logout

<b>Headers :</b>

    Accept : Application/json
    Authorization : "Bearer {customer_token}"
