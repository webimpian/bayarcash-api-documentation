# Merchant Registration

***

<mark style="color:red;">v2</mark>  <mark style="color:green;">`POST`</mark>  `console.bayar.cash/api/v2/merchant-registrations`<br>
<mark style="color:red;">v3</mark> <mark style="color:green;">`POST`</mark>  `api.console.bayar.cash/v3/merchant-registrations`

***



Please note this section only for **Bayarcash Enterprise Partner**. Please refer to your account manager for further details.

> Notes: v2 and v3 use different field names for some attributes (for example the bank fields). Fields marked "only available on v2" or "only available on v3" apply to that version only. The request requires the `X-API-Key` header.



<table data-full-width="true"><thead><tr><th width="320">Name</th><th width="495">Description</th><th width="121">Type</th><th>Condition</th></tr></thead><tbody><tr><td><code>account_type</code></td><td><code>business_account</code> or <code>personal_account</code> - only available on v2</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>organisation_name</code></td><td>Required for a business account</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>organisation_registration_number</code></td><td>Required for a business account</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>login_name</code></td><td></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>login_email</code></td><td>Must be unique</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>login_mobile_number</code></td><td></td><td><code>integer</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>password</code></td><td>Minimum 8 characters</td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>password_confirmation</code></td><td>Must match <code>password</code></td><td><code>string</code></td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>merchant_organisation_code</code></td><td>Required for a personal account - only available on v2</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>business_nature</code></td><td>Required for a personal account - only available on v2</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>business_owner_icno</code></td><td>Required for a personal account. Valid Malaysia NRIC - only available on v2</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>organisation_bank_id</code></td><td>Refer Payout Bank List - only available on v3</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>organisation_bank_account_holder</code></td><td>only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>organisation_bank_account_number</code></td><td>only available on v3</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>bank_id</code></td><td>Refer Payout Bank List - only available on v2</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>bank_account_holder</code></td><td>only available on v2</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>bank_account_no</code></td><td>only available on v2</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>package</code></td><td>Subscription package code</td><td><code>string</code></td><td>Optional</td></tr><tr><td><code>agent_id</code></td><td>The agent user ID</td><td><code>integer</code></td><td>Optional</td></tr><tr><td><code>referral_id</code></td><td>The referral ID</td><td><code>string</code></td><td>Optional</td></tr></tbody></table>

***



Example of sending <mark style="color:green;">`POST`</mark> request with cURL.



```markup
curl -X POST https://api.console.bayar.cash/v3/merchant-registrations \
  --header 'Content-Type: application/json' \
  --header 'X-API-Key: <Enterprise_Partner_API_Key>' \
  --header 'Authorization: Bearer <Personal_Access_Token>' \
  --data-raw '{
        "organisation_name": string,
        "organisation_registration_number": string,
        "organisation_bank_id": integer, // Please refer Payout Bank List
        "organisation_bank_account_holder": string,
        "organisation_bank_account_number": string,
        "login_name": string,
        "login_email": string,
        "login_mobile_number": integer,
        "password": string,
        "password_confirmation": string
      }'
```



Example of JSON structured response.



```json
{
    "success": true,
    "message": "Merchant registration success.",
    "data": {
        "id": "mr_3qjZwq",
        "name": "Mohd Ali Bin Seman",
        "email": "namasyarikat@gmail.com",
        "referral_id": null,
        "registration_status": "Incomplete",
        "login_token": "$778374mifnminvrunvrvmrmri997uIO",
        "user_profiles": {
            "organisation_name": "Nama Syarikat Sdn. Bhd.",
            "organisation_registration_number": "123456789-H",
            "contact_first_name": null,
            "contact_last_name": null,
            "contact_mobile_number": "60169165576",
            "contact_email": "namasyarikat@gmail.com",
            "organisation_bank_id": 1,
            "organisation_bank_name": "Affin Bank Berhad",
            "organisation_bank_account_number": "221233898832",
            "organisation_bank_account_holder": "Nama Syarikat Sdn. Bhd." 
        },
        "active_package_subscription": {
            "reference_number": "112234434TE",
            "package": {
                "name": "DuitNow T+ Package",
                "code": "T+"
            },
            "start_date": "2024-11-13",
            "expiry_date": "2025-11-13",
            "minimum_balance": "RM50.00",
            "payouts_schedule": "Payout next working day T+1 starting 01.00 AM"
        },
        "portal": {
            "name": "Default",
            "api_key": "3888499948593892894",
            "merchant_transaction_notification_email": "financesyarikat@gmail.com",
            "url": "https://bcl.my",
            "payment_gateways": [
                {
                    "name": "FPX",
                    "code": "FPX"
                }
            ]
        }
    }
}
```

