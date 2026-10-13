---
category: general
date: 2026-09-23
description: Leer hoe u een Code 128‑barcode genereert en de barcode‑afbeelding opslaat
  met Aspose.BarCode in Python – stapsgewijze handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: nl
lastmod: 2026-09-23
og_description: Genereer Code 128‑barcode en sla de barcode‑afbeelding op met Aspose.BarCode
  in Python. Volg dit volledige voorbeeld om de barcode te maken, aan te passen en
  te exporteren als een PNG‑bestand.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Genereer Code 128‑barcode en sla de barcode‑afbeelding op – Python‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Hoe een Code 128‑barcode te genereren en de barcode‑afbeelding op te slaan
  met Aspose.BarCode
url: /nl/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Code 128‑streepjescodes te genereren en de barcode‑afbeelding op te slaan met Aspose.BarCode

Als je een **Code 128‑barcode** wilt **genereren** en de **barcode‑afbeelding wilt opslaan** in een Python‑project, laat deze tutorial de exacte stappen zien. Met Aspose.BarCode’s `ExtCodetextBuilder` kun je platte tekst‑ en Unicode‑segmenten in één payload embedden en vervolgens het resultaat renderen als een PNG‑bestand.

Je ziet een compleet, uitvoerbaar script, een uitleg van elke regel, en tips voor veelvoorkomende valkuilen zoals het omgaan met ECI‑codering of het kiezen van de juiste uitvoermap. Geen externe documentatie nodig—kopieer, plak en voer uit.

## Voorvereisten

Voordat je begint, zorg dat je het volgende hebt:

* Python 3.8+ geïnstalleerd.
* Het `aspose.barcode`‑pakket (installeren met `pip install aspose-barcode`).
* Schrijfrechten voor de map waarin de PNG wordt opgeslagen.

De code werkt met elke symbologie die door Aspose.BarCode wordt ondersteund, maar het voorbeeld richt zich op **Code 128** omdat het alfanumerieke data efficiënt codeert en uitgebreide tekenreeksen ondersteunt.

## Stap 1: Importeer de vereiste klassen

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Waarom deze stap?* Het importeren van de klassen geeft je toegang tot de builder voor uitgebreide codetext, de writer die de afbeelding maakt, en de versie‑helper die handig kan zijn bij het debuggen van bibliotheek‑updates.

## Stap 2: Bouw de uitgebreide codetext

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

De `ExtCodetextBuilder` laat je platte ASCII‑ en Unicode‑data mengen in één barcode‑payload. Het ECI‑ (Extended Channel Interpretation)‑byte `0x03` vertelt de scanner dat de volgende bytes UTF‑8 gecodeerd zijn, wat essentieel is voor talen zoals Russisch, Chinees of Arabisch.

## Stap 3: Configureer de barcode‑writer voor Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Door `encode_type` in te stellen op `CODE_128` instrueer je de writer om een **Code 128‑barcode** te renderen. De eigenschap `code_text` ontvangt de uitgebreide string die in de vorige stap is opgebouwd.

## Stap 4: Sla de barcode‑afbeelding op als PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

De `save`‑methode schrijft de barcode naar een bestand. Het gebruik van `BarCodeImageFormat.PNG` zorgt voor verliesloze compressie en brede compatibiliteit met web‑ en mobiele toepassingen.

## Stap 5 (optioneel): Controleer de Aspose.BarCode‑bibliotheekversie

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

De exacte bibliotheekversie kennen helpt wanneer je bugs moet rapporteren of gedrag tussen releases wilt vergelijken.

## Verwachte output

Het uitvoeren van het script geeft console‑output vergelijkbaar met:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

De gegenereerde PNG (`extended_codetext.png`) ziet er als volgt uit:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*De afbeelding toont een Code 128‑barcode die zowel de ASCII‑string `ABC123` als het Russische woord “Пример” codeert.*

## Veelgestelde vragen en afhandeling van randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik een andere symbologie gebruiken?** | Ja. Vervang `BarCodeEncodeMode.CODE_128` door een andere ondersteunde modus, zoals `QR`, `EAN_13` of `PDF_417`. |
| **Wat als mijn Unicode‑tekst emoji’s bevat?** | Emoji’s zijn ook UTF‑8‑tekens, dus dezelfde `add_eci_codetext`‑aanroep werkt. Zorg ervoor dat de doel‑scanner de gebruikte ECI ondersteunt. |
| **Hoe wijzig ik de afbeeldingsgrootte?** | Stel `writer.x_dimension` en `writer.bar_height` in vóór het aanroepen van `save`. |
| **Welke map moet ik gebruiken voor `output_path`?** | Elke map waar het Python‑proces schrijfrechten voor heeft. Gebruik `os.makedirs` met `exist_ok=True` om deze automatisch aan te maken. |

## Pro‑tips

* **Vermijd hard‑gecodeerde paden.** Gebruik `os.path.join` en `Path` uit de `pathlib`‑module voor platform‑onafhankelijke compatibiliteit.
* **Valideer de barcode.** Na het opslaan kun je de afbeelding opnieuw lezen met `barcode.BarCodeReader` om te bevestigen dat de gecodeerde tekst overeenkomt met `extended_codetext`.
* **Prestatie‑tip.** Als je veel barcodes in een lus genereert, hergebruik dan één `BarCodeWriter`‑instantie en werk alleen `code_text` bij per iteratie.

## Conclusie

Je weet nu hoe je een **Code 128‑barcode** kunt **genereren** met gemengde ASCII‑ en Unicode‑data en de **barcode‑afbeelding** als PNG kunt **opslaan** met Aspose.BarCode in Python. Het volledige script behandelt het bouwen van uitgebreide codetext, het configureren van de writer, het exporteren van de afbeelding en het controleren van bibliotheekversies.

Vanaf hier kun je verder gaan met:

* Het toevoegen van voor‑/achtergrondkleuren (`writer.back_color`, `writer.fore_color`).
* Het embedden van de barcode in PDF‑bestanden met `Aspose.PDF`.
* Het gebruik van de `BarCodeReader`‑klasse om de opgeslagen afbeelding te decoderen en de inhoud automatisch te verifiëren.

Veel programmeerplezier, en voel je vrij om te experimenteren met andere symbologieën en afbeeldingsformaten!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}