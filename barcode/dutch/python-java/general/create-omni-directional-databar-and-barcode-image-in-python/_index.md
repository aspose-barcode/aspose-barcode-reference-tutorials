---
category: general
date: 2026-08-12
description: Maak een omnidirectionele databar met Python en leer hoe je een barcode‑afbeelding
  maakt met Python met behulp van Aspose.BarCode. Volg de stap‑voor‑stap‑handleiding
  voor een complete oplossing.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: nl
lastmod: 2026-08-12
og_description: Maak een omni-directionele databar met Python en genereer in enkele
  minuten een barcode‑afbeelding met Python. Deze tutorial toont een volledig, uitvoerbaar
  voorbeeld.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Creëer een omnidirectionele databar – volledige Python‑gids
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Maak omni-directionele databar- en barcode-afbeelding in Python
url: /nl/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak omni-directionele databar en barcode‑afbeelding in Python

Als je een **omni-directionele databar** wilt **maken** in een Python‑project, laat deze gids je zien hoe je dat doet en ook hoe je een **barcode‑afbeelding in Python** maakt met de Aspose.BarCode‑bibliotheek. Je krijgt een kant‑klaar script dat twee PNG‑bestanden met verschillende beeldverhoudingen genereert.

Het genereren van een DataBar die voldoet aan de Omni‑directionele specificatie is een veelvoorkomende eis voor retail‑ en logistieke toepassingen. De tutorial behandelt installatie, configuratie van de X‑dimensie, aanpassing van de beeldverhouding en het opslaan van de uiteindelijke afbeeldingen. Er zijn geen externe services nodig; alles draait lokaal.

## Wat je nodig hebt

* Python 3.8 of nieuwer geïnstalleerd op je machine.
* Toegang tot een terminal of opdrachtprompt.
* Schrijfrechten voor een map waar de barcode‑afbeeldingen worden opgeslagen.

De enige externe afhankelijkheid is **Aspose.BarCode for Python via .NET**, die het Omni‑directionele DataBar‑type direct ondersteunt.

## Stap 1: Installeer Aspose.BarCode voor Python

Aspose.BarCode biedt de `BarcodeGenerator`‑klasse die in de voorbeeldcode wordt gebruikt. Installeer het pakket met `pip`:

```bash
pip install aspose-barcode
```

Het pakket bevat de benodigde .NET‑runtime‑bindings, zodat je de .NET SDK niet apart hoeft te installeren.

## Stap 2: Importeer de bibliotheek en maak de generator

De eerste regel van het script maakt een generator voor een gestapelde Omni‑directionele DataBar. De GTIN‑14‑waarde `(01)12345678901231` wordt als voorbeeldgegevens gebruikt.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Waarom deze stap belangrijk is*: De constante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` vertelt de bibliotheek de waarde te coderen als een Omni‑directionele DataBar, het formaat dat door veel point‑of‑sale scanners wordt vereist.

## Stap 3: Stel de X‑dimensie (module‑breedte) in

De X‑dimensie bepaalt de breedte van de kleinste balkmodule. Een waarde van `2` pixels levert een duidelijke, leesbare barcode op zonder een buitensporige bestandsgrootte.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Waarom deze stap belangrijk is*: Het aanpassen van de X‑dimensie stelt je in staat de leesbaarheid en afbeeldingsgrootte in balans te brengen. Een X‑dimensie die te klein is, kan slecht renderen op printers met lage resolutie.

## Stap 4: Configureer de beeldverhouding en sla de eerste afbeelding op

De beeldverhouding beïnvloedt de totale hoogte van de DataBar ten opzichte van de breedte. Een beeldverhouding van `15` creëert een compacte visuele stijl.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tip**: Gebruik `pathlib.Path` om het uitvoerpad op te bouwen; dit maakt automatisch ontbrekende mappen aan.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Stap 5: Verander de beeldverhouding voor een tweede visuele stijl en sla een andere afbeelding op

Het wijzigen van de beeldverhouding naar `30` produceert een hogere barcode die mogelijk vereist is door specifieke scanner‑hardware.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Waarom deze stap belangrijk is*: Verschillende retailers en scanapparaten hebben uiteenlopende grootte‑beperkingen. Door beide beeldverhoudingen in één script aan te bieden, kun je de exacte stijl genereren die je nodig hebt zonder code te dupliceren.

## Volledig script – maak omni-directionele databar en barcode‑afbeelding python

Hieronder staat het volledige, uitvoerbare voorbeeld dat alle voorgaande stappen combineert. Sla het op als `generate_databar.py` en voer het uit met `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Verwachte output

Het uitvoeren van het script maakt de volgende bestanden aan:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Beide afbeeldingen tonen een geldige Omni‑directionele DataBar die kan worden gescand door standaard retail‑apparatuur.

![example of create omni directional databar barcode image in Python](example_databar.png "create omni directional databar barcode image python")

*De bovenstaande afbeelding is een placeholder die de twee opgeslagen PNG‑bestanden illustreert.*

## Veelvoorkomende problemen oplossen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `ImportError: No module named aspose` | Aspose.BarCode niet geïnstalleerd of geïnstalleerd in een andere omgeving. | Activeer de juiste virtuele omgeving en voer `pip install aspose-barcode` uit. |
| `PermissionError` bij opslaan | Het script heeft geen schrijfrechten voor de doelmap. | Kies een map waar je toegang toe hebt of voer het script uit met de juiste privileges. |
| Barcode scant niet | X‑dimensie te laag of beeldverhouding onverenigbaar met de scanner. | Verhoog `x_dimension.pixels` naar 3 of 4, en test verschillende `aspect_ratio`‑waarden (bijv. 20, 25). |
| Ontbrekende .NET‑runtime | Aspose.BarCode is afhankelijk van de .NET‑runtime op Windows/Linux. | Installeer de nieuwste .NET‑runtime vanaf de Microsoft‑site; de pakketdocumentatie biedt platform‑specifieke aanwijzingen. |

## Voorbeeld uitbreiden

Je kunt het script aanpassen om andere DataBar‑varianten te genereren (bijv. `DATABAR_STACKED`, `DATABAR_EXPANDED`). Vervang de `EncodeTypes`‑constante dienovereenkomstig:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Als je de barcode in een PDF wilt insluiten, kan Aspose.PDF for Python het PNG‑bestand direct importeren of kun je de `save`‑methode gebruiken met `BarCodeImageFormat.Pdf`.

## Conclusie

Deze tutorial liet zien hoe je **omni-directionele databar** kunt **maken** en hoe je **barcode‑afbeelding in Python** kunt **maken** met Aspose.BarCode. Je hebt nu een compleet, reproduceerbaar script dat twee PNG‑bestanden met verschillende beeldverhoudingen genereert, veelvoorkomende valkuilen afhandelt en kan worden uitgebreid naar andere barcode‑formaten.

Vervolgens kun je QR‑codes genereren, de barcode toevoegen aan PDF‑facturen, of batchverwerking automatiseren voor grote productcatalogi. Elk van deze onderwerpen bouwt voort op hetzelfde `BarcodeGenerator`‑patroon dat hier wordt gedemonstreerd. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Genereer barcode‑afbeelding – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Maak DotCode barcode‑afbeelding – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hoe maak je een barcode‑afbeelding en render je deze in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}