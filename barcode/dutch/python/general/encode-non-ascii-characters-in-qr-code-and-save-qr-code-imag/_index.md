---
category: general
date: 2026-09-10
description: Encode niet‑ASCII‑tekens in een QR‑code en sla de QR‑code‑afbeelding
  op met een eenvoudige Python‑builder. Volg een stapsgewijze handleiding met ExtCodetextBuilder
  en BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: nl
lastmod: 2026-09-10
og_description: Codeer niet‑ASCII‑tekens in een QR‑code en sla de QR‑code‑afbeelding
  op met Python. Deze tutorial laat zien hoe je uitgebreide codetekst maakt, een QR‑code
  genereert en de afbeelding opslaat.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Niet‑ASCII‑tekens coderen in QR‑code en QR‑code‑afbeelding opslaan – stapsgewijze
  Python‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Niet‑ASCII‑tekens coderen in QR‑code en QR‑code‑afbeelding opslaan
url: /nl/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Niet-ASCII tekens coderen in QR-code en QR-code afbeelding opslaan

Als je **niet-ASCII tekens** in een QR-code moet **coderen**, laat deze gids je precies zien hoe je dat doet en vervolgens **de QR-code afbeelding** opslaat op schijf. Of je nu Russische, Chinese of emoji-gegevens verwerkt, de ExtCodetextBuilder laat je gewone tekst en ECI‑gecodeerde segmenten combineren zonder handmatig met bytes te rommelen.

Je leert hoe je een extended codetext string maakt, een QR-code genereert die die string begrijpt, en uiteindelijk de barcode‑afbeelding naar een bestand schrijft. De tutorial gaat uit van basiskennis van Python en dat je de `barcode` SDK geïnstalleerd hebt.

## Vereisten

* Python 3.8+ geïnstalleerd.
* Het `barcode` Python‑pakket (of de juiste SDK) dat `ExtCodetextBuilder`, `CodetextEncodingType` en `BarcodeGenerator` levert.
* Schrijfrechten voor de map waarin je **de QR-code afbeelding** wilt opslaan.

Je kunt de SDK installeren met pip (vervang `barcode-sdk` door de daadwerkelijke pakketnaam):

```bash
pip install barcode-sdk
```

## Stap 1: Maak een extended codetext builder

De eerste stap is het instantiëren van `ExtCodetextBuilder`. Dit object verzamelt meerdere tekstsegmenten en produceert één string die de QR-code symbologie kan interpreteren.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Waarom dit belangrijk is*: QR-codes ondersteunen **extended codetext**, wat betekent dat je meerdere coderingsmodi (plain, ECI, enz.) in één barcode kunt embedden. De builder abstraheert de low‑level opmaak die door de QR-specificatie vereist is.

## Stap 2: Voeg een plain‑text segment toe

Plain text is de standaardmodus en werkt voor ASCII‑tekens. Het eerst toevoegen geeft een leesbare fallback voor scanners die ECI negeren.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Als je deze stap overslaat, zou de QR-code alleen het ECI‑segment bevatten, wat sommige oudere lezers mogelijk niet correct kunnen decoderen.

## Stap 3: Voeg een ECI‑gecodeerd segment toe voor niet‑ASCII tekens

Om tekens buiten het ASCII‑bereik op te nemen — zoals Cyrillisch, Chinees of emoji’s — moet je een ECI (Extended Channel Interpretation) codering opgeven. Hier gebruiken we UTF‑8 voor het Russische woord “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Waarom dit werkt*: De QR-specificatie definieert ECI‑waarden die de scanner vertellen welke tekenset toe te passen. Zonder de ECI‑marker zouden de ruwe bytes geïnterpreteerd worden als ISO‑8859‑1, wat leidt tot onleesbare output.

## Stap 4: Haal de gecombineerde extended codetext string op

Na het toevoegen van alle gewenste segmenten, roep je `get_extended_codetext()` aan om de uiteindelijke string te verkrijgen die de barcode‑generator verwacht.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

De afgedrukte waarde ziet eruit als een reeks controle‑karakters gevolgd door de eigenlijke tekst, maar je hoeft deze nooit handmatig te parseren.

## Stap 5: Genereer een QR-code met de extended codetext

Maak nu een `BarcodeGenerator`, stel de symbologie in op QR (de enige gangbare 2‑D symbologie die extended codetext ondersteunt), en voer de gecombineerde string in.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: Als je hetzelfde proces probeert met Code‑128 of DataMatrix, zal de SDK een uitzondering werpen omdat die formaten geen ECI‑markers kunnen interpreteren.

## Stap 6: Sla de QR-code afbeelding op

Schrijf tenslotte de barcode naar een PNG‑bestand. Dit is waar je **de QR-code afbeelding** opslaat voor later gebruik.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Zorg ervoor dat de map `output` bestaat of maak deze aan met `os.makedirs('output', exist_ok=True)` voordat je `save` aanroept.

### Volledig uitvoerbaar voorbeeld

Alle stappen samenvoegen geeft je een zelfstandige script die je direct kunt uitvoeren:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Verwachte output** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Het openen van `qr_extended.png` met een QR-scanner zal `HelloWorldПривет` weergeven. Scanners die ECI begrijpen zullen de Cyrillische tekens correct renderen; anderen tonen alleen het ASCII‑deel.

## Veelgestelde vragen & randgevallen

| Vraag | Antwoord |
|----------|--------|
| *Kan ik andere coderingen gebruiken zoals Shift‑JIS?* | Ja. Vervang `CodetextEncodingType.UTF_8` door `CodetextEncodingType.SHIFT_JIS` en geef de juiste tekst op. |
| *Wat als de gecombineerde data de QR-capaciteit overschrijdt?* | QR-codes hebben versie‑limieten (tot 177 × 177 modules). Als de builder een grootte‑exception gooit, verhoog dan het fout‑correctieniveau of splits de data over meerdere QR-codes. |
| *Moet ik een specifieke QR-versie instellen?* | De SDK selecteert automatisch de kleinste versie die bij de data past. Indien nodig kun je een versie forceren met `qr_generator.set_qr_version(10)`. |
| *Zal de afbeelding transparant zijn?* | Standaard schrijft de SDK een PNG met een witte achtergrond. Gebruik `qr_generator.set_background_color(Color.Transparent)` vóór `save` als je transparantie nodig hebt. |

## Conclusie

In deze tutorial heb je geleerd hoe je **niet-ASCII tekens** in een QR-code kunt **coderen** met behulp van de `ExtCodetextBuilder` en vervolgens **de QR-code afbeelding** kunt **opslaan** met de `BarcodeGenerator`. Het proces omvat het bouwen van een extended codetext string, het toevoegen van zowel plain‑ als ECI‑gecodeerde segmenten, het genereren van de QR‑symbologie, en tenslotte het schrijven van het afbeeldingsbestand.

Vanaf hier kun je verder verkennen:

* Het toevoegen van meer ECI‑segmenten (verschillende talen of emoji’s).
* Het aanpassen van QR‑foutcorrectieniveaus voor hogere betrouwbaarheid.
* Het embedden van de gegenereerde PNG in PDF’s of webpagina’s.

Veel programmeerplezier, en geniet van het maken van meertalige QR-codes!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe QR-code afbeelding te genereren in Python met Aspose.Barcode – Volledige gids](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Code128 barcode genereren met Aspose.Barcode Python – Volledige gids](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [productnaam weergeven met Python barcode bibliotheek – stap‑voor‑stap gids](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}