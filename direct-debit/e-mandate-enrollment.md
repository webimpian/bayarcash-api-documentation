---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# e-Mandate Enrollment

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `console.bayar.cash/api/v2/mandates`<br>
<mark style="color:red;">v3</mark> <mark style="color:green;">`POST`</mark>  `api.console.bayar.cash/v3/mandates`

***



Initialize enrollment request to Bayarcash. Make sure your account is enabled for Direct Debit payment channel.



***

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>portal_key</code></td><td>Portal key retrieve from Bayarcash console</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>order_number</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>amount</code></td><td>Between 5.00 and 30000.00</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_id_type</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_id</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_name</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_email</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_telephone_number</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_bank_code</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>payer_bank_code_hashed</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>frequency_mode</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>max_frequency</code></td><td>Maximum number of charges within a collection cycle. Defaults to 9</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>application_reason</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>effective_date</code></td><td>Defaults to the next day</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>expiry_date</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>metadata</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>return_url</code></td><td>Callback data will be sent to this URL</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>success_url</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>failed_url</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>maintenance_url</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>termination_url</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>link_expired_at</code></td><td>Mandate link expiry datetime (<code>Y-m-d H:i:s</code>). Defaults to 1 hour from creation</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:green;">`POST`</mark> request with cURL.



```markup
curl -X POST https://api.console.bayar.cash/v3/mandates \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
          "portal_key": string,
          "order_number": DD001,
          "amount": 100,
          "payer_id_type": 1,
          "payer_id": "123456121234",
          "payer_name": "Mohd Ali",
          "payer_email": "mohd.ali@gmail.com",
          "payer_telephone_number": "60191122000",
          "frequency_mode": "MT",
          "application_reason": "Enrollment for DD001",
          "effective_date": "2024-08-01",
          "expiry_date": "2025-07-01",
          "metadata": string,
          "return_url": "https://website.net/callback",
          "success_url": "https://website.net/success",
          "failed_url": "https://website.net/failed",
          "checksum": string
      }'
```



Example of JSON structured response.



```json
{
    "payer_name": "Mohd Ali",
    "payer_id_type": 1,
    "payer_id": "910109021234",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60196019001",
    "order_number": "DD001",
    "amount": 30,
    "application_type": "Enrollment",
    "application_reason": "Enrollment of DD001",
    "frequency_mode": "MT",
    "effective_date": "2024-06-15",
    "expiry_date": "2024-08-15",
    "url": "https://console.bayar.cash/payment-intent/pi_pGwZaY"
}
```

