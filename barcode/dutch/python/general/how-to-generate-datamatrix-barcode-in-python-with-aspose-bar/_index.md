---
category: general
date: 2026-08-22
description: Leer hoe je een DataMatrix‑barcode genereert in Python en Russische tekst
  codeert met Aspose.BarCode – stapsgewijze handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: nl
lastmod: 2026-08-22
og_description: Genereer een DataMatrix-barcode in Python en codeer Russische tekst
  met Aspose.BarCode. Volg het volledige voorbeeld en voer het meteen uit.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Genereer DataMatrix-barcode in Python – volledige Aspose.BarCode-tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Hoe DataMatrix-barcode te genereren in Python met Aspose.BarCode
url: /nl/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe DataMatrix-barcode te genereren in Python met Aspose.BarCode

Als je een **DataMatrix-barcode wilt genereren** in Python terwijl je **Russische tekst codeert**, laat deze gids je de exacte stappen zien. Je ziet een volledig, uitvoerbaar voorbeeld dat een uitgebreide codetext opbouwt, de barcode configureert en de afbeelding opslaat in één script.

Het maken van barcodes die niet‑ASCII tekens bevatten, roept vaak vragen op over tekensets en data‑codering. Door gebruik te maken van Aspose.BarCode’s `ExtCodetextBuilder`, kun je veilig UTF‑8‑tekst zoals Cyrillische tekens in een DataMatrix‑symbool insluiten. Het resultaat werkt met elke scanner die de DataMatrix‑standaard ondersteunt.

In deze tutorial zul je:

* Het vereiste Aspose.BarCode‑pakket installeren.
* Een uitgebreide codetext bouwen die gewone data en Russische tekst combineert.
* **DataMatrix-barcode genereren** met de uitgebreide string.
* Barcode‑parameters aanpassen zoals module‑grootte.
* De barcode opslaan als een PNG‑bestand.

Er zijn geen externe services nodig; alles draait lokaal op je machine.

## Vereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

* Python 3.8 of nieuwer geïnstalleerd.
* Een actieve Aspose.BarCode‑licentie voor Python (een gratis proefversie werkt voor ontwikkeling).
* Basiskennis van Python‑scripting.

Je kunt de Aspose.BarCode‑bibliotheek installeren via pip:

```bash
pip install aspose-barcode
```

## Stap 1: Een uitgebreide codetext‑string bouwen

De eerste taak is om een enkele string te maken die zowel de gewone product‑identificatie als de Russische zin bevat. `ExtCodetextBuilder` laat je verschillende codetext‑delen aan elkaar plakken terwijl de coderingsinformatie behouden blijft.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Waarom deze stap belangrijk is** – DataMatrix‑symbolen slaan ruwe bytes op. Wanneer je alfabetten moet combineren, moet je de encoder vertellen welke tekenset op elk segment van toepassing is. De `add_eci_codetext`‑methode voegt een ECI‑indicator toe vóór de Russische tekst, waardoor scanners de bytes interpreteren als UTF‑8. Zonder ECI zouden de Cyrillische tekens als onleesbare data verschijnen.

## Stap 2: Een DataMatrix‑barcode‑generator maken

