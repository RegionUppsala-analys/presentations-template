# Presentationsmallar – Region Uppsala

Samling av återanvändbara presentationsmallar för analyser och rapporter inom Region Uppsala. Mallarna delar samma grafiska profil och färgpalett.

---

## Innehåll

| Fil / Mapp | Beskrivning |
|---|---|
| `template.qmd` | Quarto RevealJS-mall – interaktiv HTML-presentation |
| `template.pptx` | PowerPoint-mall – statisk presentation |
| `theme.scss` | SCSS-tema för RevealJS (färger, typsnitt, layout) |
| `Kommun_Sweref99TM.shp` | Shapefil med kommungränser, hela Sverige (SWEREF99TM) |
| `Figurer/` | Logotyper och grafiska resurser |

---

## Kom igång

### RevealJS (`template.qmd`)

Kräver [R](https://www.r-project.org/) och [Quarto](https://quarto.org/) (≥ 1.4).

```r
# Paket installeras automatiskt vid första körning
quarto render template.qmd
```

Renderar till en självständig HTML-fil. Öppna i webbläsaren – **inte** i RStudio Viewer.

### PowerPoint (`template.pptx`)

Öppna direkt i PowerPoint eller Google Slides. Håll dig till de fördefinierade layouterna för att bevara den grafiska profilen.

---

## Grafisk profil

| Element | Värde |
|---|---|
| Primärfärg | `#B81867` (cerise) |
| Bakgrund | `#f7f9fb` |
| Typsnitt | Segoe UI |

Färger och typsnitt är definierade i `theme.scss` och som konstanter (`PRIMARY`, `BG`) i setup-chunken i `template.qmd` – ändra på ett ställe, uppdateras överallt.

---

## Interaktiva diagram (RevealJS)

Mallen innehåller färdiga hjälpfunktioner:

- **`theme_ru()`** – ggplot2-tema med regionens bakgrundsfärg och rutnät
- **`ru_layout()`** – plotly-layout med fast storlek (1000 × 430 px), transparent bakgrund och dold verktygsfält

```r
# Exempel
p <- ggplot(data, aes(x, y)) + geom_col() + theme_ru()
ggplotly(p, tooltip = "text") |> ru_layout(title = "Min rubrik")
```

Stödda diagramtyper: stapel, linje, scatter, karta (leaflet), interaktiv tabell (DT).

---

## Karta

Shapefilen `Kommun_Sweref99TM.shp` innehåller samtliga svenska kommuner i SWEREF99TM-projektion. Transformeras automatiskt till WGS84 (EPSG:4326) i kartblocket i `template.qmd`. Filtrera till Uppsala län med `filter(startsWith(KnKod, "03"))`.

---

## Krav

```
R        ≥ 4.3      tidyverse, plotly, leaflet, sf, DT, gt
Quarto   ≥ 1.4
```

---

*Region Uppsala – Analysenheten*
