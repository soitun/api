#### Creating One Tracking Shipment

Resource URI

####POST
```
/v2/trackings.json
```

##### Require Fields:

* `api_key`: just your api key that you get from aftership website and please keep it private;

* `tracking_number`: only one tracking number per request, empty or multiple are not supported;

* `courier`: aftership built-in slugs for supporting couriers.

##### Optional Fields:

* `title`: the `*|TITLE|*` name shown in the notification message.;

* `source`: indiate the tracking number source, for example, if the tracking is imported from `opencart`, suggested value is `opencrt`. other value may be `ebay`, `amazon`, `zencart`, etc;

* `smses`: the array of mobile phone number, use in push notification. must be full format, like USA: `+1-732-757-2923`, HK: `+852-9000-1234`;

* `emails`: the array of email addresses, use in push notification; 

* `order_id`: the `*|ORDER_ID|*` shown in the notification message.;

* `order_id_path`: the `*|ORDER_PATH|*` shown in the notification message.;

* `customer_name`: the `*|CUSTOMER_NAME|*` shown in the notification message.;

* `origin_country_iso3`: the iso3 country code of posting, use for better tracking result, with this info, the tracking result will be more detail.

* `destination_country_iso3`: the iso3 country code of destination, use for better tracking result, with this info, the tracking result will be more detail.

The ISO 3166 country code can refer to this [wiki page](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-3)

###The support couriers and their slug names

Courier Name | courier (slug name)
----------|-----------
Aramex | aramex
Argentina OCA E-Pak | oca-ar
Australia Post | australia-post
Brazil Correios | brazil-correios
Canada Post | canada-post
China EMS | china-ems
Correos de España | spain-correos-es
DHL | dhl
DHL Germany | dhl-germany
DHL Global Mail | dhl-global-mail
DPD | dpd
Danmark Post | danmark-post
Fedex | fedex
Fedex UK | fedex-uk
Flash Courier | flash-courier
Hong Kong Post | hong-kong-post
India Post | india-post
Israel Post | israel-post
Korea Post | korea-post
Malaysia Post | malaysia-post
OnTrac | ontrac
Parcel Force | parcel-force
Portugal CTT | portugal-ctt
Royal Mail | royal-mail
Russian Post | russian-post
S.F. Express | sf-express
Singapore Post | singapore-post
Singapore Speedpost | singapore-speedpost
Star Track Australia | star-track
Swiss Post | swiss-post
TNT | tnt
Thailand Thai Post | thailand-post
UPS | ups
USPS | usps

####example
```
api_key=755a12083dd17420ec4cbc8a3a60016a8d617d08&tracking_number=CL719526662DE&courier=dhl-germany
```

####response

```
{
  "success": false,
  "message": "Tracking number is already exist."
}
```

there are several possiblities for success as false;

* api_key is invalid
* either courier or tracking_number is not provided
* courier is not supported now
* internal error

==================================


#### Getting One Tracking Shipment Result

Resource URI

####GET
```
/v2/trackings.json
```

##### Require Fields:

`api_key`: just your api key that you get from aftership website and please keep it private;

`tracking_number`: only one tracking number per request, empty or multiple are not supported;

`courier`: aftership built-in slugs for supporting couriers.


####example
```
api_key=755a12083dd17420ec4cbc8a3a60016a8d617d08&tracking_number=CL719526662DE&courier=dhl-germany
```




####response

```
{
  "success": true,
 
  "message": {
    "title": "CL719526662DE",
    "tracking_number": "CL719526662DE",
    "customer_name": null,
    "order_id": null,
    "order_id_path": null,
    "source": null,
 	"smses": [],
 	"emails": [],
  	"shipment_type": "parcel",
    "shipment_weight": null,
    "shipment_package_count": 1,
    "shipment_pickup_date": "2012-10-09T18:14:00+00:00",
    "shipment_scheduled_delivery_date": null,
    "shipment_delivery_date": null,
    "signed_by": null,
    "created_at": "2012-12-13T11:10:00Z",
    "updated_at": "2012-12-14T08:25:06Z",
    
    "origin_address": null,
    "origin_country_name": "Germany",
    "origin_country_iso3": "DEU",
    "origin_state": null,
    "origin_city": null,
    "origin_zip": null,
    
    "destination_address": null,
    "destination_country_name": null,
    "destination_country_iso3": null,
    "destination_state": null,
    "destination_city": null,
    "destination_zip": null,
    
    "checkpoints": [
      {
        "city": null,
        "created_at": "2012-12-13T11:11:17Z",
        "country_name": "Germany",
        "message": "The instruction data for this shipment have been provided by the sender to DHL electronically",
        "country_iso3": "DEU",
        "tag": null,
        "checkpoint_time": "2012-10-09T18:14:00+00:00",
        "coordinates": [],
        "state": null,
        "zip": null
      },
      {
        "city": null,
        "created_at": "2012-12-13T11:11:18Z",
        "country_name": "Germany",
        "message": "The shipment has been posted by the sender at the retail outlet",
        "country_iso3": "DEU",
        "tag": "InTransit",
        "checkpoint_time": "2012-10-10T09:13:00+00:00",
        "coordinates": [],
        "state": null,
        "zip": null
      },
      {
        "city": null,
        "created_at": "2012-12-13T11:11:18Z",
        "country_name": "Hamburg, Germany",
        "message": "The international shipment has been processed in the parcel center of origin",
        "country_iso3": "DEU",
        "tag": "InTransit",
        "checkpoint_time": "2012-10-10T14:26:00+00:00",
        "coordinates": [53.5510846, 9.9936818],
        "state": null,
        "zip": null
      },
      {
        "city": null,
        "created_at": "2012-12-13T11:11:18Z",
        "country_name": "Saulheim, Germany",
        "message": "The international shipment has been processed in the export parcel center",
        "country_iso3": "DEU",
        "tag": "InTransit",
        "checkpoint_time": "2012-10-11T01:01:00+00:00",
        "coordinates": [49.8716526, 8.1465675],
        "state": null,
        "zip": null
      },
      {
        "city": null,
        "created_at": "2012-12-13T11:11:18Z",
        "country_name": "China",
        "message": "The shipment has arrived in the destination country",
        "country_iso3": "CHN",
        "tag": "InTransit",
        "checkpoint_time": "2012-10-17T14:24:00+00:00",
        "coordinates": [],
        "state": null,
        "zip": null
      }
    ]
  }
}

```


there are several possiblities for success as false;

* api_key is invalid
* either courier or tracking_number is not provided
* courier with courier is not supported now
