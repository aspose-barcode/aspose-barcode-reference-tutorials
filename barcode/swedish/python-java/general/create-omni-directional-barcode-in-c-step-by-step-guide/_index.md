---
category: general
date: 2026-07-15
description: Skapa en omnidirektionell streckkod i C# snabbt med Aspose.BarCode –
  lär dig hur du genererar streckkod i C# med justerbar stapelhöjd och X‑dimension.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: sv
lastmod: 2026-07-15
og_description: Skapa en omni‑riktad streckkod i C# med Aspose.BarCode. Lär dig hur
  du genererar streckkod i C# genom att justera XDimension och BarHeight för perfekta
  resultat.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Skapa omnidirektionell streckkod i C# – Komplett programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Skapa en omnidirektionell streckkod i C# – Steg‑för‑steg‑guide
url: /sv/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa omni‑riktad streckkod i C# – Steg‑för‑steg‑guide

Har du någonsin undrat hur man genererar en streckkod i C# som följer GS1 DataBar Omni‑Directional‑symbologin? Du är inte ensam. I den här handledningen kommer vi att **skapa omni‑riktade streckkod**‑bilder från grunden, justera X‑dimensionen och leka med stapelhöjden – allt med Aspose.BarCode‑biblioteket.

Vi går igenom ett verkligt scenario: du behöver en kompakt, högdensitetsstreckkod för en detaljhandelsetikett och du vill ha total kontroll över dess visuella storlek. I slutet har du två PNG‑filer – en med 30 px stapelhöjd och en annan med 60 px – redo att användas i vilket utskriftsflöde som helst.

## Förutsättningar

- .NET 6 (eller någon nyare .NET‑runtime) installerad på din maskin.  
- Visual Studio 2022 eller VS Code – ditt föredragna IDE räcker.  
- Ett gratis Aspose.BarCode för .NET NuGet‑paket (`Aspose.BarCode`).

Inga andra beroenden krävs. Om du aldrig har rört NuGet förut, öppna bara Package Manager Console och kör:

```powershell
Install-Package Aspose.BarCode
```

## skapa omni‑riktad streckkod – Förstå grunderna

**GS1 DataBar Omni‑Directional**‑symbologin är utformad för avläsning i alla orienteringar, vilket gör den perfekt för hyllkantsetiketter. När du anropar `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` sköter biblioteket det tunga arbetet: det kodar data, tillämpar symbologireglerna och förbereder en rasterbild.

> **Proffstips:** Omslut alltid rådata i rätt Application Identifier (AI)‑format, t.ex. `"(01)12345678901231"` för en GTIN‑14. Detta talar om för skannern vad siffrorna representerar.

## Steg 1 – Ställ in Barcode‑generatorn (how to generate barcode c#)

Först skapar vi generator‑objektet. Detta är hörnstenen i **how to generate barcode c#** med Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional`‑enumvärdet talar om för motorn vilken symbologi som ska användas. Det andra argumentet är rådatasträngen, redan omsluten i GTIN‑AI.

## Steg 2 – Justera X‑dimensionen (barcode XDimension)

**barcode XDimension** styr bredden på den minsta stapeln. Ett värde på 2 px är en bra balans mellan läsbarhet och kompaktitet för de flesta etikettskrivare.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Om du behöver ett finare eller grövre utseende, ändra bara siffran. Kom ihåg: X‑dimensionen är den grundläggande enheten; alla andra stapelbredder är multipler av detta värde.

## Steg 3 – Skapa den första bilden med 30 px stapelhöjd (barcode BarHeight)

Nu sätter vi **barcode BarHeight** till 30 px och sparar bilden. Detta ger en måttligt stor streckkod som passar bra på en standardetikett.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save`‑metoden skriver en PNG‑fil till disk. Du kan byta till `BarCodeImageFormat.Jpeg` om du föredrar JPEG‑utdata.

## Steg 4 – Öka stapelhöjden till 60 px för större etiketter (barcode BarHeight)

Ibland krävs en större streckkod – kanske för en hylletikett som sitter längre från skannern. Låt oss dubbla höjden.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Observera att vi **inte** behöver återskapa generatorn; vi justerar bara parametern och återanvänder samma objekt. Detta sparar minne och håller koden prydlig.

## Steg 5 – Spara den andra bilden (how to generate barcode c#)

Till sist sparar vi den andra PNG‑filen. Du har nu två filer som bara skiljer sig åt i stapelhöjd.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Förväntad output

- `DatabarBarHeight30Pixels.png` – en 30 px hög omni‑riktad streckkod.  
- `DatabarBarHeight60Pixels.png` – samma data, men med en 60 px hög streckkod.

Öppna filerna i någon bildvisare; du kommer att se skarpa, avläsbara staplar som följer GS1 DataBar Omni‑Directional‑specifikationen.

## Vanliga frågor & kantfall

### Vad om jag behöver en annan X‑dimension?

Tilldela helt enkelt ett nytt värde innan du anropar `Save`. För ultra‑högdensitetsutskrift kan du gå ner till 1 px, men testa först med din scanner – vissa enheter har problem med staplar under 2 px.

### Kan jag lägga till mänskligt läsbar text under streckkoden?

Ja. Sätt `barcodeGenerator.Parameters.Barcode.CodeText` till en sträng och justera eventuellt `barcodeGenerator.Parameters.Barcode.CodeLocation` till `BarCodeTextLocation.Below`. Detta är praktiskt i detaljhandelsmiljöer där det numeriska GTIN‑värdet måste vara synligt.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Är PNG det bästa formatet för utskrift?

PNG är förlustfritt, vilket bevarar de skarpa kanterna som behövs för streckkodsläsare. Om ditt efterföljande system förväntar sig ett annat format (TIFF, BMP) byter du bara `BarCodeImageFormat`‑enum.

## Fullt fungerande exempel (create omni‑directional barcode)

Nedan är det kompletta, färdiga programmet. Kopiera och klistra in det i ett nytt konsolprojekt och tryck **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Kör programmet, kontrollera utdata‑mappen, och du kommer att se de två PNG‑filerna exakt som beskrivits.

## Sammanfattning

Vi har visat **how to generate barcode C#**‑kod som skapar en **create omni‑directional barcode** med Aspose.BarCode. Genom att justera **barcode XDimension** och **barcode BarHeight** får du finjusterad kontroll över den visuella storleken utan att kompromissa med avläsningssäkerheten.

## Vad blir nästa?

- Experimentera med andra **GS1 DataBar Omni‑Directional**‑inställningar som `Color` eller `Margin`.  
- Kombinera flera streckkoder på en enda canvas med `Graphics` för komplexa etikettdesigner.  
- Integrera generatorn i ett web‑API så att din e‑handelsplattform kan generera streckkoder på begäran.

Har du ett eget knep du vill dela? Lägg en kommentar, så fortsätter vi diskussionen. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man skapar tyst zon för ITF‑14‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hur man skapar tyst zon för Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}