---
category: general
date: 2026-08-12
description: Hur man snabbt genererar streckkod med Python. Lär dig att skapa streckkod
  från data och exportera streckkodsbild med ett enda bibliotek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: sv
lastmod: 2026-08-12
og_description: Hur man genererar streckkod i Python med Aspose.BarCode. Följ den
  här guiden för att skapa streckkod från data och exportera streckkodsbilden som
  PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Hur du genererar streckkod i Python – snabb, pålitlig guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Hur man genererar streckkod i Python – komplett steg‑för‑steg‑guide
url: /sv/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du streckkod i Python – komplett steg‑för‑steg‑guide

Om du behöver **how to generate barcode** i en Python‑applikation visar den här handledningen exakt vilken kod du behöver. Du kommer att lära dig att **create barcode from data**, justera dess utseende och **export barcode image** som en PNG‑fil – allt på mindre än tio kodrader.

Att generera en streckkod kan kännas som ett separat problem jämfört med resten av din affärslogik, men med ett enda bibliotek kan du hålla processen i linje med din befintliga kodbas. I avsnitten som följer kommer du att se ett komplett, körbart exempel, förstå varför varje rad är viktig och upptäcka vanliga variationer såsom att ändra modulbredden eller rita en streckkod som bara visar konturer.

## Så genererar du streckkod med Aspose.BarCode‑biblioteket

Aspose.BarCode‑biblioteket för Python (via .NET) erbjuder ett enkelt API för många symbologier, inklusive Planet‑streckkoden som används i den här guiden. Innan du börjar, se till att du har paketet installerat:

```bash
pip install aspose-barcode
```

> **Pro tip:** Använd en virtuell miljö för att undvika versionskonflikter med andra projekt.

### 1. Importera de nödvändiga klasserna

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Dessa importeringar ger dig åtkomst till generator‑klassen, uppräkningen av streckkodstyper och bildformat‑enum som används när resultatet sparas.

### 2. Skapa streckkod från data

Det första steget är att **create barcode from data**. `BarcodeGenerator`‑konstruktorn tar symbologin och den råa strängen du vill koda.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`EncodeTypes.Planet`‑värdet väljer Planet‑streckkoden, medan `"123456"` är den data som kommer att visas i den slutliga bilden.

### 3. Justera X‑dimensionen (modulbredd)

X‑dimensionen styr bredden på varje streckkodmodul (den tunna stapeln). Att sätta den till 4 pixlar ger en tydlig, läsbar bild utan att filen blir för stor.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Why this matters:** En större X‑dimension förbättrar skanningspålitligheten på lågupplösta skrivare, medan ett mindre värde minskar filstorleken för webbbruk.

### 4. Exportera streckkodbild (fylld stil)

Nu kan du **export barcode image** med `save`‑metoden. Exemplet sparar en PNG‑fil, men du kan välja JPEG, BMP eller TIFF genom att ändra `BarCodeImageFormat`‑enum.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

Filen `PlanetFilled.png` innehåller en helt fylld Planet‑streckkod, redo för utskrift eller inbäddning i en PDF.

### 5. Skapa en andra generator för en streckkod som bara visar konturer

Om du behöver en konturversion (tomma staplar) måste du skapa en ny generator eftersom `filled_bars`‑flaggan inte kan växlas efter att bilden har sparats.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Applicera samma X‑dimensioninställning

När du skapar en andra generator måste du upprepa alla visuella inställningar du vill behålla konsekventa.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Inaktivera fyllda staplar för en konturstreckkod

Att sätta `filled_bars` till `False` instruerar renderaren att bara rita konturerna för varje modul, vilket ger en lättare bild som kan vara användbar för designändamål.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Exportera konturstreckkodsbilden

Slutligen **export barcode image** igen, den här gången sparar du konturversionen.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Du har nu två PNG‑filer: en med solida staplar (`PlanetFilled.png`) och en med endast konturer (`PlanetEmpty.png`).

## Exportera streckkodbild i andra format (valfritt)

`save`‑metoden stöder flera format. För att exportera som JPEG med 90 % kvalitet:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Om du behöver en transparent bakgrund för webbbruk, välj PNG med en alfakanal:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Vanliga variationer och kantfall

| Scenario | Nödvändig ändring | Kodsnutt |
|----------|-------------------|----------|
| **Olika symbologi** (t.ex. QR) | Använd ett annat `EncodeTypes`‑värde | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Anpassad förgrundsfärg** | Ställ in `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Högre upplösning** | Öka DPI via `image_width` och `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Stora datasträngar** | Säkerställ att datalängden passar symbologins specifikation | Validate length before creating the generator |

> **Watch out for:** Att leverera data som överskrider den maximala längden för den valda symbologin kastar ett körningsexception. Validera alltid stränglängden eller fånga `ArgumentException`.

## Fullständigt, körbart exempel

Nedan är det kompletta skriptet som du kan kopiera‑och‑klistra in i en fil med namnet `generate_planet_barcode.py`. Anpassa `YOUR_DIRECTORY` till en mapp som finns på din dator.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

När du kör detta skript skapas två PNG‑filer i den angivna katalogen. Verifiera resultatet genom att öppna bilderna i en bildvisare; båda bör visa en Planet‑streckkod som kodar strängen `123456`.

## Slutsats

Du vet nu **how to generate barcode** i Python med Aspose.BarCode, hur du **create barcode from data**, och hur du **export barcode image** i både fyllda och konturstilar. Samma mönster gäller för andra symbologier, bildformat och visuella anpassningar, vilket ger dig en flexibel grund för alla streckkod‑relaterade funktioner i din applikation.

### Nästa steg

* Utforska andra symbologier såsom QR, Code‑128 eller DataMatrix genom att byta `EncodeTypes.Planet` mot önskat värde.  
* Integrera de genererade PNG‑filerna i PDF‑rapporter med bibliotek som `ReportLab` eller `PyPDF2`.  
* Experimentera med dynamiska X‑dimensionvärden för att anpassa streckkodsstorleken baserat på skärmupplösning eller skrivardpi.

Lycka till med kodandet, och känn dig fri att anpassa exemplet så att det passar dina egna projektkrav!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}