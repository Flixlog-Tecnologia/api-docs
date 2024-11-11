### Quotation

QUOTE API HOST: **https://freight.lixlog.com/**

#### POST Quote

###### Copy as curl
``` shell
curl --request POST \
  --url https://freight.lixlog.com/quote \
  --header 'Authorization: Bearer flx_...' \
  --header 'Content-Type: application/json' \
  --data '{
    "from": "13322423",
    "to": "82840310",
    "parcels": [
        {
            "quantity": 1,
            "price": 15.0,
            "weight": 10,
            "width": 0.1,
            "height": 0.1,
            "length": 0.1
        }
    ]
}'
```


###### Example JSON Response

Value: Is the field that represents the final freight price

``` json
{
  "error": "",
  "results": [
    {
      "id": "bedf0a54-8e48-4c83-b051-23b413fdddbd",
      "value": 28.2272,
      "cost": 28.2272,
      "free_shipping": false,
      "delivery_days": 13,
      "execution_time": 52,
      "carrier": {
        "id": 129,
        "code": "rodonaves",
        "service": "Normal",
        "delivery_option_id": "lix_rodonaves_normal"
      },
      "cubed_weight": 10
    },
    {
      "id": "620f2353-8469-4e80-9fa3-6f1ebdb1f975",
      "value": 41.84,
      "cost": 41.84,
      "free_shipping": false,
      "delivery_days": 14,
      "execution_time": 319,
      "carrier": {
        "code": "jadlog",
        "service": "Econômico",
        "delivery_option_id": "lix_jadlog_economico"
      },
      "cubed_weight": 10
    },
    {
      "id": "d0c5f03e-b2b5-4b8e-b37d-a4525891976a",
      "value": 45.958181818181814,
      "cost": 45.958181818181814,
      "free_shipping": false,
      "delivery_days": 13,
      "execution_time": 52,
      "carrier": {
        "id": 137,
        "code": "tnt",
        "service": "Normal",
        "delivery_option_id": "lix_tnt_normal"
      },
      "cubed_weight": 10
    },
    {
      "id": "a17ba1df-b21f-4203-9f3b-45e57f18dbee",
      "value": 73.53977272727273,
      "cost": 73.53977272727273,
      "free_shipping": false,
      "delivery_days": 12,
      "execution_time": 52,
      "carrier": {
        "id": 138,
        "code": "saomiguel",
        "service": "Normal",
        "delivery_option_id": "lix_saomiguel_normal"
      },
      "cubed_weight": 10
    }
  ]
}
```