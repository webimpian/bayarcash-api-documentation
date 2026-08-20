# Generate DuitNow QR

***

<mark style="color:red;">v3</mark>  <mark style="color:green;">`POST`</mark>  `api.console.bayar.cash/v3/payment-intents/{payment_intent_id}/duitnow-qr`

***



Generate a DuitNow QR for an existing payment intent so you can render it on your own page or POS — no redirect to the Bayarcash checkout page. The response contains the raw QR payload (`qr_string`) and a ready-to-display PNG (`qr_image`), plus a polling URL to track the payment status.

The payment intent must have been created with a **single DuitNow QR payment channel** (codes `6`, `7`, `8`, `9`, `10`, `11`, `13`, `14`, `15` — refer to the Payment Channel page) and still be payable.

> **Tip:** For the common case you can skip this endpoint entirely — pass `generate_qr: true` when creating the payment intent and the same `duitnow_qr` object is returned inline. See the One-Step DuitNow QR section on the Payment Intent page. This endpoint remains useful for generating a **fresh QR after a previous one expired**.



Example of sending <mark style="color:green;">`POST`</mark> request with cURL. No request body is required.



```markup
curl -X POST https://api.console.bayar.cash/v3/payment-intents/pi_MGWpzp/duitnow-qr \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "type": "duitnow_qr",
    "transaction_id": "trx_z88ymJ",
    "payment_intent_id": "pi_MGWpzp",
    "qr_string": "00020201021226580014A000000615000101065...",
    "qr_image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA...",
    "qr_expires_at": "2026-08-20T14:05:12+08:00",
    "poll_url": "https://api.console.bayar.cash/v3/transactions/trx_z88ymJ/duitnow-qr/status",
    "next_poll_after_ms": 2000,
    "amount": 21.10,
    "currency": "MYR",
    "order_number": "1351"
}
```



<table data-full-width="true"><thead><tr><th width="240">Field</th><th>Description</th></tr></thead><tbody><tr><td><code>qr_string</code></td><td>Raw DuitNow QR payload — encode it into a QR image yourself if you prefer</td></tr><tr><td><code>qr_image</code></td><td>Ready-to-display PNG data URI — render it directly in an <code>&#x3C;img></code> tag. May be <code>null</code> if image rendering failed; fall back to <code>qr_string</code></td></tr><tr><td><code>qr_expires_at</code></td><td>ISO 8601 datetime. The QR is valid for about 5 minutes — show a countdown and offer a new QR after expiry</td></tr><tr><td><code>poll_url</code></td><td>Status polling endpoint for this QR's transaction</td></tr><tr><td><code>next_poll_after_ms</code></td><td>Minimum delay between polls, in milliseconds</td></tr></tbody></table>

***



## Response Codes



<table data-full-width="true"><thead><tr><th width="140">Code</th><th>Meaning</th></tr></thead><tbody><tr><td><code>201</code></td><td>A fresh QR was generated</td></tr><tr><td><code>200</code></td><td>An active (unexpired, unpaid) QR already exists for this payment intent — the same QR is returned, nothing is regenerated. Safe to call repeatedly</td></tr><tr><td><code>403</code></td><td><code>{"success": false, "message": "..."}</code> — the payment intent is not a DuitNow QR intent, is no longer payable (completed/expired/cancelled), or your account cannot accept DuitNow QR payments. The message explains why. <strong>Retrying will not help</strong></td></tr><tr><td><code>409</code></td><td>Another request is generating a QR for this payment intent right now — retry after a short delay</td></tr><tr><td><code>502</code></td><td>Temporary upstream failure — retry the request</td></tr></tbody></table>



> **Important:** After the QR expires unpaid, calling this endpoint again generates a fresh QR for the same payment intent — as long as the payment intent itself has not expired (`link_expired_at`).
