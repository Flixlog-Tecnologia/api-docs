### QuotationLogs

#### GET QuotationLogs

Available filters: channel, date_state, date_end

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://api.lixlog.com/v1/quotation_logs?page=1'
```

###### Example JSON Response
``` json
{
  "data": [
    {
      "id": 34336923,
      "channel": null,
      "zip_from": "13248100",
      "zip_to": "88210000",
      "request": {
        "parcels": [
          {
            "price": 643.89,
            "width": 0.79,
            "height": 0.34,
            "length": 1.98,
            "volume": 0,
            "weight": 15,
            "deadline": 0,
            "quantity": 2,
            "reference": "SKU123",
            "warehouse_id": ""
          }
        ]
      },
      "response": [
        {
          "id": "efc8f7b4-6e7c-43a2-965f-64d5c8ed8a35",
          "cost": 321.09090909090907,
          "value": 449.5272727272727,
          "carrier": {
            "id": 803,
            "code": "lsa",
            "meli_id": 22,
            "service": "Normal",
            "delivery_option_id": "lix_lsa_normal"
          },
          "route_id": 2817916,
          "destination": {
            "Zip": "88210000",
            "city": "Porto Belo",
            "state": "SC"
          },
          "cubed_weight": 30,
          "delivery_days": 15,
          "free_shipping": false,
          "execution_time": 108,
          "freight_rules_applied": [
            {
              "id": "425"
            },
            {
              "id": "426"
            }
          ]
        }
      ]
    }
  ]
}
```