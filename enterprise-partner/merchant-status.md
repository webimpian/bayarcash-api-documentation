# Merchant Status

***

<mark style="color:blue;">`GET`</mark> `/api/v2/merchant-registrations/{id}`



Check for merchant registration status. All registration will be approved manually by our account manager. Registration status consist of:

* Incomplete
* Pending Approval
* Approved
* Rejected



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

