---
category: general
date: 2026-11-27
description: Genereer QR‑barcode in Python met Aspose.Barcode en leer hoe je de barcode‑afbeelding
  snel naar schijf kunt opslaan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: nl
lastmod: 2026-11-27
og_description: Genereer QR‑barcode in Python met Aspose.Barcode en sla de barcode‑afbeelding
  direct op. Volg het volledige voorbeeld om QR‑codes te maken, aan te passen en op
  te slaan.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: QR-barcode genereren en afbeelding opslaan met Python – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: QR‑barcode genereren en afbeelding opslaan met Python
url: /nl/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR‑barcode genereren en afbeelding opslaan met Python

Als je een **QR‑barcode moet genereren** in een Python‑applicatie, laat deze gids je zien hoe je dat doet met de Aspose.Barcode‑bibliotheek. Je leert ook de juiste manier om een **barcode‑afbeelding op te slaan** in een lokale map, bibliotheek‑versiedetails op te halen en uitgebreide codetext‑segmenten te verwerken.

Het maken van QR‑codes is een veelvoorkomende eis voor ticketsystemen, mobiele betalingen en producttracking. Aan het einde van deze tutorial heb je een kant‑en‑klaar script dat een QR‑barcode‑afbeeldingsbestand genereert en versie‑informatie afdrukt voor debugging of compliance‑doeleinden.

## Vereisten

* Python 3.8 of nieuwer geïnstalleerd.
* Het `aspose-barcode`‑pakket. Installeer het met `pip install aspose-barcode`.
* Schrijfrechten voor de map waarin de barcode‑afbeelding wordt opgeslagen.

Er zijn geen extra externe services nodig; het volledige proces draait lokaal.

## Stap 1: Bouw een uitgebreide codetext met `ExtCodetextBuilder`

Uitgebreide codetext stelt je in staat om platte tekst en ECI‑segmenten (Extended Channel Interpretation) te combineren in één QR‑code. Dit is handig wanneer je tekens uit verschillende tekensets moet insluiten, zoals het euro‑teken.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Waarom deze stap belangrijk is:**  
`ExtCodetextBuilder` stelt de uiteindelijke string samen die de QR‑encoder zal verwerken. Zonder het bouwen van de uitgebreide codetext zou de barcode alleen platte ASCII‑tekens bevatten en kon geen locale‑specifieke symbolen weergeven.

## Stap 2: Haal de gecombineerde uitgebreide codetext‑string op

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

De uitvoer ziet er als volgt uit:

```
Extended codetext: ABC123[ECI3]€123
```

De tussen haakjes staande `[ECI3]`‑marker vertelt de QR‑encoder om over te schakelen naar de opgegeven tekenset voor de volgende tekens.

## Stap 3: Genereer de QR‑barcode met behulp van de uitgebreide codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Uitleg:**  
`BarcodeGenerator` ontvangt twee argumenten: het barcode‑type (`QR`) en de te coderen data (`extended_codetext`). De generator bereidt alle interne structuren voor die nodig zijn voor het renderen.

## Stap 4: Sla de gegenereerde barcode‑afbeelding op

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Waarom je deze aanpak moet gebruiken:**  
Het direct aanroepen van `save` schrijft de afbeelding naar schijf met het formaat dat wordt afgeleid van de bestandsextensie. De methode ondersteunt PNG, JPEG, BMP en TIFF, waardoor je flexibiliteit hebt voor verschillende downstream‑consumenten.

### Verifiëren van de opgeslagen afbeelding

Open het bestand `output/qr_extended.png` met een willekeurige afbeeldingsviewer. Je zou een QR‑code moeten zien die, bij het scannen, de string `ABC123€123` teruggeeft. De meeste moderne mobiele QR‑scanners verwerken het ECI‑segment automatisch.

## Stap 5: Vraag Aspose.BarCode‑versie‑informatie op (optioneel maar nuttig)

Het kennen van de exacte versie van de Aspose.BarCode‑bibliotheek helpt wanneer je bugs moet melden of compatibiliteit moet verifiëren.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typische uitvoer:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Volledig script – kopiëren, plakken en uitvoeren

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Het uitvoeren van het script genereert de QR‑code‑afbeelding en drukt zowel de uitgebreide codetext als de versie‑details af naar de console.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanbevolen aanpassing |
|-----------|------------------------|
| **Andere tekenset** | Verander de ECI‑identifier die wordt doorgegeven aan `add_eci_codetext`. Voor UTF‑8 gebruik `5`. |
| **Hogere foutcorrectie** | Stel `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` in vóór het aanroepen van `save`. |
| **Aangepaste afbeeldingsgrootte** | Gebruik `barcode.parameters.image_width` en `barcode.parameters.image_height` om de pixelafmetingen te bepalen. |
| **Niet‑PNG uitvoer** | Verander de bestandsextensie in `output_path` naar `.jpg` of `.bmp`. De bibliotheek selecteert automatisch de juiste encoder. |

## Pro‑tips

* **Maak de output‑map** programmatisch aan als deze mogelijk niet bestaat:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Valideer de QR‑code** na generatie door deze opnieuw te lezen met `aspose.barcode.BarcodeReader`. Dit zorgt ervoor dat de gecodeerde data overeenkomt met de verwachtingen, vooral bij gebruik van ECI‑segmenten.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Performance‑tip** – hergebruik één `BarcodeGenerator`‑instantie als je veel QR‑codes in een lus moet genereren. Reset de `code_text`‑eigenschap in plaats van elke iteratie een nieuw object te maken.

## Conclusie

Je weet nu hoe je **QR‑barcode kunt genereren** in Python met Aspose.Barcode, een uitgebreide codetext kunt bouwen die platte tekst en ECI‑segmenten combineert, en correct **barcode‑afbeeldingen kunt opslaan** op schijf. Het script laat ook zien hoe je bibliotheek‑versie‑informatie kunt ophalen voor probleemoplossing.

Volgende stappen die je kunt verkennen zijn onder andere:

* Een logo‑overlay of aangepaste kleuren toevoegen aan de QR‑code.
* De QR‑barcode direct in PDF‑bestanden insluiten met Aspose.PDF.
* Batch‑generatie automatiseren voor grote datasets.

Voel je vrij om te experimenteren met verschillende data‑payloads, foutcorrectieniveaus en afbeeldingsformaten. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode – Volledige gids](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Hoe Code 128‑barcode te genereren en barcode‑afbeelding op te slaan met Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Hoe DataMatrix‑barcode te genereren in Python met Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}