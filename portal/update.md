# Update Portal

***

<mark style="color:red;">v3</mark>  <mark style="color:orange;">`PUT`</mark>  `api.console.bayar.cash/v3/portals/{portal_id}`

***



Update an existing portal. The updated portal object is returned. Available request parameters are as below:



| Name                                                  | Description                                                                                                                     |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `name`                                                | Required. The portal name. Must be unique for the merchant.                                                                      |
| `website_url`                                         | Optional. A valid URL for the portal website.                                                                                   |
| `merchant_transaction_notification_email`             | Required. A valid email address to receive transaction notifications.                                                          |
| `secondary_merchant_transaction_notification_email`   | Optional. A secondary email address to receive transaction notifications.                                                       |
| `payment_channels`                                    | An array of payment channel IDs to enable on the portal. `FPX` is always included. Must be subscribed by the merchant.          |
| `enabled_sms_on_successful_transaction`               | Optional. Set to `1` to enable SMS notification on a successful transaction.                                                     |
| `split_payment_enabled`                               | Optional. Set to `1` to enable split payment.                                                                                   |
| `split_payment_merchants`                             | Required when `split_payment_enabled` is `1`. An array (max 3) of split payment merchants — each with `merchant_email`, `type` (`percentage`/`fix_amount`) and `value`. |
| `bank_accounts`                                       | Required when the Manual Bank Transfer channel is enabled. An array of bank accounts — each with `account_no`, `bank_id` and `payment_gateway_id`. |
| `cashier_id`                                          | Required when the DuitNow QR channel is enabled.                                                                                |

***



Example of sending <mark style="color:orange;">`PUT`</mark> request with cURL.



```markup
curl -X PUT https://api.console.bayar.cash/v3/portals/cbp_aZ9Klm \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data '{
    "name": "Payment Link",
    "website_url": "https://bcl.my/",
    "merchant_transaction_notification_email": "hai@bayarcash.com",
    "payment_channels": [3, 4]
  }'
```



Example of JSON structured response.



```json
{
    "id": "cbp_aZ9Klm",
    "created_at": "2024-10-19 12:47:07",
    "portal_key": "8baf5e234dd88c2d1375d5f386d78d8f",
    "portal_name": "Payment Link",
    "website_url": "https://bcl.my/",
    "transaction_notification_email": "hai@bayarcash.com",
    "secondary_transaction_notification_email": null,
    "custom_payment_button_text": null,
    "enabled_sms_on_successful_transaction": 0,
    "split_payment_enabled": false,
    "split_payment_merchants": [],
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
    ],
    "merchant": {
        "id": "usr_kP3xQ2",
        "name": "Web Impian Sdn. Bhd.",
        "email": "webimpian.merchant@gmail.com"
    }
}
```
