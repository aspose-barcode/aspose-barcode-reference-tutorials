---
category: general
date: 2026-08-19
description: Hur man genererar streckkod med ECI med Aspose.Barcode för Python. Lär
  dig hur du lägger till eci‑data, blandar vanlig text och sparar bilden i en tydlig
  guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: sv
lastmod: 2026-08-19
og_description: Hur man genererar streckkod med ECI med Aspose.Barcode för Python.
  Följ den här handledningen för att lära dig hur du lägger till eci‑data, anpassar
  utseendet och sparar resultatet.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Hur du genererar en streckkod med ECI med Aspose.Barcode Python – steg för
  steg
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Hur man genererar streckkod med ECI med Aspose.Barcode Python
url: /sv/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du streckkod med ECI med Aspose.Barcode Python

Om du behöver veta **hur man genererar streckkod** som innehåller både vanliga tecken och ECI‑kodad data, visar den här guiden hela processen. Du får se exakt **hur man lägger till eci**‑sektioner, justerar storlek och skriver bilden till disk med ett enda, körbart skript.

Tutorialen täcker:

* Hämta versionen av Aspose.Barcode‑biblioteket (valfritt men användbart för felsökning).  
* Bygga en utökad codetext‑sträng som blandar vanliga och ECI‑kodade tecken.  
* Skapa en streckkodsgenerator för en symbolik som stödjer utökad codetext.  
* Anpassa streckkodens dimensioner och spara den slutliga PNG‑filen.

Ingen extern dokumentation krävs; kopiera koden, kör den, så får du en streckkodsbild som inkluderar kinesiska tecken kodade med ECI 26 (UTF‑8).

## Förutsättningar

Innan du börjar, se till att du har:

* Python 3.8 eller nyare installerat.  
* `aspose-barcode`‑paketet installerat (`pip install aspose-barcode`).  
* Skrivbehörighet till den mapp där du avser att spara PNG‑filen.

Om du använder en virtuell miljö, aktivera den först för att hålla beroenden isolerade.

## Steg 1: Verifiera Aspose.Barcode‑versionen (valfritt)

Att känna till den exakta biblioteksversionen hjälper när du behöver rapportera buggar eller jämföra funktioner mellan releaser.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Varför detta är viktigt*: Versionsutskriften bekräftar att runtime‑miljön matchar den dokumentation du följer. Olika versioner kan stödja olika ECI‑värden, så det är en snabb kontroll.

## Steg 2: Bygg en utökad codetext med vanliga och ECI‑kodade delar

Aspose.Barcode tillhandahåller `ExtCodetextBuilder` för att sammanfoga vanlig data och ECI‑kodade segment. I detta exempel blandar vi en numerisk sträng med kinesiska tecken.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Förklaring*:  
* `add_plain_codetext` infogar data som streckkodssymboliken behandlar som vanliga tecken.  
* `add_eci_codetext` instruerar generatorn att lägga till en ECI‑indikator (här **26**, som motsvarar UTF‑8) före den angivna texten. Detta är exakt **hur man lägger till eci**‑data i en streckkod.

Du kan anropa `add_eci_codetext` flera gånger för att bädda in flera olika språkblock. Buildern hanterar de nödvändiga escape‑sekvenserna automatiskt.

## Steg 3: Välj en symbolik som stödjer utökad codetext

Inte alla streckkodstyper kan lagra ECI‑segment. Code 128, QR och Data Matrix är vanliga val. Exemplet använder Code 128 eftersom det är brett stödjat och fungerar bra för blandad alfanumerisk data.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Varför Code 128?*: Det accepterar hela ASCII‑intervallet och de ECI‑escape‑sekvenser som buildern producerar, vilket gör det idealiskt för scenariot “hur man genererar streckkod” som blandar vanlig och kodad text.

## Steg 4: Justera streckkodens utseende

Du kan kontrollera storlek, höjd, marginaler och många andra visuella aspekter via `parameters`‑objektet.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tips*: Om du planerar att skriva ut streckkoden, öka `x_dimension` och `bar_height` proportionellt för att behålla läsbarheten vid mål‑DPI.

## Steg 5: Spara streckkodbilden

Till sist skriver du den genererade bilden till en fil. Aspose.Barcode stödjer PNG, JPEG, BMP och många andra format.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Se till att `output`‑mappen finns eller skapa den med `os.makedirs("output", exist_ok=True)` innan du anropar `save`.

### Förväntat resultat

När du öppnar `extended_codetext.png` bör du se en Code 128‑streckkod som kodar den numeriska strängen `1234567890` följt av de kinesiska tecknen “特殊字符”. Skannar du streckkoden med en modern scanner som respekterar ECI, returneras den ursprungliga blandade strängen.

![Streckkod genererad med exempel för hur man genererar streckkod](https://example.com/images/barcode-sample.png){: .align-center alt="Streckkod genererad med exempel för hur man genererar streckkod"}

## Vanliga frågor och kantfall

### Vad gör jag om jag behöver ett annat teckensätt?

Välj rätt ECI‑värde från ISO/IEC 18004‑tabellen. Till exempel representerar ECI 27 ISO‑8859‑1 (Latin‑1). Ersätt det numeriska identifieraren i `add_eci_codetext` därefter.

### Kan jag bädda in mer än ett ECI‑block?

Ja. Anropa `add_eci_codetext` flera gånger. Buildern sätter in de nödvändiga ECI‑växlingskoderna mellan blocken och bevarar den ordning du lägger till dem.

### Stöder generatorn QR‑koder med ECI?

Absolut. Byt ut `barcode.Symbology.CODE_128` mot `barcode.Symbology.QR` och justera eventuella QR‑specifika parametrar (t.ex. felkorrigeringsnivå) via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Hur hanterar man mycket långa datasträngar?

För linjära streckkoder som Code 128 är maximal längd cirka 80 tecken när man använder utökad codetext. Överskrider du detta, överväg att byta till en tvådimensionell symbolik såsom QR eller Data Matrix, som kan lagra tusentals tecken.

## Fullt körbart skript

Nedan är hela programmet som du kan kopiera‑klistra in i en fil med namnet `generate_extended_barcode.py` och köra direkt.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkodsbild med anpassning av tilläggsutrymme med Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Hur man genererar streckkodsbild i Java med Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Hur man genererar DataMatrix‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}