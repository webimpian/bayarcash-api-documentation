# Callback

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `{return_url}` \
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `{return_url}`

***



If your server accept a callback from Bayarcash, make sure the response return `200` status code. Maximum retry from our side is 5 attempts every 300 seconds (5 minutes). Below are the status value & its corresponding label.



***

### Authorization

Example of JSON structured request. Applicable to enrollment, maintenance and termination.



```json
{
    "record_type": "authorization",
    "transaction_id": string,
    "mandate_id": string,
    "exchange_reference_number": string,
    "exchange_transaction_id": string,
    "order_number": 100,
    "currency": string,
    "amount": string,
    "payer_name": string,
    "payer_email": string,
    "payer_bank_name": string,
    "status": string,
    "status_description": string,
    "datetime": string,
    "checksum": string
}
```



***

### Bank Approval

Example of JSON structured request. Applicable to enrollment, maintenance and termination.



```json
{
    "record_type": "bank_approval",
    "approval_date": string,
    "approval_status": string,
    "mandate_id": string,
    "mandate_reference_number": string,
    "order_number": string,
    "payer_bank_code_hashed": string,
    "payer_bank_code": string,
    "payer_bank_account_no": string,
    "application_type": 01,
    "checksum": string
}
```



***

### Transaction

Example of JSON structured request. Only applicable to enrollment.



```json
{
    "record_type": "transaction",
    "batch_number": string,
    "mandate_id": string,
    "mandate_reference_number": string,
    "transaction_id": string,
    "datetime": string,
    "reference_number": string,
    "amount": 100,
    "status": string,
    "status_description": string,
    "cycle": 1,
    "checksum": string
}
```

