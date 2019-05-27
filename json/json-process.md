## JSON Parse Using PHP
```php
<?php

$request = '{
    "AUTH_ID": "193",
    "NAME": "Sheikh Mohammad Amran",
    "PRIMARY_MOBILE": "01928004636",
    "SECONDARY_MOBILE": "01928004637",
    "EMAIL": "amran@gmail.com",
    "DEFAULT_ADDRESS": {
        "ID": "80",
        "HOUSE": "100",
        "BLOCK": "J",
        "ROAD": "105"
    },
    "OTHERS_ADDRESS": [
        {
            "ID": "80",
            "HOUSE": "100",
            "BLOCK": "J",
            "ROAD": "105"
        },
        {
            "ID": "80",
            "HOUSE": "100",
            "BLOCK": "J",
            "ROAD": "105"
        }
    ]
}';


$str = json_decode($request, true);

function processDefaultAddress($value)
{

    $address = '';
    $address .= $value['ID']
        . "$$" . $value['HOUSE']
        . "$$" . $value['BLOCK']
        . "$$" . $value['ROAD'];

    return $address;
}

function processOthersAddress($val)
{
    $address = '';
    foreach ($val as $k => $value) {
        $address .= $value['ID']
            . "$$" . $value['HOUSE']
            . "$$" . $value['BLOCK']
            . "$$" . $value['ROAD'] . "||";
    }
    $address = rtrim($address, "||");
    return $address;
}

$DEFAULT_ADDRESS = $str['DEFAULT_ADDRESS'];
$OTHERS_ADDRESS = $str['OTHERS_ADDRESS'];

print(processDefaultAddress($DEFAULT_ADDRESS));
print("\n");
print(processOthersAddress($OTHERS_ADDRESS));
```
