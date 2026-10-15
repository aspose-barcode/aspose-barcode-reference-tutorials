---
category: general
date: 2026-10-15
description: Maak een barcode van een string in Python met Aspose.BarCode, leer hoe
  je een Code 128‑barcode genereert en de barcode als PNG opslaat in slechts een paar
  regels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: nl
lastmod: 2026-10-15
og_description: Maak een barcode van een string in Python om gegevens te coderen in
  een Code 128‑barcode en sla deze op als een PNG‑bestand met Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Barcode maken van een string in Python – stap‑voor‑stap gids
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
title: Barcode maken van een string in Python met Aspose.BarCode
url: /nl/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak barcode van tekenreeks in Python met Aspose.BarCode

Als je een **barcode van string** in Python moet maken, laat deze gids je de exacte stappen zien met Aspose.BarCode. Je leert hoe je een **Code 128 barcode** kunt **genereren**, het uiterlijk kunt aanpassen, en de **barcode PNG** kunt **opslaan** op schijf. De oplossing werkt op elk platform dat Python 3.9+ ondersteunt en vereist slechts een paar regels code.

Het programmatisch genereren van barcodes elimineert handmatige invoerfouten en stroomlijnt workflows zoals voorraadbeheer, ticketing en labelafdrukken. Aan het einde van deze tutorial kun je **gegevens in een barcode coderen**, afmetingen aanpassen en de afbeelding opslaan waar je maar wilt.

## Vereisten

- Python 3.9 of nieuwer geïnstalleerd  
- Internettoegang om het Aspose.BarCode‑pakket te downloaden  
- Schrijfrechten voor de map waarin je het PNG‑bestand opslaat  

Als je een virtuele omgeving gebruikt (sterk aanbevolen), activeer deze dan nu.

## Installeer Aspose.BarCode Python‑pakket

Aspose biedt een pure‑Python bibliotheek die alle gangbare barcode‑symbologieën ondersteunt, inclusief Code 128. Installeer deze met pip:

```bash
pip install aspose-barcode
```

*Pro tip:* Pin de versie (bijv. `aspose-barcode==23.9`) om onverwachte breaking changes in productie te voorkomen.

## Maak barcode van string in Python

De eerste functionele stap is het importeren van de benodigde klassen en het instantiëren van een generator voor de gewenste symbologie. Dit voorbeeld gebruikt **Code 128**, wat ideaal is voor alfanumerieke data.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Waarom dit belangrijk is:** `EncodeTypes.CODE_128` vertelt de bibliotheek welke barcode‑standaard moet worden toegepast, terwijl het tweede argument (`"1234567890"`) de **string is die je in een barcode wilt coderen**. Je kunt dit vervangen door elke ASCII‑string tot 80 tekens voor Code 128.

## Genereer Code 128 barcode

Zodra de generator klaar is, kun je de barcode‑afbeelding in het geheugen genereren. De bibliotheek rendert de barcode automatisch op basis van de opgegeven data.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

Op dit punt is `barcode_image` een instantie van `System.Drawing.Image` (op Windows) of een compatibel afbeelding‑object op andere platforms. Je kunt het direct in een GUI weergeven, in een PDF insluiten, of verder aanpassen.

## Pas barcode‑uiterlijk aan

Het fijn afstemmen van de visuele eigenschappen zorgt ervoor dat de barcode betrouwbaar wordt gescand in jouw specifieke omgeving. Veelvoorkomende aanpassingen omvatten de X‑dimensie (de breedte van de smalste balk) en de totale balkhoogte.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Waarom deze waarden aanpassen?*  
- **X‑dimensie** beïnvloedt de dichtheid van de barcode; een kleinere waarde levert een compactere barcode op die op kleine labels past.  
- **Balkhoogte** beïnvloedt de leesbaarheid; hogere balken zijn makkelijker voor scanners om van afstand te detecteren.

Je kunt ook kleuren wijzigen, marges toevoegen, of menselijk leesbare tekst insluiten via het `parameters`‑object. Raadpleeg de Aspose.BarCode‑documentatie voor de volledige lijst met opties.

