# Callback

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `{return_url}`\
<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `{return_url}`

***



If your server accept a callback from Bayarcash, make sure the response return `200` status code. Maximum retry from our side is 5 attempts every 300 seconds (5 minutes). Below are the status value & its corresponding label.



| Status Code | Status Description |
| ----------- | ------------------ |
| 0           | New                |
| 1           | Pending            |
| 2           | Failed             |
| 3           | Success            |
| 4           | Cancelled          |



***

### Pre-Transaction

Example of JSON structured request.



```json
{
    "record_type": "pre_transaction",
    "transaction_id": string,
    "exchange_reference_number": string,
    "order_number": string,
    "checksum": string
}
```



***

### Transaction

Example of JSON structured request.



```json
{
    "record_type": "transaction",
    "transaction_id": string,
    "exchange_reference_number": string,
    "exchange_transaction_id": string,
    "order_number": string,
    "currency": string,
    "amount": string,
    "payer_name": string,
    "payer_email": string,
    "payer_bank_name": string,
    "status": integer,
    "status_description": string,
    "datetime": string,
    "checksum": string
}
```



***

### Transaction Receipt

Example of JSON structured request.



```json
{
    "transaction_id": string,
    "exchange_reference_number": string,
    "exchange_transaction_id": string,
    "order_number": string,
    "currency": string,
    "amount": string,
    "payer_bank_name": string,
    "status": string,
    "status_description": string,
    "checksum": string
}
```

