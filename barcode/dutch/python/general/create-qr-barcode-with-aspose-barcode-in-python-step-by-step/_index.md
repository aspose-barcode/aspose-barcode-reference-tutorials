---
category: general
date: 2026-08-09
description: Maak een QR-barcode in Python met Aspose.BarCode. Leer hoe je uitgebreide
  codetekst maakt, het uiterlijk aanpast en de afbeelding opslaat — allemaal in één
  tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: nl
lastmod: 2026-08-09
og_description: Maak een QR-barcode in Python met Aspose.BarCode. Deze gids laat zien
  hoe je uitgebreide codetekst maakt, visuele parameters instelt en de afbeelding
  exporteert.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: QR-barcode maken met Aspose.BarCode in Python – volledig codevoorbeeld
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
title: QR‑barcode maken met Aspose.BarCode in Python – stapsgewijze handleiding
url: /nl/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR‑barcode maken met Aspose.BarCode in Python – stap‑voor‑stap gids

Als je een **QR‑barcode** in Python moet maken, leidt deze tutorial je door het volledige proces met behulp van de Aspose.BarCode‑bibliotheek. Of je nu product‑ID's, meertalige tekst of aangepaste gegevens codeert, je ziet hoe je een uitgebreide codetext bouwt, visuele instellingen aanpast en de uiteindelijke afbeelding opslaat in één enkele, uitvoerbare script.

Het voorbeeld laat ook zien hoe je de bibliotheekversie kunt weergeven, zodat je kunt verifiëren dat je een compatibele release gebruikt. Aan het einde van deze gids heb je een kant‑klaar QR‑barcode‑beeld en een duidelijk begrip van elke configuratie‑optie.

## Vereisten

- Python 3.8+ geïnstalleerd.
- Het `aspose-barcode`‑pakket (installeren via `pip install aspose-barcode`).
- Basiskennis van Python‑syntaxis.
- Schrijfrechten voor de doelmap waar het PNG‑bestand wordt opgeslagen.

> **Pro tip:** Gebruik een virtuele omgeving om versieconflicten met andere projecten te vermijden.

## Stap 1: Controleer de versie van de Aspose.BarCode‑bibliotheek

Het weergeven van de bibliotheekversie zorgt ervoor dat je een release gebruikt die uitgebreide codetext en QR‑codering ondersteunt.

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

**Waarom dit belangrijk is:**  
Oudere releases kunnen de `ExtCodetextBuilder`‑klasse missen die nodig is voor gemengde gewone en ECI‑segmenten. Het bevestigen van de versie voorkomt runtime‑fouten later in de workflow.

## Stap 2: Bouw een uitgebreide codetext‑string

Een uitgebreide codetext laat je gewone ASCII‑gegevens combineren met Unicode (ECI)‑segmenten, wat essentieel is voor meertalige QR‑codes.

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

**Waarom dit belangrijk is:**  
De `add_plain_codetext`‑methode slaat gegevens op als standaard ASCII, terwijl `add_eci_codetext` een Unicode‑blok voorziet van de juiste ECI‑designator. Deze aanpak zorgt ervoor dat QR‑scanners de Japanse tekst correct interpreteren, waardoor vervormde tekens worden voorkomen.

### Algemene variaties

- **Meerdere ECI‑segmenten:** Roep `add_eci_codetext` meerdere keren aan om verschillende talen te combineren.
- **Verschillende ECI‑identifiers:** Gebruik `27` voor ISO‑8859‑1, `28` voor ISO‑8859‑2, enz., afhankelijk van je doel‑encoding.

## Stap 3: Genereer de QR‑barcode met de uitgebreide codetext

Nu we een correct geformatteerde string hebben, kunnen we de QR‑code maken.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Waarom dit belangrijk is:**  
`EncodeTypes.QR` vertelt Aspose.BarCode om de QR‑symbologie te gebruiken. Het direct doorgeven van de `extended_codetext` koppelt de gemengde gegevens aan de QR‑matrix, waardoor zowel gewone als Unicode‑delen behouden blijven.

