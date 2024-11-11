### Trackings

#### GET Trackings by tracking code

Available status:
- in_transit
- out_for_delivery
- delivered
- failure

###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/trackings/FL3D049813B9AC-0001'
```

###### Example JSON Response
``` json
{
  "data": [
    {
      "id": 8,
      "code": null,
      "title": "Coleta realizada com sucesso",
      "message": "Pedido já foi coletado",
      "city": null,
      "state": null,
      "status": "in_transit",
      "delivery_date": null,
      "occurred_at": "2024-11-07T05:48:35.070-03:00",
      "created_at": "2024-11-07T05:48:35.073-03:00"
    },
    {
      "id": 9,
      "code": null,
      "title": "Entrega realizada com sucesso",
      "message": "Pedido foi entregue corretamente no endereço de destino",
      "city": null,
      "state": null,
      "status": "delivered",
      "delivery_date": null,
      "occurred_at": "2024-11-07T05:50:05.190-03:00",
      "created_at": "2024-11-07T05:50:05.195-03:00"
    }
  ]
}
```
