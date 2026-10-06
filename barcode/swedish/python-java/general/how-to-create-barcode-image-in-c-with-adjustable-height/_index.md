---
category: general
date: 2026-09-07
description: Lär dig hur du skapar streckkodsbilder i C# och justerar deras höjd,
  bredd och format för att snabbt generera streckkod‑PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: sv
lastmod: 2026-09-07
og_description: Skapa en streckkodsbild i C# och lär dig hur du ställer in streckkodens
  dimensioner, ändrar streckkodens höjd och genererar streckkod‑PNG‑filer för alla
  applikationer.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Skapa streckkodbild i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Hur man skapar en streckkodsbild i C# med justerbar höjd
url: /sv/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkodbild i C# med justerbar höjd

Om du behöver skapa streckkodbild i C# för ett kassasystem eller ett lagerhanteringssystem, visar den här guiden hela arbetsflödet. Du kommer att se hur du ställer in streckkodparametrar, ändrar streckkodens höjd och genererar streckkod‑PNG‑filer som uppfyller visuella krav.

Att generera en streckkodbild är en vanlig uppgift när man integrerar skanningsutrustning, skriver ut etiketter eller bygger rapporteringsdashboards. I slutet av den här handledningen har du ett återanvändbart kodsnutt som låter dig justera streckkodens X‑dimension, höjd och utdataformat utan att lämna din IDE.

## Förutsättningar

* .NET 6.0 (eller senare) installerat – koden kompileras med alla aktuella .NET SDK.
* En referens till **Aspose.BarCode**‑biblioteket (tillgängligt via NuGet `Aspose.BarCode`).
* Grundläggande kunskap om C#‑konsolapplikationer.

Dessa krav säkerställer att exemplet körs direkt på Windows, Linux eller macOS.

## Steg 1: Ställ in projektet och importera biblioteket

Skapa ett nytt konsolprojekt och lägg till streckkodspaketet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Öppna nu *Program.cs* och lägg till de nödvändiga `using`‑direktiven:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Dessa importeringar ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och bildformat‑enumar som behövs för att **skapa streckkodbild**‑filer.

## Steg 2: Initiera generatorn med önskad symbolik

Den första kodraden skapar en `BarcodeGenerator` som vet vilken streckkodstyp som ska kodas. I det här exemplet använder vi DataBar Omni‑Directional‑symboliken, men du kan ersätta `EncodeTypes.DatabarOmniDirectional` med någon annan typ som stöds av Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Strängen `"(01)12345678901231"` följer GS1 Application Identifier‑formatet, vilket många återförsäljare kräver. Att initiera generatorn är grunden för varje **hur man ställer in streckkod**‑operation som följer.

## Steg 3: Hur man ställer in streckkodsdimensioner – X‑dimension och höjd

### 3.1 Justera den smala stapelns bredd (X‑dimension)

X‑dimensionen styr tjockleken på den tunnaste stapeln. Ett värde på **2 pixlar** ger ett finare utseende, användbart när du behöver en kompakt etikett.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Ändra streckkodens höjd för visuell balans

Streckkodens höjd bestämmer hur hög streckkoden visas. Nedan visar vi två vanliga höjder—30 pixlar för en liten etikett och 60 pixlar för en större visuell. Detta demonstrerar **hur man justerar streckkod**‑höjd programatiskt.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Steg 4: Generera streckkod‑PNG‑filer med olika höjder

### 4.1 Spara den första bilden (30 px höjd)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Öka höjden och spara en andra bild

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Dessa två `Save`‑anrop illustrerar **generera streckkod PNG**‑filer med olika dimensioner samtidigt som samma generatorinstans återanvänds. Bildformatet är explicit satt till PNG, vilket bevarar förlustfri kvalitet—idealiskt för utskrift eller skärmvisning.

## Steg 5: Fullt, körbart exempel

När allt sätts ihop får du en enda `Main`‑metod som du kan kopiera in i vilket C#‑konsolprojekt som helst:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

När du kör detta program skapas två PNG‑filer i projektets utdata‑mapp:

* `DatabarBarHeight30Pixels.png` – en kompakt 30 px streckkod.
* `DatabarBarHeight60Pixels.png` – en större 60 px streckkod.

Båda filerna innehåller en **skapa streckkodbild** som kan bäddas in i HTML, skrivas ut på etiketter eller skickas till en mobilapp för skanning.

## Vanliga frågor och hantering av kantfall

| Fråga | Svar |
|-------|------|
| **Vad händer om jag behöver ett annat bildformat?** | Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`, `Bmp` eller `Gif`. Biblioteket hanterar konverteringen automatiskt. |
| **Kan jag ändra förgrunds-/bakgrundsfärger?** | Ja. Använd `generator.Parameters.Barcode.ForeColor` och `BackColor` för att sätta `System.Drawing.Color`‑värden innan du anropar `Save`. |
| **Hur genererar man en streckkod utan en fil på disk?** | Anropa `generator.GenerateBarCodeImage()` för att få ett `System.Drawing.Image`‑objekt, och strömma det sedan direkt till ett svar eller en databas. |
| **Vad händer om datasträngen överskrider symbolikens gräns?** | Generatorn kastar `ArgumentException`. Validera indata‑längden eller trunkera enligt symbolikens specifikation. |
| **Finns det ett sätt att batch‑processa flera streckkoder?** | Omge stegen i en `foreach`‑loop som uppdaterar `generator.CodeText` och `BarHeight` för varje objekt, och anropa sedan `Save` med ett unikt filnamn. |

Att hantera dessa scenarier gör handledningens **hur man justerar streckkod**‑logik robust för verkliga projekt.

## Proffstips för pålitlig streckkodsgenerering

* **Cacha generatorn** när du skapar många streckkoder av samma typ; återanvändning av objektet minskar allokeringskostnaden.
* **Ställ in `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) om du behöver högupplösta PNG‑filer för utskrift.
* **Validera GS1-data** innan du tilldelar den till `CodeText` för att undvika kodningsfel som kan leda till skanningsfel.
* **Testa på faktiska skannrar** efter att du ändrat höjd eller X‑dimension—vissa äldre enheter har minimikrav på storlek.

## Slutsats

Du vet nu hur man **skapar streckkodbild** i C#, **hur man ställer in streckkod**‑dimensioner, **hur man justerar streckkod**‑höjd, och **genererar streckkod PNG**‑filer för alla visuella krav. Genom att justera `XDimension` och `BarHeight` kan du producera kompakta eller stora streckkoder utan att ändra den underliggande datan.

Nästa steg, utforska relaterade ämnen såsom **ändra streckkodshöjd** dynamiskt baserat på användarinmatning, bädda in streckkoder i PDF‑rapporter med Aspose.PDF, eller växla till QR‑kodgenerering med `EncodeTypes.QR`. Experimentera med olika symboliker och utdataformat för att fullt behärska streckkodsskapande i C#.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Skapa GS1‑streckkods bilder i C# – Hur man snabbt genererar streckkod i C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hur man genererar streckkodbild i C# – MicroPdf417‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}