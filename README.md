# HTML a CSS 1: lekce 6

Podzim 2021, online

<small>1. listopadu 2021</small>

---

# Responzivita a media queries

---

## Layouty
+ Fixní
+ Fluidní
+ Adaptivní
+ Responzivní

---

## Fixní layout
+ Již dlouho překonaný styl
+ Fixní = statický
+ Většina elementů v px
+ Elementy se po stránce nepohybují
+ Nezáleží na velikosti obrazovky

<img src="https://miro.medium.com/max/2000/1*dUZudP2xfPLzMiw5L8ieTQ.gif" style="max-height: 180vh;" />

---

## Fluidní layout
+ Stále hodně používaný, ale překonaný
+ Většina velikostí v %
+ Elementy se po stránce nepohybují
+ Záleží na velikosti obrazovky
+ Není vhodný pro mobilní  zařízení

<img src="https://miro.medium.com/max/2000/1*Hul4o5D73lpzVeVTk2Cuag.gif" style="max-height: 180vh;" />

---

## Adaptivní layout
+ Před media queries asi nejpoužívanější
+ Pro každou velikost fixně definovaná verze
+ Elementy už se na stránce pohybují
+ Záleží na velikosti obrazovky
+ Zbytečný kód pro každou verzi

<img src="https://miro.medium.com/max/2000/1*LP6jyJPC17EVOk8nKEHYzg.gif" style="max-height: 180vh;" />

---

## Responsivní layout
+ Bere si to nejlepší z fluidního a adaptivního
+ Používají se breakpointy - media-queries
+ Rozděluje rozlišení do rozmezí
+ Elementy se přesouvají, mění pozici i velikost
+ Minimalizuje zdrojový kód

<img src="https://miro.medium.com/max/2000/1*jGg5Y0CIZSGSTDTabsarbQ.gif" style="max-height: 180vh;" />

---

## Mobile first

<img src="https://content.altexsoft.com/media/2017/04/mobile-first-design-1024x404.png" style="max-height: 130vh;" />

---

## Mobile first

+ začínám na úzké obrazovce (cca 320–360 px)
+ vše pod sebou
+ základní styly (font, barvy, velikost písma, odsazení)
+ jakmile spokojenost, zvětšuji šířku okna a opravuji ohavnosti
+ nakonec zarazím šíři stránky pomocí (max-width) někde mezi 1200–1920 px

---

## Media queries

<img src="https://www.vzhurudolu.cz/prirucka-content/dist/images/original/media-query.jpg" style="max-height: 130vh;" />

---

### Typ média

- `screen` – libovolná obrazovka, drtivá většina našich příkladů
- `print` – tisková verze HTML dokumentu
- `all` – všechna média, latí vždy. Výchozí (default hodnota)
- `speech` – hlasová zařízení, která čtou stránku (čtečka pro nevidomé, Siri, Alexa)

---

### Podmínka

- nejčastěji rozměry zařízení (šířka/výška)
- nejčastěji `(min-width)`, případně `(max-width)`
- v některých případech `(min-height)`, `(max-height)`
- Např.: `@media (min-width: 1025px) { … }`

---

## Meta viewport

```htmlmixed
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 1. cvičení - banner

+ https://github.com/Czechitas-Liberec-HTML-CSS-2021-DK/lekce_06/tree/main/cviceni/02_banner
+ Doplň CSS tak, aby červený banner nebyl vidět na obrazovkách užších než 500 pixelů.

---

## 2. cvičení 2 – sloupce

+ https://github.com/Czechitas-Liberec-HTML-CSS-2021-DK/lekce_06/tree/main/cviceni/03_sloupce
+ `Nastav v CSS pro třídy kontejner a sloupec vlastnosti tak, aby na obrazovce širší než 600px byly všechny 3 obdélníky vedle sebe.`

---


### Další podmínky

- `@media screen and (orientation: landscape)` × `(orientation: portrait)`
- `@media screen and (any-hover: hover)` ~ „zařízení opatřená myší“ (mají jeden nebo více vstupů ovládajících kurzor)


## Kombinování podmínek (AND)

- Splněny musí být všechny (logické AND)

```css

@media screen and (min-width: 60rem;) and (min-height: 900px) { … }

```

## Kombinování podmínek – OR

- Splněna musí být alespoň jedna (logické OR)

```css

@media screen and (max-width: 499px;), (min-width: 1000px) { … }

```

## 3. povinný úkol

- Zadaný v GitHub Classroom https://classroom.github.com/a/kKgsYyA6 
- Ukážeme si, co je třeba
- Odevzdat do další lekce 8.11.

---
