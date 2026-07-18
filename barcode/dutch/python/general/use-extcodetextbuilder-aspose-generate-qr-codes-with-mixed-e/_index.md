---
category: general
date: 2026-07-18
description: Gebruik extcodetextbuilder van Aspose om QR‑codes te maken die gewone
  ASCII‑ en UTF‑8‑Russische tekst combineren. Leer QR‑codegeneratie met Aspose.Barcode
  in Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: nl
lastmod: 2026-07-18
og_description: Gebruik extcodetextbuilder Aspose stelt je in staat om gewone en UTF‑8‑gecodeerde
  fragmenten te combineren in een QR‑code. Volg deze stapsgewijze handleiding voor
  Aspose.Barcode in Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: gebruik extcodetextbuilder aspose – Maak QR‑codes met gemengde ECI‑tekst
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Gebruik extcodetextbuilder aspose: Genereer QR-codes met gemengde ECI-tekst'
url: /nl/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – QR‑codes maken met gemengde ECI‑tekst

Heb je je ooit afgevraagd hoe je **extcodetextbuilder aspose** kunt gebruiken om zowel gewone Engelse als Cyrillische tekens in één QR‑code te embedden? Je bent niet de enige. Veel ontwikkelaars lopen tegen een muur wanneer ze ASCII‑ en non‑ASCII‑gegevens moeten combineren, vooral als de doel‑scanner correcte ECI‑markers (Extended Channel Interpretation) verwacht.  

In deze tutorial lopen we stap voor stap door hoe je een QR‑code maakt die “HELLO123” **en** het Russische woord “Привет” bevat, met de Python‑API van Aspose.Barcode. Aan het einde heb je een kant‑klaar script, begrijp je waarom elke aanroep belangrijk is, en weet je hoe je het proces kunt aanpassen voor andere talen of gegevensformaten.

## Wat je zult leren

- Hoe je **ExtCodetextBuilder** initialiseert en gewone plus ECI‑gecodeerde fragmenten toevoegt.  
- Waarom de **ECI‑codering**‑waarde `3` overeenkomt met UTF‑8 en hoe dat het scannen beïnvloedt.  
- De exacte volgorde om een **QR‑code generator** op te zetten met Aspose.Barcode.  
- Hoe je de resulterende afbeelding opslaat en de gemengde inhoud verifieert.  

**Prerequisites** – je hebt Python 3.8+ nodig, het `aspose-barcode`‑pakket geïnstalleerd (`pip install aspose-barcode`), en een map waarin je afbeeldingen kunt wegschrijven. Verder niets.

---

## use extcodetextbuilder aspose to build mixed codetext

Het eerste wat we nodig hebben is een `ExtCodetextBuilder`‑instantie. Beschouw het als een builder‑patroon dat verschillende stukjes tekst aan elkaar plakt terwijl automatisch de juiste ECI‑markers worden ingevoegd.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Waarom dit belangrijk is:**  
- `add_plain_codetext` houdt de gegevens onveranderd, wat perfect is voor cijfers of Engelse letters.  
- `add_eci_codetext` voegt een ECI‑segment (`[ECI:3]`) toe vóór de opgegeven string, waardoor elke conforme lezer weet dat de volgende bytes UTF‑8 zijn. Zonder dit zou de scanner de Cyrillische bytes als rommel interpreteren.

> **Pro tip:** Als je een andere tekenset nodig hebt, wijzig je de `eci_encoding`‑waarde volgens de ECI‑tabel (bijv. `26` voor ISO‑8859‑1).  

---

## Initialise QR Code generation with Aspose.Barcode

Nu we een correct geformatteerde `extended_codetext` hebben, kunnen we deze doorgeven aan de QR‑code generator. Aspose.Barcode abstraheert de low‑level QR‑matrixcreatie, zodat je je kunt concentreren op de data.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Wat gebeurt er hier?**  
- `BarcodeGenerator()` maakt een nieuw generator‑object aan met standaardinstellingen (grootte, resolutie, enz.).  
- `set_symbology` vertelt de engine dat we een QR‑code willen in plaats van bijvoorbeeld Code128.  

