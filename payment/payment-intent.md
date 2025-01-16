# Payment Intent

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `console.bayar.cash/api/v2/payment-intents`\
<mark style="color:red;">v3</mark>  <mark style="color:green;">`POST`</mark>  `api.console.bayar.cash/v3/payment-intents`

***



Initialize payment intent request to Bayarcash. Make sure your account is enabled for selected payment channel. By default only FPX channel is activated.



***

<table data-full-width="true"><thead><tr><th width="269">Name</th><th width="546">Description</th><th width="121">Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>payment_channel</code></td><td>Refer payment channel page</td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>portal_key</code></td><td>Portal key retrieve from Bayarcash console</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>order_number</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>amount</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_name</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_email</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_telephone_number</code></td><td>Currently we only accept Malaysia number</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>payer_bank_code</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>payer_bank_name</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>metadata</code></td><td>Currently only support order items from WooCommerce plugin</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>return_url</code></td><td>Server to browser redirect callback (use <mark style="color:blue;"><code>GET</code></mark>)</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>callback_url</code></td><td>Server to server redirect callback (use <mark style="color:green;"><code>POST</code></mark>) - only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:green;">`POST`</mark> request with cURL.



```markup
curl -X POST https://api.console.bayar.cash/v3/payment-intents \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
        "payment_channel": 5,
        "portal_key": string,
        "order_number": string,
        "amount": 100,
        "payer_name": string,
        "payer_email": string,
        "payer_telephone_number": integer,
        "payer_bank_code": string,
        "payer_bank_name": string,
        "metadata": string,
        "return_url": string,
        "platform_id": string,
        "checksum": string
      }'
```



Example of JSON structured response.



```json
{
    "type": "payment_intent", // only available on v3
    "id": "pi_MGWpzp", // only available on v3
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60193000123",
    "order_number": "1351",
    "amount": "21.10",
    "url": "https://console.bayar.cash/payment-intent/pi_MGWpzp"
}
```

