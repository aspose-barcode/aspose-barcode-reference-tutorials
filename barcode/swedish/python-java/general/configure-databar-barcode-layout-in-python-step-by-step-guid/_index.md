---
category: general
date: 2026-08-12
description: Konfigurera Databar-streckkodslayout i Python snabbt. Lär dig att ställa
  in kolumner, rader och spara bilder med streckkodsgeneratorbiblioteket.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: sv
lastmod: 2026-08-12
og_description: Konfigurera Databar-streckkodslayout i Python för att kontrollera
  kolumner, rader och bildutmatning. Följ den här guiden för en färdig lösning som
  är klar att köra.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Konfigurera Databar streckkodslayout i Python – komplett handledning
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Konfigurera Databar streckkodslayout i Python – steg‑för‑steg‑guide
url: /sv/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurera Databar streckkodslayout i Python – steg‑för‑steg‑guide

Om du behöver **konfigurera Databar streckkodslayout i Python**, guidar den här artikeln dig genom hela processen. Du får se hur du ställer in antalet kolumner eller rader för en Databar Expanded Stacked‑streckkod och hur du sparar den resulterande bilden med ett enda anrop till streckkodsgeneratorbiblioteket.

Att kontrollera layouten är avgörande när du bäddar in streckkoder på smal förpackning, kvitton eller mobila skärmar. I avsnitten nedan går vi igenom de nödvändiga importerna, de två layoutalternativen (kolumner och rader) och bästa praxis för att spara en ren PNG‑bild.

## Vad du behöver

* Python 3.8 eller nyare
* `aspose.barcode` (eller något kompatibelt streckkodsgenereringspaket) installerat  
  ```bash
  pip install aspose-barcode
  ```
* Skrivbehörighet till en mapp där PNG‑filerna kommer att lagras

Inga ytterligare externa verktyg krävs—biblioteket hanterar rendering, skalning och bildkodning internt.

## Så konfigurerar du Databar streckkodslayout i Python

Kärnan i lösningen är klassen `BarcodeGenerator`. Den accepterar en `EncodeTypes`‑enum som identifierar streckkodssymboliken—i detta fall `EncodeTypes.DatabarExpandedStacked`. Efter att generatorn har skapats kan du justera layouten genom att sätta egenskaperna `columns` eller `rows` på parameterobjektet `data_bar`.

### Steg 1: Importera de nödvändiga klasserna

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Dessa importeringar ger dig åtkomst till generatorn, uppräkningen för Databar‑typer och konstanten för PNG‑bildformatet.

### Steg 2: Skapa en streckkodsgenerator för Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Varför detta steg?*  
`EncodeTypes.DatabarExpandedStacked` talar om för biblioteket att producera **Databar Expanded Stacked**‑symboliken, som stödjer längre numeriska strängar samtidigt som den behåller ett kompakt fotavtryck. Det andra argumentet är data som ska kodas; det kan vara vilken sträng som helst som uppfyller Databar‑specifikationen.

### Steg 3: Ställ in antalet kolumner (horisontell layout)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** är nyckelfrasen för denna operation. När du ökar antalet kolumner sprider sig streckkoden horisontellt, vilket kan vara användbart för breda etiketter. Biblioteket beräknar automatiskt om modulbredden för att hålla den totala storleken konsekvent.

#### Proffstips
Det maximala antalet kolumner för Databar Expanded Stacked är 8. Om du anger ett värde högre än gränsen kommer det att begränsas till maxvärdet, men det är bättre att validera din inmatning i förväg.

### Steg 4: Spara streckkodsbilden med kolumnlayouten

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** är handlingen som skriver den renderade streckkoden till disk. PNG är förlustfri, vilket bevarar de skarpa kanterna som krävs för pålitlig avläsning.

### Steg 5: Skapa en andra generator för samma streckkodstyp (radlayout)

Om du föredrar en vertikal stapel arbetar du med rader istället för kolumner. Koden nedan återanvänder samma värde men skapar en ny `BarcodeGenerator`‑instans för att undvika att blanda kolumn- och radinställningar.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Steg 6: Ställ in antalet rader (vertikal layout)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** ordnar streckkodens moduler vertikalt. En layout med tre rader minskar höjden på varje enskild stapel, vilket gör streckkoden lämplig för smala kvitton eller mobila skärmar.

#### Kantfall
Om du sätter `rows` till 1 genererar biblioteket en enradig Databar (motsvarande en standard‑Databar). Värden under 1 ignoreras och återställs till standardvärdet (1 rad).

### Steg 7: Spara streckkodsbilden med radlayouten

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Återigen **save barcode image** med PNG för att hålla resultatet skarpt.

## Fullt körbart exempel

När alla delar sätts ihop får du ett självständigt skript som du kan lägga in i vilket Python‑projekt som helst.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Förväntat resultat**

När skriptet körs skapas två PNG‑filer:

* `output/ExpandedCols4.png` – en streckkod utsträckt över fyra kolumner
* `output/ExpandedRows3.png` – en streckkod komprimerad till tre rader

Båda bilderna kan öppnas i vilken bildvisare som helst eller importeras direkt i PDF‑fakturor, etikettmallar eller webbsidor.

## Vanliga frågor och felsökning

| Fråga | Svar |
|----------|--------|
| *Vad händer om streckkoden ser suddig ut?* | Öka bildens upplösning genom att sätta `barcode_generator.parameters.image_width` och `image_height` innan du anropar `save`. |
| *Kan jag använda andra bildformat?* | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` efter behov. |
| *Finns det en gräns för datalängden?* | Databar Expanded Stacked stödjer upp till 74 numeriska tecken. Att överskrida gränsen kastar ett `ArgumentException`. |
| *Hur ändrar jag förgrundsfärgen?* | Använd `barcode_generator.parameters.barcode.color = Color.Blue` (importera `System.Drawing.Color`). |
| *Kan jag kombinera kolumner och rader?* | Nej. API:et behandlar kolumner och rader som ömsesidigt uteslutande layoutlägen. Välj ett per streckkodinstans. |

## Nästa steg

Nu när du kan **konfigurera Databar streckkodslayout**, överväg att utforska dessa relaterade ämnen:

* **Lägg till textbeskrivningar** – använd `barcode_generator.parameters.barcode.code_text` för att visa det kodade värdet under bilden.
* **Bädda in streckkoden i en PDF** – kombinera den genererade PNG‑filen med `aspose.pdf` för att skapa utskrivbara dokument.
* **Dynamisk storlek** – beräkna optimalt antal kolumner eller rader baserat på etikettens dimensioner vid körning.
* **Batch‑bearbetning** – loopa över en CSV med produktkoder för att automatiskt generera ett bibliotek av streckkods‑bilder.

Experimentera med olika kolumn‑ och radvärden för att se hur de påverkar skanningspålitligheten på dina mål­enheter. Ju mer du testar, desto bättre förstår du avvägningarna mellan streckkodsstorlek, läsbarhet och utrymmesbegränsningar.

---

*Lycklig kodning! Om du fann den här handledningen användbar, dela den med kollegor eller lämna en kommentar om de layoututmaningar du stött på.*

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa DotCode streckkodsbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Skapa streckkodsbild c# – Konfigurera Codablock F rader & kolumner](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [En-dimensionell Databar streckkodshöjdsjustering](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}