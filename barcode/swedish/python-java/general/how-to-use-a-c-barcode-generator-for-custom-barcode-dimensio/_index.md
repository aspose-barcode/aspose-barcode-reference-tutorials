---
category: general
date: 2026-08-22
description: Lär dig hur en C#-streckkodsgenerator kan ändra streckkodens storlek,
  justera dimensioner och generera flera rader i en DataBar Expanded Stacked‑streckkod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: sv
lastmod: 2026-08-22
og_description: C#-tutorial för streckkodsgenerator som visar hur man ändrar streckkodsstorlek,
  justerar dimensioner och genererar streckkoder i flera rader med anpassade inställningar.
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: C#-streckkodsgeneratorguide – ändra storlek, rader och kolumner
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man använder en C#-streckkodsgenerator för anpassade streckkodsdimensioner
url: /sv/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder en C# streckkodsgenerator för anpassade streckkodsdimensioner

Om du behöver en **c# barcode generator** som låter dig **change barcode size** i realtid, visar den här guiden exakt hur. Vi kommer att generera en DataBar Expanded Stacked streckkod, justera dess bredd och höjd genom att ange anpassade kolumner och rader, och spara tre exempelbilder.

Du avslutar tutorialen med ett komplett, körbart konsolprogram som demonstrerar **custom barcode dimensions**, **generate barcode multiple rows**, och **adjust barcode dimensions** utan att lämna IDE:n.

## Vad du behöver

| Förutsättning | Varför det är viktigt |
|---------------|-----------------------|
| .NET 6.0 SDK eller senare | Tillhandahåller runtime för konsolappen |
| Visual Studio 2022 (eller VS Code) | Ger dig en editor med IntelliSense |
| Aspose.Barcode for .NET NuGet-paket | Tillhandahåller `BarcodeGenerator`-klassen som används i exemplen |
| Skrivbehörighet till en mapp på disken | Generatorn sparar PNG-filer till den här platsen |

Installera biblioteket med NuGet CLI:

```bash
dotnet add package Aspose.Barcode
```

Eller använd Visual Studio Package Manager:

```powershell
Install-Package Aspose.Barcode
```

## Steg 1: Ställ in en grundläggande C# streckkodsgenerator

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`-direktiven. Detta steg skapar en minimal **c# barcode generator** som kan generera en enkel DataBar Expanded Stacked streckkod.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**Varför detta fungerar:** `EncodeTypes.DatabarExpandedStacked` talar om för generatorn vilken symbolik som ska användas. `Save`-metoden skriver en PNG-fil till disk. Vid detta tillfälle använder streckkoden bibliotekets standardstorlek.

## Steg 2: Ändra streckkodens storlek genom att justera kolumner

Bredden på en DataBar Expanded Stacked streckkod styrs av egenskapen **columns**. Genom att sätta denna egenskap låter du **c# barcode generator** producera en bredare eller smalare streckkod.

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**Förklaring:** Kolumner påverkar det horisontella modulantalet. Fler kolumner innebär en bredare streckkod, vilket är användbart när du behöver extra utrymme för längre mänskligt läsbar text eller vid utskrift på breda etiketter.

## Steg 3: Generera streckkod med flera rader för att kontrollera höjden

Höjden styrs av egenskapen **rows**. Genom att öka raderna **generate barcode multiple rows** och gör symbolen högre — idealiskt för högupplösta skanningar.

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**Varför rader är viktiga:** Rader lägger till vertikala moduler. En högre streckkod kan förbättra läsbarheten på lågkontrastbakgrunder eller när skannerns fokuseringsavstånd varierar.

## Steg 4: Kombinera anpassade kolumner och rader för full kontroll

Nu när du vet hur du **adjust barcode dimensions**, kan du sätta båda egenskaperna tillsammans. Detta steg skapar en streckkod med sex kolumner och tio rader, vilket demonstrerar den fulla flexibiliteten hos **c# barcode generator**.

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**Resultat:** Filen `DatabarCols6Rows10.png` innehåller en streckkod som både är bredare och högre än standardinställningarna, vilket bevisar att du kan **adjust barcode dimensions** för att uppfylla alla layoutkrav.

## Komplett körbart exempel

Nedan är hela programmet som inkluderar alla fyra stegen. Kopiera det till `Program.cs`, kör `dotnet run`, och kontrollera mappen `C:\Temp\Barcodes\` för fyra PNG-filer.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### Förväntat resultat

Att köra programmet producerar fyra PNG-filer:

| Filnamn                | Visuell beskrivning |
|------------------------|---------------------|
| `DefaultDatabar.png`   | Standardbredd & -höjd |
| `DatabarCols4.png`     | Bredare streckkod (4 kolumner) |
| `DatabarRows3.png`     | Högre streckkod (3 rader) |
| `DatabarCols6Rows10.png` | Både bredare och högre (6 kolumner, 10 rader) |

Öppna någon PNG i en bildvisare; du kommer att se DataBar Expanded Stacked-mönstret justerat exakt som specificerat.

## Vanliga fallgropar och proffstips

- **Invalid column/row values** – Biblioteket kastar `ArgumentException` om du sätter ett värde utanför det stödjade intervallet (1‑12 för kolumner, 1‑10 för rader). Validera indata innan du tilldelar.
- **Directory permissions** – Om målmappen är skyddad kommer `Save` att misslyckas. Använd `System.IO.Directory.CreateDirectory` som visas för att säkerställa att sökvägen finns.
- **Performance** – Att skapa många streckkoder i en loop kan vara CPU‑intensivt. Återanvänd samma `BarcodeGenerator`-instans och ändra bara `Columns`/`Rows` mellan sparningar för att minska minnesallokeringskostnaden.
- **Scanning considerations** – Extremt höga eller breda streckkoder kan överskrida skannerns synfält. Testa med din målmaskinvara efter att du justerat dimensionerna.

## Slutsats

Du har nu ett gediget **c# barcode generator**-exempel som kan **change barcode size**, **custom barcode dimensions**, **generate barcode multiple rows**, och **adjust barcode dimensions** för att passa vilken applikation som helst. Genom att justera egenskaperna `Columns` och `Rows` får du exakt kontroll över den visuella fotavtrycket av en DataBar Expanded Stacked streckkod.

Känn dig fri att experimentera med andra symboler (`EncodeTypes.QR`, `EncodeTypes.Code128`) eller utdataformat (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`). Samma mönster — skapa en `BarcodeGenerator`, sätt dimensionsegenskaper, och anropa sedan `Save` — gäller för hela Aspose.Barcode API.

**Nästa steg**

- Utforska **error correction levels** för QR-koder.
- Kombinera **custom colors** och **background images** för att varumärka dina streckkoder.
- Integrera generatorn i en ASP.NET Core-webbtjänst för on‑demand streckkodsskapande.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hur man justerar streckkodsstorlek – Codablock F bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Hur man genererar Aztec-streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}