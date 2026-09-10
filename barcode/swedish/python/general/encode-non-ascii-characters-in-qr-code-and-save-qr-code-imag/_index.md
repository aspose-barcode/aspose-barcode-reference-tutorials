---
category: general
date: 2026-09-10
description: Koda icke‑ASCII‑tecken i en QR‑kod och spara QR‑kodbilden med en enkel
  Python‑byggare. Följ en steg‑för‑steg‑guide med ExtCodetextBuilder och BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: sv
lastmod: 2026-09-10
og_description: Koda icke‑ASCII‑tecken i en QR‑kod och spara QR‑kodens bild med Python.
  Denna handledning visar hur man bygger en utökad kodtext, genererar en QR‑kod och
  lagrar bilden.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Koda icke‑ASCII‑tecken i QR‑kod och spara QR‑kodbild – steg‑för‑steg Python‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Koda icke‑ASCII‑tecken i QR‑kod och spara QR‑kodbild.
url: /sv/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koda icke-ASCII-tecken i QR-kod och spara QR-kodbild

Om du behöver **koda icke-ASCII-tecken** i en QR-kod visar den här guiden exakt hur du gör det och sedan **sparar QR-kodbild** till disk. Oavsett om du hanterar rysk, kinesisk eller emoji‑data låter ExtCodetextBuilder dig blanda vanlig text och ECI‑kodade segment utan manuell byte‑hantering.

Du kommer att lära dig hur du skapar en utökad codetext‑sträng, genererar en QR-kod som förstår den strängen och slutligen skriver barcode‑bilden till en fil. Handledningen förutsätter grundläggande kunskaper i Python och att du har `barcode`‑SDK:n installerad.

## Förutsättningar

Innan du börjar, se till att du har:

* Python 3.8+ installerat.
* `barcode`‑Python‑paketet (eller motsvarande SDK) som tillhandahåller `ExtCodetextBuilder`, `CodetextEncodingType` och `BarcodeGenerator`.
* Skrivbehörighet till den katalog där du vill **spara QR-kodbild**.

Du kan installera SDK:n med pip (ersätt `barcode-sdk` med det faktiska paketnamnet):

```bash
pip install barcode-sdk
```

## Steg 1: Skapa en utökad codetext‑builder

Det första steget är att instansiera `ExtCodetextBuilder`. Detta objekt samlar flera textsegment och producerar en enda sträng som QR‑kodens symbolik kan tolka.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Varför detta är viktigt*: QR‑koder stödjer **utökad codetext**, vilket betyder att du kan bädda in flera kodningslägen (plain, ECI, osv.) i en barcode. Buildern abstraherar den lågnivå‑formatering som QR‑specifikationen kräver.

## Steg 2: Lägg till ett plain‑text‑segment

Plain‑text är standardläget och fungerar för ASCII‑tecken. Att lägga till det först ger en läsbar reserv för skannrar som ignorerar ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Om du utelämnade detta steg skulle QR‑koden bara innehålla ECI‑segmentet, vilket vissa äldre läsare kanske inte kan avkoda korrekt.

## Steg 3: Lägg till ett ECI‑kodad segment för icke‑ASCII‑tecken

För att inkludera tecken utanför ASCII‑intervallet — såsom kyrilliska, kinesiska eller emojis — måste du ange en ECI‑kodning (Extended Channel Interpretation). Här använder vi UTF‑8 för det ryska ordet “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Varför detta fungerar*: QR‑specifikationen definierar ECI‑värden som talar om för skannern vilket teckensnitt som ska användas. Utan ECI‑markören skulle de råa byten tolkas som ISO‑8859‑1, vilket ger förvrängd output.

## Steg 4: Hämta den kombinerade utökade codetext‑strängen

Efter att ha lagt till alla önskade segment, anropa `get_extended_codetext()` för att få den slutgiltiga strängen som barcode‑generatorn förväntar sig.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Det utskrivna värdet ser ut som en serie kontrolltecken följt av den faktiska texten, men du behöver aldrig tolka det manuellt.

## Steg 5: Generera en QR‑kod med den utökade codetexten

Skapa nu en `BarcodeGenerator`, sätt symboliken till QR (den enda vanliga 2‑D‑symboliken som stödjer utökad codetext) och mata in den kombinerade strängen.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tips*: Om du provar samma process med Code‑128 eller DataMatrix kommer SDK:n att kasta ett undantag eftersom de formaten inte kan tolka ECI‑markörer.

## Steg 6: Spara QR‑kodbilden

Sist, skriv barcode till en PNG‑fil. Här **sparar du QR‑kodbild** för senare användning.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Se till att mappen `output` finns eller skapa den med `os.makedirs('output', exist_ok=True)` innan du anropar `save`.

### Fullt körbart exempel

Att sätta ihop alla steg ger dig ett självständigt skript som du kan köra omedelbart:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Förväntad output** (konsol):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Att öppna `qr_extended.png` med någon QR‑skanner visar `HelloWorldПривет`. Skannrar som förstår ECI renderar de kyrilliska tecknen korrekt; andra visar bara ASCII‑delen.

## Vanliga frågor & edge‑cases

| Fråga | Svar |
|----------|--------|
| *Kan jag använda andra kodningar som Shift‑JIS?* | Ja. Ersätt `CodetextEncodingType.UTF_8` med `CodetextEncodingType.SHIFT_JIS` och ange lämplig text. |
| *Vad händer om den kombinerade datan överskrider QR‑kapaciteten?* | QR‑koder har versionsgränser (upp till 177 × 177 moduler). Om buildern kastar ett storleks‑undantag, öka antingen felkorrigeringsnivån eller dela upp data över flera QR‑koder. |
| *Behöver jag ange en specifik QR‑version?* | SDK:n väljer automatiskt den minsta versionen som rymmer datan. Du kan tvinga en version med `qr_generator.set_qr_version(10)` om så krävs. |
| *Kommer bilden att vara transparent?* | Som standard skriver SDK:n en PNG med vit bakgrund. Använd `qr_generator.set_background_color(Color.Transparent)` före `save` om du behöver transparens. |

## Slutsats

I den här handledningen lärde du dig hur du **kodar icke-ASCII-tecken** i en QR‑kod med `ExtCodetextBuilder` och sedan **sparar QR‑kodbild** med `BarcodeGenerator`. Processen innebär att bygga en utökad codetext‑sträng, lägga till både plain‑ och ECI‑kodade segment, generera QR‑symboliken och slutligen skriva bildfilen.

Från här kan du utforska:

* Lägg till fler ECI‑segment (olika språk eller emojis).
* Justera QR‑felkorrigeringsnivåer för högre pålitlighet.
* Bädda in den genererade PNG‑filen i PDF‑ eller webbsidor.

Lycka till med kodningen, och ha kul med att skapa flerspråkiga QR‑koder!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar QR‑kodbild i Python med Aspose.Barcode – Full guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generera Code128‑barcode med Aspose.Barcode Python – Full guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [visa produktnamn med Python barcode‑bibliotek – steg‑för‑steg‑guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}