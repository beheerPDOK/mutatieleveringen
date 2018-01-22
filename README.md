# How To Mutaties

Deze pagina geeft een beschrijving hoe de mutaties van de BGTv3 te downloaden zijn.

---

## Inhoud

- Object
- Objects en delivery's
- Download service api
- How to download mutaties

---

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
- Toevoeging - wordt bericht - Object wordt gecreeerd - [toevoeging.xml](../master/voorbeeldbericht/toevoeging.xml)
- Wijziging - was-wordt bericht - Object wordt gewijzigd - [wijziging.xml](../master/voorbeeldbericht/wijziging.xml)
- Verwijdering - Was bericht -  Object wordt vernietigd - [verwijdering.xml](../master/voorbeeldbericht/verwijdering.xml)

## Download service api

| Refence Name      | RequestType | Api                                                             | Omschrijving                 |
| ----------------- | ----------- | --------------------------------------------------------------- | ---------------------------- |
| download-full     | GET         | /api/v2/deliveries/bgtv3/citygml/download-full                  | Download de initiële stand   |
| download-since    | GET         | /api/v2/deliveries/bgtv3/citygml/since/{deliveryId}             | Download de delivery ids     |
| download-delivery | GET         | /api/v2/deliveries/bgtv3/citygml/download-delivery/{deliveryId} | Download de delivery with id |


## How to download mutaties

Voor het aansluiten van de download zul je de volgende stappen moeten uitvoeren:
1. Download een initiële stand met de **"download-full"** link, dit levert je de volledige gezipte stand van vandaag qua levering. 
Verwachting zal dit enkele gig bestanden zijn. Meestal volledig alleen met toevoegingen. **In dit bestand zit een aanleveringId deze heb je nodig voor het opvragen van een volgend delivery**.
2. Door middel van **"download-since"** kun je opvragen of er nog nieuwe aanleveringen zijn. **Zet hiervoor het aanleveringId in link van de delivery.** 
Dit geeft uiteindelijk een lijst met nog te downloaden delivery's
3. Elke delivery kan nu gedownload worden door middel van het verkregen delivery id met de download-since in de **"download-delivery"** te zetten. 

