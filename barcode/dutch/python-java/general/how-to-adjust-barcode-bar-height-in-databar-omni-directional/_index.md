---
category: general
date: 2026-11-27
description: Leer hoe u de balkhoogte van de barcode kunt aanpassen in een DataBar
  Omni‑Directional barcodegenerator. Stapsgewijze code toont het instellen van hoogtes
  op 30 px en 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: nl
lastmod: 2026-11-27
og_description: Pas de hoogte van de streepjes in een DataBar Omni‑Directional barcodegenerator
  aan met Python. Volg de volledige gids om hoogtes, X‑dimensie in te stellen en PNG‑afbeeldingen
  op te slaan.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Pas de hoogte van de barcodebalk aan in de DataBar Omni‑Directionele generator
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Hoe de hoogte van de barcodebalk aan te passen in de DataBar Omni‑Directional
  generator
url: /nl/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de balkhoogte van een barcode aan te passen in de DataBar Omni‑Directional generator

Als je de **balkhoogte van een barcode** voor een DataBar Omni‑Directional barcode moet **aanpassen**, laat deze gids je precies zien hoe. Je ziet een volledig, uitvoerbaar Python‑voorbeeld dat de balkhoogte wijzigt van 30 px naar 60 px terwijl de X‑dimension en het afbeeldingsformaat consistent blijven.

Het wijzigen van de visuele afmetingen van een barcode is een veelvoorkomende eis wanneer de barcode moet passen in een specifieke labelgrootte of ontwerprichtlijn. Naast de balkhoogte wil je misschien ook de **X‑dimension** (modulegrootte) aanpassen of een ander **barcode‑afbeeldingsformaat** kiezen, zoals PNG of JPEG.

In deze tutorial leer je:

* De vereiste bibliotheek installeren (GroupDocs.Barcode for Python)
* Een DataBar Omni‑Directional barcode‑generator maken
* De modulegrootte instellen met `XDimension`
* De balkhoogte‑eigenschap twee keer aanpassen
* De resulterende afbeeldingen opslaan in het gewenste **BarCodeImageFormat**

Ervaring met de GroupDocs API is niet vereist — alleen basiskennis van Python.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* Python 3.8 of nieuwer geïnstalleerd
* `groupdocs.barcode`‑pakket (`pip install groupdocs-barcode`)  
* Schrijfrechten op een map waar de PNG‑bestanden worden opgeslagen

Als je niet bekend bent met de **DataBar Omni‑Directional barcode**, codeert deze een 14‑cijferige GTIN en wordt veel gebruikt in de detailhandel voor scannen vanuit elke oriëntatie.

## Stap 1: De DataBar Omni‑Directional barcode‑generator instellen

Importeer eerst de benodigde klassen en maak een instantie van de generator met de GTIN‑gegevens die je wilt coderen.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Waarom dit belangrijk is:* De constante `EncodeTypes.DatabarOmniDirectional` vertelt de bibliotheek om de Omni‑Directional symbologie te genereren. De gegevensreeks bevat de AI `(01)` die een GTIN‑14‑waarde aangeeft.

## Stap 2: De X‑dimension (modulegrootte) definiëren

De X‑dimension bepaalt de breedte van de smalste balk. Een veelgebruikte waarde voor weergave op het scherm is **2 px per module**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Het gebruik van een consistente **set XDimension** zorgt ervoor dat de barcode correct schaalt over verschillende printers en scanners.

## Stap 3: De balkhoogte aanpassen naar 30 px en de afbeelding opslaan

Nu wijzigen we de balkhoogte‑eigenschap. De eerste hoogte die we gebruiken is **30 px**, wat geschikt is voor kleine labels.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

De constante `BarCodeImageFormat.Png` selecteert het **barcode‑afbeeldingsformaat** PNG, dat verliesvrije kwaliteit behoudt.

### Verwacht resultaat

Het bestand `DatabarBarHeight30Pixels.png` bevat een DataBar Omni‑Directional barcode waarvan de balken 30 px hoog zijn. Hieronder staat een tijdelijke voorbeeldweergave:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tip:** Als je de PNG opent in een beeldbewerkingsprogramma, zie je de exacte balkhoogte. De smalle balken zijn 2 px breed, zoals eerder gedefinieerd.

## Stap 4: De balkhoogte wijzigen naar 60 px voor een hogere barcode

Voor toepassingen die een grotere visuele voetafdruk vereisen — zoals een vrachtlabel — kun je de balkhoogte verhogen naar **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Alleen de `BarHeight`‑eigenschap verandert; de X‑dimension en codering blijven gelijk, zodat de barcode scanbaar blijft.

## Stap 5: De bijgewerkte barcode‑afbeelding opslaan

Schrijf tenslotte de hogere barcode naar een tweede PNG‑bestand.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Verwacht resultaat

Het bestand `DatabarBarHeight60Pixels.png` toont dezelfde gecodeerde gegevens, maar elke balk is nu 60 px hoog. Het visuele verschil wordt hieronder geïllustreerd:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Volledig, uitvoerbaar voorbeeld

Alles samengevoegd, hier is het volledige script dat je kunt kopiëren‑plakken in een bestand genaamd `adjust_barcode_height.py` en direct kunt uitvoeren.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Voer het script uit:

```bash
python adjust_barcode_height.py
```

Je zou twee PNG‑bestanden in de map `output` moeten zien, elk met de ingestelde balkhoogte.

## Veelgestelde vragen en randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik JPEG in plaats van PNG gebruiken?** | Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`. JPEG is verliesgevend, dus geef de voorkeur aan PNG voor nauwkeurig scannen. |
| **Wat als ik een balkhoogte nodig heb die geen veelvoud van 10 is?** | De eigenschap `BarHeight.Pixels` accepteert elke gehele waarde. Wijs gewoon het gewenste aantal pixels toe (bijv. `45`). |
| **Heeft het wijzigen van de balkhoogte invloed op de gecodeerde gegevens?** | Nee. Alleen de visuele weergave verandert; de onderliggende gegevensreeks blijft identiek. |
| **Hoe wijzig ik de X‑dimension na het opslaan van de eerste afbeelding?** | Je kunt `gen.parameters.barcode.x_dimension.pixels` op elk moment aanpassen vóór het aanroepen van `save()`. De wijziging wordt toegepast op volgende afbeeldingen. |
| **Is de generator thread‑safe?** | De `BarcodeGenerator`‑instantie is niet gegarandeerd thread‑safe. Maak een aparte instantie per thread als je gelijktijdig barcodes genereert. |

## Conclusie

Je weet nu hoe je de **balkhoogte van een barcode** kunt **aanpassen** in een DataBar Omni‑Directional barcode‑generator met Python. De tutorial behandelde het maken van de generator, het instellen van de **X‑dimension**, het wijzigen van de **barcode‑balkhoogte**‑eigenschap, en het opslaan van afbeeldingen in het gewenste **barcode‑afbeeldingsformaat**.

Vanaf hier kun je experimenteren met andere hoogtes, verschillende modulegroottes, of overschakelen naar alternatieve afbeeldingsformaten zoals JPEG of BMP. Je kunt ook extra **barcode generator python**‑functies verkennen, zoals het toevoegen van menselijk leesbare tekst of het wijzigen van kleurenschema's.

Veel plezier met coderen, en houd je barcodes scherp en perfect van formaat!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe de breedte in te stellen en de hoogte aan te passen voor een GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Omni‑directional databar en barcode‑afbeelding maken in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode‑generator – barcode‑hoogte wijzigen](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}