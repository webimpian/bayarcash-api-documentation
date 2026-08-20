# Cancel Payment Intent

***

<mark style="color:red;">v2</mark>  <mark style="color:red;">`DELETE`</mark>  `console.bayar.cash/api/v2/payment-intents/{payment_intent_id}`<br>
<mark style="color:red;">v3</mark> <mark style="color:red;">`DELETE`</mark>  `api.console.bayar.cash/v3/payment-intents/{payment_intent_id}`

***



Cancel an existing payment intent so that no further payment can be made against it. Only a payment intent that has **not** been paid and is still cancellable can be cancelled. Once cancelled, the payment intent link can no longer be used.

> Notes: A payment intent can only be cancelled while it is awaiting payment. If a transaction is currently `pending`, the payer must wait until it is finalized (`successful`/`unsuccessful`/`expired`) before the payment intent can be cancelled. A payment intent that has already been `paid` cannot be cancelled — the request will return an error response (`403` on v3, `500` on v2).

Example of sending <mark style="color:red;">`DELETE`</mark> request with cURL.



```markup
curl -X DELETE https://api.console.bayar.cash/v3/payment-intents/pi_PGPP2G \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response when the payment intent is successfully cancelled. The cancelled payment intent object is returned.



```json
{
    "type": "payment_intent", // only available on v3
    "id": "pi_PGPP2G", // only available on v3
    "status": "cancelled",
    "last_attempt": null,
    "paid_at": "",
    "order_number": "ORD001",
    "amount": "10.50",
    "currency": "MYR",
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60169166656",
    "payment_gateway": {
        "id": 1,
        "name": "FPX",
        "code": "FPX"
    },
    "attempts": []
}
```



Example of JSON structured response when the payment intent cannot be cancelled (for example, it has already been paid or a payment attempt is still pending).



```json
{
    "success": false,
    "message": "Payment intent cannot be cancelled."
}
```
