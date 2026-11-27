---
category: general
date: 2026-11-27
description: Lär dig hur du justerar stapelhöjden i en DataBar Omni‑Directional streckkodsgenerator.
  Steg‑för‑steg‑kod visar hur du ställer in höjderna till 30 px och 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: sv
lastmod: 2026-11-27
og_description: Justera stapelhöjden för streckkoden i en DataBar Omni‑Directional
  streckkodsgenerator med Python. Följ den kompletta guiden för att ställa in höjder,
  X‑dimension och spara PNG‑bilder.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Justera stapelhöjden i DataBar Omni‑Directional‑generatorn
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Hur man justerar stapelhöjden på streckkoden i DataBar Omni‑Directional‑generatorn
url: /sv/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man justerar stapelhöjden för streckkoden i DataBar Omni‑Directional generator

Om du behöver **justera stapelhöjden för streckkoden** för en DataBar Omni‑Directional streckkod, visar den här guiden exakt hur du gör. Du får se ett komplett, körbart Python‑exempel som ändrar stapelhöjden från 30 px till 60 px samtidigt som X‑dimensionen och bildformatet förblir oförändrade.

Att ändra en streckkods visuella dimensioner är ett vanligt krav när streckkoden måste passa en specifik etikettstorlek eller designriktlinje. Förutom stapelhöjd kan du också vilja justera **X‑dimensionen** (modulstorlek) eller välja ett annat **streckkod bildformat** såsom PNG eller JPEG.

I den här handledningen kommer du att:

* Installera det nödvändiga biblioteket (GroupDocs.Barcode för Python)
* Skapa en DataBar Omni‑Directional streckkodsgenerator
* Ställ in modulstorleken med `XDimension`
* Justera stapelhöjdsegenskapen två gånger
* Spara de resulterande bilderna i önskat **BarCodeImageFormat**

Ingen tidigare erfarenhet av GroupDocs API krävs—bara grundläggande kunskaper i Python.

## Förutsättningar

Innan du börjar, se till att du har:

* Python 3.8 eller nyare installerat
* `groupdocs.barcode`‑paketet (`pip install groupdocs-barcode`)  
* Skrivrättighet till en mapp där PNG‑filerna kommer att sparas

Om du inte är bekant med **DataBar Omni‑Directional streckkod**, kodar den ett 14‑siffrigt GTIN och används i stor utsträckning inom detaljhandeln för avläsning från vilken orientering som helst.

## Steg 1: Ställ in DataBar Omni‑Directional streckkodsgeneratorn

Först importerar du de nödvändiga klasserna och skapar en instans av generatorn med GTIN‑data som du vill koda.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Varför detta är viktigt:* Konstanten `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket att producera Omni‑Directional‑symbologin. Datat strängen innehåller AI `(01)` som markerar ett GTIN‑14‑värde.

## Steg 2: Definiera X‑dimensionen (modulstorlek)

X‑dimensionen styr bredden på den smalaste stapeln. Ett vanligt värde för rendering på skärm är **2 px per modul**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Att använda en konsekvent **set XDimension** säkerställer att streckkoden skalar korrekt över olika skrivare och skannrar.

## Steg 3: Justera stapelhöjden till 30 px och spara bilden

Nu ändrar vi stapelhöjdsegenskapen. Den första höjden vi använder är **30 px**, vilket är lämpligt för små etiketter.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png`‑konstanten väljer **streckkod bildformat** PNG, vilket bevarar förlustfri kvalitet.

### Förväntat resultat

Filen `DatabarBarHeight30Pixels.png` innehåller en DataBar Omni‑Directional streckkod vars staplar är 30 px höga. Nedan är en platshållar‑förhandsvisning:

![DataBar streckkod med 30 px stapelhöjd](images/databar_30px.png "DataBar streckkod med 30 px stapelhöjd")

> **Tips:** Om du öppnar PNG‑filen i en bildredigerare kommer du att se den exakta stapelhöjden. De smala staplarna är 2 px breda, som definierat tidigare.

## Steg 4: Ändra stapelhöjden till 60 px för en högre streckkod

För applikationer som kräver ett större visuellt avtryck—t.ex. en fraktetikett—kan du öka stapelhöjden till **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Endast `BarHeight`‑egenskapen ändras; X‑dimensionen och kodningen förblir desamma, så streckkoden förblir läsbar.

## Steg 5: Spara den uppdaterade streckkodsbilden

Slutligen skriver du den högre streckkoden till en andra PNG‑fil.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Förväntat resultat

Filen `DatabarBarHeight60Pixels.png` visar samma data kodade, men varje stapel är nu 60 px hög. Den visuella skillnaden illustreras nedan:

![DataBar streckkod med 60 px stapelhöjd](images/databar_60px.png "DataBar streckkod med 60 px stapelhöjd")

## Fullständigt, körbart exempel

När allt sätts ihop, här är det kompletta skriptet som du kan kopiera‑klistra in i en fil med namnet `adjust_barcode_height.py` och köra direkt.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Kör skriptet:

```bash
python adjust_barcode_height.py
```

Du bör se två PNG‑filer i mappen `output`, där varje fil återspeglar den stapelhöjd du angav.

## Vanliga frågor och kantfall

| Fråga | Svar |
|----------|--------|
| **Kan jag använda JPEG istället för PNG?** | Ja. Ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`. JPEG är förlustkomprimerat, så föredra PNG för exakt avläsning. |
| **Vad händer om jag behöver en stapelhöjd som inte är en multipel av 10?** | `BarHeight.Pixels`‑egenskapen accepterar vilket heltal som helst. Tilldela bara önskat pixelantal (t.ex. `45`). |
| **Påverkar ändring av stapelhöjden den kodade datan?** | Nej. Endast den visuella representationen förändras; den underliggande datasträngen förblir identisk. |
| **Hur ändrar jag X‑dimensionen efter att ha sparat den första bilden?** | Du kan ändra `gen.parameters.barcode.x_dimension.pixels` när som helst innan du anropar `save()`. Ändringen kommer att gälla för efterföljande bilder. |
| **Är generatorn trådsäker?** | `BarcodeGenerator`‑instansen är inte garanterat trådsäker. Skapa en separat instans per tråd om du genererar streckkoder samtidigt. |

## Slutsats

Du vet nu hur du **justerar stapelhöjden för streckkoden** i en DataBar Omni‑Directional streckkodsgenerator med Python. Handledningen täckte att skapa generatorn, sätta **X‑dimensionen**, ändra **stapelhöjd**‑egenskapen och spara bilder i önskat **streckkod bildformat**.

Härifrån kan du experimentera med andra höjder, olika modulstorlekar, eller byta till alternativa bildformat såsom JPEG eller BMP. Du kan också utforska ytterligare **barcode generator python**‑funktioner som att lägga till mänskligt läsbar text eller ändra färgscheman.

Lycka till med kodningen, och håll dina streckkoder skarpa och perfekt dimensionerade!

## Vad bör du lära dig härnäst?

Följande handledningar täcker nära besläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man ställer in bredd och justerar höjd för en GS1 DataBar Omni‑Directional streckkod](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Skapa omni‑directional databar och streckkodsbild i Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net streckkodsgenerator – ändra streckkodshöjd](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}