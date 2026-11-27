---
category: general
date: 2026-11-27
description: Leer hoe je een barcode met tekst maakt en een planet‑barcode genereert
  in Python—stap‑voor‑stap gids voor high‑resolution PNG‑uitvoer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: nl
lastmod: 2026-11-27
og_description: Maak een barcode met tekst en genereer een planeetbarcode in Python.
  Volg deze complete gids om een PNG met hoge resolutie te maken.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Maak een barcode met tekst in Python – genereer eenvoudig een Planet-barcode
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
title: Hoe een barcode met tekst te maken met het Planet‑formaat in Python
url: /nl/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode met tekst te maken met het Planet‑formaat in Python

Als je een **barcode met tekst** moet maken voor een mailsysteem, laat deze tutorial je precies zien hoe je dat doet. Je ziet een beknopt, end‑to‑end voorbeeld dat een Planet‑barcode genereert, de resolutie aanpast en het resultaat opslaat als een PNG‑afbeelding.

Barcodes genereren is een veelvoorkomende eis voor logistiek, voorraadbeheer en ticket‑toepassingen. In deze gids leer je niet alleen **hoe je barcode‑bestanden genereert**, maar ook waarom elke configuratiestap belangrijk is en hoe je typische valkuilen kunt vermijden.

## Wat je zult leren

* De Planet‑barcode‑generator instellen met aangepaste tekst.  
* De X‑dimensie aanpassen om de beeldscherpte te verhogen.  
* De barcode opslaan als een PNG‑bestand dat kan worden afgedrukt of op het web kan worden weergegeven.  
* Het voorbeeld uitbreiden naar andere barcode‑typen of uitvoerformaten.

**Prerequisites**

* Python 3.8 of nieuwer.  
* Het `aspose-barcode`‑pakket (of een andere compatibele bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` biedt).  
* Basiskennis van Python‑scripting.

Je kunt het vereiste pakket installeren met:

```bash
pip install aspose-barcode
```

---

## Stap 1: Barcode met tekst maken – initialiseert de generator

Het eerste wat je moet doen is een `BarcodeGenerator`‑instantie maken die weet welke symbologie te gebruiken en welke tekst te coderen. Voor een Planet‑barcode geeft de enum‑waarde `EncodeTypes.Planet` de bibliotheek de opdracht de USPS Planet‑specificatie te volgen.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Waarom dit belangrijk is:**  
Het `BarcodeGenerator`‑object omvat alle instellingen voor de barcode. De tekst al bij de constructie doorgeven garandeert dat de gecodeerde waarde onveranderlijk blijft gedurende de rest van het proces, waardoor onbedoelde mismatches later worden voorkomen.

---

## Stap 2: Instellingen aanpassen – hoe een barcode met hogere resolutie te genereren

Een barcode met lage resolutie kan er wazig uitzien wanneer deze op een labelprinter wordt afgedrukt. De X‑dimensie (module‑breedte) bepaalt de grootte van elke individuele balk. Instellen op 4 pixels levert een scherp, high‑resolution‑beeld op dat geschikt is voor de meeste moderne printers.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Uitleg:**  
* `gen.parameters.barcode.x_dimension.pixels` map direct naar de fysieke breedte van één module.  
* Een waarde van **4** betekent dat elke balk vier pixels breed is, wat ongeveer overeenkomt met 0,127 mm bij 300 dpi — binnen het aanbevolen bereik voor USPS Planet‑barcodes.  

**Pro tip:** Als je een andere DPI nodig hebt, bereken dan de pixelbreedte dienovereenkomstig (bijv. 2 pixels voor 150 dpi, 8 pixels voor 600 dpi).

---

## Stap 3: De afbeelding opslaan – planet‑barcode genereren als PNG

Nu de generator is geconfigureerd, kun je de barcode renderen naar een afbeeldingsbestand. PNG is loss‑less, waardoor het exacte module‑patroon behouden blijft.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Resultaat:**  
Het uitvoeren van het script maakt een bestand genaamd `PostalPlanetBarHeightNone.png` aan dat een Planet‑barcode bevat met de string “123456”. De afbeeldingsafmetingen zullen ongeveer 200 × 100 pixels zijn, afhankelijk van de X‑dimensie die je hebt gekozen.

---

## Optioneel: De barcode visueel verifiëren

Je kunt de gegenereerde PNG snel openen met elke beeldviewer om te bevestigen dat de barcode scherp is en de mens‑leesbare tekst onder het patroon aanwezig is.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Als de afbeelding wazig lijkt, ga dan terug naar **Stap 2** en verhoog de X‑dimensie totdat de balken duidelijk gedefinieerd zijn.

---

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing |
|-----------|------------|
| **Andere tekstlengte** | Planet‑barcodes ondersteunen maximaal 12 numerieke tekens. Als je dit overschrijdt, zal de bibliotheek een uitzondering werpen. |
| **Alternatief uitvoerformaat** | Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp` voor andere use‑cases. |
| **Aangepaste voor‑/achtergrondkleuren** | Gebruik `gen.parameters.barcode.barcode_color = Color.Blue` en `gen.parameters.barcode.back_color = Color.White`. |
| **Geen mens‑leesbare tekst** | Stel `gen.parameters.barcode.hide_code_text = True` in om een barcode zonder ondertitel te genereren. |
| **Batch‑generatie** | Loop over een lijst met strings, maak voor elk een nieuwe `BarcodeGenerator` en sla ze op onder unieke bestandsnamen. |

Deze variaties laten je **planet‑barcode**‑bestanden genereren die passen bij een breed scala aan zakelijke eisen.

---

## Volledig script – klaar om uit te voeren

Hieronder vind je het complete, zelfstandige script dat je kunt kopiëren, plakken en uitvoeren. Het bevat alle imports, foutafhandeling en commentaar.

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

**Uitleg van het script**

* De functie `create_planet_barcode` omvat de drie kernstappen, waardoor de code herbruikbaar is.  
* Invoervalidatie zorgt ervoor dat je de Planet‑specificatie volgt (alleen numeriek, max 12 cijfers).  
* De functie maakt de output‑map automatisch aan, zodat je geen mappen handmatig hoeft te beheren.  
* Na generatie opent het script de afbeelding met Pillow (`PIL`) voor directe verificatie.

---

## Conclusie

Je weet nu hoe je **barcode met tekst** kunt **maken** en **planet‑barcode**‑bestanden kunt genereren in Python. De gids behandelde initialisatie, resolutie‑afstemming en bestandsoutput, plus optionele aanpassingen en veelvoorkomende randgevallen.  

Vanaf hier kun je:

* `EncodeTypes.Planet` vervangen door andere symbologieën (bijv. `EncodeTypes.Code128`) om hetzelfde patroon te hergebruiken.  
* De functie integreren in een webservice die barcode‑afbeeldingen op aanvraag retourneert.  
* Experimenteren met batch‑verwerking om duizenden barcodes voor bulk‑mailing te produceren.

Voel je vrij het script aan te passen aan de behoeften van je project en deel je resultaten in de reacties. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}