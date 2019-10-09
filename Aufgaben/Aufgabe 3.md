# Übung 3 - Bindings, Event-Modifier und Slots
In dieser Übung habe ich euch einiges an Schreibarbeit  abgenommen und bereits einige Komponenten selbst implementiert. Eine Zutat ist nun zu einer eigenen Komponente geworden, `Ingredient.svelte`. Aus dem Trash-Icon-Button wurde ein `IconButton.svelte`, welches sich überall mit beliebigen Icons einsetzen lässt. Die dritte neue Komponente, um die sich diese Übung hauptsächlich dreht, heißt `IngredientInput.svelte`. Mit ihr soll am Ende der Übung eine neue Zutat angelegt und an die vorhandene Liste angehängt werden können.



**IngredientInput.svelte**

1. Benutze die `bind:`-Direktive um die Eingabefelder mit entsprechenden Variablen biderektional zu verbinden. 
1. Definiere an der `form` einen Listener für das `submit`-Event. Benutze dabei einen passenden Event-Modifier, um das Default-Submit-Verhalten der Form zu deaktivieren.
2. Beim Absenden der Form setze ein benutzerdefiniertes Event ab, z.B. `save` und gebe das neue `ingredient`-Objekt als `detail` mit.
3. Beim Klick auf den `IconButton` *Abbrechen* soll ein weiteres, benutzerdefiniertes Event abgefeuert werden, `cancel`.

**Recipe.svelte**

5. Deklariere in `Recipe` eine neue Variable, z.B. `showInput`,  über welche die Sichtbarkeit der Komponente `IngredientInput` gesteuert werden soll. Initial soll die Komponente unsichtbar bleiben.
6. Sie kann wieder eingeblendet werden, sobald auf die Schaltfläche *Zutat hinzufügen* geklickt wurde
7. Als Nächstes definiere an der `IngredientInput` zwei Event-Listener für die Events `save` und `cancel` und implementiere entsprechende Handler-Funktionen
8. Der *save*-Handler soll das übermittelte `ingredient`-Objekt an das vorhandene Array anhängen und anschließend die Eingabe-Komponente ausblenden - `showInput` auf `false` setzen.
9. Beim Abbrechen soll die Eingabe-Komponente lediglich ausgeblendet werden.

**Optional**

10. Implementiere eine generische Button-Komponente, in der ein `slot` zum Einsatz kommt und das Standard click-Event des inneren button-Tags an die Komponente weitergeleitet wird.
11. Setze diese Komponente in `Recipe` ein, um die Handler-Funktion `toShoppingList` aufzurufen

**CSS für `Button.svelte`**

```css
  button {
    background: #00897b;
    border-color: #00897b;
    color: #fefefe;
    padding: 0.75rem 1.5rem;
    border-radius: 4px;
    transition: background-color 250ms ease-in-out;
    cursor: pointer;
  }
  button:hover {
    background: #00a493;
    border-color: #00a493;
  }
  button:active {
    background: #007468;
    border-color: #007468;
  }
```
