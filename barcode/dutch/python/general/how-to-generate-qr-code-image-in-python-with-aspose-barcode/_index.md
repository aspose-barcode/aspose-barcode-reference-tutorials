---
category: general
date: 2026-07-15
description: Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode. Leer
  stap‑voor‑stap QR‑code‑creatie met uitgebreide codetekst, ECI‑codering en Unicode‑ondersteuning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: nl
lastmod: 2026-07-15
og_description: Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode.
  Deze gids leidt je stap voor stap door het maken van QR‑codes met uitgebreide codetekst,
  ECI‑codering en Unicode‑tekens.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Hoe een QR-code-afbeelding te genereren in Python – Aspose.Barcode volledige
  tutorial
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Hoe een QR‑code afbeelding te genereren in Python met Aspose.Barcode – Volledige
  gids
url: /nl/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode – Volledige gids

Heb je je ooit afgevraagd **hoe je een QR‑code‑afbeelding** in Python kunt genereren zonder tientallen bibliotheken te moeten doorzoeken? Je bent niet de enige. Veel ontwikkelaars hebben een betrouwbare manier nodig om meertalige tekst—denk aan Russisch, Arabisch of emoji’s—in een QR‑code te embedden, en de ingebouwde bibliotheken schieten vaak tekort.

Het punt is: Aspose.Barcode voor Python maakt dit verrassend eenvoudig. In deze tutorial lopen we stap voor stap door het proces, van het installeren van het pakket tot het samenstellen van een uitgebreide codetext‑string die platte ASCII combineert met ECI‑gecodeerde Unicode. Aan het einde heb je een kant‑klaar QR‑code‑beeld op schijf.

## Wat deze gids behandelt

- Het installeren van **Aspose.Barcode** voor Python (compatibel met Python 3.8+)
- Het bouwen van een **uitgebreide codetext** die platte en Unicode‑segmenten combineert
- Het gebruik van **ECI‑codering** om Russische tekens correct weer te geven
- Het configureren van de `BarcodeGenerator` om een QR‑code te produceren
- Het opslaan van de uitvoerafbeelding in PNG‑formaat
- Tips, veelvoorkomende valkuilen en vervolgstappen (zoals logo’s toevoegen of foutcorrectie aanpassen)

Ervaring met Aspose is niet vereist; alleen een basis‑Python‑installatie en nieuwsgierigheid naar QR‑codes.

---

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

1. **Python 3.8 of nieuwer** geïnstalleerd op je machine.  
2. Een **virtuele omgeving** (optioneel maar aanbevolen) om afhankelijkheden netjes te houden.  
3. **pip**‑toegang om het `aspose-barcode`‑pakket te installeren.  
4. Schrijfrechten in een map waar de gegenereerde PNG wordt opgeslagen.

Als een van deze punten onbekend is, pauzeer dan hier en stel ze in—zodra ze klaar zijn, is de rest een eitje.

---

## Stap 1: Installeer Aspose.Barcode voor Python

De eerste hindernis is het verkrijgen van de bibliotheek. Aspose distribueert haar pakketten op PyPI, dus één `pip`‑commando doet het werk:

```bash
pip install aspose-barcode
```

> **Pro tip:** Als je binnen een virtuele omgeving werkt, houd je je globale site‑packages schoon. Als je permissiefouten krijgt, plaats dan `--user` vóór het commando of voer het uit met `sudo` (hoewel dat zelden nodig is op moderne systemen).

Na de installatie kun je dit verifiëren met:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Als de versie zonder klachten wordt weergegeven, ben je klaar om verder te gaan.

---

## Stap 2: Maak een **Extended Codetext Builder**‑instantie

Aspose.Barcode biedt de klasse `ExtCodetextBuilder` om complexe QR‑payloads samen te stellen. Beschouw het als een kleine teksteditor die de juiste controle‑karakters voor elk segment kan voorvoegen.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Waarom een builder gebruiken? Het direct samenvoegen van ruwe bytes is foutgevoelig; de builder garandeert de juiste ECI (Extended Channel Interpretation)‑schakelingen, zodat jouw QR‑scanner elke taal correct kan decoderen.

---

## Stap 3: Begin schoon (optioneel maar netjes)

Als je dezelfde builder‑instantie hergebruikt, wist `clear()` eventuele eerdere data. Het is een vangnet dat voorkomt dat oude segmenten in de volgende QR lekken.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Je kunt deze regel weglaten bij de eerste uitvoering van het script, maar het behouden maakt de code idempotent—handig wanneer je deze logica in een functie embedt die meerdere keren kan worden aangeroepen.

---

## Stap 4: Voeg een platte (niet‑gecodeerde) segment toe

De meeste QR‑codes beginnen met een eenvoudige ASCII‑string—bijvoorbeeld een identifier of een URL. De methode `add_plain_codetext` voegt precies dat toe, zonder ECI‑marker.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

In dit voorbeeld gebruiken we `"HelloWorld"` als placeholder. Vervang het door wat je nodig hebt—misschien een product‑SKU of een korte boodschap.

---

