# Mandate ID

***

<mark style="color:green;">`GET`</mark> `/api/v2/mandates/{mandate_id}`

At any given time, you can request a mandate ID to check on the status. It will return the mandate object.



```json
{
  "data": {
    "id": "md_nq5oAG",
    "created_at": "2024-06-27T09:53:09.000000Z",
    "updated_at": "2024-06-27T09:57:27.000000Z",
    "order_no": "DDD-24060323",
    "order_description": "Enrollment of DDD-24060323",
    "buyer_name": "Mohd Ali",
    "buyer_id": "890109021234",
    "buyer_id_type": "1",
    "buyer_email": "mohfali@gmail.com",
    "buyer_tel_no": "60199004044",
    "currency": "MYR",
    "amount": "200.00",
    "mandate_no": "E-20241719482236",
    "buyer_bank_account_no": "033112228108",
    "mandate_application_type": null,
    "mandate_application_reason": null,
    "mandate_max_frequency": "9",
    "mandate_frequency_mode": "MT",
    "mandate_effective_date": "2024-06-30",
    "mandate_expiry_date": "2025-06-30",
    "mandate_status": 4,
    "return_url": "https://sistem-website.com/mandates/callback",
    "failed_url": "https://sistem-website.com/mandates/DDD-24060323/failed",
    "maintenance_url": null,
    "termination_url": null,
    "success_url": "https://sistem-website.com/mandates/DDD-24060323/success",
    "raw_data": [],
    "receipt_url": "https://sistem-website.com/mandates/transactions/receipt",
    "transaction_update_url": "https://sistem-website.com/mandates/transactions/update",
    "payment_gateway": {
      "name": null,
      "code": null
    },
    "portal": "Portal Direct Debit Website A",
    "merchant": {
      "name": "Syarikat Sdn. Bhd.",
      "email": "notification@syarikat.com"
    }
  }
}
```

