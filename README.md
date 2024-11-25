# XMas Workshop  - How to build a Greeting Card

In diesem Workshop werden wir gemeinsam eine interaktive Grußkarte für die Weihnachtszeit bauen. Du kannst sie später an Freunde und Verwandte senden und zeigen was du alles gelernt hast. ✨

Beginn mit unserem [Template](https://codepen.io/neuefische/pen/BaXMKjv). Bevor wir loslegen können, müssen wir diesen Starter Code verstehen.
### Das Template Verstehen

Du siehst vor dir das Template für die Weihnachtskarte. Es gibt drei Reiter - HTML, CSS und JavaScript (JS) - sowie die Darstellung der Website mit einer leeren weißen Karte.
Den JS Reiter können wir vorerst ignorieren, stattdessen fokussieren wir uns auf das HTML:

> HTML
```html
<main class="card">
  <article class="front">
    <canvas class='canvas'></canvas>
    <!-- Front side content -->
  </article>

  <article class="back">
    <!-- Back side content -->
  </article>
</main>
```

Du siehst hier die Struktur von dem Inhalt der Website. Sie wird mit sogenannten `Elementen` , die man ineinander verschachteln kann, beschrieben. Z.B. besteht die Grußkarte aus einem `main` Element, in dem sich 2 `article` Elemente befinden. Das sieht man daran, dass sich die `article` Elemente zwischen dem öffnenden `<main>` Tag und dem schließenden `</main>` Tag befinden. Alles zwischen diesen beiden Tags befindet sich "in dem `main` Element". 
Genau befindet sich das `canvas` Element "in dem ersten  `article` Element", da es zwischen dessen öffnenden und schließendem Tag platziert ist. 

Die `class` Attribute, die einige Elemente bekommen, werden zum Stylen von den Elementen verwendet. Das Aussehen wird mit CSS Klassen definiert. Auch wenn der CSS Reiter noch leer ist, wir haben ein wenig CSS schon vorbereitet und eingebunden, damit du nicht bei Null starten musst. So haben wir unter anderem die Größe der Karte, abgerundeten Ecken und den leichten Schlagschatten definiert, die du an der Karte vielleicht schon bemerkt hast.

### Das erste eigene HTML Element
Lass uns nun das erste HTML Element du der Vorderseite der Karte hinzufügen, eine `h1` Überschrift:
> HTML
```html
  <article class="front">
    <canvas class='canvas'></canvas>
    <!-- Front side content -->
    <h1>Merry XMas!</h1>
  </article>
```

Nun Sollte der Text "Merry XMas!" in fetter Schrift auf der Karte zu sehen sein. 

### Die erste CSS Klasse definieren
Der Text sieht so etwas langweilig aus, lass uns ihn mit einer CSS Klasse stylen! Wir nennen die Klasse `headline`, vergeben sie auf dem `h1` Element und definieren sie ebenfalls in dem CSS Reiter:
> HTML
```html
 <h1 class='headline'>Merry XMas!</h1>
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
  backround: url(...);
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
  <article class='back'>
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
