# e-Mandate Maintenance

***

<mark style="color:red;">v2</mark>  <mark style="color:orange;">`PUT`</mark>  `console.bayar.cash/api/v2/mandates/{mandate_id}`<br>
<mark style="color:red;">v3</mark>  <mark style="color:orange;">`PUT`</mark>  `api.console.bayar.cash/v3/mandates/{mandate_id}`

***



Update an existing Direct Debit (e-Mandate). The mandate must be `active`. The `order_number` is taken from the mandate and does not need to be supplied.



<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>amount</code></td><td>Between 5.00 and 30000.00</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_email</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_telephone_number</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>frequency_mode</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>max_frequency</code></td><td>Maximum number of charges within a collection cycle. Defaults to 9</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>application_reason</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>metadata</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>link_expired_at</code></td><td>Mandate link expiry datetime (<code>Y-m-d H:i:s</code>). Defaults to 1 hour from creation</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:orange;">`PUT`</mark> request with cURL.



```markup
curl -X PUT https://api.console.bayar.cash/v3/mandates/md_MGWpzp \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
          "amount": 100,
          "payer_email": "mohd.ali@gmail.com",
          "payer_telephone_number": "60191122000",
          "frequency_mode": "MT",
          "max_frequency": 9,
          "application_reason": "Maintenance for DD001"
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
    "application_type": "Maintenance",
    "application_reason": "Maintenance of DD001",
    "frequency_mode": "YR",
    "effective_date": "2024-06-15",
    "expiry_date": "2024-08-15",
    "url": "https://console.bayar.cash/payment-intent/pi_pGwZaY"
}
```

