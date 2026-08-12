---
category: general
date: 2026-08-12
description: Configureer de Databar-barcode-indeling snel in Python. Leer kolommen
  en rijen instellen en afbeeldingen opslaan met de barcode-generatorbibliotheek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: nl
lastmod: 2026-08-12
og_description: Configureer de Databar‑barcode‑indeling in Python om kolommen, rijen
  en afbeeldingoutput te beheren. Volg deze gids voor een kant‑klaar oplossing.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configureer Databar barcode‑indeling in Python – volledige tutorial
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
title: Configureer Databar‑barcode‑indeling in Python – stapsgewijze handleiding
url: /nl/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configureer Databar barcode lay-out in Python – stapsgewijze handleiding

Als je **Databar barcode lay-out in Python** moet configureren, leidt deze gids je door het volledige proces. Je ziet hoe je het aantal kolommen of rijen voor een Databar Expanded Stacked barcode instelt en hoe je de resulterende afbeelding opslaat met één aanroep van de barcode‑generatorbibliotheek.

Het beheersen van de lay-out is essentieel wanneer je barcodes op smalle verpakkingen, bonnen of mobiele schermen embedt. In de onderstaande secties behandelen we de benodigde imports, de twee lay-outopties (kolommen en rijen) en de best practices voor het opslaan van een schone PNG‑afbeelding.

## Wat je nodig hebt

* Python 3.8 of nieuwer
* `aspose.barcode` (of een compatibel barcode‑generatiepakket) geïnstalleerd  
  ```bash
  pip install aspose-barcode
  ```
* Schrijfrechten voor een map waar de PNG‑bestanden worden opgeslagen

Er zijn geen extra externe tools nodig — de bibliotheek behandelt rendering, schaling en beeldcodering intern.

## Hoe Databar barcode lay-out in Python te configureren

De kern van de oplossing is de `BarcodeGenerator`‑klasse. Deze accepteert een `EncodeTypes`‑enum die de barcode‑symbologie identificeert — in dit geval `EncodeTypes.DatabarExpandedStacked`. Na het aanmaken van de generator kun je de lay-out aanpassen door de `columns`‑ of `rows`‑eigenschappen in te stellen op het `data_bar`‑parameterobject.

### Stap 1: Importeer de vereiste klassen

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Deze imports geven je toegang tot de generator, de enumeratie voor Databar‑typen, en de constante voor het PNG‑afbeeldingsformaat.

### Stap 2: Maak een barcode‑generator voor Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Waarom deze stap?*  
`EncodeTypes.DatabarExpandedStacked` vertelt de bibliotheek om de **Databar Expanded Stacked**‑symbologie te produceren, die langere numerieke tekenreeksen ondersteunt terwijl hij een compacte footprint behoudt. Het tweede argument is de te coderen data; dit kan elke string zijn die voldoet aan de Databar‑specificatie.

### Stap 3: Stel het aantal kolommen in (horizontale lay-out)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** is de sleutelzin voor deze bewerking. Wanneer je het aantal kolommen verhoogt, spreidt de barcode zich horizontaal uit, wat nuttig kan zijn voor brede etiketten. De bibliotheek berekent automatisch de module‑breedte opnieuw om de totale grootte consistent te houden.

#### Pro‑tip
Het maximale aantal kolommen voor Databar Expanded Stacked is 8. Een waarde hoger dan de limiet wordt begrensd tot het maximum, maar het is beter om je invoer vooraf te valideren.

### Stap 4: Sla de barcode‑afbeelding op met de kolom‑lay-out

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** is de actie die de gerenderde barcode naar schijf schrijft. PNG is verliesloos, waardoor de scherpe randen behouden blijven die nodig zijn voor betrouwbare scanning.

### Stap 5: Maak een tweede generator voor hetzelfde barcode‑type (rij‑lay-out)

