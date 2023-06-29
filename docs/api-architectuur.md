# API-architectuur

## Definitie en verschijningsvormen van API's

### Definitie

Met een *application programming interface* (API) ontsluit een softwareapplicatie functionaliteit voor gebruik door
andere softwareapplicaties, zonder die andere applicaties te belasten met hoe die functionaliteit wordt uitgevoerd.

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
API-deployments. Idealiter hoort bij elke API-deployment een API-overeenkomst[^1]. Een API-overeenkomst betreft één of
meer API-specificaties. Waar het onderscheid tussen specificatie, implementatie, deployment en overeenkomst niet van
belang is, spreekt de API-strategie kortweg van een *API*. De verantwoordelijkheden die horen bij deze
verschijningsvormen staan geordend in een rollenmodel (zie [paragraaf 2.5](#rollen)).

[^1]: Als eenzelfde partij aanbieder en afnemer is, staat de term API-overeenkomst voor interne architectuurbeslissing.

De API-strategie betreft alle aspecten van API's die van belang zijn voor de interoperabiliteit tussen aanbiedere en
afnemer. Daaronder vallen:

- de gegevens en acties;
- alle technische eigenschappen van de API die een potentiële API-afnemer moet kennen;
- de processen rondom API-specificatie en -documentatie.

Op onderdelen kunnen API-specificaties verwijzen naar breder toepasbare specificatie-onderdelen (en uiteindelijk naar
internationale technische basisstandaarden).

## Typologieën van API's

De internationale gemeenschap classificeert API's op verschillende manieren. Het algemene deel van de Nederlandse
API-strategie[^2] biedt daarvan goede voorbeelden:

[^2]: [Typologie van API's](https://docs.geostandaarden.nl/api/API-Strategie/#typologie-van-api-s)

- interne – en externe API-overeenkomsten;
- unrestricted-use en restricted-use API deployments;
- interactiepatronen;
- system −, process − en convenience API's.

### Interne en externe API-overeenkomsten

De Nederlandse API-strategie onderscheidt interne en externe API's. Interne API's vinden toepassing binnen één
organisatie; externe API's worden gebruikt voor verkeer tussen organisaties. Als de inhoudelijk eindverantwoordelijke
aanbieder dezelfde partij is als de inhoudelijk eindverantwoordelijke afnemer, werkt die partij met interne API's. Zijn
aanbieder en afnemer verschillende partijen dan spelen tussen die partijen externe API's.

Het onderscheid tussen intern en extern is een kwestie voor de API-overeenkomst. Dezelfde API-specificatie,
API-implementatie of API-deployment kan zowel extern als intern worden ingezet. Die vrijheid wil de API-strategie ook
behouden. Hooguit waar eisen aan API-overeenkomsten worden gesteld, kan het onderscheid aan de orde komen.

### Unrestricted − en restricted-use API-deployments

De Nederlandse API-strategie verdeelt externe API's in *open*[^3] en *gesloten* API's. Bij gesloten API's gelden
voorwaarden om de gespecificeerde functionaliteit te mogen gebruiken. Voor de verificatie van het recht op gebruik zijn
ook autorisatie-API's en authenticatie-API's nodig. Bij open API's (gebruikt voor bijvoorbeeld open data) ontbreken
toegangsvoorwaarden en ontbreekt de behoefte aan autorisatie en authenticatie. Internationaal echter betekent *open API*
iets anders. Omdat de API-strategie voor de zorg de internationale termen wil overnemen, gebruikt zij voor het
onderhavige onderscheid de termen *unrestricted-use API* en *restricted-use API*.

[^3]: niet te verwarren met de technologie OpenAPI uit [paragraaf 2.4](#infrastructuur)

Het onderscheid tussen unrestricted-use en restricted-use API's speelt uiteindelijk bij een API-deployment. Daarin
krijgt toegangsbeleid zijn beslag, dat in voorafgaande API-overeenkomsten, API-specificaties en API-implementatie vorm
heeft gekregen.

De Nederlandse API-strategie verdeelt de restricted-use API's naar de betrokken partijen: burger, bedrijf, overheid. Het
is de vraag of deze driedeling zinvol is voor de doelen van de API-strategie voor de zorg. In de zorg springen
natuurlijk allereerst de zorgaanbieder en de patiënt (of anders genoemd) in het oog. Maar ook andere organisatiesoorten
spelen een belangrijke rol in het zorginformatieverkeer: overheidsuitvoerders, verzekeraars, kwaliteitsregistraties,
onderzoeksorganisatie en andere. De API-strategie voor de zorg maakt op voorhand geen keuze voor typen partijen in het
zorginformatiestelsel, zorgsectoren of dergelijke. De kans bestaat zelfs dat API's die bedoeld zijn voor
patiënt-zorgaanbiederverkeer ook bruikbaar zijn voor ander verkeer.

### Interactiepatronen

API's verschillen ook in hoe client en server afstemmen *wanneer* en *welke* gegevens uitgewisseld moeten worden. De
client weet welke gegevens hij nodig heeft, de server weet wanneer die beschikbaar zijn. In het meest eenvoudige patroon
(*pull*-patroon of *polling*) vraagt de client en antwoordt de server. Nadeel daarvan is dat, wanneer er helemaal geen
nieuwe gegevens blijken te zijn, de client het later nog eens moet proberen. Dat kan leiden tot onnodig
vraag−antwoordverkeer[^4].

[^4]:
    HTTP kent technische mogelijkheden voor het beperken van dit verkeer aan de server-zijde, namelijk met het in de
    cache identificeren van versies van resources, met een zogenoemde ETag.

Een ander patroon is het *push*-patroon waarin de server het initiatief neemt op het moment dat nieuwe gegevens
beschikbaar zijn. De server stuurt naar de clients die daarvoor staan geregistreerd, het bericht dat er wijzigingen zijn
en welke. Ook hieraan kleven in sommige situaties nadelen. Omdat de client weet welke gegevens hij wanneer nodig heeft,
kan het tweede deel van de boodschap (wat de wijzigingen zijn) voorbarig worden.

Een subtieler patroon is de *pull-notificatie* of *notified-pull*. De server vertelt de client eerst dát er nieuwe
gegevens beschikbaar zijn (de *notificatie*). In reactie daarop vraagt de client op door hem gekozen momenten deze of
andere servers de gegevens. Door de scheiding tussen dát en wát is dit patroon het meest geraffineerd in de afstemming
tussen client en server en in de mogelijkheden voor dataminimalisatie. Bovendien is dit patroon veiliger omdat de client
gevraagd kan worden zich opnieuw te authentiseren voordat de gegevens zelf worden gestuurd.

De API-strategie voor de zorg kent vooraf geen voorkeur voor een van deze drie patronen. Het derde patroon spreekt de
client en server het meest precies aan: de cliënt voor het wát, de server voor het dát. Het pull-patroon legt beide bij
de client, het push-patroon juist bij de server. Dat maakt deze twee eenvoudiger dan *notified-pull*. Al naar gelang de
situatie geniet één van de drie de voorkeur.

### System API's, process API's en convenience API's

Een andere indeling is die naar kolom (tier) in de software-architectuur (van betrokken applicatie) waarop de API
aangrijpt. Een system API grijpt aan op de database, een process API op de business logica en de *convenience* of
*experience* API op de user interface.

Dit onderscheid is in de API-strategie voor de zorg van groot belang. Het onderscheid tussen *system* API en *process*
API weerspiegelt het onderscheid tussen verwerking van informatie (links in afbeelding 1) en uitwisseling van informatie
(rechts in afbeelding 1) in het zorginformatiestelsel.[^5]

[^5]:
    Afbeelding 1 noemt system API's en process API's data-API's en transactie-API's. Engelstalige teksten gebruiken de
    in de software-community gangbare termen.

De huidige behoefte aan informatiebeschikbaarheid maakt dit onderscheid actueel en legt de nadruk op data-API's, hoewel
de API-strategie ook transactie-API's betreft.

De nationale API-strategie onderscheidt ook *business* en *exposure* API's. De functionaliteit van business API's omvat
specifieke (proces)aspecten. Bij exposure API's ontbreken die en is de functionaliteit algemeen en gegevensgericht. Zo'n
onderscheid mist scherpte, lijkt op het vorige onderscheid en is daarom vooralsnog niet van waarde in de API-strategie
voor de zorg.

### Open API's, technisch gestandaardiseerde API's en volledig gestandaardiseerde API's

De doelstelling van de API-strategie geeft aanleiding om drie kwaliteitstreden te onderscheiden: open API's, technische
gestandaardiseerde API's en volledig gestandaardiseerde API's (afbeelding 2). Voor een beschrijving zie
[paragraaf 1.2](./een-api-strategie-voor-de-zorg.md#doel-en-groeipad-van-een-api-strategie).

### Tot slot

Van de hier benoemde typologieën spelen er dus twee een funderende rol in de API-strategie voor de zorg:

- het architectuur-onderscheid tussen data-API's en transactie-API's (afbeelding 1);
- het kwaliteits-onderscheid tussen open API's, technisch gestandaardiseerde API's en volledig gestandaardiseerde API's
  (afbeelding 2).

Beide typologieën betreffen allereerst API-specificaties, maar gelden ook voor de API-implementaties en API-deployments
die gebaseerd zijn op zo'n API-specificatie.