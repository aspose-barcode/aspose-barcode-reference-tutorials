---
category: general
date: 2026-07-18
description: använd ExtCodeTextBuilder Aspose för att skapa QR‑koder som kombinerar
  vanlig ASCII och UTF‑8 rysk text. Lär dig Aspose.Barcode QR‑kodgenerering i Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: sv
lastmod: 2026-07-18
og_description: Använd extcodetextbuilder i Aspose för att blanda vanliga och UTF‑8‑kodade
  fragment i en QR‑kod. Följ den här steg‑för‑steg‑guiden för Aspose.Barcode i Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: använd extcodetextbuilder aspose – Skapa QR‑koder med blandad ECI‑text
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
title: 'använd extcodetextbuilder aspose: Generera QR‑koder med blandad ECI‑text'
url: /sv/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# använd extcodetextbuilder aspose – Bygg QR‑koder med blandad ECI‑text

Har du någonsin undrat hur man **använd extcodetextbuilder aspose** för att bädda in både vanlig engelsk och kyrillisk text i en enda QR‑kod? Du är inte ensam. Många utvecklare stöter på problem när de måste blanda ASCII‑ och icke‑ASCII‑data, särskilt när den avsedda scannern förväntar sig korrekta ECI‑markörer (Extended Channel Interpretation).

I den här handledningen går vi igenom de exakta stegen för att skapa en QR‑kod som innehåller “HELLO123” **och** det ryska ordet “Привет”, allt med Aspose.Barcode’s Python‑API. När du är klar har du ett färdigt skript, förstår varför varje anrop är viktigt, och vet hur du kan justera processen för andra språk eller dataformat.

## Vad du kommer att lära dig

- Hur man **initialize ExtCodetextBuilder** och lägger till vanliga samt ECI‑kodade fragment.  
- Varför **ECI‑kodning**‑värdet `3` motsvarar UTF‑8 och hur det påverkar avläsning.  
- Den exakta sekvensen för att konfigurera en **QR Code generator** med Aspose.Barcode.  
- Hur man sparar den resulterande bilden och verifierar den blandade innehållet.  

**Förutsättningar** – du behöver Python 3.8+, paketet `aspose-barcode` installerat (`pip install aspose-barcode`), och en mapp du kan skriva bilder till. Inget mer.

---

## använd extcodetextbuilder aspose för att bygga blandad kodtext

Det första vi behöver är en `ExtCodetextBuilder`‑instans. Tänk på den som ett builder‑mönster som sammanfogar olika textbitar samtidigt som den automatiskt sätter in rätt ECI‑markörer bakom kulisserna.

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

**Varför detta är viktigt:**  
- `add_plain_codetext` behåller data som den är, vilket är perfekt för siffror eller engelska bokstäver.  
- `add_eci_codetext` sätter in ett ECI‑segment (`[ECI:3]`) före den angivna strängen och talar om för alla kompatibla läsare att följande byte är UTF‑8. Utan detta skulle scannern tolka de kyrilliska bytena som skräp.

> **Pro tip:** Om du behöver ett annat teckensätt, ändra `eci_encoding`‑värdet enligt ECI‑tabellen (t.ex. `26` för ISO‑8859‑1).  

---

## Initiera QR‑kodsgenerering med Aspose.Barcode

Nu när vi har en korrekt formaterad `extended_codetext` kan vi överlämna den till QR‑kodsgeneratorn. Aspose.Barcode abstraherar bort den lågnivå‑QR‑matris‑skapandet så att du kan fokusera på datan.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Vad händer här?**  
- `BarcodeGenerator()` skapar ett nytt generator‑objekt med standardinställningar (storlek, upplösning osv.).  
- `set_symbology` talar om för motorn att vi vill ha en QR‑kod snarare än t.ex. Code128.  

Om du behöver en högre felkorrigeringsnivå kan du anropa `qr_generator.parameters.barcode.qr_error_level = ...` innan du tilldelar kodtexten.

---

## Tilldela den utökade kodtexten till QR‑generatorn

Med generatorn klar är nästa steg helt enkelt att mata in den blandade strängen vi byggde tidigare.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Varför inte använda `set_codetext`?**  
`set_codetext` behandlar indata som vanlig text och tar bort eventuella ECI‑markörer. `set_extended_codetext` bevarar de råa bytena, inklusive ECI‑segmentet, så att scannern ser rätt språkbyte.

---

## Spara QR‑kodbilden och verifiera resultatet

Till sist skriver vi QR‑koden till disk. Aspose.Barcode stödjer PNG, JPEG, BMP och fler; PNG är ett säkert standardval eftersom det bevarar förlustfri data.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Du bör nu ha en PNG‑fil på den angivna platsen. Öppna den med någon QR‑scanner‑app som stödjer ECI (de flesta moderna smartphones gör det). Skanna en gång – du ser “HELLO123”. Skanna igen (eller använd en scanner som visar rådata) – du får även “Привет”. De två delarna visas som en enda payload, exakt som vi byggde den.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: exempel på QR‑kod med extcodetextbuilder aspose som visar blandad ECI‑text*

---

## Fullt, körklart skript

Sätter vi ihop allt får du det kompletta programmet som du kan kopiera‑klistra in i en fil med namnet `qr_mixed_eci.py`:

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

Kör det med:

```bash
python qr_mixed_eci.py
```

Du får ett konsolmeddelande som bekräftar sparplatsen, och PNG‑filen dyker upp precis där du angav.

---

## Vanliga frågor och specialfall

### Vad händer om min scanner inte känner igen den kyrilliska delen?
Se till att scanner‑appen annonserar ECI‑stöd. Äldre hårdvara kan ignorera ECI‑segmentet och behandla bytena som ISO‑8859‑1, vilket ger förvrängda tecken.

### Kan jag lägga till mer än två fragment?
Absolut. Anropa `add_plain_codetext` eller `add_eci_codetext` så många gånger du behöver. Buildern kommer att sammanfoga dem i den ordning du anropar metoderna.

### Hur ändrar jag QR‑kodens storlek eller förgrundsfärg?
Använd `qr_generator.parameters`‑objektet:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Finns det ett sätt att bädda in binär data (t.ex. en liten fil) tillsammans med text?
Ja. Använd `add_binary_codetext` med en byte‑array och kombinera den med en lämplig ECI om den binära datan representerar ett specifikt teckensätt. Buildern hanterar de nödvändiga lägesbytena.

---

## Slutsats

Du vet nu **hur du använder extcodetextbuilder aspose** för att skapa QR‑koder som sömlöst blandar vanlig ASCII‑text och UTF‑8‑kodad rysk text. Genom att utnyttja `ExtCodetextBuilder`, sätta rätt **ECI‑kodning** och mata in resultatet i en **Aspose.Barcode QR‑kodsgenerator**, får du en enda, standard‑kompatibel bild som fungerar på moderna scannrar.  

Från och med nu kan du prova att byta `eci_encoding=3` mot andra språkidentifierare, eller experimentera med ytterligare vanliga fragment för att bygga flerspråkiga payloads. Du kan också utforska `BarCodeImageFormat`‑alternativen för att exportera SVG eller PDF om du behöver vektorgrafik.  

Lycka till med kodningen, och känn dig fri att lämna en kommentar om du stöter på problem – din feedback hjälper till att göra dessa guider ännu bättre!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [Generera streckkod Java – Ställ in kodtext med Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Skapa streckkod aspose .net – Konfigurera DataMatrix kodtext](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec kodtextkodning med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}