Met de uitgebreide codetext klaar, maak je een `BarcodeGenerator` aan en specificeer je het type `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Waarom DataMatrix?** – DataMatrix is een tweedimensionale barcode die tot 2.335 alfanumerieke tekens of 1.556 bytes kan opslaan. Het is ideaal voor kleine objecten, industriële onderdelen en situaties waarin je meertalige tekst moet insluiten.

## Stap 3: (Optioneel) Barcode‑parameters configureren

Aspose.BarCode biedt veel parameters. Voor de meeste toepassingen leveren de standaardinstellingen een leesbaar symbool op. Je wilt echter mogelijk de grootte van elke module (het kleinste vierkant in de matrix) aanpassen om aan de printvereisten te voldoen.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Andere nuttige parameters zijn onder meer het foutcorrectieniveau, de marge en de achtergrondkleur. Pas ze alleen aan als je doel‑scanomgeving specifieke toleranties vereist.

## Stap 4: De barcode‑afbeelding opslaan

Schrijf tenslotte de barcode naar een bestand. De `save`‑methode ondersteunt PNG, JPEG, BMP en verschillende vectorformaten.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Wanneer je `extended_codetext.png` opent, zie je een scherp DataMatrix‑symbool. Het scannen ervan met een standaard DataMatrix‑lezer geeft de twee delen terug:

1. **ABC123** – de gewone identificatie.
2. **Привет** – de Russische groet, correct gedecodeerd als UTF‑8.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige script dat je kunt kopiëren‑plakken in een bestand met de naam `generate_datamatrix.py`. Vervang `YOUR_DIRECTORY` door een bestaande map op je systeem.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Voer het script uit vanaf de opdrachtregel:

```bash
python generate_datamatrix.py
```

Je zou console‑output moeten zien die lijkt op:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Het resultaat verifiëren

Om te bevestigen dat de barcode de Russische zin correct codeert:

1. Open het PNG‑bestand in een afbeeldingsviewer.
2. Gebruik een DataMatrix‑scanapp (veel mobiele apps ondersteunen dit) of een hardware‑scanner.
3. De gedecodeerde string moet `ABC123Привет` weergeven (of de twee delen gescheiden, afhankelijk van de scanner‑UI).

Als de Russische tekens als onzin verschijnen, controleer dan of de scanner ECI UTF‑8 ondersteunt. De meeste moderne lezers doen dat, maar oudere apparaten hebben mogelijk expliciete configuratie nodig.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Oorzaak | Oplossing |
|-------|-------|-----|
| Vervormde Cyrillische output | Ontbrekende ECI‑indicator | Gebruik `add_eci_codetext` met `eci_encoding=3`. |
| Barcode te klein voor printer | Standaard module‑grootte te fijn voor lage DPI | Verhoog `x_dimension` (bijv. `3.0` of `4.0`). |
| Bestand niet opgeslagen | Ongeldig mappad | Zorg dat `YOUR_DIRECTORY` bestaat en schrijfbaar is. |
| Scanner kan niet lezen | Overmatige datadichtheid | Verminder de hoeveelheid gecodeerde data of verhoog het foutcorrectieniveau (`generator.parameters.barcode.error_correction_level`). |

## Het voorbeeld uitbreiden

Je kunt dit patroon aanpassen voor andere talen of datatypes:

* **Japanse of Arabische tekst coderen** – wijzig `eci_encoding` naar de juiste waarde (bijv. 5 voor ISO‑8859‑5, 6 voor ISO‑8859‑7).  
* **Meerdere ECI‑segmenten toevoegen** – roep `add_eci_codetext` meerdere keren aan, elk met zijn eigen codering.  
* **In plaats daarvan een QR‑code maken** – vervang `EncodeTypes.DATA_MATRIX` door `EncodeTypes.QR`.  

Alle andere stappen blijven identiek omdat de `ExtCodetextBuilder` de low‑level byte‑afhandeling abstraheert.

## Conclusie

Je weet nu hoe je **DataMatrix‑barcode kunt genereren** in Python en **Russische tekst kunt coderen** met de uitgebreide codetext‑functie van Aspose.BarCode. Het volledige script behandelt tekenset‑onderhandeling, barcode‑creatie en afbeeldingsoutput met slechts een paar regels code.

Verken vervolgens andere barcode‑symbologieën (PDF417, Aztec) of integreer de generator in een webservice die PNG‑afbeeldingen op aanvraag retourneert. Dezelfde principes — het bouwen van een uitgebreide codetext en het selecteren van de juiste `EncodeTypes` — zijn van toepassing op de volledige Aspose.BarCode‑suite.

Veel programmeerplezier, en geniet van de kracht van meertalige barcode‑generatie!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)
- [Genereer een DataMatrix‑barcode in ASCII‑modus met Aspose.BarCode voor .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Hoe DataMatrix‑barcodes (ECC 200) te genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}