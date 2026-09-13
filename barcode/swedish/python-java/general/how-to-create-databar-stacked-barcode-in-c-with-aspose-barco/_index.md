---
category: general
date: 2026-09-13
description: Skapa staplad databar-kod i C# snabbt med Aspose.Barcode – lär dig att
  ställa in kolumner, rader och spara bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: sv
lastmod: 2026-09-13
og_description: Skapa staplad databar-kod i C# med Aspose.Barcode. Denna guide visar
  hur du konfigurerar kolumner, rader och exporterar PNG‑bilder.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Skapa en Databar Stacked‑streckkod i C# – Fullständig steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Hur man skapar staplad databar‑streckkod i C# med Aspose.Barcode
url: /sv/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar databar staplad streckkod i C# med Aspose.Barcode

Om du behöver **skapa databar staplad streckkod** i en .NET‑applikation, ger den här guiden dig en komplett, färdig‑att‑köra‑lösning. Du kommer att se exakt hur du konfigurerar antalet kolumner, justerar rader och sparar resultatet som en PNG‑fil — allt med Aspose.Barcode för .NET‑biblioteket.

Att generera en **Databar Expanded Stacked**‑streckkod är ingen gåta när du förstår det trestegs‑arbetsflödet: skapa generatorn, ställ in önskade dimensioner och skriv bilden till disk. Följande avsnitt guidar dig genom varje del, förklarar varför inställningarna är viktiga och visar dig det slutgiltiga resultatet som du kan verifiera omedelbart.

## Förutsättningar

Innan du börjar, se till att du har:

- **Visual Studio 2022** (eller någon annan C#‑IDE) med .NET 6+ installerat.
- **Aspose.Barcode for .NET** NuGet‑paket (`Install-Package Aspose.Barcode`).
- Skrivrättigheter till en mapp där PNG‑filerna ska sparas.

Inga ytterligare beroenden krävs.

## Steg 1: Ställ in projektet och lägg till Aspose.Barcode

1. Skapa ett nytt Console App‑projekt:

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Lägg till Aspose.Barcode‑paketet:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Öppna **Program.cs** och lägg till de nödvändiga `using`‑satserna:

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Dessa steg säkerställer att **C# barcode generator**‑klasserna är tillgängliga i din kod.

## Steg 2: Skapa en generator för en Databar staplad streckkod

Det första objektet du behöver är en `BarcodeGenerator` konfigurerad för **Databar Expanded Stacked**‑symbologi. Detta objekt är ingångspunkten för alla streckkod‑relaterade operationer.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Varför detta är viktigt:**  
`EncodeTypes.DatabarExpandedStacked` talar om för Aspose.Barcode att använda den staplade versionen av DataBar‑familjen, vilket är idealiskt för begränsade höjdområden som kvitton. Det andra argumentet förser streckkoden med den data som ska kodas; du kan ersätta det med vilken numerisk eller alfanumerisk sträng som helst som följer DataBar‑standarden.

## Steg 3: Konfigurera streckkodskolumner och spara bilden

En staplad DataBar kan visas med ett konfigurerbart antal **kolumner**. Standardvärdet är tre, men du kan behöva fyra kolumner för längre datasträngar. Justera `Columns`‑egenskapen innan du sparar.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Förklaring:**  
- `Parameters.Barcode.DataBar.Columns` påverkar direkt den horisontella segmenteringen av streckkoden. Fler kolumner ger en bredare bild men behåller samma höjd.  
- `Save` skriver streckkoden till en PNG‑fil. Andra format (JPEG, BMP, SVG) stöds också genom att ange ett annat `BarCodeImageFormat`‑värde.

## Steg 4: Skapa en annan generator och konfigurera streckkodsrader

Ibland kräver skanningsmiljön en högre streckkod, vilket du uppnår genom att öka antalet **rader**. Följande kodsnutt skapar en andra generator‑instans, sätter tre rader och sparar resultatet.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Varför en separat instans?**  
Att ändra `Rows` på samma `BarcodeGenerator` efter ett `Save`‑anrop skulle också fungera, men att skapa en ny instans håller varje konfiguration isolerad och gör koden lättare att läsa — särskilt när du senare expanderar guiden för att täcka fler variationer (t.ex. olika datasträngar eller felkorrigeringsnivåer).

## Steg 5: Verifiera de genererade streckkoderna

Öppna de två PNG‑filerna du just skapade. Du bör se:

- **DatabarCols4.png** – en bredare streckkod bestående av fyra vertikala kolumner.  
- **DatabarRows3.png** – en högre streckkod bestående av tre horisontella rader.

Båda bilderna kodar samma text (`"Databar Expanded Stacked long"`), men deras visuella strukturer skiljer sig åt. Skanna dem med någon standard‑DataBar‑scanner eller en mobilapp som stöder DataBar för att bekräfta att de avkodas korrekt.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Hur du undviker det |
|-------|----------------|-----------------|
| **Fel mapp-sökväg** | `Save` kastar `DirectoryNotFoundException` om katalogen inte finns. | Använd `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` innan du anropar `Save`. |
| **För många kolumner/rader** | DataBar‑specifikationerna begränsar kolumner till 4 och rader till 3. | Håll dig inom det tillåtna intervallet; Aspose.Barcode kastar annars `ArgumentOutOfRangeException`. |
| **Oläslig streckkod** | Låg bildupplösning kan göra streckkoden suddig. | Öka DPI via `barcodeGenerator.Parameters.ImageResolution` om du behöver högre kvalitet (t.ex. 300 dpi). |
| **Fel datatyp** | DataBar accepterar endast numeriska strängar upp till 13 siffror för vissa lägen. | Validera din inmatningssträng innan du skickar den till generatorn. |

## Utöka exemplet

Nu när du kan **skapa databar staplad streckkod** med anpassade kolumner och rader, kanske du vill utforska:

- **Ändra förgrund-/bakgrundsfärger** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).  
- **Lägga till en tyst zon** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).  
- **Exportera till SVG** för upplösningsoberoende rendering (`BarCodeImageFormat.Svg`).

