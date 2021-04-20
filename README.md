# Tvořím web A–Z: lekce 6

jaro 2021, Praha

<small>20. dubna 2021</small>

---

## Box sizing

- vlastnost, která určuje, jak se budou počítat rozměry prvku
- chceme `box-sizing: border-box;`, viz začátek našeho CSS
- [příklad na CodePen](https://cdpn.io/Kout/debug/WNRNGgX)

---

# Responzivita a media queries

---

## Media queries

```css
@media screen and (min-width: 60rem;) {
    /* Pravidla, která se uplatní pouze, když platí obalující podmínka. */
    h1 {
        font-size: 3.5rem;
    }
}
```

note:

- v případě šířek hovoříme o tzv. _breakpointu_, kdy se skokově nějak změní vzhled prvku
- nedejte se zmást frameworky jako je Bootstrap, které mají pevně dané breakpointy (mobil, tablet, desktop), breakpointy předávejte dle potřeby

---

### Typ média

- `screen` – libovolná obrazovka, drtivá většina našich příkladů
- `print` – tisková verze HTML dokumentu
- `all` – všechna média, tj. platí vždy
- `speech` – hlasová zařízení, která čtou stránku (čtečka pro nevidomé, Siri, Alexa)

note:

- tiskové styly je slušné ke stránce připojit a skrýt v nich balast, nepotřebný na papíře (záhlaví, navigace, zápatí), barvy změnit na černobílé apod. Skrýváme pomocí `display: none;`

---

### Podmínka

- nejčastěji rozměry zařízení (šířka/výška)
- nejčastěji `(min-width)`, případně `(max-width)`
- v některých případech `(min-height)`, `(max-height)`

note:

- Jak se vyhodnotí `(max-height)`?
- pravidla pro (min-height) třeba, když je třeba zmenšit záhlaví, aby byl vidět obsah stránky
- Tohle všechno funguje pouze za předpokladu, že v hlavičce (`<head>`) stránky uvedu kouzelný meta tag…

---

## Meta viewport

```htmlmixed
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

note:

- bez něj se web nebude chovat responzivně

---

### Další podmínky

- `@media screen and (orientation: landscape)` × `(orientation: portrait)`
- `@media screen and (any-hover: hover)` ~ „zařízení opatřená myší“ (mají jeden nebo více vstupů ovládajících kurzor)

---

## Kombinování podmínek

---

### Splněny musí být všechny (logické AND)

```css

@media screen and (min-width: 60rem;) and (min-height: 900px) { … }

```

note:

- musí platit to i to
- máme vlastně už v základním zápise: screen + šířka

---

### Splněna musí být alespoň jedna (logické OR)

```css

@media screen and (max-width: 499px;), (min-width: 1000px) { … }

```

note:

- platí buď pro šířky do 500 px a pak zase od 1000 px nahoru

---

## Mobile first

- začínám na úzké obrazovce (cca 320–360 px)
- vše pod sebou
- základní styly (font, barvy, velikost písma, odsazení)
- jakmile spokojenost, zvětšuji šířku okna a opravuji ohavnosti
- nakonec zarazím šíři stránky pomocí (`max-width`) někde mezi 1200–1920 px

note:

- čisté HTML (bez CSS) je 100% responzivní
- Všechna výše uvedené šířky ber orientečně!!! Vždycky záleží na konkrétním designu a obsahu stránky.
- neřešte zařízení, ale design ⇒ když je to ošklivé, přidejte breakpoint a upravte vzhled

---

# Proměnné vlastnosti <br> (CSS custom properties)

note:

- mají mnohem širší použití, ale nám zatím postačí využít je jako prosté proměnné pro opakující se hodnoty (barvy, odsazení)


---

## Proměnné vlastnosti

```css
:root {
    --primary: #40bf95;
}

h1 {
    color: var(--primary);
}

```

- `:root` ~ root element => prvek `html`

note:

- kořenový prvek
- jsou to vlastnosti, definovat je musíme pro nějaký prvek
- obvykle je to prvek `html`

---
