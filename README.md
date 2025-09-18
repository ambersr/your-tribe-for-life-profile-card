# Visitekaartje Sprint 13

In sprint 13 heb ik gewerkt aan mijn visitekaartje. Daarbij lag de nadruk om het visitekaartje dynamisch te maken met het framework SvelteKit. Het doel is om kennis te maken met gebruik van SvelteKit en zoveel mogelijk informatie op mijn visitekaartje dynamisch te maken.

### Over mij
Ik ben Amber Schalker, 22 jaar en woonachtig in Nieuwegein. Op dit moment zit ik in het 2e jaar van de studie Frontend Design & Development aan de Hogeschool van Amsterdam. Naast mijn studie vind ik het leuk om te lezen, hard te lopen en af en toe naar concerten en festivals gaan. 

Live link naar mijn visitekaartje: https://edu.nl/cud63

![mockup-profile-card](https://github.com/user-attachments/assets/c2ee9171-dad1-4c80-8792-46600aed25a8)

## Inhoudsopgave
  * [Beschrijving](#beschrijving)
  * [Kenmerken](#kenmerken)
  * [Installatie](#installatie)
  * [Bronnen](#bronnen)
  * [Licentie](#licentie)

## Beschrijving

### Mobile first
- Mobile first gebouwd
- `@media queries` toegevoegd om de card responsive te maken

https://github.com/ambersr/your-tribe-for-life-profile-card/blob/574310dbd98d39eac1b1cb1be203fc81c2ab5d6e/src/routes/%2Blayout.svelte#L55-L67

### Herbruikbare component
- De knoppen op de pagina zijn herbruikbare componenten. Deze wordt in de `$lib` als component `DarkButton.svelte` aangemaakt. In het component wordt de tekst ingeladen via `<slot />`

https://github.com/ambersr/your-tribe-for-life-profile-card/blob/574310dbd98d39eac1b1cb1be203fc81c2ab5d6e/src/lib/components/DarkButton.svelte#L1-L24

### Hover animation card
- Als je over de card hovered scaled de visite card met je muis mee. Hierdoor krijgt de 'minimalistische' visitekaartje meer speelsheid.

https://github.com/user-attachments/assets/28f07a10-0e3f-4c26-ab52-a2dad7a28bac


## Kenmerken
In dit project gebruik ik SvelteKit om een dynamische visitekaartje te bouwen met herbruikbare componenten en routes. Data wordt opgehaald via de Directus API. 

### Routes
- [`/`](https://github.com/ambersr/your-tribe-for-life-profile-card/blob/main/src/routes/%2Bpage.svelte): Op de home pagina wordt het visitekaartje getoond.

### Componenten 
- [`DarkButton`](https://github.com/ambersr/your-tribe-for-life-profile-card/blob/main/src/lib/components/DarkButton.svelte): In dit component staat de knop die gebruikt wordt in het visite kaartje en de header.

### Data
Data wordt opgehaald in `+page.server.js`. Hierin wordt een fetch gedaan naar de Directus API, wordt de data verwerkt en gerenderd naar de `+page.svelte` pagina. 
- Zie de [`+page.server.js` van de home pagina](https://github.com/ambersr/your-tribe-for-life-profile-card/blob/main/src/routes/%2Bpage.server.js). 

## Installatie
Om dit project te bouwen moeten onderstaande stappen uitgevoerd worden. `Node.js` en `npm` (of alternatieven, zoals `pnpm` of `yarn`) zijn een vereiste package manager om te kunnen beginnen.  

### Project aanmaken 
- Als je een nieuwe SvelteKit project wil starten, voer volgende commando's uit in de terminal:

```
npx sv create
```

- Volg vervolgens de stappen die in de terminal verschijnen.

### Installeren 
- Nadat het project is uitgevoerd, voer onderstaand command uit om alle dependencies te installeren

```
npm install
```

### Ontwikkelen
-  Als alle dependencies zijn geïnstalleerd, kan de ontwikkelserver gestart worden. Doe dit met onderstaand commando, en krijg automatisch veranderingen te zien:

```
npm run dev -- --open
```

### Builden 
- Op een productversie van je app te maken:

```
npm run build
```

- En op de productieversie te bekijken:

```
npm run preview
```

## Bronnen
- [Ontwerp in Figma](https://www.figma.com/design/CtPASxzpUzUxQg4aRkL1Zh/Webdesign-visitekaartje?node-id=83-49&t=M2TCJakN7QoOVNmP-1)
- Inspiratie opgedaan van [Awwards](https://www.awwwards.com/)

## Licentie
This project is licensed under the terms of the [MIT license](./LICENSE).
