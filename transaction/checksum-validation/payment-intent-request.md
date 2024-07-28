# Payment Intent Request

***



Sample code using PHP to validate payment intent checksum.



```php
<?php
    $secretKey = 'xxxxx';  // Your API secret key obtain from Bayarcash portal
    
    $payloadData = [
        "payment_channel" => 1,
        "order_number" => "ORD-0060",
        "amount" => "60.00",
        "payer_name" => "Mohd Ali",
        "payer_email" => "mohd.ali@gmail.com"
    ];
    
    ksort($payloadData);  // Sort the payload data by key
    $payloadString = implode('|', $payloadData);  // Concatenate values with '|'
    
    $checksum = hash_hmac('sha256', $stringPayload, $secretKey); // Generate HMAC SHA256 checksum
```

