# Übung 1
## Template-Syntax

Die Ausgangslage für diese Übung stellt die Datei *App.svelte* dar. Hier wollen wir das noch statische Markup mit den Daten aus dem `<script>`-Tag verknüpfen und das Entfernen einzelner Zutaten implementieren. Konkret sind die folgenden Schritte notwendig:

## TODOs
**App.svelte**

1. In `App.svelte` die Variable `title` im Markup einbinden
2. Mit Hilfe von `{#each items as item} ... {/each}` über Zutaten iterieren und sie, wie im Markup definiert, ausgeben
3. Innerhalb der Schleife die optionalen Properties eines `ingredient`-Objekts mit `{#if condition} ... {/if}` einblenden
4. Das Löschen einer Zutat implementieren

## Hinweise 
Das `click`-Event mit der Direktive `on:click` abfangen und mittels einer Arrow-Function Argumente übergeben:

```
<button on:click={() => removeItem(item)}>
```

## Installation
Abhängigkeiten installieren ...

```bash
cd recipes-01
npm install
```

... Anwendung mit [Rollup](https://rollupjs.org) bauen und den Dev-Server starten:

```bash
npm run dev
```

Die Anwendung ist nun unter [localhost:5000](http://localhost:5000) erreichbar



