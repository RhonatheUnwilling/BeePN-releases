# BeePN — uitgiftepunt

Dit is geen open source en geen broncode. Deze repo bestaat om één reden: het
programma BeePN moet kunnen opzoeken of er een nieuwere versie van zichzelf is.

Hier staat daarom niet meer dan:

- **`versie.json`** — een paar honderd bytes met het nieuwste versienummer, de
  downloadlink en de sha256 van dat bestand
- **`LICENSE`** — de voorwaarden waaronder BeePN mag worden gebruikt

De pakketten zelf hangen onder [Releases](../../releases) als bijlage, niet als
bestand in deze repo.

## Voor wie hier per ongeluk belandt

BeePN is een intern hulpmiddel: het geeft op locatie een overzicht van je
netwerkverbindingen, zet de netwerkadapter op het vaste IP-adres van een
gebouw, controleert of je VPN openstaat en pingt adressen.

Het valt onder de **PolyForm Internal Use License 1.0.0**: gebruiken en
aanpassen mag voor de interne bedrijfsvoering van je eigen organisatie,
verspreiden niet — ook niet van een aangepaste versie, en je kunt je
toestemming niet doorgeven.

Aanvullend, buiten de tekst van PolyForm om: de software en de broncode ervan
mogen niet worden gebruikt als trainingsmateriaal voor machinaal lerende
modellen of AI-systemen.

De volledige tekst staat in [`LICENSE`](LICENSE) en gaat ook mee in elk pakket.

© 2026 W.C.J. Tiddens. Alle rechten die de licentie niet uitdrukkelijk geeft
blijven voorbehouden aan de maker.

## Hoe het bijwerken werkt

BeePN kijkt **niet** uit zichzelf. Onder Instellingen zit een knop; druk je
daarop, dan leest hij `versie.json` van `raw.githubusercontent.com`. Dat is
bewust niet de GitHub-API: die staat zonder inloggen op zestig verzoeken per
uur per IP-adres, en op een kantoornetwerk delen alle gebruikers er één.

Staat er een hoger versienummer, dan vraagt BeePN of je wilt bijwerken. Zeg je
ja, dan wordt de zip opgehaald, de sha256 gecontroleerd, en pas daarna
uitgepakt en geïnstalleerd.

Bijwerken kan alleen bij een geïnstalleerde BeePN. Draait hij draagbaar of
vanuit een uitgepakt pakket, dan staat de knop uit.

## Een nieuwe versie uitgeven

1. `bouw_pakket.bat` draaien in de map van BeePN. Dat levert
   `pakket\BeePN-v<versie>.zip` — meteen de naam die de bijlage moet hebben —
   en drukt de sha256 al af in de vorm waarin hij in `versie.json` hoort.
2. Een release aanmaken met tag `v<versie>` en die zip als bijlage.
3. `versie.json` in deze repo bijwerken: versienummer, datum, de downloadlink
   van die bijlage, de sha256 en één regel over wat er nieuw is.

Stap 3 is wat BeePN te zien krijgt. Zolang `versie.json` niet is bijgewerkt,
merkt niemand dat er een release staat.
