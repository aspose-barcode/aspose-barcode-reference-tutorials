---
category: general
date: 2026-10-15
description: Skapa streckkod från en sträng med Aspose.Barcode för Python. Lär dig
  hur du genererar streckkod, ställer in dimensioner och sparar som PNG på några minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: sv
lastmod: 2026-10-15
og_description: Skapa streckkod från sträng med Aspose.Barcode för Python. Denna handledning
  visar dig steg för steg hur du genererar en poststreckkod och sparar den som PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Skapa streckkod från en sträng i Python – Aspose guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Hur man skapar en streckkod från en sträng i Python med Aspose
url: /sv/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod från sträng i Python med Aspose

Om du snabbt behöver **skapa streckkod från sträng**, gör Aspose.Barcode för Python det enkelt. I den här guiden kommer du att se exakt **hur man genererar streckkod**‑bilder, justerar X‑dimensionen och sparar resultatet som en PNG‑fil — allt med bara några rader kod.

Du får också ett komplett **exempel på streckkodsgenerator** som du kan kopiera och klistra in i ditt eget projekt. Inga externa skript eller komplex konfiguration krävs, och handledningen fungerar med den aktuella Aspose.Barcode 23.10‑utgåvan.

## Förutsättningar

- Python 3.8+ installerat på din maskin  
- En aktiv Aspose.Barcode för Python‑licens (gratis provversion fungerar för utvärdering)  
- `pip install aspose-barcode` körd i din virtuella miljö  

Dessa komponenter säkerställer att koden körs utan importfel.

## Skapa streckkod från sträng med Aspose.Barcode (Python)

Det första steget är att instansiera `BarcodeGenerator` med önskad symbologi — i detta fall **Planet**‑poststreckkoden — och den sträng du vill koda.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Varför detta är viktigt:**  
`EncodeTypes.Planet` talar om för Aspose att använda Planet‑postsymbologi, som är avsedd för postsortering i många länder. Det andra argumentet (`"123456"`) är den råa strängen som kommer att kodas till streckkoden. Genom att ändra detta värde kan du **skapa streckkod från sträng** för vilken postkod eller spårningsnummer du än behöver.

## Hur man genererar streckkod med anpassade dimensioner

En poststreckkods modulbredd (X‑dimensionen) måste ofta matcha utskriftsspecifikationer. Aspose låter dig ange bredden i pixlar samtidigt som höjden beräknas automatiskt.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Varför du kan vilja justera detta:**  
En större X‑dimension gör staplarna tjockare, vilket kan förbättra skanningspålitligheten på lågupplösta skrivare. Omvänt minskar ett mindre värde bildstorleken för webbbruk. Denna rad visar **hur man genererar streckkod**‑bilder som uppfyller exakta storlekskrav.

## Spara streckkodsbilden

Efter att ha konfigurerat generatorn anropar du helt enkelt `save`. Metoden accepterar sökvägen för utdata och det bildformat du önskar.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Vad du får:**  
En PNG‑fil med namnet `PostalPlanetAuto.png` som innehåller Planet‑streckkoden som kodar `"123456"`. Du kan öppna filen i någon bildvisare för att verifiera resultatet.

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="Skärmdump av en genererad poststreckkod sparad som PNG"}

## Fullständigt exempel på streckkodsgenerator

Nedan är det kompletta, färdiga skriptet som inkluderar alla stegen ovan. Kopiera det till en fil som heter `generate_postal_barcode.py` och kör `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Förväntat resultat

När skriptet körs får du:

```
Barcode saved to PostalPlanetAuto.png
```

…och skapar en fil `PostalPlanetAuto.png` som ser ut så här:

![Generated Planet barcode](barcode_example.png){.align-center alt="Genererad Planet-streckkod sparad som PNG"}

## Vanliga variationer och kantfall

| Situation | Vad som ska ändras | Varför |
|-----------|--------------------|--------|
| **Olika symbologi** (t.ex. Code128) | Byt `EncodeTypes.Planet` mot `EncodeTypes.Code128` | Gör det möjligt att **generera streckkod** för lageretiketter, inte bara postkoder. |
| **Längre datasträngar** | Säkerställ att den valda symbologin stödjer längden; för Planet måste du hålla 6 siffror. | Förhindrar körningsfel `ValueError`. |
| **Högre upplösning** | Öka `x_dimension.pixels` till 6 eller 8. | Skapar tjockare staplar för hög‑DPI‑utskrift. |
| **Andra bildformat** | Använd `BarCodeImageFormat.JPEG` eller `BarCodeImageFormat.GIF`. | Användbart när PNG inte är lämpligt för ditt arbetsflöde. |
| **Kör i en webbtjänst** | Byt ut filsystemets `save`‑anrop mot en `BytesIO`‑ström och returnera bytes. | Möjliggör generering av streckkod i farten i Flask eller Django. |

**Proffstips:** Validera alltid inmatningssträngen innan du anropar `BarcodeGenerator`. Ogiltiga data (fel längd, icke‑numeriska tecken för Planet) kommer att kasta ett undantag och bryta din applikation.

## Hur man genererar streckkod i en Flask‑endpoint (valfritt nästa steg)

Om du vill exponera **exemplet på streckkodsgeneratorn** som ett REST‑API kan du omsluta funktionen `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Detta kodsnutt visar hur man **genererar streckkod** på begäran utan att skriva till disk, vilket är praktiskt för mikrotjänster.

## Slutsats

Du vet nu hur du **skapar streckkod från sträng** i Python med Aspose.Barcode, hur du **genererar streckkod** med anpassade dimensioner och hur du **sparar** resultatet som en PNG‑fil. Det kompletta **exemplet på streckkodsgeneratorn** innehåller inmatningsvalidering, felhantering och en återanvändbar funktion som du kan integrera i större applikationer.

Nästa steg är att utforska andra symbologier (`EncodeTypes.Code128`, `EncodeTypes.QR`) eller bädda in generatorn i ett webb‑ramverk som Flask eller Django. Båda stegen kommer att fördjupa din förståelse för **aspose barcode python**‑biblioteket och utöka de sätt du kan **generera poststreckkod**‑bilder för verkliga projekt.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod i Python – komplett steg‑för‑steg‑guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Skapa streckkod PNG i Python – Fullständig Aspose.Barcode‑guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Hur man genererar streckkod med ECI med Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}