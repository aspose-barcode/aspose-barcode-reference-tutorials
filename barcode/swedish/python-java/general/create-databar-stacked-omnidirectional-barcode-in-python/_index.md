---
category: general
date: 2026-07-30
description: Skapa Databar Stacked Omnidirectional streckkod i Python. Följ den här
  steg‑för‑steg‑guiden för att konfigurera bildförhållande, XDimension och exportera
  PNG med en python‑streckkodsgenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: sv
lastmod: 2026-07-30
og_description: Skapa Databar Stacked Omnidirectional streckkod i Python. Denna handledning
  visar hur du ställer in XDimension, justerar DataBar-aspektförhållandet och sparar
  som PNG med BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Skapa Databar staplad omnidirektionell streckkod – Python‑handledning
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Skapa staplad omnidirektionell Databar‑streckkod i Python
url: /sv/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Databar Stacked Omnidirectional streckkod i Python

Har du någonsin behövt **skapa databar stacked omnidirectional** streckkod i Python men varit osäker på var du ska börja? Du är inte ensam—många utvecklare stöter på samma problem när de först experimenterar med `BarcodeGenerator`-klassen. Den goda nyheten är att hela processen är ganska enkel när du förstår de viktigaste egenskaperna.

I den här guiden går vi igenom ett komplett, körbart exempel som använder en **python barcode generator** för att sätta XDimension, justera DataBar-aspektförhållandet och slutligen exportera två PNG‑filer. I slutet har du en solid förståelse för hur du genererar högkvalitativa stacked omnidirectional‑symboler för vilket lager‑ eller logistikprojekt som helst.

## Vad du kommer att lära dig

- Hur du instansierar en **databar stacked omnidirectional** generator med en GTIN‑14‑payload.  
- Varför **XDimension pixelstorlek** är viktig för skanningspålitlighet.  
- Påverkan av **DataBar-aspektförhållandet** på radbredd kontra höjd.  
- Hur du sparar resultatet som en **BarCodeImageFormat PNG**‑fil.  
- Tips för att återanvända samma generatorobjekt för att producera flera varianter utan extra minnesbelastning.

### Förutsättningar

- Python 3.8+ (biblioteket vi använder är ren‑Python, inga kompilerade wheels behövs).  
- Paketet `barcode-generator` (installera via `pip install barcode-generator`).  
- En mapp du kan skriva till – skriptet kommer att dumpa två PNG‑bilder där.

Om du är bekväm med grundläggande Python‑importer och objekt‑orienterad kod, är du redo att köra.

## Skapa Databar Stacked Omnidirectional streckkod – Stegöversikt

Nedan delar vi upp arbetsflödet i sex små steg. Varje steg är ett självständigt kodavsnitt som du kan kopiera‑klistra in i en REPL eller skriptfil. Känn dig fri att experimentera—att ändra aspektförhållandet eller XDimension ger dig omedelbart en annan visuell stil.

---

## Steg 1: Skapa Databar Stacked Omnidirectional generator

Det första vi gör är att **skapa databar stacked omnidirectional** generatorinstans, genom att skicka in rätt `EncodeTypes`‑enum och datasträngen.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Varför detta är viktigt:** Flaggan `EncodeTypes.DatabarStackedOmniDirectional` talar om för biblioteket att producera en stacked omnidirectional‑symbol, vilket är den enda DataBar‑varianten som kan koda upp till 14 siffror samtidigt som den är läsbar från alla vinklar.

---

## Konfigurera XDimension pixelstorlek

**XDimension pixelstorlek** styr den minsta modulen (den tunnaste svarta stapeln). Ett värde på `2` pixlar fungerar bra för de flesta skärm‑display‑scenarier.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Proffstips:** Om du planerar att skriva ut streckkoden i hög DPI, öka detta värde till 3 eller 4 för att undvika suddiga kanter.

---

## Justera DataBar-aspektförhållande (15)

**DataBar-aspektförhållandet** bestämmer hur bred varje rad är jämfört med dess höjd. Ett aspektförhållande på `15` ger bredare rader, vilket många skannrar föredrar för snabb rörelsespårning.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Varför 15?** Den officiella GS1‑specifikationen rekommenderar ett förhållande mellan 10 och 20 för stacked omnidirectional‑symboler. Vi väljer `15` som ett balanserat standardvärde.

---

## Exportera streckkod som PNG med BarCodeImageFormat

Nu när generatorn är konfigurerad sparar vi bilden. Enum‑värdet `BarCodeImageFormat.Png` säkerställer förlustfri output, perfekt för efterföljande bearbetning.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Vad du kommer att se:** Öppna den resulterande PNG‑filen; du bör märka en ren, högkontraststreckkod med relativt breda rader.

---

## Ändra DataBar-aspektförhållande till 30

Ibland behöver du högre rader istället för bredare—kanske för att passa en smal etikett. Att byta **DataBar-aspektförhållandet** till `30` gör varje rad högre.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** Mycket höga förhållanden (t.ex. >40) kan göra att streckkoden överskrider vanliga etikett‑höjder, så testa på en riktig skrivare innan du bestämmer dig.

---

## Exportera streckkod igen med nytt aspektförhållande

Slutligen återanvänder vi samma `barcode_generator`‑objekt för att skriva en andra PNG. Ingen anledning att skapa om generatorn—byt bara egenskapen och anropa `Save` igen.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Resultat:** Du har nu två PNG‑filer—en med breda rader (`AR15`) och en annan med höga rader (`AR30`). Jämför dem sida‑vid‑sida för att avgöra vilken som fungerar bäst för din skanner‑konfiguration.

---

## Fullt fungerande exempel

När allt sätts ihop, här är det kompletta skriptet du kan köra omedelbart. Ersätt `YOUR_DIRECTORY` med en absolut sökväg på din maskin.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Förväntad output** (i din konsol):

```
✅ Two PNG files created – AR15 and AR30
```

Och två bildfiler visas i mål‑mappen, redo för skannertester.

---

## Slutsats

Vi har just **skapat databar stacked omnidirectional** streckkoder i Python, justerat **XDimension pixelstorlek**, experimenterat med två olika **DataBar-aspektförhållande**‑inställningar, och exporterat resultaten som **BarCodeImageFormat PNG**‑filer. Hela arbetsflödet ryms i ett fåtal rader, men ger dig full kontroll över de visuella egenskaper som är viktigast för skannrar.

Vad blir nästa steg? Prova att byta payload till ett annat GTIN, lek med färger genom att konvertera PNG‑filen till en palett‑baserad bild, eller generera en PDF‑rapport som bäddar in båda PNG‑filerna sida‑vid‑sida. `BarcodeGenerator`‑klassen är tillräckligt flexibel för att hantera alla dessa scenarier, så känn dig fri att experimentera.

Har du frågor om ett specifikt användningsfall eller stöter på ett fel? Lämna en kommentar nedan, så hjälper jag gärna till. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkod bild – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}