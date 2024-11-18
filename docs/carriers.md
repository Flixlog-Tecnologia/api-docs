### Carriers

#### GET Carriers


###### Copy as curl
``` shell
curl --request GET --header 'Authorization: Bearer flx_...' --url 'https://2.flixlog.com/api/carriers'
```

###### Example JSON Response
``` json
{
	"pagination": {
		"prev_url": "/api/carriers?page=",
		"next_url": "/api/carriers?page=",
		"count": 2,
		"page": 1,
		"next": 1
	},
	"data": [
		{
			"id": 5,
			"federal_tax": "12345678945783",
			"state_tax": "",
			"phone": "41995065196",
			"created_at": "2024-02-22T13:34:57.002-03:00",
			"updated_at": "2024-07-12T16:42:04.980-03:00",
			"name": "Favorita",
			"display_name": "Favoritinha",
			"code": "favorita",
			"tms": "ssw",
			"link": {
				"_self": "/api/carriers/5"
			}
		},
		{
			"id": 6,
			"federal_tax": "02141029000119",
			"state_tax": "9026909640",
			"phone": "4131238712",
			"created_at": "2024-02-22T13:42:21.443-03:00",
			"updated_at": "2024-02-22T13:42:21.443-03:00",
			"name": "Rodobras Transportes Rodoviários Ltda",
			"display_name": "RODOBRAS",
			"code": "rodobras",
			"tms": "ssw",
			"link": {
				"_self": "/api/carriers/6"
			}
		}
	]
}
```