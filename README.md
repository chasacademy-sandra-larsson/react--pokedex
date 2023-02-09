
# Workshop: Komma igång med React, Komponenter och Props

## Vad du kommer lära dig:
* Sätta upp ett Reactprojekt med Vite
* Skapa din första Reactkomponent
* Använda dig av JSX
* Använda dig av flera komponenter
* Skicka information från en komponent till en annan komponent (props)
* Hur man renderar listor i React med hjälp av funktionen map()
* Skriva logik (funktioner) inuti komponenter
* Hantera props med Object Destructering
* Dela upp varje funktionskomponent i moduler som imorteras i App.jsx

## Diskussionsfrågor
* Vad står SPA för?
* Vad är JSX?
* Vad gör React unikt?
* Vad är en prop? 

# Övning: Pokedex

Syftet med övningen är lära sig att bygga en enkel React-app flera komponenenter och props som skickar information mellan dem.

Din uppgift: Du skapa en s.k Pokedex som innehåller några utvalda Pokemenkort med respektive information om vardera Pokemon. Rendering ska se ut (ungefär) som denna bild. 
![Pokedex](/pokedex.png=250x250)

## Del 1

Du ska skapa 3 olika komponenter: 

### App 
Den här komponenten ska rendera ut endast en Pokedex-komponent

### Pokedex 
Den här komponenten ska ta emot en array av objekt som beskriver varje Pokemon

### Pokecard
Den här komponenten visar en Pokemen med namn, bild, typ och experience 

I App-komponenten ska följande lista skickas med som props till Pokedex-komponenten.

```
[
  {id: 4,   name: 'Charmander', type: 'fire',     base_experience: 62},
  {id: 7,   name: 'Squirtle',   type: 'water',    base_experience: 63},
  {id: 11,  name: 'Metapod',    type: 'bug',      base_experience: 72},
  {id: 12,  name: 'Butterfree', type: 'flying',   base_experience: 178},
  {id: 25,  name: 'Pikachu',    type: 'electric', base_experience: 112},
  {id: 39,  name: 'Jigglypuff', type: 'normal',   base_experience: 95},
  {id: 94,  name: 'Gengar',     type: 'poison',   base_experience: 225},
  {id: 133, name: 'Eevee',      type: 'normal',   base_experience: 65}
]
```

För varje Pokemon ska följande bild läsas in till <img src=""> - enligt id.
https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png.

## Del 2

Modifiera din App komponent så att den renderar en Pokegame komponent. Pokegame ska ta emot listan av pokemons och sedan ska det slumpas 2 händer med 4 st pokemens. Pokegame ska alltså rendera 2 st Pokedex. 
I Pokegame ska total experience beröknas baserat på summan av vardera base_experience i vardera hand och skickas med som props till Pokedex. 
I Pokegame ska man också kunna avgöra vilken hand som har högst total experience och skicka med en props isWinner. I Pokedex ska det nu också visas en rubrik "This hand wins" om isWinner är true. 

### Styling

Styla för enklare layout (flexbox, grid). CSS:en kan läggas i App.css. Senare i kursen kommer vi titta på andra sätt att använda CSS i React.
