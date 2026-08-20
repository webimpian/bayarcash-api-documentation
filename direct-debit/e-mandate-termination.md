# e-Mandate Termination

***

<mark style="color:red;">v2</mark><mark style="color:red;">`DELETE`</mark>  `console.bayar.cash/api/v2/mandates/{mandate_id}`<br>
<mark style="color:red;">v3</mark><mark style="color:red;">`DELETE`</mark>  `api.console.bayar.cash/v3/mandates/{mandate_id}`

***



Terminate an existing Direct Debit (e-Mandate). The mandate must be `active`. The `order_number` is taken from the mandate and does not need to be supplied.



<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>application_reason</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>link_expired_at</code></td><td>Mandate link expiry datetime (<code>Y-m-d H:i:s</code>). Defaults to 1 hour from creation</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:red;">`DELETE`</mark> request with cURL.



```markup
curl -X DELETE https://api.console.bayar.cash/v3/mandates/md_MGWpzp \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
          "application_reason": "Termination for DD001"
      }'
```



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

