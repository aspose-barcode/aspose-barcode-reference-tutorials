---
category: general
date: 2026-08-09
description: Skapa QR‑streckkod i Python med Aspose.BarCode. Lär dig hur du bygger
  utökad kodtext, justerar utseendet och sparar bilden – allt i en handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: sv
lastmod: 2026-08-09
og_description: Skapa QR-streckkod i Python med Aspose.BarCode. Denna guide visar
  hur du bygger utökad kodtext, ställer in visuella parametrar och exporterar bilden.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Skapa QR-streckkod med Aspose.BarCode i Python – fullständigt kodexempel
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Skapa QR‑streckkod med Aspose.BarCode i Python – steg‑för‑steg guide
url: /sv/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa QR‑streckkod med Aspose.BarCode i Python – steg‑för‑steg‑guide

Om du behöver **skapa QR‑streckkod** i Python, guidar den här handledningen dig genom hela processen med hjälp av Aspose.BarCode‑biblioteket. Oavsett om du kodar produkt‑ID:n, flerspråkig text eller anpassade data, kommer du att se hur du bygger en utökad kodtext, justerar visuella inställningar och sparar den slutgiltiga bilden i ett enda körbart skript.

Exemplet visar också hur du visar biblioteksversionen, vilket hjälper dig att verifiera att du kör en kompatibel version. I slutet av den här guiden har du en färdig‑att‑använda QR‑streckkodbild och en tydlig förståelse för varje konfigurationsalternativ.

## Förutsättningar

- Python 3.8+ installerat.
- Paketet `aspose-barcode` (installera via `pip install aspose-barcode`).
- Grundläggande kunskap om Python‑syntax.
- Skrivbehörighet till utmatningskatalogen där PNG‑filen kommer att sparas.

> **Proffstips:** Använd en virtuell miljö för att undvika versionskonflikter med andra projekt.

## Steg 1: Verifiera Aspose.BarCode‑bibliotekets version

Att visa biblioteksversionen säkerställer att du använder en version som stöder utökad kodtext och QR‑kodning.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Varför detta är viktigt:**  
Äldre versioner kan sakna klassen `ExtCodetextBuilder` som krävs för blandade vanliga och ECI‑segment. Att bekräfta versionen förhindrar körningsfel senare i arbetsflödet.

## Steg 2: Bygg en utökad kodtextsträng

En utökad kodtext låter dig kombinera vanlig ASCII‑data med Unicode‑(ECI‑)segment, vilket är nödvändigt för flerspråkiga QR‑koder.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Varför detta är viktigt:**  
Metoden `add_plain_codetext` lagrar data som standard‑ASCII, medan `add_eci_codetext` prefixar ett Unicode‑block med rätt ECI‑designator. Detta tillvägagångssätt säkerställer att QR‑skannrar tolkar den japanska texten korrekt och undviker förvrängda tecken.

### Vanliga varianter

- **Flera ECI‑segment:** Anropa `add_eci_codetext` flera gånger för att blanda flera språk.
- **Olika ECI‑identifierare:** Använd `27` för ISO‑8859‑1, `28` för ISO‑8859‑2 osv., beroende på din mål‑kodning.

## Steg 3: Generera QR‑streckkoden med den utökade kodtexten

Nu när vi har en korrekt formaterad sträng kan vi skapa QR‑koden.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Varför detta är viktigt:**  
`EncodeTypes.QR` instruerar Aspose.BarCode att använda QR‑symbolen. Genom att skicka `extended_codetext` direkt länkas den blandade datan till QR‑matrisen, vilket bevarar både den vanliga och Unicode‑delen.

## Steg 4: Justera visuell utformning (valfritt men rekommenderat)

Finjustering av streckkodens visuella parametrar förbättrar skanningspålitligheten och matchar varumärkesriktlinjer.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Varför detta är viktigt:**  
- **`x_dimension`** styr storleken på varje QR‑modul; för liten kan orsaka läsfel på lågupplösta enheter.  
- **`border_width`** lägger till en tyst zon. Vissa skannrar kräver minst en 4‑modul tyst zon; biblioteket lägger till detta automatiskt, men du kan öka det för extra säkerhet.

### Hantering av kantfall

- **Högdensitetsdata:** Om den kodade datan är stor kan du behöva öka `x_dimension` eller välja en högre felkorrigeringsnivå (via `qr_generator.parameters.qr.error_correction_level`).  
- **Transparent bakgrund:** Ställ in `qr_generator.parameters.barcode.bg_color = Color.Transparent` för PNG‑filer med alfakanaler.

## Steg 5: Spara QR‑streckkodbilden

Skriv slutligen bilden till disk i ditt föredragna format.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Varför detta är viktigt:**  
Att spara som PNG bevarar förlustfri kvalitet, vilket är idealiskt för QR‑koder som behöver skarpa kanter. Om du behöver ett annat format för en webbapplikation, ändra helt enkelt `BarCodeImageFormat`‑enumerationen.

### Verifiera resultatet

Öppna den sparade filen i någon bildvisare. Du bör se en QR‑kod som, när den skannas, returnerar den kombinerade strängen:

```
ABC12345
こんにちは
```

De flesta moderna QR‑skanner‑appar visar först den vanliga delen och renderar sedan den japanska hälsningen korrekt.

---

## Fullständigt körbart skript

Kopiera hela blocket nedan till en fil med namnet `create_qr_barcode.py` och kör den med `python create_qr_barcode.py`. Anpassa `YOUR_DIRECTORY` till en skrivbar mapp på din maskin.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

När du kör detta skript skrivs versionen, den utökade kodtexten och en bekräftelse på att PNG‑filen har skapats ut.

---

## Slutsats

Du vet nu hur du **skapar QR‑streckkod**‑bilder i Python med hjälp av Aspose.BarCode. Handledningen täckte:

1. Verifiera biblioteksversionen.
2. Bygga utökad kodtext med vanliga och ECI‑(Unicode)‑segment.
3. Generera QR‑koden.
4. Anpassa visuella parametrar såsom modulstorlek och kantbredd.
5. Spara den slutgiltiga bilden i PNG‑format.

Härifrån kan du utforska:

- Ändra felkorrigeringsnivåer (`qr_generator.parameters.qr.error_correction_level`).
- Lägga till en logotyp eller bakgrundsbild (`qr_generator.parameters.qr.logo`).
- Exportera till andra format som SVG för skalbara webb‑grafik.
- Integrera generatorn i en Flask‑ eller Django‑endpoint för QR‑skapande i realtid.

Experimentera med olika datapayloads och visuella inställningar för att passa din applikations varumärke och skanningskrav. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig behärska ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar dotcode utökad kodtext med Aspose.BarCode för .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Skapa streckkod Aspose .NET – Konfigurera DataMatrix‑kodtext](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Hur man skapar tyst zon för ITF-14‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}