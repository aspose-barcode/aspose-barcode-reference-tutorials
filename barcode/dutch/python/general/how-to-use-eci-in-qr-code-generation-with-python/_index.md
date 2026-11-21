---
category: general
date: 2026-11-20
description: Leer hoe je ECI gebruikt, QR-codes genereert uit tekst, de builder leegt
  en QR-afbeeldingen opslaat met de Python barcode‑bibliotheek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: nl
lastmod: 2026-11-20
og_description: Hoe ECI te gebruiken om QR te genereren vanuit tekst, de QR‑builder
  te wissen en de QR‑afbeelding op te slaan – een volledige stap‑voor‑stap‑handleiding.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Hoe ECI te gebruiken bij het genereren van QR‑codes met Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Hoe ECI te gebruiken in QR-codegeneratie met Python
url: /nl/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe ECI te gebruiken bij QR-codegeneratie met Python

Als je **hoe eci te gebruiken** bij het maken van QR-codes nodig hebt, laat deze gids de exacte stappen zien. Je zult zien hoe je QR vanuit tekst genereert, de builder leegt, en uiteindelijk de QR‑afbeelding opslaat — allemaal met een paar regels Python.

QR‑codes die meertalige gegevens bevatten, vereisen vaak een Extended Channel Interpretation (ECI)‑segment zodat scanners weten welke tekenset ze moeten toepassen. Deze tutorial leidt je door het bouwen van een uitgebreide codetext, het legen van de builder bij hergebruik, en het opslaan van het resultaat als een PNG‑bestand.

## Vereisten

- Python 3.8+ geïnstalleerd.
- Het Aspose.BarCode for Python via .NET‑pakket (of een compatibele `barcode`‑bibliotheek die `ExtCodetextBuilder` en `BarcodeGenerator` biedt).
- Basiskennis van QR‑codeconcepten.

Installeer de bibliotheek met pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Gebruik een virtuele omgeving om versieconflicten te vermijden.

## Stap 1: Importeer de vereiste klassen

De primaire klassen waarmee je werkt zijn `ExtCodetextBuilder` voor het construeren van uitgebreide codetext en `BarcodeGenerator` voor het renderen van de QR‑code.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Deze imports geven je toegang tot de builder‑methoden (`add_plain_codetext`, `add_eci_codetext`, etc.) en de generator‑functies `set_code_text`, `set_symbology` en `save`.

## Stap 2: Maak en configureer de ExtCodetextBuilder

Het aanmaken van een nieuw builder‑object is het eerste concrete voorbeeld van **hoe eci te gebruiken**. Je kunt de builder later ook leegmaken als je deze opnieuw wilt gebruiken.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Het aanroepen van `clear()` zorgt ervoor dat de builder met een schone staat begint, wat essentieel is bij het genereren van meerdere QR‑codes in een lus.

## Stap 3: Voeg platte (niet‑ECI) codetext toe

Platte tekst heeft geen ECI‑segment nodig. Gebruik `add_plain_codetext` voor ASCII‑compatibele strings.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

De builder bevat nu het platte segment `"HelloWorld"`.

## Stap 4: Voeg een ECI‑gecodeerd segment toe

Hier is de kern van **hoe eci te gebruiken**: je specificeert de ECI‑waarde (26 voor UTF‑8) en levert de Unicode‑string die je wilt coderen. Hierdoor kan de QR‑code Russisch, Chinees of een andere taal bevatten die niet door de standaard ISO‑8859‑1‑set wordt gedekt.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Waarom dit belangrijk is:** Zonder de ECI‑indicator zou een scanner de bytes interpreteren met de standaard tekenset en onleesbare tekens tonen voor niet‑ASCII‑tekst.

## Stap 5: Haal de gecombineerde uitgebreide codetext‑string op

Na het toevoegen van alle vereiste segmenten, haal je de uiteindelijke string op die aan de QR‑generator wordt doorgegeven.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

De afgedrukte waarde ziet er ongeveer zo uit:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Het exacte formaat hangt af van de bibliotheek, maar het belangrijke is dat de ECI‑marker (`[ECI26]`) voorafgaat aan de UTF‑8‑payload.

## Stap 6: Genereer de QR‑code met de gecombineerde tekst

Nu kun je **QR vanuit tekst genereren** door de uitgebreide codetext door te geven aan `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Wanneer je `qr_extended.png` opent, verschijnt er een QR‑code die zowel de platte Engelse string als de Russische groet codeert. Het scannen ervan met een moderne QR‑scanner toont correct “HelloWorld” en “Привет”.

### Waarom je `clear()` moet aanroepen voordat je de builder opnieuw gebruikt

Als je meerdere QR‑codes in een lus genereert, zal het vergeten om de builder te legen oude segmenten met nieuwe combineren, waardoor een ongeldige code ontstaat. Hier is een kort patroon:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Dit fragment illustreert **hoe de builder te legen** en **hoe QR vanuit tekst te genereren** herhaaldelijk.

## Randgevallen en veelvoorkomende valkuilen

| Situatie | Waar op te letten | Hoe te handelen |
|-----------|-------------------|-----------------|
| **Niet‑ondersteunde ECI‑waarde** | De bibliotheek gooit `InvalidArgumentException`. | Gebruik alleen ECI‑waarden die in de specificatie staan (bijv. 26 voor UTF‑8, 20 voor Shift‑JIS). |
| **Zeer lange gecombineerde tekst** | QR‑versie kan de maximale capaciteit overschrijden. | Verhoog de QR‑versie automatisch (`qr_generator.set_qr_version(QRVersion.AUTO)`) of splits de data over meerdere QR‑codes. |
| **Bestandssysteem‑toegangsrechten** | `save` faalt met `IOError`. | Zorg dat de doelmap bestaat en dat het proces schrijfrechten heeft. |
| **Onjuiste weergave van tekenset** | Scanner toont onleesbare tekens. | Controleer of de juiste ECI‑waarde overeenkomt met de feitelijke codering van de string. |

## Volledig uitvoerbaar voorbeeld

Hieronder staat een zelf‑containend script dat je kunt kopiëren, plakken en uitvoeren. Het bevat alle imports, foutafhandeling en commentaren voor duidelijkheid.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Het uitvoeren van dit script produceert `output/qr_extended.png`, een QR‑code die zowel Engelse als Russische tekst correct codeert.

## Conclusie

Je weet nu **hoe eci te gebruiken** bij het bouwen van QR‑codes, hoe je **de QR‑builder leegt** vóór hergebruik, hoe je **QR vanuit tekst genereert**, en de exacte stappen om **QR‑afbeelding op te slaan** met Python. Door het bovenstaande patroon te volgen, kun je elke Unicode‑string in een QR‑code embedden terwijl de builder‑status voorspelbaar blijft.

### Wat is het volgende?

- Verken andere ECI‑waarden voor talen zoals Chinees (ECI 20) of ISO‑8859‑5.  
- Pas fout‑correctieniveaus aan (`qr_generator.set_error_correction_level`) om de scan‑betrouwbaarheid te verbeteren.  
- Combineer meerdere ECI‑segmenten in één QR voor gemengde‑taalberichten.

Veel programmeerplezier, en geniet van het maken van meertalige QR‑codes!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode met ECI te genereren met Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Hoe QR‑code‑afbeelding te genereren in Python met Aspose.Barcode – Volledige gids](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Hoe een barcode te genereren in Python – volledige stapsgewijze gids](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}