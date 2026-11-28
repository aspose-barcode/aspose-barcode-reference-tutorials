---
category: general
date: 2026-11-27
description: Generera QR‑streckkod i Python med Aspose.Barcode och lär dig hur du
  snabbt sparar streckkodsbilden till disk.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: sv
lastmod: 2026-11-27
og_description: Generera QR-kod i Python med Aspose.Barcode och spara streckkodsbilden
  omedelbart. Följ det kompletta exemplet för att skapa, anpassa och lagra QR-koder.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Generera QR‑kod och spara bild med Python – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Generera QR-streckkod och spara bild med Python
url: /sv/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera QR‑streckkod och spara bild med Python

Om du behöver **generera QR‑streckkod** i en Python‑applikation visar den här guiden hur du gör det med Aspose.Barcode‑biblioteket. Du får också lära dig det korrekta sättet att **spara streckkodsbild** till en lokal mapp, hämta biblioteksversionsinformation och hantera utökade codetext‑segment.

Att skapa QR‑koder är ett vanligt krav för biljettsystem, mobila betalningar och produktspårning. I slutet av den här tutorialen har du ett färdigt skript som producerar en QR‑streckkodsbildfil och skriver ut versionsinformation för felsökning eller efterlevnad.

## Förutsättningar

Innan du börjar, se till att du har:

* Python 3.8 eller nyare installerat.
* `aspose-barcode`‑paketet. Installera det med `pip install aspose-barcode`.
* Skrivrättigheter till den katalog där streckkodsbilden ska lagras.

Inga ytterligare externa tjänster krävs; hela processen körs lokalt.

## Steg 1: Bygg en utökad codetext med `ExtCodetextBuilder`

Utökad codetext låter dig blanda vanlig text och ECI (Extended Channel Interpretation)-segment i en enda QR‑kod. Detta är användbart när du behöver bädda in tecken från olika teckenuppsättningar, såsom Euro‑tecknet.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Varför detta steg är viktigt:**  
`ExtCodetextBuilder` samlar den slutgiltiga strängen som QR‑kodgeneratorn kommer att bearbeta. Utan att bygga den utökade codetexten skulle streckkoden bara innehålla vanlig ASCII‑text och kunde inte representera lokalspecifika symboler.

## Steg 2: Hämta den kombinerade utökade codetext‑strängen

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Resultatet ser ut så här:

```
Extended codetext: ABC123[ECI3]€123
```

Den hakparentes‑omslutna `[ECI3]`‑markören talar om för QR‑kodgeneratorn att byta till den angivna teckenuppsättningen för de följande tecknen.

## Steg 3: Generera QR‑streckkoden med den utökade codetexten

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Förklaring:**  
`BarcodeGenerator` tar två argument: streckkodstypen (`QR`) och data att koda (`extended_codetext`). Generatorn förbereder alla interna strukturer som behövs för rendering.

## Steg 4: Spara den genererade streckkodsbilden

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Varför du bör använda detta tillvägagångssätt:**  
Att anropa `save` skriver direkt bilden till disk med formatet som härleds från filändelsen. Metoden stöder PNG, JPEG, BMP och TIFF, vilket ger dig flexibilitet för olika downstream‑konsumenter.

### Verifiera den sparade bilden

Öppna filen `output/qr_extended.png` i någon bildvisare. Du bör se en QR‑kod som, när den skannas, returnerar strängen `ABC123€123`. De flesta moderna mobila QR‑skannrar hanterar ECI‑segmentet automatiskt.

## Steg 5: Hämta Aspose.BarCode‑versionsinformation (valfritt men användbart)

Att känna till den exakta versionen av Aspose.BarCode‑biblioteket hjälper när du behöver rapportera buggar eller verifiera kompatibilitet.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typiskt utdata:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Fullt skript – kopiera, klistra in och kör

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

När du kör skriptet produceras QR‑kodsbilden och både den utökade codetexten samt versionsdetaljer skrivs ut i konsolen.

## Vanliga variationer och kantfall

| Situation | Rekommenderad justering |
|-----------|------------------------|
| **Olika teckenuppsättning** | Ändra ECI‑identifieraren som skickas till `add_eci_codetext`. För UTF‑8 använd `5`. |
| **Högre felkorrigering** | Sätt `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` innan du anropar `save`. |
| **Anpassad bildstorlek** | Använd `barcode.parameters.image_width` och `barcode.parameters.image_height` för att styra pixelmåtten. |
| **Icke‑PNG‑utdata** | Ändra filändelsen i `output_path` till `.jpg` eller `.bmp`. Biblioteket väljer automatiskt rätt encoder. |

## Pro‑tips

* **Skapa utmatningsmappen** programatiskt om den kanske inte finns:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validera QR‑koden** efter generering genom att läsa den med `aspose.barcode.BarcodeReader`. Detta säkerställer att den kodade datan matchar förväntningarna, särskilt när ECI‑segment används.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Prestandatips** – återanvänd en enda `BarcodeGenerator`‑instans om du behöver generera många QR‑koder i en loop. Återställ egenskapen `code_text` istället för att skapa ett nytt objekt varje iteration.

## Slutsats

Du vet nu hur du **genererar QR‑streckkod** i Python med Aspose.Barcode, bygger en utökad codetext som blandar vanlig text och ECI‑segment, och korrekt **sparar streckkodsbild** till disk. Skriptet visar också hur du hämtar biblioteksversionsinformation för felsökning.

Nästa steg du kan utforska inkluderar:

* Lägga till logotyp‑overlay eller anpassade färger i QR‑koden.
* Bädda in QR‑streckkoden direkt i PDF‑filer med Aspose.PDF.
* Automatisera batch‑generering för stora datamängder.

Känn dig fri att experimentera med olika datapayloads, felkorrigeringsnivåer och bildformat. Lycka till med kodningen!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}