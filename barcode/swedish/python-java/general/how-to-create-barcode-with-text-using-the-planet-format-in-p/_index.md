---
category: general
date: 2026-11-27
description: Lär dig hur du skapar en streckkod med text och genererar planet‑streckkod
  i Python — steg‑för‑steg‑guide för högupplöst PNG‑utdata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: sv
lastmod: 2026-11-27
og_description: Skapa streckkod med text och generera planetstreckkod i Python. Följ
  den här kompletta guiden för att skapa en högupplöst PNG.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Skapa streckkod med text i Python – generera Planet-streckkod enkelt
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Hur man skapar en streckkod med text med Planet‑formatet i Python
url: /sv/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod med text i Planet‑formatet i Python

Om du behöver **skapa streckkod med text** för ett postningssystem visar den här handledningen exakt hur du gör. Du får ett koncist, end‑to‑end‑exempel som genererar en Planet‑streckkod, justerar upplösningen och sparar resultatet som en PNG‑bild.

Att generera streckkoder är ett vanligt krav för logistik, lager och biljettsystem. I den här guiden lär du dig inte bara **hur man genererar streckkod**‑filer, utan också varför varje konfigurationssteg är viktigt och hur du undviker vanliga fallgropar.

## Vad du kommer att lära dig

* Ställa in Planet‑streckkodsgeneratorn med anpassad text.  
* Justera X‑dimensionen för att öka bildskärpan.  
* Spara streckkoden som en PNG‑fil som kan skrivas ut eller visas på webben.  
* Utöka exemplet till andra streckkodstyper eller utdataformat.

**Förutsättningar**

* Python 3.8 eller nyare.  
* `aspose-barcode`‑paketet (eller något kompatibelt bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`).  
* Grundläggande kunskap om Python‑skriptning.

Du kan installera det nödvändiga paketet med:

```bash
pip install aspose-barcode
```

---

## Steg 1: Skapa streckkod med text – initiera generatorn

Det första du måste göra är att skapa en `BarcodeGenerator`‑instans som vet vilken symbolik som ska användas och vilken text som ska kodas. För en Planet‑streckkod anger enum‑värdet `EncodeTypes.Planet` att biblioteket ska följa USPS Planet‑specifikationen.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Varför detta är viktigt:**  
`BarcodeGenerator`‑objektet kapslar in alla inställningar för streckkoden. Att ange texten redan vid konstruktionen garanterar att det kodade värdet är oföränderligt under resten av processen, vilket eliminerar oavsiktliga missmatchningar senare.

---

## Steg 2: Justera inställningar – hur man genererar streckkod med högre upplösning

En lågupplöst streckkod kan se suddig ut när den skrivs ut på en etikettprinter. X‑dimensionen (modulbredd) styr storleken på varje enskild stapel. Att sätta den till 4 pixlar ger en skarp, högupplöst bild som passar de flesta moderna skrivare.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Förklaring:**  
* `gen.parameters.barcode.x_dimension.pixels` motsvarar den fysiska bredden på en enskild modul.  
* Värdet **4** betyder att varje stapel är fyra pixlar bred, vilket ungefär motsvarar 0.127 mm vid 300 dpi – väl inom det rekommenderade intervallet för USPS Planet‑streckkoder.  

**Proffstips:** Om du behöver en annan DPI, beräkna pixelbredden därefter (t.ex. 2 pixlar för 150 dpi, 8 pixlar för 600 dpi).

---

## Steg 3: Spara bilden – generera planet‑streckkod som PNG

Nu när generatorn är konfigurerad kan du rendera streckkoden till en bildfil. PNG är förlustfri, vilket säkerställer att det exakta modulmönstret bevaras.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Resultat:**  
När skriptet körs skapas en fil med namnet `PostalPlanetBarHeightNone.png` som innehåller en Planet‑streckkod som kodar strängen “123456”. Bildens dimensioner blir ungefär 200 × 100 pixlar, beroende på den X‑dimension du valde.

---

## Valfritt: Verifiera streckkoden visuellt

Du kan snabbt öppna den genererade PNG‑filen i någon bildvisare för att bekräfta att streckkoden är skarp och den mänskligt läsbara texten finns under mönstret.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Om bilden ser oskarp ut, gå tillbaka till **Steg 2** och öka X‑dimensionen tills staplarna är tydligt definierade.

---

## Vanliga variationer och kantfall

| Situation | Justering |
|-----------|-----------|
| **Olika textlängd** | Planet‑streckkoder stödjer upp till 12 numeriska tecken. Överskrids detta, kastar biblioteket ett undantag. |
| **Alternativt utdataformat** | Byt `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp` för andra användningsfall. |
| **Anpassade förgrund-/bakgrundsfärger** | Använd `gen.parameters.barcode.barcode_color = Color.Blue` och `gen.parameters.barcode.back_color = Color.White`. |
| **Ingen mänskligt läsbar text** | Sätt `gen.parameters.barcode.hide_code_text = True` för att generera en streckkod utan text under. |
| **Batch‑generering** | Loopa över en lista med strängar, skapa en ny `BarcodeGenerator` för varje och spara dem med unika filnamn. |

Dessa variationer låter dig **generera planet‑streckkod**‑filer som passar ett brett spektrum av affärskrav.

---

## Fullt skript – redo att köra

Nedan finns det kompletta, självständiga skriptet som du kan kopiera, klistra in och köra. Det innehåller alla importeringar, felhantering och kommentarer.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Förklaring av skriptet**

* Funktionen `create_planet_barcode` kapslar in de tre kärnstegen, vilket gör koden återanvändbar.  
* Indatavalidering säkerställer att du följer Planet‑specifikationen (endast numeriskt, max 12 siffror).  
* Funktionen skapar automatiskt utdata‑mappen, så du behöver inte hantera kataloger manuellt.  
* Efter generering öppnar skriptet bilden med Pillow (`PIL`) för omedelbar verifiering.

---

## Slutsats

Du vet nu hur du **skapar streckkod med text** och **genererar planet‑streckkod**‑filer i Python. Guiden täckte initiering, upplösningsjustering och filutmatning, samt valfria anpassningar och vanliga kantfall.  

Från och med nu kan du:

* Byta `EncodeTypes.Planet` mot andra symboler (t.ex. `EncodeTypes.Code128`) för att återanvända samma mönster.  
* Integrera funktionen i en webbtjänst som returnerar streckkods‑bilder på begäran.  
* Experimentera med batch‑behandling för att producera tusentals streckkoder för massutskick.

Känn dig fri att anpassa skriptet efter ditt projekts behov och dela dina resultat i kommentarerna. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod i Python – komplett steg‑för‑steg guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Skapa streckkod PNG i Python – steg‑för‑steg guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Hur man skapar planet‑streckkod PNG med Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}