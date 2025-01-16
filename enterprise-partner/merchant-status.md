# Merchant Status

***

<mark style="color:red;">v2</mark>  <mark style="color:blue;">`GET`</mark>  `console.bayar.cash/api/v2/merchant-registrations/{id}`\
<mark style="color:red;">v3</mark> <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/merchant-registrations/{id}`

***



As our enterprise partners, you can check for merchant registration status via API. All registration will be approved manually by our account manager. Registration status consist of:



<table><thead><tr><th width="227">Status</th><th>Description</th></tr></thead><tbody><tr><td>Incomplete</td><td>Our system successfully recorded the registration. Merchant can start collect the payment but the payout will be put on hold until merchant complete the submission of needed documents.</td></tr><tr><td>Pending Approval</td><td>Merchant submitted the KYC/KYB documents &#x26; our account manager is reviewing.</td></tr><tr><td>Approved</td><td>Merchant registration is approved &#x26; payout is processing.</td></tr><tr><td>Rejected</td><td>Merchant registration is rejected. Further details, please contact our account manager.</td></tr></tbody></table>



Example of JSON structured response.



```json
{
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
```