## Stap 5: Voeg een **ECI‑gecodeerd** segment toe (UTF‑8 = 26)

Nu het meertalige deel. De ECI‑waarde **26** correspondeert met UTF‑8, de de‑facto standaard voor Unicode. Door `26` samen met een Russische zin door te geven, vertellen we de QR‑scanner om over te schakelen naar UTF‑8 vóór het lezen van de volgende tekens.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Je kunt `26` vervangen door andere ECI‑waarden (bijv. `27` voor ISO‑8859‑1) als je een andere codering nodig hebt. De builder voegt automatisch de juiste controle‑karakters in.

---

## Stap 6: Haal de gecombineerde Extended Codetext op

Zodra alle segmenten zijn toegevoegd, haal je de uiteindelijke string op die de QR‑generator zal gebruiken. Deze string bevat onzichtbare controle‑sequenties, maar je kunt hem nog steeds afdrukken voor debugging.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

De console‑output zal er rommelig uitzien (vanwege de ingebedde controle‑bytes), wat volkomen normaal is. Het belangrijke is dat de builder de platte en Unicode‑delen correct aan elkaar heeft geplakt.

---

## Stap 7: Configureer de Barcode Generator

Nu geven we de uitgebreide codetext door aan Aspose’s `BarcodeGenerator`. Stel de symbologie in op `QR` en wijs de gecombineerde string toe aan `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Je kunt hier extra eigenschappen aanpassen—zoals `resolution`, `error_correction_level` of `foreground_color`. Die opties staan beschreven in de Aspose‑documentatie, maar voor een basisafbeelding werken de standaardinstellingen prima.

---

## Stap 8: Sla de gegenereerde QR‑code‑afbeelding op

Tot slot schrijven we de QR‑code naar schijf. De `save`‑methode accepteert een pad en een optioneel formaat; PNG is een veilige standaard.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Open de resulterende `qr_extended.png` met een willekeurige beeldviewer. Scannen met een smartphone zou twee afzonderlijke berichten moeten tonen: “HelloWorld” en “Привет”. De meeste moderne QR‑readers verwerken de ECI‑schakel automatisch.

---

## Volledig werkend voorbeeld

Alles bij elkaar, hier is het complete script dat je kunt kopiëren‑plakken en uitvoeren:

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Verwachte output** (console):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Open `qr_extended.png` → scan → je ziet “HelloWorld” gevolgd door “Привет”.

---

## Veelgestelde vragen & randgevallen

### 1. *Wat als ik meer dan twee segmenten nodig heb?*  
Roep simpelweg `add_plain_codetext` of `add_eci_codetext` zo vaak aan als je wilt. De builder behoudt de juiste volgorde, zodat de QR‑code elk segment in de door jou opgegeven volgorde bevat.

### 2. *Kan ik emoji’s embedden?*  
Ja—emoji’s zijn gewoon Unicode‑tekens. Gebruik de UTF‑8‑ECI (waarde 26) en geef de emoji‑string door, bv. `builder.add_eci_codetext(26, "🚀")`. De QR toont de raket‑emoji op scanners die dit ondersteunen.

### 3. *Wat als de QR te dicht wordt?*  
QR‑codes hebben versie‑limieten. Als je de data‑capaciteit overschrijdt, zal Aspose automatisch de versie verhogen naar een grotere grootte, maar de afbeelding kan dan groter worden. Om de grootte te beheersen, kun je het fout‑correctieniveau verlagen:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Moet ik me zorgen maken over andere character sets dan UTF‑8?*  
Alleen als je legacy‑systemen hebt die een specifieke codering vereisen (bijv. ISO‑8859‑1). In dat geval vervang je `26` door de juiste ECI‑waarde (zie Aspose’s ECI‑tabel). Voor de meeste moderne apps is UTF‑8 de veiligste keuze.

### 5. *Hoe voeg ik een logo toe in het midden?*  
Aspose.Barcode ondersteunt `barcode.generator.QRCodeParameters.logo_image`. Laad een afbeelding met Pillow (`from PIL import Image`) en wijs deze toe:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

Het logo wordt over de QR gelegd terwijl de scanbaarheid behouden blijft (Aspose past automatisch de quiet zones aan).

---

## Pro‑tips voor productie

- **Cache de builder** als je dezelfde QR herhaaldelijk genereert; dit voorkomt het telkens opnieuw opbouwen van de uitgebreide string.  
- **Valideer de output** met een unit‑test die de QR decodeert (bijv. met `zxing` of `pyzbar`) om te controleren of je ECI‑schakelingen correct zijn.  
- **Gebruik een deterministische bestandsnaam** (bijvoorbeeld een hash van de payload) om overschrijven van bestaande afbeeldingen te voorkomen.  
- **Let op licenties**: Aspose.Barcode is commerciële software. De gratis evaluatie werkt voor ontwikkeling, maar een licentie is vereist voor productie‑implementaties.

---

## Volgende stappen & gerelateerde onderwerpen

Nu je **weet hoe je een QR‑code genereert**


## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementaties in je eigen projecten te verkennen.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}