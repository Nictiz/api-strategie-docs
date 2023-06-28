# Een API-strategie voor de zorg

## Strategisch aandacht voor API's

### Data beschikbaar voor hergebruik

API's (application programming interfaces) zijn technische koppelvlakken binnen en tussen digitale informatiesystemen.
Zij ontsluiten data en transacties: de data die door die systemen worden vastgelegd en de transacties die door die
systemen worden uitgevoerd. Voor data en transacties worden aparte typen API's onderscheiden. Data-API's zorgen voor
technische *databeschikbaarheid*[^1]: zij ontsluiten data buiten transacties om. Zo onthullen zij op een gecontroleerde
manier gegevens uit het ene systeem voor hergebruik door het andere systeem. Dat maakt data-API's van strategisch belang
voor het zorginformatiestelsel.

[^1]: Zie ook [API's voor databeschikbaarheid](./api-architectuur.md#apis-voor-databeschikbaarheid).

### Standaardisatie van informatie

In het zorginformatiestelsel worden informatiestandaarden - voor hetzij registratie, hetzij uitwisseling - ontwikkeld en
beheerd door verschillende partijen en met verschillende eindverantwoordelijke houders. Elke informatiestandaard is
bedoeld voor een zorgsituatie of *use case* en beschrijft:

- in gebruikerstaal wat er aan de orde is (conceptueel);
- de gegevensset die daaraan invulling geeft (logisch);
- de API's waarlangs informatiesystemen die gegevenssets uitwisselen (technisch).

Daarmee vervullen data- en transactie-API's een sleutelrol in de *standaardisatie van informatie* in het
zorginformatiestelsel.

### Samenhang tussen informatiestandaarden

Het is van groot belang dat informatiestandaarden samenhangen. Dat borgt hun gebruiksvriendelijkheid en
implementeerbaarheid. Eenzelfde zorgmedewerker is immers betrokken in vele zorgsituaties; diens informatiesysteem ook,
maar weer in andere combinaties. Dat is nu al het geval en dat zal alleen maar toenemen door voorziene ontwikkelingen
naar passende zorg en hybride zorg. Passende zorg vraagt om intensievere samenwerking en hybride zorg vraagt meer
digitale middelen, die naadloos aansluiten bij de fysieke zorgverlening.

Samenhang tussen informatiestandaarden vereist dat hun gegevenssets zijn samengesteld uit dezelfde
*zorginformatiebouwstenen*. Die bouwstenen zijn dan per stuk herkenbaar voor zorgverleners en implementeerbaar in
informatiesystemen – los van de specifieke zorgsituatie en het zorginformatiesysteem. API's kunnen dan net zo worden
samengesteld uit technische fragmenten, als gegevenssets bestaan uit zorginformatiebouwstenen[^2]. Daarmee spelen API's op
systeemniveau een strategische rol in de *samenhang in specificatie* van het zorginformatiestelsel.

[^2]: Een actueel voorbeeld hiervan is opgenomen in [Bijlage A](./apis-en-informatiebouwstenen-voorbeeld.md).

### Scheiding tussen API-specificatie en API-implementatie

Binnen een zorginformatiestelsel is eerst belangrijk wat digitale systemen doen en daarna hoe. In softwarekringen maakt
men daarvoor onderscheid tussen een API-specificatie en een API-implementatie. Een API-specificatie is een document
waarin precies staat wat een API te bieden heeft. Een API-implementatie is de software die doet wat de API-specificatie
zegt. Deze scheiding is van strategisch belang voor de regievoering op het zorginformatiestelsel. Zij maakt het mogelijk
om precieze afspraken te maken en besluiten te nemen (regie te voeren) over wat er nodig is los van de vraag hoe de
software moet worden gebouwd.

De scheiding tussen specificatie en implementatie heeft op termijn een tweede strategisch effect. Zij maakt het mogelijk
om vanuit eenzelfde API-specificatie verschillende softwareleveranciers verschillende API-implementaties te laten
bouwen. Dit bevordert een open softwaremarkt. Dit vraagt wel een inhoudelijk rijk genoeg gedocumenteerde
API-specificatie, die willekeurige softwareontwikkelaars mogen gebruiken zonder juridische beperkingen. Net zoals bij
open standaarden.

*Implementatie-onafhankelijkheid* van API-specificaties is geen eis vanaf het prille begin. Het is een actief te
bevorderen kwaliteit in een voldoende volwassen softwaremarkt. Dit komt omdat API-specificaties doorgaans pas op papier
komen nadat er een (eerste) implementatie is gemaakt. Dit geldt zeker in innovatieve domeinen waarin standaardisatie nog
minder vergevorderd is.

### Technologie-gedreven innovatie

API's zijn dus strategisch belangrijk voor databeschikbaarheid, voor standaardisatie en voor samenhang in specificatie.
Toch is de grote rol van API's op deze punten uiteindelijk niet leidend maar dienend. Dat betekent dat een API-strategie
(op systeemniveau) voor de verwezenlijking van haar doelen kritiek afhankelijk blijft van andere deelstrategieën van het
zorginformatiestelsel, op hogere niveaus (afbeelding 1)[^3]. Technologie kan de rol van die hogere niveaus onmogelijk
overnemen. Technologie kan wél de noodzaak van die andere deelstrategieën duidelijker maken.

Een zorginformatiestelsel dat inzet op passende en hybride zorg moet de kracht van API's inzetten op het juiste niveau.

Digitale technologie is en blijft een middel voor informatiegebruiksdoelen. Toch kunnen API's een krachtige en welkome
rol spelen in het uitdagen en ontdekken van nieuwe informatiebehoeften. Via API's kunnen data en transacties technisch
beschikbaar komen: nog voordat deze op de hogere niveaus gespecificeerd en gestandaardiseerd zijn en nog voordat deze
implementatie-onafhankelijk zijn. Een API-strategie voor de zorg moet ook deze technologie-gedreven innovatiekracht van
API's haar werk laten doen. Maar ze moet er wel voor blijven zorgen dat API's uiteindelijk altijd ondergebracht worden
in expliciete informatiebehoeften, implementatie-onafhankelijk.

[^3]:
    Het model op de achtergrond is een verfijning van het lagenmodel van Nictiz voor interoperabiliteit.
    [Bijlage B](./toelichting-op-de-verfijning-van-het-vijflagenmodel.md) licht de relatie tussen de modellen preciezer
    toe.

### Wat voorafging

De ontwikkeling van een API-strategie voor het zorginformatiestelsel heeft Nictiz ter hand genomen, in samenwerking met
vele anderen. Dit is een vervolg op een eerder door Nictiz uitgebracht advies aan het Ministerie van Volksgezondheid,
Welzijn en Sport (VWS). Dat advies werd gevraagd in de context van de beantwoording van Kamervragen over het
wetsvoorstel Wegiz (Wet Elektronische gegevensuitwisseling in de zorg).