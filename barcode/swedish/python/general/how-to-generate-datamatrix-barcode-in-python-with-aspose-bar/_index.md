---
category: general
date: 2026-08-22
description: Lär dig att generera DataMatrix‑streckkod i Python och koda rysk text
  med Aspose.BarCode – steg‑för‑steg‑guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: sv
lastmod: 2026-08-22
og_description: Generera DataMatrix-streckkod i Python och koda rysk text med Aspose.BarCode.
  Följ hela exemplet och kör det omedelbart.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Generera DataMatrix-streckkod i Python – komplett Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Hur man genererar DataMatrix‑streckkod i Python med Aspose.BarCode
url: /sv/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du DataMatrix-streckkod i Python med Aspose.BarCode

Om du behöver **generera DataMatrix-streckkod** i Python samtidigt som du **kodar rysk text**, visar den här guiden de exakta stegen. Du får se ett komplett, körbart exempel som bygger en utökad kodtext, konfigurerar streckkoden och sparar bilden i ett enda skript.

Att skapa streckkoder som innehåller icke‑ASCII‑tecken väcker ofta frågor om teckenuppsättningar och data‑kodning. Genom att använda Aspose.BarCode:s `ExtCodetextBuilder` kan du säkert bädda in UTF‑8‑text, såsom kyrilliska tecken, i en DataMatrix‑symbol. Resultatet fungerar med alla skannrar som stöder DataMatrix‑standarden.

I den här handledningen kommer du att:

* Installera det erforderliga Aspose.BarCode‑paketet.  
* Bygga en utökad kodtext som blandar vanlig data och rysk text.  
* **Generera DataMatrix-streckkod** med den utökade strängen.  
* Justera streckkodens parametrar som modulstorlek.  
* Spara streckkoden som en PNG‑fil.

Inga externa tjänster krävs; allt körs lokalt på din maskin.

## Förutsättningar

Innan du börjar, se till att du har:

* Python 3.8 eller nyare installerat.  
* En aktiv Aspose.BarCode‑licens för Python (en gratis provlicens fungerar för utveckling).  
* Grundläggande kunskap om Python‑skriptning.

Du kan installera Aspose.BarCode‑biblioteket via pip:

```bash
pip install aspose-barcode
```

## Steg 1: Bygg en utökad kodtextsträng

Den första uppgiften är att skapa en enda sträng som innehåller både den enkla produktidentifieraren och den ryska frasen. `ExtCodetextBuilder` låter dig concatenera olika kodtextdelar samtidigt som deras kodningsinformation bevaras.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Varför detta steg är viktigt** – DataMatrix‑symboler lagrar råa byte. När du behöver blanda alfabet måste du tala om för kodaren vilken teckenuppsättning som gäller för varje segment. Metoden `add_eci_codetext` sätter in en ECI‑indikator före den ryska texten, vilket säkerställer att skannrar tolkar bytena som UTF‑8. Utan ECI skulle de kyrilliska tecknen visas som förvrängd data.

## Steg 2: Skapa en DataMatrix‑streckkodsgenerator

När den utökade kodtexten är klar, instansiera en `BarcodeGenerator` och ange typen `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Varför DataMatrix?** – DataMatrix är en tvådimensionell streckkod som kan lagra upp till 2 335 alfanumeriska tecken eller 1 556 byte. Den är idealisk för små föremål, industriella delar och situationer där du behöver bädda in flerspråkig text.

## Steg 3: (Valfritt) Konfigurera streckkodens parametrar

Aspose.BarCode exponerar många parametrar. För de flesta användningsfall ger standardinställningarna en läsbar symbol. Du kan dock vilja kontrollera storleken på varje modul (den minsta kvadraten i matrisen) för att matcha utskriftskraven.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Andra användbara parametrar inkluderar felkorrigeringsnivå, marginal och bakgrundsfärg. Justera dem endast om din mål‑scannermiljö kräver specifika toleranser.

## Steg 4: Spara streckkodsbilden

Skriv slutligen streckkoden till en fil. Metoden `save` stöder PNG, JPEG, BMP och flera vektorformat.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

När du öppnar `extended_codetext.png` ser du en skarp DataMatrix‑symbol. Att skanna den med en standard‑DataMatrix‑läsare returnerar de två delarna:

1. **ABC123** – den enkla identifieraren.  
2. **Привет** – den ryska hälsningen, korrekt avkodad som UTF‑8.

## Fullt, körbart exempel

Nedan är hela skriptet som du kan kopiera‑och‑klistra in i en fil med namnet `generate_datamatrix.py`. Ersätt `YOUR_DIRECTORY` med en befintlig mapp på ditt system.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Kör skriptet från kommandoraden:

```bash
python generate_datamatrix.py
```

Du bör se konsolutdata liknande:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Verifiera resultatet

För att bekräfta att streckkoden korrekt kodar den ryska frasen:

1. Öppna PNG‑filen i en bildvisare.  
2. Använd någon DataMatrix‑skanningsapp (många mobilappar stödjer det) eller en hårdvaruskanner.  
3. Den avkodade strängen bör visa `ABC123Привет` (eller de två delarna separerade beroende på skannarens UI).

Om de ryska tecknen visas som nonsens, dubbelkolla att skannern stödjer ECI UTF‑8. De flesta moderna läsare gör det, men äldre enheter kan behöva explicit konfiguration.

## Vanliga fallgropar och hur du undviker dem

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Förvrängd kyrillisk utskrift | Saknad ECI‑indikator | Använd `add_eci_codetext` med `eci_encoding=3`. |
| Streckkod för liten för skrivare | Standardmodulstorlek för fin för låg DPI | Öka `x_dimension` (t.ex. `3.0` eller `4.0`). |
| Filen sparas inte | Ogiltig sökväg till katalog | Säkerställ att `YOUR_DIRECTORY` finns och är skrivbar. |
| Skannern kan inte läsa | Överdriven datatäthet | Minska mängden kodad data eller öka felkorrigeringsnivån (`generator.parameters.barcode.error_correction_level`). |

## Utöka exemplet

Du kan anpassa detta mönster för andra språk eller datatyper:

* **Koda japansk eller arabisk text** – ändra `eci_encoding` till lämpligt värde (t.ex. 5 för ISO‑8859‑5, 6 för ISO‑8859‑7).  
* **Lägg till flera ECI‑segment** – anropa `add_eci_codetext` flera gånger, varje med sin egen kodning.  
* **Skapa en QR‑kod istället** – ersätt `EncodeTypes.DATA_MATRIX` med `EncodeTypes.QR`.  

Alla andra steg förblir identiska eftersom `ExtCodetextBuilder` abstraherar den lågnivå‑byte‑hanteringen.

## Slutsats

Du vet nu hur du **genererar DataMatrix‑streckkod** i Python och **kodar rysk text** med Aspose.BarCode:s utökade kodtextfunktion. Det kompletta skriptet hanterar teckenuppsättnings‑förhandling, streckkodsskapande och bildutmatning med bara några rader kod.

Nästa steg är att utforska andra streckkodssymboler (PDF417, Aztec) eller integrera generatorn i en webbtjänst som returnerar PNG‑bilder på begäran. Samma principer – att bygga en utökad kodtext och välja rätt `EncodeTypes` – gäller för hela Aspose.BarCode‑sviten.

Lycka till med kodningen, och njut av kraften i flerspråkig streckkodsgenerering!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix-streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generera en DataMatrix-streckkod i ASCII‑läge med Aspose.BarCode för .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Hur man genererar DataMatrix-streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}