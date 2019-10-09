# Übung 1 - Template-Syntax
Die Ausgangslage für diese Übung stellt die Datei *App.svelte* dar. Hier wollen wir das noch statische Markup mit den Daten aus dem `<script>`-Tag verknüpfen und das Entfernen einzelner Zutaten implementieren. Konkret sind die folgenden Schritte notwendig:

**in App.svelte**

1. die Variable `title` im Markup einbinden
2. Mit Hilfe von `{#each items as item} ... {/each}` über Zutaten iterieren und sie, wie im Markup definiert, ausgeben
3. Innerhalb der Schleife die optionalen Properties eines `ingredient`-Objekts mit `{#if condition} ... {/if}` ein- bzw ausblenden
4. Das Löschen einer Zutat implementieren



**Hinweis:**

Das `click`-Event mit der Direktive `on:click` abfangen und mittels einer Arrow-Function die zu löschende Zutat an die entsprechende Event-Handler-Funktion übergeben:

```
<button on:click={() => removeItem(item)}>
```



