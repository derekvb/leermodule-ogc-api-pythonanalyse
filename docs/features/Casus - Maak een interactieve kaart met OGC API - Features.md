# Maak een interactieve kaart met OGC API - Features
Tot nu toe hebben we vooral gekeken naar visualisatie van data. Het bekijken van geodata is maar slechts één aspect van het gebruiken van geodata. In dit onderdeel voeg je data aan je kaart toe die je op een interactieve manier kunt gebruiken. Je doet dit met behulp van de JavaScript library MapLibre. En aan de hand van een casus. 

Eerst introduceren we de casus waaraan je gaat werken. Daarna voeg je geodata aan je kaart toe in de vorm van een statisch GeoJSON bestand. En tot slot voeg je een OGC API - Features toe aan jouw kaart. 

!!! info

    De nu volgende oefeningen zijn identiek aan oefeningen van [Casus - Maak een kaart met OGC API - Tiles](<../tiles/Casus - Maak een kaart met OGC API - Tiles.md>). Wanneer je deze oefeningen al gedaan hebt, ga dan [hier](<#plot-een-geojson-bestand-op-de-kaart>) verder. 

## Introductie casus

Hoe is de leefbaarheid in jouw buurt of wijk? Dat gaan we onderzoeken in deze opdracht. Je gaat een kaart maken die inzicht geeft in de kwaliteit van de leefomgeving van jouw buurt. 

Hoe kun je inzicht geven in de leefbaarheid? Dat kan met verschillende kaartlagen. Zijn er bijvoorbeeld voldoende bomen? Zijn er voldoende scholen in de buurt? Je gaat dit in kaart brengen voor de buurt waar jij woont. 

Met geodata kun je inzicht geven in dit soort vraagstukken. PDOK ontsluit allerlei data over de leefomgeving (maar ook andere thema's) middels OGC API's. En specialisten en ontwikkelaars kunnen met behulp van die API's kaarten en viewers maken om beleidsmakers, analisten en inwoners inzicht te geven in de leefomgeving. 

In deze casus nemen we jou stap voor stap mee:

1. **Maak een ontwerp voor jouw webmap:** voor wie maak je deze webmap? Wat is het doel en welke data is daarvoor nodig en in welke vorm?
2. **Zet een ontwikkelomgeving op:** zet code klaar om mee te werken.
3. **Maak een kaartviewer die als basis kan dienen:** begin met een onderlegger. 
4. **Vind geschikte featuredata:** zoek en vind databronnen.
5. **Voeg de featuredata toe aan jouw kaart:** voeg de kaartlagen toe aan jouw webmap. 
6. **Evalueer het eindresultaat:** komt de webmap overeen met jouw ontwerp?

Je gaat nu aan de hand van bovenstaande stappen jouw eigen webmap maken met OGC API - Features. Stapje voor stapje en met behulp van voorbeelden kom je steeds verder. 

Laten we beginnen! 

## Ontwerp jouw webmap

Een goed informatieproduct is nergens zonder een goed ontwerp. Dat geldt zeker voor een webmap. Het is goed om van tevoren na te denken over het doel van de kaart, wie de doelgroep is en wat die doelgroep precies nodig heeft. Anders wordt het een onbruikbare webmap. 

Laten we een ontwerp maken voor de webmap aan de hand van de volgende vragen:

- **Doelgroep:** voor wie is de webmap bedoeld?
- **Doel en scope:** welk doel wil de doelgroep bereiken met de webmap?
- **Benodigde informatie:** welke data is daarvoor nodig en in welke vorm?
- **Geografische afbakening en schaal:** voor welk gebied maak je de webmap en wat is het schaalniveau?

Maak een kort en bondig *ontwerpdocument* waarin je deze vragen beantwoord. 

Voor elk aspect doen we een suggestie. Voor deze fictieve casus kun je de suggestie volgen, maar je bent natuurlijk vrij om zelf iets te bedenken. 

### Doelgroep

Het is belangrijk om te weten wie de doelgroep van de webmap is. Want elke doelgroep heeft weer andere wensen en heeft andere informatie nodig. 

Stel jezelf de vragen: wie is de doelgroep van de kaart? Voor wie moet de kaart inzicht geven? En bestaat die doelgroep uit experts of een breder publiek? Experts zullen waarschijnlijk gedetailleerde informatie nodig hebben. Het is niet erg als er jargon gebruikt wordt. Een breed publiek heeft waarschijnlijk meer behoefte aan meer algemene informatie. Vaktermen moeten dan vermeden worden. 

!!! warning "Toegankelijkheid"

    Hou ook rekening met toegankelijkheid: moet de webmap ook geschikt zijn voor doelgroepen met minder digitale vaardigheden of met visuele beperkingen?

!!! tip

    Normaal gesproken is dit natuurlijk een belangrijke overweging. 
    
    Wij raden aan om voor deze fictieve opdracht de 'geïnteresseerde burger' als doelgroep te nemen. Met deze brede doelgroep voorkom je het risico dat je geen geschikte data kunt vinden, en haal je toch de leerdoelen.

    Natuurlijk mag je zelf ook iets anders kiezen. 

**:arrow_right: Noteer de doelgroep in jouw ontwerpdocument.**

### Doel en scope

Het is belangrijk om een doel voor ogen te hebben voor de webmap.

Stel jezelf de volgende vragen: Welk doel wil de doelgroep bereiken met jouw webmap? Welke vragen worden ermee beantwoord? En wat is de vraag achter de vraag? Met andere woorden: wat wil de gebruiker doen met de informatie in de kaart?

Stel dat we als doel nemen: *inzicht bieden in de leefbaarheid van jouw buurt*. Wat versta je precies onder *inzicht*? En wat versta je precies onder het begrip *leefbaarheid*? 

Een zekere afbakening is ook handig. Waar is de kaart voor bedoeld en waar is de kaart vooral niet voort bedoeld? Met één kaart kun je helaas geen wereldvrede stichten. Met andere woorden: wat is de scope van deze webmap? 

!!! tip

    Normaal gesproken is dit natuurlijk een belangrijke overweging. 
    
    Wij raden aan om voor deze fictieve opdracht 'inzicht bieden in de kwaliteit van de leefomgeving van een buurt' te nemen als doel. Met dit brede doel voorkom je het risico dat je geen geschikte data kunt vinden, en haal je toch de leerdoelen. 

    Natuurlijk mag je zelf ook iets anders kiezen.

**:arrow_right: Noteer het doel en de scope in jouw ontwerpdocument.**

### Benodigde informatie

De doelgroep wil een bepaald doel bereiken met behulp van jouw webmap.

Wat voor soort informatie is er nodig om de doelgroep te helpen met het bereiken van hun doel? Welke informatie/data is daar voor nodig? En in welke vorm moet de data worden aangeboden? 

- **Wat voor informatiebehoefte:** Is er behoefte aan operationele informatie, of informatie die vooral wordt gebruikt voor besluiten op tactisch of strategisch niveau?
- **Aggregatieniveau:** op welk niveau moet de data geaggregeerd zijn? Is er vooral detail nodig of abstracte informatie (bijvoorbeeld gemiddeldes)?
- **Tijdschaal:** op welke tijdschaal is er informatie nodig? Actuele data of bijvoorbeeld gemiddeldes over de afgelopen jaren?
- **Visualisatie:** hoe moet de data worden gevisualiseerd? 

Welke informatie benodigd is en in welke vorm bepaalt welke datasets je gebruikt voor je webmap.

!!! warning "Toegankelijkheid"

    Hou ook rekening met toegankelijkheid bij de visualisatie: moet de webmap ook geschikt zijn voor bijvoorbeeld kleurenblinden? 

**:arrow_right: Noteer de benodigde informatie en vorm in jouw ontwerpdocument.**

### Geografische afbakening en schaal

Op welk schaalniveau wil jouw doelgroep de informatie hebben? Is dit op landelijk niveau? Op gemeentelijk niveau? Of bijvoorbeeld op wijkniveau?

Het geografische schaalniveau bepaalt ook of de data gedetailleerd of abstract moet zijn. 

En hoe baken je het gebied af? Je kan de kaart maken voor de plek waar jij woont, maar dit mag ook een andere plek in Nederland zijn. 

!!! tip

    Normaal gesproken is dit natuurlijk een belangrijke overweging. 
    
    Wij raden aan om voor deze fictieve opdracht jouw eigen buurt te gebruiken. 

    Natuurlijk mag je zelf ook iets anders kiezen.

**:arrow_right: Noteer de geografische afbakening en de schaal in jouw ontwerpdocument.**

Als het goed is, heb je nu een ontwerp met de volgende aspecten:

- **Doelgroep:** voor wie is de webmap bedoeld?
- **Doel en scope:** welk doel wil de doelgroep bereiken met de webmap?
- **Benodigde informatie:** welke data is daarvoor nodig en in welke vorm?
- **Geografische afbakening en schaal:** voor welk gebied maak je de webmap en wat is het schaalniveau?

## Maak jouw eigen webmap

Nu het ontwerp gereed is, is het tijd om aan de slag te gaan. Allereerst zet je een ontwikkelomgeving op om in te werken en te testen. Vervolgens maak je op basis van het voorbeeld, dat we beschikbaar hebben gesteld in deze repo, een webmap die als basis dient voor de rest van je project. Tot slot zoek je featuredata die geschikt is voor jouw web map en voeg je deze toe.

### Zet een ontwikkelomgeving op

Zet een ontwikkelomgeving op waarin je de webmap kunt ontwikkkelen en testen. 

Als eerste heb je de voorbeeldcode nodig die wij hebben gemaakt en die te vinden is in deze repository. In de casus ga je voortborduren op het voorbeeld, zodat je niet het wiel opnieuw uit hoeft te vinden.

Als het goed is heb je in het onderdeel [Analyseer een voorbeeldkaart](<./Analyseer een voorbeeldkaart.md/#bekijk-het-voorbeeld-in-een-code-editor>) deze GitHub repository al gecloned. Maar mocht je dit nog niet gedaan hebben: hier volgt de uitleg. 

Wij suggereren twee verschillende aanpakken: in een IDE werken of werken met een file manager en een teksteditor. 

 Hieronder volgt de uitleg voor Visual Studio Code en de meer klassieke aanpak. Maar uiteraard kun je zelf ook een andere IDE of een andere aanpak gebruiken. 

=== "VSCode"

    1. Open VSCode
    2. Klik op 'Clone Git Repository'

        ![Klik op 'Clone Git Repository'](../assets/casus/VSCode_clone-1.png)
    
        Gebruik daarbij de volgende URL: <https://github.com/PDOK/leermodule-ogc-api>

        ![Plak de URL](../assets/casus/VSCode_clone-2.png)
    
    3. Kies een locatie op jouw schijf om de repository te downloaden en klik op 'Select as Repository Destination'

    4. Wacht tot de repository is gedownload

    5. Klik op 'Open':

        ![Klik op 'Open'](../assets/casus/VSCode_clone-3.png)    

    6. Klik op 'Yes, I trust the authors':

        ![Klik op 'Yes, I trust the authors'](../assets/casus/VSCode_clone-4.png) 

    7. Bekijk de bestanden in de Explorer (linkertabblad)

        De voorbeeldcode bevindt zich in `docs/voorbeelden/features`

    8. Maak in de repository een nieuwe folder aan, en zet daarin een kopie van de voorbeeldcode.

        Op die manier hou je het voorbeeld schoon en kun je daar altijd op teruggrijpen.  

    9. Zet een lokale test web server op in de folder die je zojuist hebt gemaakt:

        Open een Terminal (View -> Terminal) en voer uit:

        ```
        cd %jouwfolder
        python -m http.server
        ```

        Vervang `%jouwfolder` door de locatie van de folder waar jij de voorbeeldcode naartoe hebt gekopieerd

    10. Ga in je webbrowser naar `localhost:8000` om het voorbeeld te bekijken.

=== "Klassieke aanpak met file manager en teksteditor"

    1. Ga naar de repository op GitHub: <https://github.com/PDOK/leermodule-ogc-api>
    2. Klik op 'Code' en vervolgens op Download ZIP

        ![alt text](../assets/casus/Git-clone.png)

    3. Pak de zip uit op jouw schijf

    4. Bekijk de bestanden in een File explorer 

        De voorbeeldcode bevindt zich in de folder `docs/voorbeelden/features`

    5. Maak in de repository een nieuwe folder aan, en zet daarin een kopie van de voorbeeldcode.

        Op die manier hou je het voorbeeld schoon en kun je daar altijd op teruggrijpen.  

    6. Open een commandline

    7. Zet een lokale test web server op in de folder die je zojuist hebt gemaakt:

        ```
        cd %jouwfolder
        python -m http.server
        ```

        Vervang `%jouwfolder` door de locatie van de folder waar jij de voorbeeldcode naartoe hebt gekopieerd

    8. Ga in je webbrowser naar localhost:8000 om het voorbeeld te bekijken.

    Je kunt de code vervolgens bewerken in een teksteditor zoals Notepad++ of Sublime Text. 

### Maak een basiskaart

In deze stap maak je op basis van het voorbeeld een webmap die als basis dient voor de rest van het project. 

Voordat we echt aan de slag gaan met data, moet er een goede basis liggen. In `index.html` en `main.js` ga je zelf de volgende zaken aanpassen op basis van jouw ontwerp:

- Titel van de webmap
- Achtergrondkaart en bijbehorende stijl
- Geografisch:
    - Initieel zoomniveau
    - Initieel center
    - De 'bounds' van de kaart

#### Pas index.html aan

**:arrow_right: Open `index.html`**

**:arrow_right: Pas de titel aan:**

    <title>Jouw titel</title>

**:arrow_right: Vergeet je wijzigingen niet op te slaan**

#### Pas main.js aan

**:arrow_right: Open `main.js`**

    const map = new maplibregl.Map({
    container: 'map', // container id
    style: 'https://api.pdok.nl/kadaster/brt-achtergrondkaart/ogc/v1/styles/standaard__webmercatorquad?f=json', // style URL
    center: [5.44, 52.05], // starting position [lng, lat]
    zoom: 7, // starting zoomlevel
    minZoom: 6, // minimum zoomlevel zoom out
    maxZoom: 14 // maximum zoomlevel zoom in

In het voorbeeld hebben we gekozen voor de BRT Achtergrondkaart met de standaard stijl in WebMercator. We raden sterk aan om in jouw eigen web map ook de WebMercator BRT Achtergrondkaart te gebruiken. Wel zou je een andere stijl dan de standaard stijl kunnen gebruiken:

**:arrow_right: Ga naar <https://api.pdok.nl/kadaster/brt-achtergrondkaart/ogc/v1/styles>**

**:arrow_right: Kies met behulp van de voorbeeldweergave een WebMercatorQuad style**

**:arrow_right: Plak de URL in jouw code**

Standaard krijg je heel Nederland te zien wanneer je de kaart opent. Het is handiger als de kaart meteen is ingezoomd op jouw eigen interessegebied. 

**:arrow_right: Ga naar <https://vibhorsingh.com/boundingbox/>**

**Zoom in naar jouw interessegebied**

**Gebruik het Center in jouw `main.js`:**

![center kopiëren](../assets/casus/boundingbox.png)

    center: [5.44, 52.05]

Wellicht wil je ook dat gebruikers alleen jouw interessegebied kunnen bekijken en de kaart niet daar buiten kunnen verplaatsen. Je kunt dit bereiken door 'maxBounds' in te stellen. 

In combinatie met de 'maxBounds' is het ook handig om het initiële, maximale en minimale zoomniveau te beperken. Laten we dat eerst doen.

**:arrow_right: Open jouw eigen webmap in een webbrowser**

**:arrow_right: Open het netwerk-tabblad in de developer tools**

**:arrow_right: Zoom in naar het gewenste:**

- **Initiële zoomniveau**
- **Zoomniveau dat de gebruiker maximaal mag uitzoomen**
- **Zoomniveau dat de gebruiker maximaal mag inzoom**

**:arrow_right: Noteer/kopieer hierbij de zoomlevels die je ziet in de URL's van de tegelrequests:**

![Kopieer het zoomlevel](../assets/casus/url-request.png)

Voeg deze zoomlevels toe in je code:

    zoom: 7, // starting zoomlevel
    minZoom: 6, // minimum zoomlevel zoom out
    maxZoom: 14 // maximum zoomlevel zoom in

Je hebt nu de zoomlevels afgedwongen voor de gebruiker. Laten we nu het `maxBounds` opzoeken. De `maxBounds` zijn coördinaten die als het ware de begrenzing van het kaartvenster vormen. Om die coördinaten te bepalen kunnen we weer de Bounding box online tool gebruiken. 

**:arrow_right: Kijk nogmaals op <https://vibhorsingh.com/boundingbox/>**

**:arrow_right: Zoom zo ver mogelijk uit op jouw interessegebied, zodat het nét in het kaartvenster past**

**:arrow_right: Kopieer de coördinaten achter 'Map':**

![bounds kopiëren](../assets/casus/bounds.png)

!!! tip

    Let op dat de `maxBounds`, `maxZoom` en `minZoom` in overeenstemming met elkaar moeten zijn. Wanneer de ingestelde `maxBounds` zich buiten het gebied bevinden dat je initieel ziet, zal het niet goed werken. Dit vraagt wat trial-and-error. 

**:arrow_right: Voeg de volgende code toe aan jouw `main.js`:**

    maxBounds: [5.08530, 52.07246], [5.16769, 52.10060] //vervang de coördinaten door jouw eigen coördinaten. 

**:arrow_right: Test jouw web map: Werkt het goed en is jouw interessegebied volledig zichtbaar?**

Als het goed is, heeft jouw kaart nu een goed initieel zoomlevel, minimum zoomlevel, maximum zoomlevel en is de view beperkt tot jouw interessegebied. 

!!! info "Zoomlevel"

    Wellicht is het je opgevallen dat je op <https://vibhorsingh.com/boundingbox/> ook het zoomlevel kunt zien. Toch gebruiken we het netwerktabblad in onze eigen webmap om de zoomlevels te achterhalen. Er is namelijk een verschil tussen het zoomlevel in de tool en het zoomlevel in onze eigen webmap. 

!!! question "Vraag"

    Waar wordt het verschil tussen het zoomlevel in <https://vibhorsingh.com/boundingbox/> en het zoomlevel in je eigen webmap door veroorzaakt?

??? success "Antwoord"

    De boundingbox tool gebruikt 'XYZ' tiles van Mapbox. Die gebruiken een ander tiling scheme: de tegelgrootte is bijvoorbeeld 512x512 pixels ipv 256x256 pixels. 

De basis staat nu! 

### Plot een GeoJSON bestand op de kaart

Laten we eens simpel beginnen en een GeoJSON-bestandje aan onze kaart toevoegen en visualiseren.

!!! info "GeoJSON"

    GeoJSON is een bestandsformaat, gebaseerd op JSON, om geodata op te slaan en uit te wisselen. Dit bestandsformaat is vooral geschikt voor uitwisseling van geodata via het internet. Libraries zoals MapLibre en Leaflet kunnen er goed mee overweg. 

In de map `voorbeelden/features` is een GeoJSON-bestand aanwezig met daarin alle vestigingen van het Kadaster in Nederland: `kadaster.geojson`. 

Laten we eerst de inhoud van de GeoJSON eens inspecteren.

**:arrow_right: Bekijk `kadaster.geojson` in een code editor**

Laten we de GeoJSON toevoegen aan onze kaart!

**:arrow_right: Voeg de volgende code toe aan `main.js`:**

	map.on('load', () => {
		map.addSource('', {
			type: 'geojson',
			data: ''
		});
		map.addLayer({
			'id': '',
			'type': 'circle',
			'source': '',
			'paint': {
				"circle-radius": 5, // straal van de cirkel
				"circle-stroke-color": "#000000" // kleur van de cirkel
			}
		});
	});

**:arrow_right: Vul zelf de ontbrekende onderdelen in.**

??? hint 

    Kijk nog eens in het [vorige hoofdstuk](<./Analyseer een voorbeeldkaart.md>) of in `main.js` om te zien hoe je een bron en een kaartlaag toevoegt.

Kom je er niet uit? Klik het antwoord dan open:

??? success "Antwoord"

		map.on('load', () => {
			map.addSource('kadastersource', { // zelfgekozen naam voor de bron
				type: 'geojson',
				data: './kadaster.geojson' // bestandsnaam van het geojson-bestand
			});
			map.addLayer({
				'id': 'kadaster', // zelfgekozen naam voor de kaartlaag
				'type': 'circle',
				'source': 'kadastersource', // naam van de bron, zie hierboven
				'paint': {
					"circle-radius": 5, // straal van de cirkel
					"circle-stroke-color": "#000000" // kleur van de cirkel
				}
			});
		});

**:arrow_right: Test of jouw code werkt in de browser.**

Als het goed is, ziet jouw kaart er nu zo uit:

![kadastervestigingen op de kaart](../assets/casus/kadaster_geojson.png)

!!! info

    Kijk voor meer voorbeelden in [de officiële documentatie van MapLibre](<https://maplibre.org/maplibre-gl-js/docs/examples/add-a-geojson-polygon/>).

!!! question "Vraag"

    Is het toevoegen van een GeoJSON-bestand een handige manier om data toe te voegen? Wanneer is dit wel handig en wanneer niet?

??? hint

    `kadaster.geojson` is een statisch bestand

??? success "Antwoord"

    `kadaster.geojson` is een statisch bestand dat je zelf moet hosten. Het nadeel van een los bestandje is dat het al snel verouderd is. Wanneer er een Kadastervestiging bij komt of informatie verandert, is jouw webmap meteen verouderd. Het is veel werk om jouw bestand dan weer up-to-date te maken.

    Nee, dit is dus geen handige manier om data toe te voegen. Tenzij je zeker weet dat de data nooit zal veranderen, maar die kans is klein. 

Natuurlijk vind je op PDOK API's en web services die altijd up-to-date zijn. Als je gebruik maakt van de API's van PDOK weet je zeker dat je niet met verouderde data werkt. PDOK is een stabiele databron met altijd actuele data. 

We gaan nu dan ook aan de slag met het toevoegen van featuredata (collecties) van PDOK OGC API - Features. 

### Vind geschikte featuredata

De basis staat! Nu is het tijd om kaartlagen toe te voegen. Als het goed is, heb je in de ontwerpfase geïdentificeerd welke informatie je wilt tonen. Nu ga je hier geschikte databronnen voor zoeken. 

Er zijn veel verschillende plekken waar je geodatasets kunt vinden. We beperken ons voor nu tot het [Nationaal Georegister](https://www.nationaalgeoregister.nl/) en [PDOK.nl](https://www.pdok.nl/). 

!!! info "Nationaal Georegister"

    Het Nationaal Georegister (NGR) is een vindplek voor geodatasets. Organisaties kunnen hun data kenbaar maken via het NGR. De data wordt niet gehost op het NGR, er wordt slechts een verwijzing opgenomen naar de databron. Daarnaast vind je voor elke dataset een beschrijving en gegevens over de contactpersoon, actualiteit en nog veel meer. Het NGR is dus een metadataregister: het bevat data over data. 

    PDOK daarentegen is een databron: op het PDOK-platform hosten organisaties hun data. Data van PDOK is vindbaar op [de website van PDOK](<https://www.pdok.nl/datasets>), maar ook op het NGR. 

Er zijn veel verschillende soorten geodatasets. Je kunt data downloaden in verschillende bestandsformaten, zoals Geopackage, maar ook via verschillende soorten web services en API's. Voor dit onderdeel van de leermodule beperken we ons tot de **OGC API - Features datasets van PDOK**. 

We gaan nu naar het Nationaal Georegister en stellen daar filters in zodat we alleen OGC API - Features van PDOK te zien krijgen:

**:arrow_right: Ga naar <https://www.nationaalgeoregister.nl/>**

**:arrow_right: Laat de zoekbalk leeg en klik op 'Zoeken'**

We krijgen nu alle datasets op het NGR te zien (hoeveel zijn het er?) maar we kunnen nu wel de zoekopdracht verder verfijnen met de filters aan de linkerkant. 

**:arrow_right: Vink bij Organisaties alleen 'Beheer PDOK' aan**

![vink Beheer PDOK aan op NGR](../assets/casus/ngr_pdok.png)

**:arrow_right: Vink nu bij Brontype alleen 'service' aan**

!!! info

    In het NGR wordt onderscheid gemaakt tussen Datasets en Services. Een Dataset wordt ontsloten via 1 of meerdere services. Een Dataset record gaat over de dataset zelf en bevat voor inhoudelijke informatie over die dataset. Een Service record gaat over de verschillende ontsluitingen van een dataset, zoals WFS, WMS of Atom. 

    Bijvoorbeeld: de dataset BGT heeft meerdere services: download API, OGC API - Tiles, OGC API - Features en WMTS. 
    
    En in dit geval zijn we op zoek naar alle OGC API - Features ontsluitingen. 

**:arrow_right: Vink nu bij Online Bronnen alleen 'OGC:API features' aan**

(misschien moet je op 'meer' klikken voordat je deze te zien krijgt)

Nu krijg je alle OGC API - Features van PDOK te zien:

![Alle datasets met OGC API - Features op NGR](../assets/casus/ngr_features_resultaten_blur.png)

!!! question "Vraag"

    Hoeveel OGC API - Features services krijg je nu te zien?

??? success "Antwoord"

    Momenteel (december 2025) zijn er 94 datasets met een OGC API - Features:

    ![het aantal datasets met een ogc api - features](../assets/casus/aantal_ogc_api-features.png)

!!! info

    Alle datasets van PDOK zijn ook vindbaar via [pdok.nl/datasets](<https://www.pdok.nl/datasets>). De API's van PDOK (onder andere download API's en OGC API's) zijn bovendien vindbaar via [api.pdok.nl](<https://api.pdok.nl/>). Echter, het Nationaal Georegister heeft betere mogelijkheden om het aanbod te doorzoeken (bijvoorbeeld met de filters die je zojuist hebt gebruikt)

Nu je weet hoe je op NGR alle beschikbare OGC API - Features kunt vinden, is het tijd om te onderzoeken welke datasets geschikt zijn voor jouw casus. 

!!! question "Vraag"

    Welke OGC API - Features herken je al uit de eerdere oefeningen? 

Ga op ontdekkingstocht in het beschikbare aanbod. Doe dit aan de hand van jouw ontwerp. 

**:arrow_right: Verken de verschillende datasets op NGR en onderzoek de geschiktheid voor jouw casus:**

- **Lees de beschrijvingen**
- **Bekijk de landing pages: welke collecties zijn er? Wat bevatten die collecties?**

**:arrow_right: Kijk nog eens naar jouw ontwerp:**

- **Is de dataset geschikt voor jouw doelgroep?**
- **Bevat de dataset informatie die relevant is voor jouw doel?**
- **Bevat de dataset informatie in een geschikte vorm?**
- **Is de geografische afbakening en schaal geschikt voor jouw doel?**

Voer vervolgens de volgende stappen uit (we leggen hierna uit hoe je dit precies doet aan de hand van een voorbeeld). 

**:arrow_right: Zoek de URL van de collectie op.**

**:arrow_right: Voeg de collectie toe aan jouw web map.**

We laten nu zien hoe je één kaartlaag toevoegt. We doen dit met de 'NWB - Wegen OGC API Features'. 

Daarna is het aan jou om dit zelf te doen met andere kaartlagen. 

**:arrow_right: Ga weer terug naar NGR, naar de OGC API - Features resultaten:**

![Alle datasets met OGC API - Tiles op NGR](../assets/casus/ngr_features_resultaten.png)

**:arrow_right: Zoek en klik op 'NWB - Wegen OGC API Features'**

!!! hint "Gebruik indien nodig de zoekbalk of filters"

![OGC API - Features van de NWB wegen in het Nationaal Georegister](../assets/casus/ngr_nwb_features.png)

**:arrow_right: Lees de beschrijving en bekijk de gerelateerde dataset 'Nationaal wegenbestand - wegen - Wegvakken en hectometerpunten (NWB)' (dit is het het bijbehorende dataset record)**

**:arrow_right: Klik onder 'Downloads, views en links' op de API URL**

Je gaat nu naar de inmiddels welbekende landing page!

### Voeg OGC API – Features collecties toe aan je kaart

We gaan nu een OGC API - Features toevoegen aan onze kaart.

**:arrow_right: Noteer (kopieer) de URL van de landing page van de 'Nationaal wegenbestand - wegen - Wegvakken en hectometerpunten (NWB)' OGC API.**

**Ga op de landing page naar 'Collections'.**

**Klik op de collectie 'Wegvakken'.**

![de wegvakken collectie](../assets/casus/wegvakken_collectie.png)

Dit zijn alle wegen van heel Nederland. 

**Noteer de naam van de collectie in de URL.** 

Door de volgende code toe te voegen aan main.js, kun je de wegvakken collectie uit de Nationaal wegenbestand OGC API toevoegen aan je webmap.

**:arrow_right: Voeg onderstaande code toe aan main.js:**

	map.on('load', () => {
		const wegvakkensource = 'wegvakken-src'

		new OGCFeatureCollection(wegvakkensource, map, {
			url: 'https://api.pdok.nl/rws/nationaal-wegenbestand-wegen/ogc/v1',
			collectionId: 'wegvakken',
			limit: 1000
		})

		map.addLayer({
			'id': 'wegvakken',
			'source': wegvakkensource,
			'type': 'line',
			'paint': {
				'line-color': '#000000',
				'line-width': 2
			}
		});
	})

**:arrow_right: Bekijk jouw kaart en test of je de wegvakken ziet.**

!!! question "Vraag"

    Wat valt je op? Zie je meteen alle wegen?

??? success "Antwoord"
    
    Nee, je ziet niet meteen alle wegen. Je ziet hier en daar een snippertje. 

    Dit komt doordat de OGC API - Features niet geoptimaliseerd is voor zoveel features. De requests worden met behulp van de bounding box opgeknipt, maar het aantal features dat in een bounding box zit, overstijgt de 1000 ruim. 

    ![snippertjes](../assets/casus/features_snippertjes.png)

!!! question "Vraag"

    Hoe kun je ervoor zorgen dat je wel een compleet beeld krijgt? 

??? success "Antwoord"

    Wanneer je ver genoeg inzoomt, zie je wel alle features (alle wegen). Een bounding box bevat dan niet meer 1000 features.

OGC API - Features is niet gemaakt met visualisatie als hoofddoel. Voor visualisatie is OGC API - Tiles geschikter. Toch kan het nuttign zijn om OGC API - Features te visualiseren, bijvoorbeeld wanneer je interactieve dingen met de data wilt doen. 

Laten we ervoor zorgen dat de gebruiker niet meer die snippertjes te zien krijgt, maar een volledig beeld van de dataset. 

We gaan dit doen door de weergave van de kaartlaag pas in te schakelen op een bepaald zoomniveau. 

Eerst kijken we op welk zoomniveau alle features te zien zijn. 

**:arrow_right: Zoom op de webmap in totdat je alle features ziet:**

![ingezoomd zodat alle features zichtbaar zijn](../assets/casus/features_ingezoomd_zichtbaar_requests.png)

**:arrow_right: Kijk in het netwerktabblad van de developer tools op welk zoomniveau je zit:**

- **Bekijk de URL van het laatste tile request. Bijvoorbeeld <https://api.pdok.nl/kadaster/brt-achtergrondkaart/ogc/v1/tiles/WebMercatorQuad/8/83/132?f=mvt> (fictief voorbeeld)**
- **Het eerste getal achter `WebMercatorQuad` is het zoomlevel (in het fictieve voorbeeld hierboven dus 8) Noteer dit.**

**:arrow_right: Voeg de volgende code toe aan de functie `map.addLayer()` in `main.js`:**

    "minzoom": X, // vervang X door het zoomlevel

Klap de hint uit als je er niet uit komt. 

??? hint

    De code:

		map.on('load', () => {
			const wegvakkensource = 'wegvakken-src'

			new OGCFeatureCollection(wegvakkensource, map, {
				url: 'https://api.pdok.nl/rws/nationaal-wegenbestand-wegen/ogc/v1',
				collectionId: 'wegvakken',
				limit: 1000
			})

			map.addLayer({
				'id': 'wegvakken',
				'source': wegvakkensource,
				"minzoom": 14, // zichtbaar vanaf zoomlevel 14
				'type': 'line',
				'paint': {
					'line-color': '#000000',
					'line-width': 2
				}
			});
		})

    Je voegt dit toe na `const map = new maplibregl.Map()`

!!! tip

    Je kunt overigens met "maxzoom" instellen dat een kaartlaag niet meer zichtbaar is vanaf een bepaald zoomlevel. 

Wanneer je de code hebt toegevoegd, zouden de features pas op een geschikt zoomlevel zichtbaar moeten worden. 

**:arrow_right: Bekijk nu jouw webmap en controleer of dit zo is.**

![de features zijn nog niet zichtbaar](../assets/casus/features_ingezoomd_nog_niet_zichtbaar.png)

Eén zoomlevel verder:

![1 niveau verder ingezoomd zijn de features wel zichtbaar](../assets/casus/features_ingezoomd_zichtbaar.png)

!!! info "Visualisatie"

    Als je wil, kun je de kleuren veranderen naar iets anders dan zwart. Kijk bij [OGC API - Tiles](<../tiles/Casus - Maak een kaart met OGC API - Tiles.md/#optie-3-maak-zelf-een-nieuwe-style-from-scratch>) en leer hoe je dit kunt doen. 

Mooi, je hebt nu een collectie uit de OGC API van het Nationaal Wegenbestand toegevoegd aan jouw web map. Vervolgens heb je ingesteld dat de kaartlaag pas vanaf een bepaald zoomlevel zichtbaar wordt. 

!!! warning "TO DO"

    Interactie toevoegen. Maak gebruik van: filter (+ historie), 1 item, bounding box, relaties

#### Samenvatting kaartlagen toevoegen

Je hebt nu gezien hoe je kaartlagen kunt toevoegen via main.js. Hieronder vatten we het nog eens samen: 

| Onderdeel | Variabele | Beschrijving |
| --------- | --------- | ------------ |
| `new OGCFeatureCollection()` | `url` | URL van de landing page |
| | `collectionId` | Naam van de collectie die je wilt toevoegen |
| | `limit` | Aantal features dat per request wordt opgevraagd |
| `map.addLayer()` | `id` | Zelfgekozen naam voor de kaartlaag |
| | `source` | Naam van de hierboven gedefinieerde bron |
| | `type` | Type kaartlaag (symbol, line of fill?) |
| | `paint` | Hoe moet de kaartlaag worden gevisualiseerd? |

#### Opdracht: voeg zelf kaartlagen toe

Je hebt nu gezien dat je kaartlagen op meerdere manieren kunt toevoegen en stylen. We hebben dit aan de hand van voorbeelden voor gedaan.  

Het is nu aan jou om verschillende extra kaartlagen toe te voegen. Je mag zelf bepalen op welke manier je dit doet, maar:

**:arrow_right: Voeg minimaal 4 extra kaartlagen toe**

**:arrow_right: Waarvan minimaal:**

- **1 kaartlaag met punten (van het type `symbol` of `circle`)**
- **1 kaartlaag met lijnen (van het type `line`)**
- **1 kaartlaag met polygonen (van het type `fill`)**

Grijp terug op je ontwerp om te bepalen welke kaartlagen je het beste kunt toevoegen. 

### Optioneel: extra functionaliteit

!!! info "Dit onderdeel is optioneel"

Voeg extra functionaliteit aan de webmap toe. Kijk hiervoor in de officiële documentatie van MapLibre:

- [MapLibre GL JS API](<https://maplibre.org/maplibre-gl-js/docs/API/>)
- [MapLibre GL JS voorbeelden](<https://maplibre.org/maplibre-gl-js/docs/examples/>)
- [Plugins voor MapLibre GL JS](<https://maplibre.org/maplibre-gl-js/docs/plugins/>)

Je kunt denken aan extra functionaliteit zoals:

- [Een legenda, zodat het voor de gebruiker duidelijk is wat de kleuren betekenen](<https://github.com/watergis/maplibre-gl-legend>);
- [Pop-ups met extra informatie over de objecten in de kaart](<https://maplibre.org/maplibre-gl-js/docs/examples/attach-a-popup-to-a-marker-instance/>);
- [Controls, zoals knoppen om in te zoomen](<https://github.com/korywka/mapbox-controls>).

## Evalueer het eindresultaat

Pak het ontwerp van jouw webmap er weer bij. En vergelijk het ontwerp met het eindresultaat aan de hand van de volgende criteria:

- **Doelgroep:** is jouw webmap geschikt voor de doelgroep die je voor ogen had?
- **Doel en scope:** is de doelgroep in staat om het doel dat je voor ogen had te bereiken?
- **Benodigde informatie:** bevat jouw webmap de informatie die nodig is om het doel te bereiken in een geschikte vorm?
- **Geografische afbakening en schaal:** is de data in jouw webmap geschikt voor het beoogde schaalniveau?

Samenvattend: stelt jouw webmap de doelgroep in staat om hun vragen te beantwoorden? Biedt het meerwaarde voor de gebruiker? 

**:arrow_right: Evalueer jouw eindproduct.**

**:arrow_right: Pas jouw eindproduct zonodig aan.**

## Conclusie

Je hebt als het goed is een prachtige webmap gemaakt. Gefeliciteerd! Laten we eens nagaan wat we allemaal gedaan hebben:

| Onderdeel | Beschrijving |
| --- | --- |
| Maak een ontwerp voor jouw webmap | Aan de hand van doelgroep, doel, benodigde informatie en geografische afbakening. |
| Zet een ontwikkelomgeving op | Code kopiëren en klaarzetten. |
| Maak een basiskaart | De onderlegger (`index.html` en `main.js`) voor de rest van het product. |
| Vind geschikte featuredata | Geschikte datasets vinden via het Nationaal Georegister. |
| Voeg de featuredata toe aan jouw kaart | Toevoegen van een source en layer aan `main.js` |
| Evalueer het eindresultaat | Voldeed het eindproduct aan het ontwerp? |