## Stap 4: Pas het uiterlijk aan (optioneel maar aanbevolen)

Fijn afstellen van de visuele parameters van de barcode verbetert de scanbetrouwbaarheid en sluit aan bij branding‑richtlijnen.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Waarom dit belangrijk is:**  
- **`x_dimension`** bepaalt de grootte van elke QR‑module; te klein kan leesfouten veroorzaken op apparaten met lage resolutie.  
- **`border_width`** voegt een stille zone toe. Sommige scanners vereisen minstens een stille zone van 4 modules; de bibliotheek voegt dit automatisch toe, maar je kunt het vergroten voor extra veiligheid.

### Afhandeling van randgevallen

- **Gegevens met hoge dichtheid:** Als de gecodeerde gegevens groot zijn, moet je mogelijk `x_dimension` verhogen of een hoger foutcorrectieniveau kiezen (via `qr_generator.parameters.qr.error_correction_level`).  
- **Transparante achtergrond:** Stel `qr_generator.parameters.barcode.bg_color = Color.Transparent` in voor PNG‑bestanden met alfakanalen.

## Stap 5: Sla de QR‑barcode‑afbeelding op

Schrijf tenslotte de afbeelding naar schijf in het door jou gewenste formaat.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Waarom dit belangrijk is:**  
Opslaan als PNG behoudt verliesvrije kwaliteit, wat ideaal is voor QR‑codes die scherpe randen nodig hebben. Als je een ander formaat voor een webapplicatie nodig hebt, wijzig dan eenvoudig de `BarCodeImageFormat`‑enumeratie.

### Resultaat verifiëren

Open het opgeslagen bestand in een willekeurige afbeeldingsviewer. Je zou een QR‑code moeten zien die, bij scanning, de gecombineerde string retourneert:

```
ABC12345
こんにちは
```

De meeste moderne QR‑scanner‑apps tonen eerst het gewone segment en renderen vervolgens de Japanse begroeting correct.

---

## Volledig uitvoerbaar script

Kopieer het volledige blok hieronder naar een bestand genaamd `create_qr_barcode.py` en voer het uit met `python create_qr_barcode.py`. Pas `YOUR_DIRECTORY` aan naar een map waarin je kunt schrijven op je computer.

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

Het uitvoeren van dit script geeft de versie, de uitgebreide codetext en een bevestiging dat het PNG‑bestand is aangemaakt.

---

## Conclusie

Je weet nu hoe je **QR‑barcode**‑afbeeldingen in Python kunt maken met Aspose.BarCode. De tutorial behandelde:

1. Het verifiëren van de bibliotheekversie.  
2. Het bouwen van een uitgebreide codetext met gewone en ECI (Unicode) segmenten.  
3. Het genereren van de QR‑code.  
4. Het aanpassen van visuele parameters zoals modulegrootte en randbreedte.  
5. Het opslaan van de uiteindelijke afbeelding in PNG‑formaat.

Vanaf hier kun je verkennen:

- Het wijzigen van foutcorrectieniveaus (`qr_generator.parameters.qr.error_correction_level`).  
- Het toevoegen van een logo of achtergrondafbeelding (`qr_generator.parameters.qr.logo`).  
- Exporteren naar andere formaten zoals SVG voor schaalbare webgrafieken.  
- De generator integreren in een Flask‑ of Django‑endpoint voor realtime QR‑creatie.

Experimenteer met verschillende gegevenspayloads en visuele instellingen om te passen bij de branding en scanvereisten van jouw applicatie. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je dotcode uitgebreide codetext met Aspose.BarCode voor .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Barcode maken aspose .net - Configureren van DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Hoe maak je Barcode Quiet Zone voor ITF-14 met Aspose.BarCode voor .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}