# Voortgang Game Backlog

## Wie zijn wij
- Student A: Bente
- Student B: Ronas

## Les 1
- Repository gemaakt door: Bente
- Screenshots: zie map `bewijs/`
- Screenshot installatie Bente: bewijs/Overzicht-games.png
- Validatiefout: bewijs/Validatie-fout.png
- Screenshot installatie Ronas: bewijs/ronas-installatie.png
- Oefencommits: Bente "Eigen ondertitel toegevoegd", Ronas "Namen duo toegevoegd"

## Kennischeck les 1

1. Wat is het verschil tussen de docenten-template, jullie repository en een clone?
   - Antwoord: De template is het startproject van de docent. Jullie repository is een eigen kopie daarvan op GitHub, waar wij samen in werken. Een clone is de kopie van onze repository op onze eigen laptop.

2. Waarom ziet je partner een wijziging pas na jouw push en diens pull?
   - Antwoord: Een commit staat eerst alleen op mijn eigen laptop. Met een push zet ik hem op GitHub. Mijn partner haalt hem daarna op met een pull. Zonder push en pull blijven de laptops los van elkaar.

3. Welke bestanden worden bij de installatie lokaal aangemaakt?
   - Antwoord: Het bestand .env, de map vendor (PHP-pakketten), de map node_modules (JavaScript-pakketten) en de database database/database.sqlite. Git negeert deze bestanden.

4. Waarom krijgt je partner jouw games niet via GitHub?
   - Antwoord: De games staan in de database op mijn eigen laptop. Die database wordt niet in Git gezet. Via GitHub delen we alleen de code.

5. Waar wordt de titel gecontroleerd en hoe komen de games bij React terecht?
   - Antwoord: De titel wordt gecontroleerd in GameController.php met $request->validate(). De controller haalt de games uit de database en geeft ze met Inertia::render door aan de React-pagina. Daar zijn het props.

## Les 2

### Wie maakte wat
| Onderdeel | Gemaakt door | Getest door |
|---|---|---|
| A: status bewaren | | |
| B: zoeken | | |
| C: uitgespeelde games tellen | | |
| D: wis zoeken | | |
| E: aantal resultaten | | |

### Testtabel
| Test | Verwacht | Uitkomst | Geslaagd? |
|---|---|---|---|
| Toevoegen en vernieuwen | Game blijft in de lijst | | |
| Lege titel versturen | "Vul een titel in." en geen extra game | | |
| Titel van 81 tekens | "Gebruik maximaal 80 tekens." en geen extra game | | |
| Status heen en terug wijzigen, telkens vernieuwen | Status blijft opgeslagen | | |
| `MARIO` en `mario` zoeken | Beide vinden Mario Kart | | |
| `zzzz` zoeken | Geen kaarten en "Geen games gevonden" | | |
| Zoeken met 1 uitgespeelde game van 3 | Voortgang blijft "1 van 3 uitgespeeld" | | |
| Wis zoeken gebruiken | Zoekveld leeg en alle kaarten terug | | |
| Resultatenteller controleren | 3 van 3, 1 van 3 en 0 van 3 | | |
| Uitloggen en `/games` openen | Je komt bij het inlogscherm | | |
| Tweede account op dezelfde laptop | Nieuwe, lege collectie | | |
| Code pushen en partner laten pullen | Partner ziet de code, maar houdt eigen games | | |

### Kennischeck les 2

1. Waarom heeft de status een Laravel-route en save() nodig?
   - Antwoord: Een knop in React kan niets opslaan. De knop stuurt een verzoek naar Laravel. De route roept de controller aan en die zet de nieuwe status met save() in de database. Anders is de status weg na het vernieuwen.

2. Wat is het verschil tussen inloggen en eigenaar zijn van een game?
   - Antwoord: Inloggen laat zien wie je bent. Eigenaar zijn betekent dat de game bij jouw account hoort (user_id). De server controleert dat, zodat je geen games van anderen kunt wijzigen.

3. Wat zijn props en state in deze pagina?
   - Antwoord: Props komen van Laravel, zoals de lijst games. State is tijdelijk en hoort bij de pagina in React, zoals de zoektekst (search). Bij vernieuwen is de state weg, de games blijven bestaan.

4. Waarom gebruikt de voortgang games en de resultatenteller visibleGames?
   - Antwoord: De voortgang telt alle games, ook als je zoekt. De resultatenteller telt alleen de games die je na het zoeken ziet. Daarom gebruiken ze andere lijsten.

5. Waarom heeft "Wis zoeken" geen database nodig?
   - Antwoord: De knop maakt alleen de zoektekst in React leeg. Dat verandert wat je ziet, niet wat is opgeslagen.

### Overdracht via GitHub
