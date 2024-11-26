# XMas Workshop - How to build a Greeting Card

In diesem Workshop werden wir gemeinsam eine interaktive Grußkarte für die Weihnachtszeit bauen. Du kannst sie später an Freunde und Verwandte senden und zeigen was du alles gelernt hast. ✨

Beginn mit unserem [Template](https://codepen.io/neuefische/pen/BaXMKjv). Kopiere dir diese Vorlage indem du auf `fork` unten rechts in der Aktionsleiste drückst. Du wirst aufgefordert, dich einzuloggen. Wähle die Option "Bei CodePen registrieren". Du solltest im Anschluss einen Account sowie eine eigene Kopie der Vorlage haben.

Bevor wir loslegen können, müssen wir allerdings diese Vorlage verstehen.

### Das Template Verstehen

Du siehst vor dir das Template für die Weihnachtskarte. Es gibt drei Reiter - HTML, CSS und JavaScript (JS) - sowie die Darstellung der Website mit einer leeren weißen Karte. Den JS Reiter können wir vorerst ignorieren, stattdessen fokussieren wir uns auf das HTML:

> HTML

```html
<main class="card">
  <article class="front">
    <!-- Front side content -->
  </article>

  <article class="back">
    <!-- Back side content -->
  </article>
</main>
```

Du siehst hier die Struktur von dem Inhalt der Website. Sie wird mit sogenannten `Elementen` , die man ineinander verschachteln kann, beschrieben. Z.B. besteht die Grußkarte aus einem `main` Element, in dem sich 2 `article` Elemente befinden. Das sieht man daran, dass sich die `article` Elemente zwischen dem öffnenden `<main>` Tag und dem schließenden `</main>` Tag befinden. Alles zwischen diesen beiden Tags befindet sich "in dem `main` Element".

Die `class` Attribute werden zum Stylen von den Elementen verwendet. Das Aussehen wird mit CSS Klassen wie z.B. `card` order `front` definiert. Auch wenn der CSS Reiter noch leer ist, wir haben ein wenig CSS schon vorbereitet und eingebunden, damit du nicht bei Null starten musst. So haben wir unter anderem die Größe der Karte, abgerundeten Ecken und den leichten Schlagschatten definiert, die du an der Karte vielleicht schon bemerkt hast.

### Das erste eigene HTML Element

Lass uns nun das erste HTML Element du der Vorderseite der Karte hinzufügen, eine `h1` Überschrift:

> HTML

```html
<article class="front">
  <!-- Front side content -->
  <h1>Merry XMas!</h1>
</article>
```

Nun Sollte der Text "Merry XMas!" in fetter Schrift auf der Karte zu sehen sein.

### Die erste CSS Klasse definieren

Der Text sieht so etwas langweilig aus, lass uns ihn mit einer CSS Klasse stylen! Wir nennen die Klasse `headline`, vergeben sie auf dem `h1` Element und definieren sie ebenfalls in dem CSS Reiter:

> HTML

```html
<h1 class="headline">Merry XMas!</h1>
```

> CSS

```css
.headline {
  text-align: center;
  font-size: 48px;
  font-family: Mea Culpa;
}
```

In der Klasse `headline` definieren wir drei Eigenschaften:

- `text-align: center`: Der Text soll zentriert ausgerichtet werden.
- `font-size: 48px`: der Text hat eine Schriftgröße von 48 Pixeln.
- `font-family: Mea Culpa`: Wir definieren die Schriftart die wir verwenden wollen. Du kannst auch eine andere der folgenden Fonts wählen: `Mea Culpa`, `Roboto`,`WindSong`, `Knewave` oder `Pacifico`.

### Den Text auf der Karte Zentrieren

Der Text sollte auf der Mitte der Karte zu sehen sein, dafür müssen wir dem Eltern Element (der `article`) sagen, dass es seinen Inhalt zentriert darstellen soll. Wir können dafür die bereit bestehende Klasse `front` verwenden:

> CSS

```css
.front {
  align-content: center;
}
```

### Farbe ins Spiel bringen

Unsere Karte wirkt noch recht leblos. Lass uns ein Hintergrundbild für die Vorderseite hinzufügen:

> CSS

```css
.front {
  align-content: center;
  background: url(...);
  background-size: cover;
  background-position: center;
  border: solid white 8px;
}
```

- `background: url(...)`: Das Bild, das als Hintergrund für die Vorderseite eingesetzt werden soll. Ersetze die drei Punkte durch einen Bildlink von z.B. [Pexels.com](https://pexels.com) oder nutze eins userer Bilder mittels `background: var(--image-1);` (es gibt `image-1` bis `image-5`).
- `background-size: cover`: Sagt dem Hintergrundbild, dass es sich an die Größe des Elements anpassen soll.
- `background-position: center`: Zentriert das Bild.
- `border: solid white 8px`: Gibt der Vorderseite einen weißen Rand, der 8 Pixel breit ist.

Wir können ggf. die Farbe unseres Textes anpassen, damit sie besser lesbar ist:

> CSS

```css
.headline {
  ...
  color: white;
}
```

- `color: white`: Setzt die Textfarbe auf weiß. Man kann viele andere Farben angeben, z.B. `black`, `red`, `hotpink` und viele mehr.

Unsere Vorderseite sieht nun super aus! Jetzt können wir uns an die Hinterseite machen.

### Die Karte drehen

Wenn du versuchst, etwas in das zweite `article` Element zu schreiben wirst du feststellen, dass es nicht auf unserer Karte erscheint. Das liegt daran, das die Rückseite zur Zeit versteckt ist. Wir können sie sichtbar machen, indem wir die Karte drehen:

> HTML

```html
<main class="card flipped">
  ...
  <article class="back">
    <!-- Back side content -->
    some Text for testing...
  </article>
</main>
```

> CSS

```css
.flipped {
  transform: rotateY(180deg);
}
```

- `transform: rotateY(180deg)`: Dreht das Element um die Y Achse herum. Dadurch wird der `article` mit der Klasse `back` sichtbar und der erste `article` wird versteckt.

Nun sollte die Vorderseite nicht mehr sichtbar sein und er Text "some Text for testing..." erscheinen.

### Die Rückseite gestalten

Nun können wir die Rückseite mit Inhalt füllen. Schreib einen Text an eine besondere Person oder Bekannten, oder Grüß alle deine Freunde:

> HTML

```html
<article class='back'>
  <!-- Back side content -->
  <h2 class="text-header">Moin Roly!<h2>
  <p class="text-header">Hamburg ist einfach zauberhaft während der Weihnachtszeit. Es gibt zahllose Wintermärkte, heißen Glühwein und allerlei Leckereien.
  </p>
  <p class="text">Du musst dir umbedingt auch das Wasserschloss ansehen, wenn du mal wieder in der Stadt bist. Gerade in der Dämmerung ist es einfach magisch.</p>
  <p class="text">Bis Bald!</p>
  <span class="signature">Felix</span>
</article>
```

In mehreren `h2`, `p` und `span` Elementen können wir unseren Text strukturieren. zwischen den einzelnen Elementen können wir die Abstände und Textgrößen der einzelnen Abschnitte definieren:

> CSS

```css
.back {
  padding: 8px;
  background-color: crimson;
  color: #ffefef;
  align-content: center;
}
```

- `padding: 8px`: Setzt einen inneren Abstand von 8px zu allen Rändern.
- `background-color: crimson`: Verändert die Hintergrundfarbe von weiß zu einem Rotton.
- `color: #ffefef`: Dies ist ein HexCode für eine helle Farbe. Mit diesen Codes kann man jede Farbe setzen, die man sich wünschen kann.

> CSS

```css
.text-header {
  font-size: 36px;
  margin-bottom: 24px;
}

.text {
  margin-bottom: 12px;
}

.signature {
  font-family: Mea Culpa;
  font-style: italic;
  text-align: center;
  font-size: 24px;
}
```

- `margin-bottom: 24px`: Fügt einen äußeren Abstand am unteren Rand von dem Element von 24 Pixeln hinzu.
- `font-style: italic`: Es wird kursive Schrift für dieses Element verwendet.

Nun haben wir sowohl die Vorder - als auch die Rückseite unserer Karte wunderschön gestaltet. Jetzt muss der Nutzer nur noch die Karte selbst drehen können.

### Die Karte mittels JS drehen

Zuerst nehmen wir die Klasse `flipped` von unserer Karte, damit wir wieder die Vorderseite sehen können:

> HTML

```html
<main class="card">...</main>
```

Damit der Nutzer den Inhalt einer Website verändern kann, brauchen wir JavaScript. Das Ziel ist, dass die Karte gewendet wird, wenn der Nutzer auf diese klickt. In dem JS Reiter befindet sich schon folgender code:

> JS

```js
const card = document.querySelector(".card");

function handleCardClick() {
  console.log("card was clicked.");
  // -->
}

card.addEventListener("click", handleCardClick);
```

- `const card = document.querySelector(".card")` : Es wird das Element mit der Klasse `card` in dem HTML Dokument gefunden und in einer Variable `card` gespeichert. Diese Variable kann man später weiterverwenden.
- `function handleCardClick() { ... }`: Eine Funktion namens `handleCardClick`. Funktionen sind Blöcke von Code, die immer wieder ausgeführt werden können, indem man die Funktion "aufruft".
- `console.log("card was clicked.")`: Ein Befehl um den text "card was clicked." in der Console des Browsers darzustellen. Diese Zeile Code wird ausgeführt, wenn `handleCardClick` aufgerufen wird.
- `card.addEventListener("click", handleCardClick)`: Mit dieser Zeile Code sagen wir dem Browser, dass jedes Mal die Funktion `handleCardClick` aufgerufen werden soll, wenn der Nutzer auf das Element `card` klickt. (Also das `main` Element mit der Klasse `card`, welches wir im HTML Reiter sehen können)

Puh, ganz schön kompliziert. Keine Sorge, wir müssen nicht mehr viel verändern, damit die Karte gedreht werden kann.

Wenn du die Console öffnest (mit dem Schalter "Console" unten links) und auf die Karte klickst, solltest der Text "card was clicked." erscheinen. Damit sehen wir, dass die Funktion `handleCardClick` ausgeführt wurde. Jetzt müssen wir nur noch den Code schreiben, der die Karte umdrehen lässt:

> JS

```js
function handleCardClick() {
  card.classList.add("flipped");
}
```

- `card.classList.add("flipped")`: Wir fügen der Karte die Klasse `flipped` hinzu, also genau das, was wir schon manuell in dem HTML Reiter vorher gemacht haben.

Wenn wir jetzt auf die Karte klicken dreht sie sich wie von Zauberhand um. Wahrhaft magisch!

Es fehlt nur noch ein kleines Detail: Wenn wir versuchen, die Karte ein zweites Mal zu wenden, will es uns nicht gelingen. Was, wenn man drüber nachdenkt, logisch ist: Wir können die Klasse `flipped` im Moment nur hinzufügen, aber nicht wegnehmen. Dafür müssen wir ein kleines Detail ändern:

> JS

```js
function handleCardClick() {
  card.classList.toggle("flipped");
}
```

- `classList.toggle`: Anstatt die Klasse hinzuzufügen, "togglen" oder schalten wir die Klasse um. Wenn sie vorhanden ist, wird sie entfernt; wenn sie fehlt, wird sie hinzugefügt.

Et Voila! Unsere Karte lässt sich nun nach belieben wenden.

### Ein wenig weihnachtlicher Zauber

Zu guter letzt haben wir eine kleines Geschenk für euch vorbereitet, welches eurer Weihnachtskarte einen Hauch Weihnachtszauber verleiht. Fügt folgende Zeile dem CSS Hinzu:

> JS

```js
addChristmasMagic(30, "white");
```

Ihr könnt unterschiedlice Zahlen und Farben anstelle von `30` und `"white"` wählen und sehen was passiert. ✨

### Abschluss

Wir hoffen euch hat unser kleiner Workshop gefallen und dass ihr Lust auf Mehr bekommen habt! In unseren [Bootcamps](https://www.neuefische.de/) könnt ihr tief in das Thema Entwicklung eintauchen und eure Karriere als Web Entwickler\*in starten.

Wir wünschen weiterhin eine Gute Zeit und natürlich ein Frohes Fest! ❄️🎁
