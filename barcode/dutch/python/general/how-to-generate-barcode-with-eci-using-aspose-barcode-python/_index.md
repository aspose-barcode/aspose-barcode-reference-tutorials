---
category: general
date: 2026-08-19
description: Hoe een barcode met ECI te genereren met Aspose.Barcode voor Python.
  Leer hoe je ECI-gegevens toevoegt, platte tekst combineert en de afbeelding opslaat
  in één duidelijke gids.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: nl
lastmod: 2026-08-19
og_description: Hoe een barcode met ECI te genereren met Aspose.Barcode voor Python.
  Volg deze tutorial om te leren hoe je ECI-gegevens toevoegt, het uiterlijk aanpast
  en het resultaat opslaat.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Hoe een barcode met ECI te genereren met Aspose.Barcode Python – stap‑voor‑stap
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
title: Hoe een barcode met ECI te genereren met Aspose.Barcode Python
url: /nl/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode genereren met ECI met Aspose.Barcode Python

Als je wilt weten **hoe je een barcode genereert** die zowel gewone tekens als ECI‑gecodeerde gegevens bevat, laat deze gids het volledige proces zien. Je ziet precies **hoe je eci**-secties toevoegt, de grootte aanpast en de afbeelding naar schijf schrijft met één enkel, uitvoerbaar script.

De tutorial behandelt:

* Het ophalen van de Aspose.Barcode bibliotheekversie (optioneel maar nuttig voor debugging).  
* Het bouwen van een uitgebreide codetext‑string die gewone en ECI‑gecodeerde tekens combineert.  
* Het maken van een barcode‑generator voor een symbologie die uitgebreide codetext ondersteunt.  
* Het aanpassen van de barcode‑afmetingen en het opslaan van het uiteindelijke PNG‑bestand.

Er is geen externe documentatie nodig; kopieer de code, voer deze uit, en je hebt een barcode‑afbeelding die Chinese tekens bevat gecodeerd met ECI 26 (UTF‑8).

## Vereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

* Python 3.8 of nieuwer geïnstalleerd.  
* `aspose-barcode`-pakket geïnstalleerd (`pip install aspose-barcode`).  
* Schrijfrechten voor de map waarin je het PNG‑bestand wilt opslaan.

Als je een virtuele omgeving gebruikt, activeer deze dan eerst om afhankelijkheden geïsoleerd te houden.

## Stap 1: Controleer de Aspose.Barcode versie (optioneel)

Het kennen van de exacte bibliotheekversie helpt wanneer je bugs moet melden of functies tussen releases wilt vergelijken.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Waarom dit belangrijk is*: De versie‑output bevestigt dat de runtime overeenkomt met de documentatie die je volgt. Verschillende versies kunnen verschillende ECI‑waarden ondersteunen, dus het is een snelle sanity‑check.

## Stap 2: Bouw een uitgebreide codetext met gewone en ECI‑gecodeerde delen

Aspose.Barcode biedt `ExtCodetextBuilder` om gewone data en ECI‑gecodeerde segmenten samen te voegen. In dit voorbeeld combineren we een numerieke string met Chinese tekens.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Uitleg*:  
* `add_plain_codetext` voegt data in die de barcode‑symbologie behandelt als gewone tekens.  
* `add_eci_codetext` instrueert de generator om een ECI‑indicator (hier **26**, wat overeenkomt met UTF‑8) vóór de opgegeven tekst te plaatsen. Dit is precies **hoe je eci**‑data aan een barcode toevoegt.

Je kunt `add_eci_codetext` meerdere keren aanroepen om verschillende taalblokken in te sluiten. De builder verwerkt automatisch de benodigde escape‑sequenties.

## Stap 3: Kies een symbologie die uitgebreide codetext ondersteunt

Niet elk barcode‑type kan ECI‑segmenten opslaan. Code 128, QR en Data Matrix zijn veelgebruikte keuzes. Het voorbeeld gebruikt Code 128 omdat het breed ondersteund wordt en goed werkt voor gemengde alfanumerieke data.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Waarom Code 128?*: Het accepteert het volledige ASCII‑bereik en de ECI‑escape‑sequenties die door de builder worden geproduceerd, waardoor het ideaal is voor het “hoe een barcode te genereren” scenario dat gewone en gecodeerde tekst combineert.

## Stap 4: Pas de barcode‑uiterlijk aan

Je kunt grootte, hoogte, marges en vele andere visuele aspecten regelen via het `parameters`‑object.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tip*: Als je van plan bent de barcode af te drukken, verhoog dan `x_dimension` en `bar_height` evenredig om de leesbaarheid bij de doel‑DPI te behouden.

## Stap 5: Sla de barcode‑afbeelding op

Schrijf tenslotte de gegenereerde afbeelding naar een bestand. Aspose.Barcode ondersteunt PNG, JPEG, BMP en vele andere formaten.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Zorg ervoor dat de `output`‑map bestaat of maak deze aan met `os.makedirs("output", exist_ok=True)` voordat je `save` aanroept.

### Verwacht resultaat

Wanneer je `extended_codetext.png` opent, zou je een Code 128 barcode moeten zien die de numerieke string `1234567890` encodeert, gevolgd door de Chinese tekens “特殊字符”. Het scannen van de barcode met een moderne scanner die ECI respecteert, zal de oorspronkelijke gemengde string teruggeven.

![Barcode gegenereerd met voorbeeld hoe barcode te genereren](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode gegenereerd met voorbeeld hoe barcode te genereren"}

## Veelgestelde vragen en randgevallen

### Wat als ik een andere tekenset nodig heb?

Kies de juiste ECI‑waarde uit de ISO/IEC 18004‑tabel. Bijvoorbeeld, ECI 27 staat voor ISO‑8859‑1 (Latin‑1). Vervang de numerieke identifier in `add_eci_codetext` dienovereenkomstig.

### Kan ik meer dan één ECI‑blok insluiten?

Ja. Roep `add_eci_codetext` meerdere keren aan. De builder voegt de benodigde ECI‑wisselcodes tussen de blokken in, waarbij de volgorde die je toevoegt behouden blijft.

### Ondersteunt de generator QR‑codes met ECI?

Absoluut. Vervang `barcode.Symbology.CODE_128` door `barcode.Symbology.QR` en pas eventuele QR‑specifieke parameters (bijv. foutcorrectieniveau) aan via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Hoe om te gaan met zeer lange gegevensreeksen?

Voor lineaire barcodes zoals Code 128 is de maximale lengte ongeveer 80 tekens bij gebruik van uitgebreide codetext. Als je dit overschrijdt, overweeg dan over te schakelen naar een tweedimensionale symbologie zoals QR of Data Matrix, die duizenden tekens kan opslaan.

## Volledig, uitvoerbaar script

Hieronder staat het volledige programma dat je kunt kopiëren‑plakken in een bestand genaamd `generate_extended_barcode.py` en direct kunt uitvoeren.

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


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode‑afbeelding te genereren met aanvullende ruimte‑aanpassing met Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Hoe een barcode‑afbeelding te genereren in Java met Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Hoe een DataMatrix‑barcode te genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}