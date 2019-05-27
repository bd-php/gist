## Bio JSON Parse
```php
<?php

$bio = [
    "name" => "amran",
    "age" => "100",
    "phone" => "01928004636",
    "address" => [
        "village" => "chanderbagh",
        "post" => "vowal jamalpur",
        "upzilla" => "kaligonj",
        "zilla" => "Gazipur",
        "roads" => [
            "100",
            "200",
            "300"
        ]
    ]
];

$jsonEncoded = json_encode($bio);
$jsonDecoded = json_decode($jsonEncoded, true);

$n = 2;

if (isset($jsonDecoded['address']['roads'][$n]) != null) {
    echo $jsonDecoded['address']['roads'][$n];
} else {
    echo "Can't Found";
}
```
