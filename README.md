
# React workshop #1: Komma igång med React, Komponenter och Props

Denna workshop behandlar s 11-52, 68-78 i kursboken "The road to React" av Robin Wieruch.

### Innehåll denna workshop:
* Sätta upp ett Reactprojekt med Vite 
* Skapa din första Reactkomponent
* Använda dig av JSX
* Använda dig av flera komponenter
* Skicka information från en komponent till en annan komponent (props)
* Hur man renderar listor i React med hjälp av funktionen map()
* Skriva logik (funktioner) inuti komponenter
* Dela upp varje funktionskomponent i moduler som importeras i App.jsx
* Hantera props med Object Destructering (s 68-78)

### Redovisning:
* Du/gruppen redovisar svaren på instuderingsfrågorna muntligt under workshop. 
* Du redovisar slutresultat av övningen Pokedex (se nedan) 

Om du inte kan delta på workshopen, redovisar du ovanstående nästkommande workshop.


### Sätta upp ett Reactprojekt med Vite 

Se s 11-18 i kursboken

* Se till att du har Node.js installerat, https://nodejs.org/en/. 
* Navigera i terminalen där du vill installera din reactapp.
* Kör sedan du följande instruktion i terminalen

```
npm create vite@latest my-app -- --template react
```

### Instuderingsfrågor

Diskutera följande frågor i studiegruppen och redovisa för lärare. Gör egna anteckningar i syfte för kommande teorihandbok om React.

* Vad står SPA för?
* Vad är JSX?
* Vad gör React unikt?
* Vad är en prop? 

# Övning: Pokedex

Syftet med övningen är lära sig att bygga en enkel react med flera komponenenter samt props som skickar information mellan dem.

### Din uppgift: 
Du skapa en s.k Pokedex som innehåller några utvalda Pokemenkort med respektive information om vardera Pokemon. Renderingen ska se ut (ungefär) som denna bild. 

![Pokedex](/pokedex.png)

Använd dig av följande data:
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

## Del 1
Du ska skapa 3 olika komponenter: 

### App 
Den här komponenten ska rendera ut endast en Pokedex-komponent, där datat om pokemons ska skickas med som props.

### Pokedex 
Den här komponenten ska ta emot datat om pokements (en array av objekt) och rendera vardera Pokecard. Använd dig av map()!

### Pokecard
Den här komponenten visar en Pokemen med namn, bild, typ och experience 
För varje Pokemon ska följande bild läsas in enligt id för en pokemon.
https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png.

## Del 2

* Nu ska du även skapa en Pokegame-komponent
* Modifiera din App-komponent så att den renderar en Pokegame istället för en Pokedex
* Pokegame ska ta emot data med pokemons och sedan slumpa 2 st "händer" med 4 st pokemens vardera. Pokegame ska alltså rendera 2 st Pokedex. 
* I Pokegame ska du beräkna summan av `base_experience` för vardera hand. Summan ska skickas med som props till Pokedex.
* I Pokegame ska man kunna avgöra vilken hand av pokemonkort som har högst experience. Skicka med ännu en props till Pokedex som heter `isWinner` som är true om handen har högst experience eller false om den inte har det. 
* I Pokedex-komponenten ska det nu också visas en rubrik "This hand wins!!" om isWinner är true. 

### Styling

Styla för enklare layout (flexbox, grid). CSS:en kan läggas i App.css. Senare i kursen kommer vi titta på andra sätt att använda CSS i React.
