# Checksum Validation

***



To ensure a secured request to Bayarcash API, you need to generate a checksum value using your API secret key. This checksum must be included in your request to validate its integrity and authenticity.&#x20;

You can generate your API secret key from Bayarcash portal at profile page.



{% hint style="success" %}
Note: The checksum value and checksum validation are optional, but it is recommended for enhanced security.
{% endhint %}



***

### Payment Intent Request

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



***

### Pre-Transaction Callback

Sample code using PHP to validate pre-transaction callback checksum.



```php
<?php
    $secretKey = 'xxxxx';  // Your API secret key obtain from Bayarcash portal
    
    $callbackChecksum = $callbackData['checksum'];
    
    $payloadData = [
        "record_type" => $callbackData['record_type'],
        "exchange_reference_number" => $callbackData['exchange_reference_number'],
        "order_number" => $callbackData['order_number'],
    ];
    
    ksort($payloadData);  // Sort the payload data by key
    $payloadString = implode('|', $payloadData);  // Concatenate values with '|'
    
    $validResponse= hash_hmac('sha256', $payloadString, $secretKey) === $callbackChecksum;  // Validate checksum
```

