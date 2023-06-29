# API-architectuur

## Definitie en verschijningsvormen van API's

### Definitie

Met een *application programming interface* (API) ontsluit een softwareapplicatie functionaliteit voor gebruik door andere
softwareapplicaties, zonder die andere applicaties te belasten met hoe die functionaliteit wordt uitgevoerd.

### Aanbieder en afnemer

API's hebben aanbieders en afnemers. Een aanbieder ontsluit een functionaliteit (volgens de API-specificatie). Een
afnemer gebruikt deze functionaliteit door een API aan te roepen. Afnemers kunnen meer API's aanroepen en bij
verschillende aanbieders.

### Verschijningsvormen: overeenkomst, specificatie, deployment en implementatie

Een afnemer gaat met de aanbieder een API-overeenkomst aan. Daarin staan hun afspraken over de functionele en
niet-functionele kenmerken van de API en gebruiks- en leveringsvoorwaarden. De term *overeenkomst* mag breed worden
opgevat. Als een partij aanbieder en afnemer tegelijk is, betreft de overeenkomst een intern architectuurbesluit.

De functionaliteit wordt beschreven om andere applicaties te laten weten wat hun wordt aangeboden en hoe zij hierop
kunnen aansluiten. Die technische specificatie is de *API-specificatie*. Zowel aanbieder als afnemer moet software
hebben draaien die het eigen aandeel in het API-verkeer afhandelt: de *API-deployments*. Die gebruiken
softwareproducten waarin de API-specificatie zijn ingebouwd: de *API-implementaties*.

Bij elke API-specificatie horen één of meer API-implementaties en bij elke API-implementatie horen één of meer
API-deployments. Idealiter hoort bij elke API-deployment een API-overeenkomst[^5]. Een API-overeenkomst betreft één of
meer API-specificaties. Waar het onderscheid tussen specificatie, implementatie, deployment en overeenkomst niet van
belang is, spreekt de API-strategie kortweg van een *API*. De verantwoordelijkheden die horen bij deze
verschijningsvormen staan geordend in een rollenmodel (zie [paragraaf 2.5](#rollen)).

[^5]: Als eenzelfde partij aanbieder en afnemer is, staat de term API-overeenkomst voor interne architectuurbeslissing.

De API-strategie betreft alle aspecten van API's die van belang zijn voor de interoperabiliteit tussen aanbiedere en
afnemer. Daaronder vallen:

- de gegevens en acties;
- alle technische eigenschappen van de API die een potentiële API-afnemer moet kennen;
- de processen rondom API-specificatie en -documentatie.

Op onderdelen kunnen API-specificaties verwijzen naar breder toepasbare specificatie-onderdelen (en uiteindelijk naar
internationale technische basisstandaarden).