Als je een hoger foutcorrectieniveau nodig hebt, kun je `qr_generator.parameters.barcode.qr_error_level = ...` aanroepen vóór het toewijzen van de codetext.

---

## Assign the extended codetext to the QR generator

Met de generator klaar, is de volgende stap simpelweg het voeden van de gemengde string die we eerder hebben opgebouwd.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Waarom niet `set_codetext` gebruiken?**  
`set_codetext` behandelt de invoer als platte tekst en verwijdert eventuele ECI‑markers. `set_extended_codetext` behoudt de ruwe bytes, inclusief het ECI‑segment, zodat de scanner de juiste taalwissel ziet.

---

## Save the QR Code image and verify the result

Tot slot schrijven we de QR‑code naar schijf. Aspose.Barcode ondersteunt PNG, JPEG, BMP en meer; PNG is een veilige standaard omdat het verliesvrije data behoudt.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Je zou nu een PNG‑bestand moeten hebben op de opgegeven locatie. Open het met een QR‑scanner‑app die ECI ondersteunt (de meeste moderne smartphones doen dat). Scan één keer – je ziet “HELLO123”. Scan opnieuw (of gebruik een scanner die ruwe data toont) – je krijgt ook “Привет”. De twee delen verschijnen als één enkele payload, precies zoals we het hebben opgebouwd.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Afbeeldings‑alt‑tekst: use extcodetextbuilder aspose QR code example showing mixed ECI text*

---

## Full, Ready‑to‑Run Script

Alles bij elkaar, hier is het volledige programma dat je kunt kopiëren‑plakken in een bestand genaamd `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Voer het uit met:

```bash
python qr_mixed_eci.py
```

Je ziet een console‑bericht dat de opslaglocatie bevestigt, en de PNG verschijnt precies waar je hebt aangegeven.

---

## Common Questions & Edge Cases

### What if my scanner doesn’t recognize the Cyrillic part?
Zorg ervoor dat de scanner‑app ECI‑ondersteuning aangeeft. Oudere hardware kan het ECI‑segment negeren en de bytes behandelen als ISO‑8859‑1, wat resulteert in onleesbare tekens.

### Can I add more than two fragments?
Absoluut. Roep `add_plain_codetext` of `add_eci_codetext` zo vaak aan als je nodig hebt. De builder plakt ze in de volgorde waarin je de methoden aanroept.

### How do I change the QR Code size or foreground color?
Gebruik het object `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Is there a way to embed binary data (e.g., a small file) alongside text?
Ja. Gebruik `add_binary_codetext` met een byte‑array, en combineer dit met een passende ECI als de binary een specifieke tekenset vertegenwoordigt. De builder regelt de benodigde moduswisselingen.

---

## Conclusion

Je weet nu **hoe je extcodetextbuilder aspose** kunt gebruiken om QR‑codes te maken die naadloos gewone ASCII‑ en UTF‑8‑gecodeerde Russische tekst combineren. Door `ExtCodetextBuilder` te benutten, de juiste **ECI‑codering** in te stellen, en het resultaat in een **Aspose.Barcode QR‑code generator** te voeren, krijg je één standaard‑conforme afbeelding die werkt op moderne scanners.  

Vanaf hier kun je `eci_encoding=3` vervangen door andere taal‑identifiers, of experimenteren met extra gewone fragmenten om meertalige payloads te bouwen. Je kunt ook de `BarCodeImageFormat`‑opties verkennen om SVG of PDF te exporteren als je vector‑graphics nodig hebt.  

Happy coding, en laat gerust een reactie achter als je ergens vastloopt—jouw feedback helpt deze handleidingen nog beter te maken!

## What Should You Learn Next?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementaties in je eigen projecten te verkennen.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}