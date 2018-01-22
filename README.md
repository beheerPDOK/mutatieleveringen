# How To Mutaties

Deze pagina geeft een overzicht hoe de mutaties van de BGTv3 te verwerken zijn.

### Inhoud

- Object
- Objects en delivery's
- Mogelijkheden api 
- How to download mutaties

## Object
Een object bestaat uit de volgende informatie elementen:
- Object_id
- Object_type
- Id
- Geometry van het object

Object_id samen met id is een unieke combinatie. ObjectId kan vaker voorkomen maar samen met het Id is deze uniek per levering.

## Objects en delivery's
Een delivery/mutatielevering kan meerdere objecten en zelfs meerdere objecten met hetzelfde objectid bevatten. 
Een delivery is hierbij opgedeeld in 3 soorten mutatieberichten, in combinatie met een was-wordt model;
- Toevoeging - wordt bericht - Object wordt gecreeerd
- Wijziging - was-wordt bericht - Object wordt gewijzigd
- Verwijdering - Was bericht -  Object wordt vernietigd

Voorbeelden:
Toevoeging -> 
Wijziging ->
Verwijdering ->

## Mogelijkheden api

| RequestType   | Api                                                             | Omschrijving                 |
| ------------- |:---------------------------------------------------------------:| ----------------------------:|
| GET           | /api/v2/deliveries/bgtv3/citygml/download-full                  | Download de initiële stand   |
| GET           | /api/v2/deliveries/bgtv3/citygml/since/{deliveryId}             | Download de delivery ids     |
| GET           | /api/v2/deliveries/bgtv3/citygml/download-delivery/{deliveryId} | Download de delivery with id |


## How to download mutaties

Voor het aansluiten van de download 