## Hoe barcode opslaan als PNG

Het opslaan van de gegenereerde afbeelding is de laatste stap in de **create barcode from string** workflow. De bibliotheek ondersteunt verschillende formaten; PNG is verliesloos en breed ondersteund.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

De `save`‑methode schrijft de afbeelding naar het bestandssysteem met het door jou opgegeven formaat. Als de doelmap (`output/` in dit voorbeeld) niet bestaat, zal Python een `FileNotFoundError` genereren. Maak de map van tevoren aan of behandel de uitzondering:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Verwacht resultaat:** Na het uitvoeren van het script bevat `output/barcode.png` een duidelijke Code 128 barcode die `"1234567890"` codeert. Het openen van het bestand in een willekeurige afbeeldingsviewer toont een zwart‑op‑wit barcode klaar om te scannen.

## Volledig, uitvoerbaar voorbeeld

Door alle onderdelen samen te voegen, hier is een zelfstandige script die je kunt kopiëren, plakken en uitvoeren:

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

Voer het script uit met `python create_barcode.py`. Als alles correct is geïnstalleerd, zie je:

```
Barcode saved to output/barcode.png
```

Open het PNG‑bestand en controleer dat de barcode overeenkomt met de oorspronkelijke string met behulp van een barcode‑scanner app.

## Veelgestelde vragen en randgevallen

- **Wat als ik een andere symbologie nodig heb?**  
  Vervang `EncodeTypes.CODE_128` door een andere enum‑waarde zoals `EncodeTypes.QR`, `EncodeTypes.EAN_13` of `EncodeTypes.PDF_417`. De rest van de code blijft hetzelfde.

- **Kan ik een barcode genereren van niet‑ASCII tekens?**  
  Code 128 ondersteunt de volledige 128‑karakter ASCII‑set. Voor Unicode‑data, overweeg QR Code (`EncodeTypes.QR`) die UTF‑8 natively verwerkt.

- **Hoe wijzig ik het afbeeldingsformaat?**  
  Geef een ander lid van `BarCodeImageFormat` door aan `save`, bijv. `BarCodeImageFormat.JPEG` of `BarCodeImageFormat.BMP`.

- **Wat als de uitvoermap alleen‑lezen is?**  
  Plaats de `save`‑aanroep in een try/except‑blok en behandel `PermissionError` op een nette manier, bijvoorbeeld door de gebruiker om een alternatief pad te vragen.

- **Performance tip:**  
  Het genereren van duizenden barcodes in een lus kan CPU‑intensief zijn. Hergebruik een enkele `BarcodeGenerator`‑instantie en werk alleen `generator.parameters.barcode.code_text` bij tussen iteraties.

## Conclusie

Je weet nu hoe je een **barcode van string** in Python kunt **maken** met Aspose.BarCode, een **Code 128 barcode** kunt **genereren**, de grootte kunt aanpassen, en een **barcode PNG** kunt **opslaan** op schijf. Deze end‑to‑end oplossing stelt je in staat om **gegevens in een barcode te coderen** snel en betrouwbaar, waardoor het eenvoudig is om barcodes te integreren in voorraadsystemen, ticketing‑platforms of elke applicatie die machine‑leesbare identifiers vereist.

**Volgende stappen**

- Verken andere symbologieën (`generate code 128 barcode` alternatieven) zoals QR of DataMatrix.  
- Voeg foutafhandelingslogica toe om het script robuust te maken voor productiegebruik (`how to save barcode` fouten).  
- Integreer de gegenereerde PNG in PDF‑s of HTML‑rapporten (`generate barcode png` voor het web).  

Veel programmeerplezier, en geniet van de eenvoud van programmatische barcode‑generatie!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe Code 128 barcode te genereren en barcode‑afbeelding op te slaan met Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode – Volledige gids](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Barcode PNG maken in Python – Volledige Aspose.Barcode‑gids](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}