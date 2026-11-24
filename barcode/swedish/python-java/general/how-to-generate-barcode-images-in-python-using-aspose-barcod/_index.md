---
category: general
date: 2026-11-23
description: Hur man genererar streckkodsbilder i Python med Aspose.BarCode. Lär dig
  att skapa en Planet‑streckkod, justera X‑dimensionen och skapa en PNG med tomma
  staplar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: sv
lastmod: 2026-11-23
og_description: Hur man genererar streckkod i Python med Aspose.BarCode. Denna handledning
  guidar dig genom att skapa en Planet‑streckkod med tomma staplar och spara den som
  en PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Hur man genererar streckkod i Python – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Hur man genererar streckkodsbilder i Python med Aspose.BarCode
url: /sv/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkodsbilder i Python med Aspose.BarCode

Att generera streckkodsbilder i Python är enkelt med Aspose.BarCode-biblioteket. Denna guide visar dig steg‑för‑steg hur du genererar en streckkod med Planet‑symbologi, anpassar X‑dimensionen och skapar en PNG‑fil i stil med tomma staplar.

Du får se ett komplett, körbart skript som du kan kopiera in i ditt projekt. Handledningen täcker också vanliga variationer — som att byta till en annan symbologi eller utdataformat — så att du kan anpassa lösningen efter dina egna krav.

## Förutsättningar

* Python 3.8 eller nyare installerat.
* Tillgång till en terminal eller kommandoprompt.
* En aktiv Aspose.BarCode för Python-licens (den kostnadsfria utvärderingen fungerar för testning).
* Grundläggande kunskap om Python-paketshantering (`pip`).

## Steg 1: Installera Aspose.BarCode-paketet

Aspose distribuerar sitt Python‑API via PyPI. Installera det med den vanliga paketshanteraren:

```bash
pip install asposebarcode
```

> **Proffstips:** Använd en virtuell miljö (`python -m venv venv`) för att hålla beroenden isolerade från andra projekt.

## Steg 2: Importera de nödvändiga Aspose.BarCode-klasserna

Import‑satsen hämtar generatorn, uppräkningen av symbologier och bildformat‑enumerationen.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` skapar streckkodobjektet.
* `EncodeTypes` listar alla stödda symbologier — här använder vi `Planet`.
* `BarCodeImageFormat` definierar filtypen för utdata (PNG, JPEG osv.).

## Steg 3: Skapa en streckkodsgenerator för Planet‑symbologin

Instansiera generatorn med önskad symbologi och den data du vill koda.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`Planet`‑symbologin skapar ett cirkulärt mönster som är idealiskt för dekorativa eller varumärkesändamål.

## Steg 4: Justera X‑dimensionen (modulbredd)

X‑dimensionen styr bredden på den minsta stapeln (modulen). Att sätta den till 4 pixlar ger en klar, högupplöst bild.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Att ändra X‑dimensionen är användbart när du behöver en streckkod som skalas bra för utskrift eller skärmvisning.

## Steg 5: Inaktivera fyllda staplar för en stil med tomma staplar

En streckkod med tomma staplar visar endast konturerna av staplarna, vilket kan vara användbart i designintensiva applikationer.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

När `filled_bars` är `False` ritar generatorn ihåliga former istället för solida.

## Steg 6: Spara streckkodsbilden som en PNG‑fil

Slutligen skriver du streckkoden till disk. PNG är förlustfri och brett stöd.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

`save`‑metoden skapar automatiskt målkatalogen om den inte finns.

## Fullständigt exempel – ett komplett, körbart skript

När du sätter ihop alla delar får du ett fristående program som du kan köra omedelbart:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Förväntat resultat:** Efter att ha kört skriptet innehåller `output/PlanetEmptyBars.png` en 200 × 200 pixel bild av en Planet‑streckkod med ihåliga staplar. Att öppna filen i någon bildvisare visar det cirkulära mönstret med det numeriska värdet kodade inuti.

## Vanliga variationer och kantfall

### Byta till en annan symbologi

Om du behöver en QR‑kod, Code 128 eller något annat format, ersätt `EncodeTypes.Planet` med det lämpliga enum‑värdet:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Ändra bildformatet

Aspose.BarCode stödjer PNG, JPEG, BMP och TIFF. För att generera en JPEG istället:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Justera bildstorlek utan att förlora kvalitet

Du kan styra de övergripande bilddimensionerna via egenskapen `resolution` eller genom att skala X‑dimensionen och Y‑dimensionen tillsammans. För högupplösta utskrifter, ange ett högre DPI:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Hantera långa datasträngar

Planet‑symbologin har en begränsad datakapacitet (upp till 8 tecken). Om du försöker koda en längre sträng, kastar generatorn ett undantag. Validera längden innan du skapar streckkoden:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Tips och fallgropar

* **Licensaktivering:** För produktionsanvändning, applicera din licensfil tidigt i skriptet med `asposebarcode.License().set_license("Aspose.Total.lic")`. Att hoppa över detta steg kommer att infoga ett vattenmärke i utdata‑bilden.
* **Trådsäkerhet:** `BarcodeGenerator`‑instanser är inte trådsäkra. Skapa en separat instans per tråd om du genererar streckkoder parallellt.
* **Prestanda:** Återanvändning av en generator för flera värden (genom att anropa `barcode.value = "new data"`) är snabbare än att konstruera ett nytt objekt varje gång.
* **Filsökvägar:** Använd `os.path.join` för att bygga plattformsoberoende sökvägar, särskilt vid distribution på Linux eller macOS.

## Slutsats

Du vet nu hur du genererar streckkodsbilder i Python med Aspose.BarCode, anpassar X‑dimensionen, skapar en stil med tomma staplar och sparar resultatet som en PNG. Det kompletta exemplet kan anpassas till andra symbologier, utdataformat och visuella stilar, vilket ger dig en flexibel grund för alla streckkod‑relaterade funktioner i dina applikationer.

**Nästa steg:** Utforska ytterligare sekundära nyckelord som *Python barcode generation* genom att prova olika kodningar, experimentera med *barcode image PNG*-komprimeringsinställningar, eller integrera de genererade bilderna i en webbtjänst med Flask eller FastAPI. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar planet‑streckkod PNG med Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Hur man skapar streckkodsbilder i Python med Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [Hur man genererar QR‑kod‑bild i Python med Aspose.Barcode – Fullständig guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}