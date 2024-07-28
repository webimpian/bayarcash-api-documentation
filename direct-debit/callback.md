# Callback

***

<mark style="color:green;">`POST`</mark> `{return_url}`



If your server accept a callback from Bayarcash, make sure the response return `200` status code. Maximum retry from our side is 3 attempt.



***

### Authorization

JSON structured request.



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

