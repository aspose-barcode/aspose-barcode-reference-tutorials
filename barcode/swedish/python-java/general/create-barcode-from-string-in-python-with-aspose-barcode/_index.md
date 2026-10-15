---
category: general
date: 2026-10-15
description: Skapa streckkod från en sträng i Python med Aspose.BarCode, lär dig hur
  du genererar Code 128‑streckkod och sparar streckkoden som PNG på bara några rader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: sv
lastmod: 2026-10-15
og_description: Skapa streckkod från sträng i Python för att koda data till en Code 128‑streckkod
  och spara den som en PNG‑fil med Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Skapa streckkod från sträng i Python – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Skapa streckkod från sträng i Python med Aspose.BarCode
url: /sv/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod från sträng i Python med Aspose.BarCode

Om du behöver **create barcode from string** i Python, visar den här guiden de exakta stegen med Aspose.BarCode. Du kommer att lära dig hur du **generate Code 128 barcode**, justerar dess utseende och **save barcode PNG** till disk. Lösningen fungerar på alla plattformar som stödjer Python 3.9+ och kräver bara några rader kod.

Att generera streckkoder programatiskt eliminerar manuella inmatningsfel och effektiviserar arbetsflöden såsom lagerhantering, biljettutfärdande och etikettutskrift. I slutet av den här handledningen kommer du att kunna **encode data into barcode**, anpassa dimensioner och lagra bilden där du behöver den.

## Förutsättningar

- Python 3.9 eller nyare installerat  
- Internetåtkomst för att ladda ner Aspose.BarCode-paketet  
- Skrivbehörighet till den katalog där du kommer att spara PNG-filen  

Om du använder en virtuell miljö (starkt rekommenderat), aktivera den nu.

## Installera Aspose.BarCode Python-paketet

Aspose tillhandahåller ett rent Python‑bibliotek som hanterar alla vanliga streckkodssymbologier, inklusive Code 128. Installera det med pip:

```bash
pip install aspose-barcode
```

*Pro tip:* Fäst versionen (t.ex. `aspose-barcode==23.9`) för att undvika oväntade brytande förändringar i produktion.

## Skapa streckkod från sträng i Python

Det första funktionella steget är att importera de nödvändiga klasserna och skapa en generator för den önskade symbologin. Detta exempel använder **Code 128**, vilket är idealiskt för alfanumerisk data.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Why this matters:** `EncodeTypes.CODE_128` talar om för biblioteket vilken streckkodstandard som ska tillämpas, medan det andra argumentet (`"1234567890"`) är **string you want to encode into barcode**. Du kan ersätta det med vilken ASCII-sträng som helst upp till 80 tecken för Code 128.

## Generera Code 128 streckkod

När generatorn är klar kan du skapa streckkodsbilden i minnet. Biblioteket renderar automatiskt streckkoden baserat på den angivna datan.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

På den här punkten är `barcode_image` en instans av `System.Drawing.Image` (på Windows) eller ett kompatibelt bildobjekt på andra plattformar. Du kan visa den direkt i ett GUI, bädda in den i en PDF eller fortsätta anpassa den.

## Justera streckkodens utseende

Finjustering av de visuella egenskaperna säkerställer att streckkoden skannas pålitligt i din specifika miljö. Vanliga justeringar inkluderar X‑dimensionen (bredden på den smalaste stapeln) och den totala stapelhöjden.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Varför justera dessa värden?*  
- **X dimension** påverkar streckkodens densitet; ett mindre värde ger en tätare streckkod som passar på små etiketter.  
- **Bar height** påverkar läsbarheten; högre staplar är lättare för skannrar att upptäcka på avstånd.

Du kan också ändra färger, lägga till marginaler eller bädda in mänskligt läsbar text via `parameters`‑objektet. Se Aspose.BarCode-dokumentationen för den fullständiga listan av alternativ.

## Så sparar du streckkod som PNG

Att spara den genererade bilden är det sista steget i **create barcode from string**‑arbetsflödet. Biblioteket stödjer flera format; PNG är förlustfritt och brett stödjat.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

`save`‑metoden skriver bilden till filsystemet med det format du anger. Om mål katalogen (`output/` i detta exempel) inte finns, kommer Python att kasta ett `FileNotFoundError`. Skapa katalogen i förväg eller hantera undantaget:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Expected result:** Efter att ha kört skriptet innehåller `output/barcode.png` en tydlig Code 128 streckkod som kodar `"1234567890"`. Att öppna filen i någon bildvisare visar en svart‑på‑vit streckkod redo för skanning.

## Fullt, körbart exempel

Genom att sätta ihop alla bitar, här är ett självständigt skript som du kan kopiera, klistra in och köra:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Kör skriptet med `python create_barcode.py`. Om allt är installerat korrekt kommer du att se:

```
Barcode saved to output/barcode.png
```

Öppna PNG-filen och verifiera att streckkoden matchar den ursprungliga strängen med någon streckkodsläsarapp.

## Vanliga frågor och kantfall

- **What if I need a different symbology?**  
  Ersätt `EncodeTypes.CODE_128` med ett annat enum‑värde såsom `EncodeTypes.QR`, `EncodeTypes.EAN_13` eller `EncodeTypes.PDF_417`. Resten av koden förblir densamma.

- **Can I generate a barcode from non‑ASCII characters?**  
  Code 128 stödjer hela 128‑teckens ASCII‑uppsättningen. För Unicode‑data, överväg att använda QR Code (`EncodeTypes.QR`) som hanterar UTF‑8 nativt.

- **How do I change the image format?**  
  Skicka en annan medlem av `BarCodeImageFormat` till `save`, t.ex. `BarCodeImageFormat.JPEG` eller `BarCodeImageFormat.BMP`.

- **What if the output directory is read‑only?**  
  Omge `save`‑anropet med ett try/except‑block och hantera `PermissionError` på ett smidigt sätt, kanske genom att be användaren om en alternativ sökväg.

- **Performance tip:**  
  Att generera tusentals streckkoder i en loop kan vara CPU‑intensivt. Återanvänd en enda `BarcodeGenerator`‑instans och uppdatera bara `generator.parameters.barcode.code_text` mellan iterationer.

## Slutsats

Du vet nu hur du **create barcode from string** i Python med Aspose.BarCode, **generate Code 128 barcode**, anpassar dess storlek och **save barcode PNG** till disk. Denna end‑to‑end‑lösning låter dig **encode data into barcode** snabbt och pålitligt, vilket gör det enkelt att integrera streckkoder i lagersystem, biljettplattformar eller någon applikation som kräver maskinläsbara identifierare.

**Next steps**

- Utforska andra symbologier (`generate code 128 barcode`-alternativ) såsom QR eller DataMatrix.  
- Lägg till felhanteringslogik för att göra skriptet robust för produktionsbruk (`how to save barcode`-fel).  
- Bädda in den genererade PNG‑filen i PDF‑ eller HTML‑rapporter (`generate barcode png` för webben).  

Lycklig kodning, och njut av enkelheten med programmatisk streckkodsgenerering!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}