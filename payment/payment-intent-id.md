# Payment Intent ID

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/payment-intents/{payment_intent_id}`

***



At any given time, you can request a payment intent ID to check on the payment status. It will return the payment intent object.

Example of sending GET request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/payment-intents/trx_z88ymJ \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "type": "payment_intent",
    "id": "pi_PGPP2G",
    "status": "paid",
    "last_attempt": "2024-12-30 12:07:57",
    "paid_at": "2024-12-30 12:07:57",
    "order_number": "ORD001",
    "amount": "10.50",
    "currency": "MYR",
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "+60169166656",
    "attempts": [
        {
            "transaction_id": "trx_YdoXvn",
            "created_at": "2024-12-30 12:07:57",
            "payer_name": "Mohd Ali",
            "payer_email": "mohd.ali@gmail.com",
            "payer_telephone_number": "+60169166656",
            "order_number": "ORD001",
            "currency": "MYR",
            "amount": "10.50",
            "exchange_reference_number": "1-735-272-902-315691",
            "exchange_transaction_id": "2412271215020084",
            "payer_bank_name": "SBI Bank A",
            "status": 3,
            "status_description": "Approved",
            "payment_gateway": {
                "id": 1,
                "name": "FPX",
                "code": "FPX"
            }
        },
        {
            "transaction_id": "trx_GWlpvW",
            "created_at": "2024-12-27 12:15:02",
            "payer_name": "Mohd Ali",
            "payer_email": "mohd.ali@gmail.com",
            "payer_telephone_number": "+60169166656",
            "order_number": "ORD001",
            "currency": "MYR",
            "amount": "10.50",
            "exchange_reference_number": "1-735-272-902-315691",
            "exchange_transaction_id": "2412271215020084",
            "payer_bank_name": "SBI Bank A",
            "status": 2,
            "status_description": "Unsuccessful",
            "payment_gateway": {
                "id": 1,
                "name": "FPX",
                "code": "FPX"
            }
        }
    ]
}
```

