# Transaction Callback

***



Sample code using PHP to validate transaction callback checksum. Example below if you are using our v3 endpoint (`api.console.bayar.cash/v3`) with payload data from `callback_url`.



```php
<?php
    $secretKey = 'xxxxx';  // Your API secret key obtain from Bayarcash portal
    
    $callbackChecksum = $callbackData['checksum'];
    
    $payloadData = [
        "record_type"               => $callbackData['record_type'],
        "transaction_id"            => $callbackData['transaction_id'],
        "exchange_reference_number" => $callbackData['exchange_reference_number'],
        "exchange_transaction_id"   => $callbackData['exchange_transaction_id'],
        "order_number"              => $callbackData['order_number'],
        "currency"                  => $callbackData['currency'],
        "amount"                    => $callbackData['amount'],
        "payer_name"                => $callbackData['payer_name'],
        "payer_email"               => $callbackData['payer_email'],
        "payer_bank_name"           => $callbackData['payer_bank_name'],
        "status"                    => $callbackData['status'],
        "status_description"        => $callbackData['status_description'],
        "datetime"                  => $callbackData['datetime'],
    ];
    
    ksort($payloadData);  // Sort the payload data by key
    $payloadString = implode('|', $payloadData);  // Concatenate values with '|'
    
    $validResponse = hash_hmac('sha256', $payloadString, $secretKey) === $callbackChecksum;  // Validate checksum
```



For v2 endpoint (`console.bayar.cash/api/v2`), below are example with payload data from `return_url`.



```php
<?php
    $secretKey = 'xxxxx';  // Your API secret key obtain from Bayarcash portal
    
    $callbackChecksum = $callbackData['checksum'];
    
    $payloadData = [
        'transaction_id'            => $callbackData['transaction_id'],
        'exchange_reference_number' => $callbackData['exchange_reference_number'],
        'exchange_transaction_id'   => $callbackData['exchange_transaction_id'],
        'order_number'              => $callbackData['order_number'],
        'currency'                  => $callbackData['currency'],
        'amount'                    => $callbackData['amount'],
        'payer_bank_name'           => $callbackData['payer_bank_name'],
        'status'                    => $callbackData['status'],
        'status_description'        => $callbackData['status_description'],
    ];
    
    ksort($payloadData);  // Sort the payload data by key
    $payloadString = implode('|', $payloadData);  // Concatenate values with '|'
    
    $validResponse = hash_hmac('sha256', $payloadString, $secretKey) === $callbackChecksum;  // Validate checksum
```

