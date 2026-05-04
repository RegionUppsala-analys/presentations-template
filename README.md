# Presentationsmallar – Region Uppsala

Samling av återanvändbara presentationsmallar för analyser och rapporter inom Region Uppsala. Mallarna delar samma grafiska profil och färgpalett.

---

## Innehåll

| Fil / Mapp | Beskrivning |
|---|---|
| `index.qmd` | Quarto RevealJS-mall – interaktiv HTML-presentation |
| `template.pptx` | PowerPoint-mall – statisk presentation |
| `theme.scss` | SCSS-tema för RevealJS (färger, typsnitt, layout) |
| `Kommun_Sweref99TM.shp` | Shapefil med kommungränser, hela Sverige (SWEREF99TM) |
| `Figurer/` | Logotyper och grafiska resurser |

---

## Kom igång

### RevealJS (`index.qmd`)

Kräver [R](https://www.r-project.org/) och [Quarto](https://quarto.org/) (≥ 1.4).

```r
# Paket installeras automatiskt vid första körning
quarto render index.qmd
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

Färger och typsnitt är definierade i `theme.scss` och som konstanter (`PRIMARY`, `BG`) i setup-chunken i `index.qmd` – ändra på ett ställe, uppdateras överallt.

---

## Krav

```
R        ≥ 4.3      tidyverse, plotly, leaflet, sf, gt
Quarto   ≥ 1.4
```

---

*Region Uppsala – Analysenheten*
