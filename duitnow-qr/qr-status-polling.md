# QR Status Polling

***

<mark style="color:red;">v3</mark>  <mark style="color:blue;">`GET`</mark>  `api.console.bayar.cash/v3/transactions/{transaction_id}/duitnow-qr/status`

***



Lightweight polling endpoint for a DuitNow QR transaction created via the Generate DuitNow QR endpoint (or `generate_qr: true`). Use it to update your payment page while the payer scans.

> **Tip:** Webhooks to your payment intent `callback_url` remain the **primary** payment notification — treat this endpoint as a UI fallback only. Fulfil orders from the callback, not from polling.



Example of sending <mark style="color:blue;">`GET`</mark> request with cURL.



```markup
curl -X GET https://api.console.bayar.cash/v3/transactions/trx_z88ymJ/duitnow-qr/status \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer <Personal_Access_Token>'
```



Example of JSON structured response.



```json
{
    "transaction_id": "trx_z88ymJ",
    "status": 0,
    "status_description": "New",
    "is_terminal": false,
    "qr_expired": false,
    "qr_expires_at": "2026-08-20T14:05:12+08:00",
    "next_poll_after_ms": 2000
}
```



<table data-full-width="true"><thead><tr><th width="240">Field</th><th>Description</th></tr></thead><tbody><tr><td><code>status</code></td><td>Transaction status code: <code>0</code> New, <code>1</code> Pending, <code>2</code> Unsuccessful, <code>3</code> Successful, <code>4</code> Cancelled, <code>5</code> Abandoned</td></tr><tr><td><code>is_terminal</code></td><td><code>true</code> once the status is final — stop polling and show the result</td></tr><tr><td><code>qr_expired</code></td><td><code>true</code> once <code>qr_expires_at</code> has passed — stop polling; the underlying transaction may stay non-terminal until housekeeping ages it out. Treat an expired QR as failed and generate a new one if the payer still wants to pay</td></tr><tr><td><code>next_poll_after_ms</code></td><td>Minimum delay before your next poll. <code>null</code> when the status is terminal or the QR has expired — <strong>stop polling</strong></td></tr></tbody></table>

***



## Polling Rules



* Respect `next_poll_after_ms` between polls (default 2000 ms).
* Stop polling when `is_terminal` is `true` **or** `qr_expired` is `true` (`next_poll_after_ms` will be `null`).
* Requests are rate limited to **30 per minute per transaction**, plus an overall per-merchant ceiling. A `429` response includes a `Retry-After` header — wait that many seconds before polling again.

```json
{
    "code": 429,
    "message": "Too many requests."
}
```