Alla dessa alternativ är dokumenterade i [Aspose.Barcode for .NET API reference](https://docs.aspose.com/barcode/net/).

## Fullständig källkod

Nedan finns det fullständiga, körbara programmet som innehåller varje steg som beskrivits ovan. Kopiera det till din `Program.cs`, ersätt `YOUR_DIRECTORY` med en faktisk sökväg och kör `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

När programmet körs skapas två PNG‑filer som demonstrerar hur **barcode columns** och **barcode rows** påverkar den visuella layouten av en **Databar Expanded Stacked**‑symbol.

## Slutsats

Du vet nu hur du **skapar databar staplad streckkod** i C# med Aspose.Barcode för .NET. Genom att justera egenskaperna `Columns` och `Rows` kan du generera streckkoder som passar ett brett spektrum av utrymmesbegränsningar samtidigt som dataintegriteten bevaras. Exemplet täcker allt från projektuppsättning till felsökning och ger dig en solid grund för mer avancerade streckkodsscenarier.

**Nästa steg:**  
- Experimentera med olika datasträngar och se hur kolumn‑/rad‑gränser påverkar läsbarheten.  
- Kombinera denna kod med ett webb‑API för att generera streckkoder på begäran.  
- Utforska andra symbologier (t.ex. QR, Code128) med samma `BarcodeGenerator`‑mönster.

Lycka till med kodningen, och må dina skanningar alltid lyckas!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator C# – Skapa DataBar Expanded Stacked‑bilder](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked barcode guide – hur man genererar och dimensionerar den i C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Generera Aspose.BarCode Databar‑streckkod med .NET‑API – Rad‑ och kolumnkonfiguration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}