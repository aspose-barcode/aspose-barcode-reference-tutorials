---
category: general
date: 2026-08-12
description: Skapa omnidirektionell databar med Python och lär dig hur du skapar streckkodsbild
  i Python med Aspose.BarCode. Följ steg‑för‑steg‑guiden för en komplett lösning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: sv
lastmod: 2026-08-12
og_description: Skapa en omnidirektionell databar med Python och generera en streckkodbild
  i Python på några minuter. Den här handledningen visar ett komplett, körbart exempel.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Skapa omnidirektionell databar – fullständig Python‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Skapa en omnidirektionell databar- och streckkodbild i Python
url: /sv/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa omnidirektionell databar och streckkodbild i Python

Om du behöver **skapa omnidirektionell databar** i ett Python‑projekt, visar den här guiden hur du gör det och även hur du **skapar streckkodbild i Python** med Aspose.BarCode‑biblioteket. Du får ett färdigt skript som genererar två PNG‑filer med olika bildförhållanden.

Att generera en DataBar som följer den omnidirektionella specifikationen är ett vanligt krav för detaljhandels‑ och logistikapplikationer. Handledningen täcker installation, konfiguration av X‑dimensionen, justering av bildförhållandet och sparande av de slutliga bilderna. Inga externa tjänster krävs; allt körs lokalt.

## Vad du behöver

* Python 3.8 eller nyare installerat på din maskin.
* Tillgång till en terminal eller kommandoprompt.
* Skrivrättighet till en mapp där streckkodbilderna ska sparas.

Den enda tredjepartsberoendet är **Aspose.BarCode for Python via .NET**, som stöder den omnidirektionella DataBar‑typen direkt ur lådan.

## Steg 1: Installera Aspose.BarCode för Python

Aspose.BarCode tillhandahåller klassen `BarcodeGenerator` som används i exempel‑koden. Installera paketet med `pip`:

```bash
pip install aspose-barcode
```

Paketet innehåller de nödvändiga .NET‑runtime‑bindningarna, så du behöver inte installera .NET‑SDK separat.

## Steg 2: Importera biblioteket och skapa generatorn

Den första raden i skriptet skapar en generator för en staplad omnidirektionell DataBar. GTIN‑14‑värdet `(01)12345678901231` används som exempeldata.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Varför detta steg är viktigt*: Konstanten `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` talar om för biblioteket att koda värdet som en omnidirektionell DataBar, vilket är det format som många kassascannrar kräver.

## Steg 3: Ställ in X‑dimensionen (modulbredd)

X‑dimensionen definierar bredden på den minsta stapelmodulen. Ett värde på `2` pixlar ger en tydlig, läsbar streckkod utan onödig filstorlek.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Varför detta steg är viktigt*: Genom att justera X‑dimensionen kan du balansera läsbarhet och bildstorlek. En X‑dimension som är för liten kan återges dåligt på lågupplösta skrivare.

## Steg 4: Konfigurera bildförhållandet och spara den första bilden

Bildförhållandet påverkar DataBarens totala höjd i förhållande till dess bredd. Ett bildförhållande på `15` skapar en kompakt visuell stil.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Proffstips**: Använd `pathlib.Path` för att bygga utdata‑sökvägen, vilket automatiskt skapar saknade kataloger.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Steg 5: Ändra bildförhållandet för en andra visuell stil och spara en annan bild

Att byta bildförhållandet till `30` ger en högre streckkod som kan krävas av specifik scanner‑hardware.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Varför detta steg är viktigt*: Olika återförsäljare och scanningsenheter har olika storleksbegränsningar. Genom att erbjuda båda bildförhållandena i ett enda skript kan du generera exakt den stil du behöver utan att duplicera kod.

## Fullt skript – skapa omnidirektionell databar och streckkodbild i Python

Nedan är det kompletta, körbara exemplet som inkluderar alla tidigare steg. Spara det som `generate_databar.py` och kör det med `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Förväntat resultat

När skriptet körs skapas följande filer:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Båda bilderna visar en giltig omnidirektionell DataBar som kan skannas av standardutrustning i detaljhandeln.

![exempel på skapa omnidirektionell databar streckkodbild i Python](example_databar.png "skapa omnidirektionell databar streckkodbild i Python")

*Bilden ovan är en platshållare som illustrerar de två sparade PNG‑filerna.*

## Hantera vanliga problem

| Problem | Orsak | Lösning |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode är inte installerat eller installerat i en annan miljö. | Aktivera rätt virtuell miljö och kör `pip install aspose-barcode`. |
| `PermissionError` när du sparar | Skriptet saknar skrivrättighet till mål‑mappen. | Välj en katalog du har rättigheter till eller kör skriptet med lämpliga privilegier. |
| Streckkoden skannas inte | X‑dimensionen är för låg eller bildförhållandet är inkompatibelt med scannern. | Öka `x_dimension.pixels` till 3 eller 4, och testa olika `aspect_ratio`‑värden (t.ex. 20, 25). |
| Saknad .NET‑runtime | Aspose.BarCode är beroende av .NET‑runtime på Windows/Linux. | Installera den senaste .NET‑runtime från Microsofts webbplats; paketdokumentationen ger plattforms‑specifik vägledning. |

## Utöka exemplet

Du kan anpassa skriptet för att generera andra DataBar‑varianter (t.ex. `DATABAR_STACKED`, `DATABAR_EXPANDED`). Byt ut `EncodeTypes`‑konstanten därefter:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Om du behöver bädda in streckkoden i en PDF, kan Aspose.PDF for Python importera PNG‑filen direkt eller så kan du använda `save`‑metoden med `BarCodeImageFormat.Pdf`.

## Slutsats

Denna handledning visade hur man **skapar omnidirektionell databar** och hur man **skapar streckkodbild i Python** med Aspose.BarCode. Du har nu ett komplett, reproducerbart skript som genererar två PNG‑filer med olika bildförhållanden, hanterar vanliga fallgropar och kan utökas till andra streckkodformat.

Nästa steg är att utforska generering av QR‑koder, lägga till streckkoden i PDF‑fakturor eller automatisera batch‑behandling för stora produktkataloger. Varje ämne bygger på samma `BarcodeGenerator`‑mönster som demonstrerats här. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkodbild – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Skapa DotCode streckkodbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hur man skapar streckkodbild och renderar den i Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}