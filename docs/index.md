# Introductie

Welkom bij de Leermodule “Geodata bevragen en gebruiken met de OGC API’s van PDOK” !

In deze leermodule ga je aan de slag met de OGC API’s van [PDOK](https://www.pdok.nl/) (Publieke Dienstverlening Op de Kaart). PDOK is hét geodataplatform van de Nederlandse overheid. Je leert in deze leermodule hoe je met behulp van OGC API’s geografische data in je browser kunt bekijken, hoe je de data kunt bevragen en hoe je de data op een interactieve kaart kunt tonen. Denk bijvoorbeeld aan een kaart waarop je kunt zien hoeveel inwoners er bij jou in de buurt wonen. 

!!! info "Doe mee!"

	Help ons mee met het verder verbeteren van deze leermodule! [Suggesties en verbetervoorstellen](#doe-mee) zijn welkom. 

## Wat is een OGC API? 

Een OGC API is een gestandaardiseerde interface voor het bekijken en bevragen van geografische data. Met een API, een Application Programming Interface, kunnen ontwikkelaars op een eenvoudige manier data van andere bronnen in hun eigen software integreren. Een API is dus een stopcontact voor data. Je hebt, in tegenstelling tot vroeger, geen specifieke kennis over geodata meer nodig om dit te kunnen. 
De OGC API standaard is ontwikkeld door het OGC. Het OGC (Open Geospatial Consortium) is een wereldwijde organisatie die standaarden voor het uitwisselen van geodata maakt. 
OGC API is een wereldwijde standaard. Dat zorgt ervoor dat iedereen op dezelfde manier geodata kan gebruiken. Dat bespaart een hoop tijd, geld en frustratie. 

Onderstaand overzicht laat zien hoe de OGC API standaard is gebouwd met bouwblokken. Al deze bouwblokken bevatten één of meerdere specificaties die door OGC zijn opgesteld en door de geocommunity zijn goedgekeurd.

![De OGC API bouwblokken](assets/ogc-api-building-blocks.png)

!!! info "OGC API bouwblokken"

	Voor meer informatie over de OGC API bouwblokken, zie [Achtergrondinformatie](./achtergrondinformatie/Wat zijn OGC APIs.md)

## Voor wie is deze leermodule bedoeld?

In eerste instantie is deze leermodule bedoeld voor IT-studenten. Jij bent bijvoorbeeld web developer of data-analist (in opleiding). Je hoeft geen ervaring met geodata te hebben om deze module te kunnen volgen. 

## Wat ga je leren?

!!! abstract "Leerdoelen"

	Na voltooiing van de leermodule:

	- Ben je je bewust van de meerwaarde van geo-informatie;
	- Ben je je bewust van de meerwaarde van het ontsluiten van geodata met gestandaardiseerde API's;
	- Ben je bekend met PDOK en het Kadaster en wat zij doen;
	- Ken je de mogelijkheden van geodata en kun je voorbeelden van toepassingen noemen;
	- Weet je wat een OGC API is, hoe die in elkaar zit, kun je de verschillende onderdelen benoemen en wat die onderdelen doen;
	- Weet je welke onderdelen van OGC API PDOK heeft geïmplementeerd en hoe PDOK dat heeft gedaan;
	- Weet je hoe een webmap werkt;
	- Kun je de landing page van de PDOK OGC API's gebruiken;
	- Kun je de URL's van de OGC API's vinden en gebruiken;
	- Kun je API GET requests samenstellen voor OGC API's:
		- Kun je featuredata bevragen met OGC API - Features;
		- Kun je tiles opvragen met OGC API - Tiles;
	- Kun je OGC API's toevoegen aan een webmap.

	Kortom: je kunt straks OGC API's gebruiken en implementeren. 

## Benodigde voorkennis

Om deze leermodule goed te kunnen volgen, is het handig dat je al kunt werken met (REST) API's en data. Daarnaast is basiskennis web development en JavaScript noodzakelijk. Voor het deel ['Analyseer data met OGC API - Features met Python'](<features/Casus - Analyseer data met OGC API - Features met Python.md>) gaan we ervan uit dat je Python kunt en bekend bent met notebookomgevingen. En tot slot kun je omgaan met de commandline. 

## Uit welke onderdelen bestaat deze leermodule?

Deze leermodule bestaat uit vier onderdelen. Afhankelijk van je voorkennis kun je kiezen hoe je door de stof heen gaat.

### 👉 Nieuw met OGC API’s en geografische webservices?
Begin dan bij **Achtergrondinformatie** en werk de onderdelen op volgorde door.

### 👉 Al bekend met WMS, WMTS en WFS?
Dan kun je **Achtergrondinformatie** overslaan en direct starten met **OGC API – Tiles** of **OGC API – Features**.

### Overzicht van de onderdelen

| Onderdeel | Beschrijving |
| ----------- | ----------- |
| [Achtergrondinformatie](./achtergrondinformatie/Introductie.md) | *Wat is geografische data? Wat zijn OGC API’s? En wat doet PDOK?* |
| [OGC API – Tiles](./tiles/Introductie.md) | *Bekijk geodata op de kaart* |
| [OGC API – Features](./features/Introductie.md) | *Maak een interactieve kaart: Vraag objectinformatie op, werk op een interactieve manier met data* |
| [Afronding](Afronding.md) |  |

## Doe mee!

Sommige onderdelen zijn nog in ontwikkeling en nog niet compleet. Doe met ons mee!
	
Heb je suggesties voor aanvullingen, verbeteringen of zie je een fout? Die zijn altijd welkom!

[Maak een issue aan op GitHub](https://github.com/PDOK/leermodule-ogc-api/issues) of [maak een pull request](https://github.com/PDOK/leermodule-ogc-api/pulls). 




