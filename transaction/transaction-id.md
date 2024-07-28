# Transaction ID

***

<mark style="color:blue;">`GET`</mark> `api/v2/transactions/{transaction_id}`



At any given time, you can request a transaction ID to check on the current status. It will return the transaction object.

Sending via command line using cURL.



```markup
curl -X GET https://console.bayar.cash/api/v2/transactions/trx_z88ymJ \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <Personal_Access_Token>'
```



JSON structured response.



```json
{
  "payer_name": "Mohd Ali",
  "payer_email": "mohd.ali@gmail.com",
  "payer_telephone_number": "60199000123",
  "order_number": "874",
  "amount": "63.60",
  "url": "https://console.bayar.cash/payment-intent/pi_KYdojq"
}
```

