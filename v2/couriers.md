#### Getting All Couriers

Resource URI

####GET
```
/v2/couriers.json
```

##### Require Fields:

* `api_key`: just your api key that you get from aftership website and please keep it private;

####example
```
api_key=755a12083dd17420ec4cbc8a3a60016a8d617d08
```

####response

```
{
  "success": true,
  "couriers": [
      {
        "slug": "dhl",
        "name": "DHL"
      },
      {
        "slug": "ups",
        "name": "UPS"
      },
      {
        "slug": "fedex",
        "name": "Fedex"
      }
  ]
}
```

there are several possiblities for success as false;

* api_key is invalid
* internal error

###Now we supported more than 45 couriers

Courier Name | courier (slug name)
----------|-----------
Aramex | aramexArgentina OCA E-Pak | oca-arAustralia Post | australia-postBrazil Correios | brazil-correiosCanada Post | canada-postChina EMS | china-emsCorreos de España | spain-correos-esDHL Germany | dhl-germanyDHL Global Mail | dhl-global-mailDHL Netherlands | dhl-nlDHL Poland | dhl-polandDHL | dhlDPD | dpdDanmark Post | danmark-postFedex UK | fedex-ukFedex | fedexFlash Courier | flash-courierHong Kong Post | hong-kong-postIndia Post | india-postInternational Seur | international-seurIsrael Post | israel-postKorea Post | korea-postLa Poste Colissimo | la-poste-colissimoMalaysia Post | malaysia-postOPEK | opekOnTrac | ontracParcel Force | parcel-forcePortugal CTT | portugal-cttPortugal Seur | portugal-seurPurolator | purolatorRoyal Mail | royal-mailRussian Post | russian-postS.F. Express | sf-expressSaudi Post | saudi-postSingapore Post | singapore-postSingapore Speedpost | singapore-speedpostSiodemka | siodemkaSpanish Seur | spanish-seurStar Track Australia | star-trackSwiss Post | swiss-postTAQBIN Hong Kong | taqbin-hkTAQBIN Singapore | taqbin-sgTNT | tntThailand Thai Post | thailand-postUPS | upsUSPS | usps