Als je de voorkeur geeft aan een verticale stapeling, werk je met rijen in plaats van kolommen. De onderstaande code hergebruikt dezelfde waarde maar maakt een nieuwe `BarcodeGenerator`‑instantie aan om het mengen van kolom‑ en rij‑instellingen te voorkomen.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Stap 6: Stel het aantal rijen in (verticale lay-out)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** rangschikt de barcode‑modules verticaal. Een lay-out met drie rijen verkleint de hoogte van elke individuele stapel, waardoor de barcode geschikt is voor smalle bonnen of mobiele schermen.

#### Randgeval
Als je `rows` op 1 zet, genereert de bibliotheek een één‑rij Databar (equivalent aan een standaard Databar). Waarden onder 1 worden genegeerd en teruggezet naar de standaard (1 rij).

### Stap 7: Sla de barcode‑afbeelding op met de rij‑lay-out

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Opnieuw gebruiken we **save barcode image** met PNG om de output scherp te houden.

## Volledig uitvoerbaar voorbeeld

Alle onderdelen samenvoegen levert een zelfstandige script op die je in elk Python‑project kunt plaatsen.

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

**Verwachte output**

Het uitvoeren van het script maakt twee PNG‑bestanden aan:

* `output/ExpandedCols4.png` – een barcode uitgerekt over vier kolommen
* `output/ExpandedRows3.png` – een barcode samengeperst in drie rijen

Beide afbeeldingen kunnen worden geopend in elke afbeeldingsviewer of direct worden geïmporteerd in PDF‑facturen, etiket‑templates of webpagina's.

## Veelgestelde vragen en probleemoplossing

| Vraag | Antwoord |
|----------|--------|
| *Wat als de barcode er onscherp uitziet?* | Verhoog de beeldresolutie door `barcode_generator.parameters.image_width` en `image_height` in te stellen vóór het aanroepen van `save`. |
| *Kan ik andere afbeeldingsformaten gebruiken?* | Ja. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` indien nodig. |
| *Is er een limiet op de datalengte?* | Databar Expanded Stacked ondersteunt tot 74 numerieke tekens. Het overschrijden van de limiet veroorzaakt een `ArgumentException`. |
| *Hoe wijzig ik de voorgrondkleur?* | Gebruik `barcode_generator.parameters.barcode.color = Color.Blue` (import `System.Drawing.Color`). |
| *Kan ik kolommen en rijen combineren?* | Nee. De API behandelt kolommen en rijen als onderling exclusieve lay-outmodi. Kies er één per barcode‑instantie. |

## Volgende stappen

Nu je **Databar barcode lay-out** kunt **configureren**, overweeg dan deze gerelateerde onderwerpen:

* **Tekstbijschriften toevoegen** – gebruik `barcode_generator.parameters.barcode.code_text` om de gecodeerde waarde onder de afbeelding weer te geven.
* **De barcode in een PDF embedden** – combineer de gegenereerde PNG met `aspose.pdf` om afdrukbare documenten te maken.
* **Dynamische grootte** – bereken optimale kolom‑ of rij‑aantallen op basis van labelafmetingen tijdens runtime.
* **Batchverwerking** – loop over een CSV met productcodes om automatisch een bibliotheek van barcode‑afbeeldingen te genereren.

Experimenteer met verschillende kolom‑ en rij‑waarden om te zien hoe ze de scanbetrouwbaarheid op je doelsystemen beïnvloeden. Hoe meer je test, hoe beter je de afwegingen tussen barcode‑grootte, leesbaarheid en ruimtebeperkingen begrijpt.

---

*Happy coding! Als je deze tutorial nuttig vond, deel hem dan met teamgenoten of laat een reactie achter over de lay‑outuitdagingen die je bent tegengekomen.*

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak DotCode barcode afbeelding – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Maak barcode afbeelding c# – Configureer Codablock F rijen & kolommen](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Eéndimensionale Databar barcode hoogte‑aanpassing](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}