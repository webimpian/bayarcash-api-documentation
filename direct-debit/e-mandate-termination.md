# e-Mandate Termination

***

<mark style="color:red;">v2</mark>  <mark style="color:red;"></mark><mark style="color:red;">`DELETE`</mark>  `console.bayar.cash/api/v2/mandates/{mandate_id}`\
<mark style="color:red;">v3</mark> <mark style="color:red;">`DELETE`</mark>  `api.console.bayar.cash/v3/mandates/{mandate_id}`

***



Example of JSON structured response.



```json
{
    "payer_name": "Mohd Ali",
    "payer_id_type": 1,
    "payer_id": "910109021234",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60198109001",
    "order_number": "DD001",
    "amount": 30,
    "application_type": "Termination",
    "application_reason": "Termination of DD001",
    "frequency_mode": "YR",
    "effective_date": "2024-06-15",
    "expiry_date": "2024-08-15",
    "url": "https://console.bayar.cash/payment-intent/pi_pGwZaY"
}
```

