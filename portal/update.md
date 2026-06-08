# Update Portal

***

<mark style="color:red;">v2</mark>  <mark style="color:orange;">`PUT`</mark>  `console.bayar.cash/api/v2/portals/{portal_id}`<br>
<mark style="color:red;">v3</mark> <mark style="color:orange;">`PUT`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Update an existing portal. `FPX` is always enabled. The payment channels provided must already be subscribed by the merchant. The updated portal object is returned.



<table data-full-width="true"><thead><tr><th width="269">Name</th><th width="546">Description</th><th width="121">Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>name</code></td><td>Portal name. Must be unique for the merchant</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>merchant_transaction_notification_email</code></td><td>Email address to receive transaction notifications</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>url</code></td><td>Portal website URL (named <code>website_url</code> on v3)</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>secondary_merchant_transaction_notification_email</code></td><td>Secondary notification email - only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>payment_channels</code></td><td>Array of payment channel IDs to enable. Refer payment channel page</td><td><code>array</code></td><td>Optional</td></tr><tr><td><code>bank_accounts</code></td><td>Required when Manual Bank Transfer (2) is enabled. Array of <code>{ account_no, bank_id, payment_gateway_id }</code></td><td><code>array</code></td><td>Optional</td></tr><tr><td><code>enabled_sms_on_successful_transaction</code></td><td>Enable SMS notification on a successful transaction</td><td><code>boolean</code></td><td>Optional</td></tr><tr><td><code>split_payment_enabled</code></td><td>Enable split payment - only available on v3</td><td><code>boolean</code></td><td>Optional</td></tr><tr><td><code>split_payment_merchants</code></td><td>Array of <code>{ merchant_email, type (fix_amount/percentage), value }</code> - only available on v3</td><td><code>array</code></td><td>Optional</td></tr><tr><td><code>cashier_id</code></td><td>Required when DuitNow QR (6) is enabled - only available on v3</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>enable_incoming_transaction_webhook</code></td><td>Enable incoming transaction webhook - only available on v2</td><td><code>boolean</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:orange;">`PUT`</mark> request with cURL.



```markup
curl -X PUT https://api.console.bayar.cash/v3/portals/prt_PGMo1q \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
        "name": "Payment Link",
        "website_url": "https://bcl.my/",
        "merchant_transaction_notification_email": "hai@bayarcash.com",
        "payment_channels": [3, 4]
      }'
```



Example of JSON structured response.



```json
{
    "id": "prt_PGMo1q",
    "created_at": "2024-10-19 12:47:07",
    "portal_key": "8baf5e234dd88c2d1375d5f386d78d8f",
    "portal_name": "Payment Link",
    "url": "https://bcl.my/",
    "transaction_notification_email": "hai@bayarcash.com",
    "secondary_transaction_notification_email": null,
    "custom_payment_button_text": null,
    "payment_channels": [
        {
            "id": 1,
            "code": "FPX",
            "name": "FPX"
        },
        {
            "id": 3,
            "code": "FpxDirectDebit",
            "name": "Direct Debit"
        },
        {
            "id": 4,
            "code": "FpxLineOfCredit",
            "name": "FPX Line of Credit"
        }
    ]
}
```
