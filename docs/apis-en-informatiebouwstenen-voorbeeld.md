# API's en informatiebouwstenen: voorbeeld

Een vijfenvijftigjarige vrouw gebruikt haar Persoonlijke Gezondheidsomgeving (PGO) om een verzameling zorggegevens over
zichzelf te downloaden uit het dossier van haar huisarts. Dit geeft haar in één oogopslag een beeld van haar gezondheid
en wat daarover in het dossier bekend is. Bovendien kan zij deze gegevens delen met andere zorgaanbieders bij wie zij
onder behandeling is of komt. Wanneer de PGO, de huisarts en die andere zorgaanbieders daarvoor de MedMij-afspraken
gebruiken, kan dit interoperabel en vertrouwd.

In het kader van MedMij zijn hiervoor zogenoemde *gegevensdiensten* gestandaardiseerd en opgenomen in een
[catalogus](https://afsprakenstelsel.medmij.nl/display/MMCatalogus/Actuele+gegevensdiensten). Haar huisarts heeft
besloten de gegevensdienst *Verzamelen Basisgegevens zorg 3.0* aan te bieden en de PGO heeft besloten die voor haar
gebruikers ook af te nemen, niet alleen van deze huisarts, maar van alle zorgaanbieders die in MedMij-verband deze
gegevensdienst aanbieden.

Om dit mogelijk te maken hebben de PGO-leverancier en de applicatiedienstverlener van de huisarts een standaard moeten
laten inbouwen. De informatiestandaard bij deze gegevensdienst heet de
[Basisgegevensset zorg](https://afsprakenstelsel.medmij.nl/display/MMCatalogus/Actuele+gegevensdiensten) en kent maar
liefst 28 verschillende stukjes informatie, die de vrouw dus ineens uit het huisartsdossier kan downloaden. Voor elk van
die 28 stukjes, de zogenoemde informatiebouwstenen, is een vertaling gemaakt naar een API. Die API's zijn
geïmplementeerd op de PGO en op het dossiersysteem van de huisarts, elk voor zijn respectievelijke helft: de afnemers-
of de aanbiederszijde.

Doordat die specificaties gestandaardiseerd zijn, kunnen alle PGO's die dat willen de betreffende gegevens voor hun
gebruikers ophalen bij alle zorgaanbieders die die gegevens aanbieden. Dat gebeurt dan steeds in het vertrouwde
MedMij-kader. Maar de standaardisatie- en implementatie-inspanning voor deze API's kan ook nuttig blijken voor andere
contexten dan MedMij alleen. Zo is het denkbaar dat dezelfde gegevensset ook rechtstreeks tussen zorgaanbiedersdossiers
moet kunnen worden uitgewisseld, nog steeds onder passende afspraken, maar in een andere context dan de huidige
MedMij-afspraken. Die kans wordt des te groter als daarbij niet steeds alle 28 API's tegelijk aan de orde zijn, maar een
selectie ervan, passend bij een specifieke uitwisselbehoefte.

Het zou van de betreffende zorgaanbieders en hun applicatiedienstverleners dan veel vergen om voor elke nieuwe context
en selectie opnieuw een standaard te moeten implementeren, en zich daarop te moeten kwalificeren. Voor de
standaardisatie-organisatie Nictiz vergt het bovendien ook veel om voor elke nieuwe context en selectie een nieuwe
standaard te moeten ontwikkelen en beheren. De tijd en kosten die dit vergt kunnen een stevige wissel trekken op het
tempo en zelfs de realiseerbaarheid überhaupt van al die behoeften aan gegevensuitwisseling.

Dat roept de vraag op of de standaardisatie-, implementatie- en kwalificatie-inspanning zich niet zou moeten richten op
elke API apart, zodat daarna API's naar believen kunnen worden toegepast en gecombineerd in allerlei contexten zonder
die inspanningen te hoeven herhalen.