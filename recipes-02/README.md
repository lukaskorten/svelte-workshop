# Übung 2
## Nested Components

In dieser Übung lernen wir verschachtelte Komponenten kennen. Ziel dieser Übung soll vor allem der Umgang mit *Input* und *Output* einer Svelte Komponente sein. Als *Input* einer Komponente dienen in Svelte *Properties*, als *Output* können entweder die Standard-Events weitergeleitet oder benutzerdefinierte Events erzeugt werden.

## TODOs

1. Die Logik und das Markup für die Anzeige eines Rezepts in eine eigene Komponente `Recipe.svelte` auslagern. Das Löschen einer Zutat soll jedoch weiterhin in der `App.svelte` stattfinden. Legt für die neue Komponente gerne ein Unterverzeichnis an, z.B. `recipe`. 
2. In `recipe/Recipe.svelte` die Properties `title` und `ingredients` definieren.
3. Beim Klick auf das Löschen-Button soll ein benutzerdefiniertes Event gefeuert werden, welches als `detail` das zu löschende `ingredient`-Objekt übergeben bekommt.    
4. In der Root-Komponente `App.svelte` `Recipe.svelte` importieren und anstelle des vorherigen Markups, die neue Komponente einsetzen.
5. Auf das benutzerdefinierte Event lauschen und die Logik zum Löschen einer Zutat implementieren. 
 
## Hinweise
**Properties deklarieren**
```javascript
export let foo;
export let bar = 'Bar'; 
```

**Benutzerdefinierte Events**

```javascript
import { createEventDispatcher } from 'svelte';

...
// Dispatch-Funktion erzeugen
const dispatch = createEventDispatcher();

...
// Benutzerdefiniertes Event feuern
dispatch('myevent', 'Hallo!');

```

```html
<script>
  function doSomething(event) {
    console.log(event.detail); // => Hallo!
  }
</script>

<MyComponent on:myevent={doSomething} />
```

## Installation
Abhängigkeiten installieren ...

```bash
cd recipes-02
npm install
```

...den Dev-Server starten [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Die Anwendung ist nun unter [localhost:5000](http://localhost:5000) erreichbar
