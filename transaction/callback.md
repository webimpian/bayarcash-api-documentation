# Callback

***

<mark style="color:green;">`POST`</mark> `{return_url}`



If your server accept a callback from Bayarcash, make sure the response return `200` status code. Maximum retry from our side is 3 attempt. Below are the status value & its corresponding label.



| Status Code | Status Description |
| ----------- | ------------------ |
| 0           | New                |
| 1           | Pending            |
| 2           | Failed             |
| 3           | Success            |
| 4           | Cancelled          |



***

### Pre-Transaction

JSON structured request.



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

JSON structured request.



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

