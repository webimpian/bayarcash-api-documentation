# Payment Intent

***

<mark style="color:green;">`POST`</mark> `/api/v2/payment-intents`&#x20;



Initialize payment intent request to Bayarcash. Make sure your account is enabled for selected payment channel. By default only FPX channel is activated.



***

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>payment_channel</code></td><td>Please <a href="https://api.webimpian.support/bayarcash/transaction/initialize-payment#payment-channel">refer below reference</a></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>portal_key</code></td><td>Portal key retrieve from Bayarcash console</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>order_number</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>amount</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_name</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_email</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>payer_telephone_number</code></td><td>Currently we only accept MY</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>payer_bank_code</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>payer_bank_name</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>metadata</code></td><td>Currently only support order items from WooCommerce plugin</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>return_url</code></td><td>Callback data will be sent to this URL</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>platform_id</code></td><td></td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>checksum</code></td><td></td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Sending via command line using cURL.



```markup
curl -X POST https://console.bayar.cash/api/v2/payment-intents \
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



JSON structured response.



```json
{
    "payer_name": "Mohd Ali",
    "payer_email": "mohd.ali@gmail.com",
    "payer_telephone_number": "60193000123",
    "order_number": "1351",
    "amount": "21.10",
    "url": "https://console.bayar.cash/payment-intent/pi_MGWpzp"
}
```



***

### Payment Channel

Make sure you have activate below payment channel before making any request to our endpoint.



| Code | Description                                                    |
| ---- | -------------------------------------------------------------- |
| `1`  | FPX (Default payment channel)                                  |
| `2`  | Manual Bank Transfer                                           |
| `3`  | Direct Debit (enrollment, maintenance and termination via FPX) |
| `4`  | FPX Line of Credit                                             |
| `5`  | DuitNow Online Banking/Wallets                                 |
| `6`  | DuitNow QR                                                     |
| `7`  | SPayLater (BNPL from Shopee)                                   |
| `8`  | Boost PayFlex (BNPL from Boost)                                |
| `9`  | QRIS Indonesia Online Banking                                  |
| `10` | QRIS Indonesia eWallet                                         |

