---
category: general
date: 2026-07-24
description: Barcode Generator C#-handledning som visar hur man genererar en streckkodsbild,
  ställer in kolumner, ställer in rader och skapar Databar-streckkod med bara några
  rader kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: sv
lastmod: 2026-07-24
og_description: Barcode Generator C#‑tutorialen guidar dig genom att generera en streckkodsbild,
  konfigurera kolumner och rader samt skapa en Databar‑streckkod med tydliga kodexempel.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Streckkodsgenerator C# – Skapa DataBar staplade streckkoder snabbt
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Streckkodsgenerator C# – Skapa DataBar Expanded Stacked‑bilder
url: /sv/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Komplett guide till DataBar Expanded Stacked

Har du någonsin undrat hur man använder **barcode generator c#** för att snabbt skapa skarpa, läsbara bilder? Kanske har du stirrat på ett tomt projekt, osäker på var kolumnerna eller raderna ska placeras, eller hur man faktiskt *generate barcode image* filer utan huvudvärk. Nåväl, du är på rätt plats. I den här handledningen kommer vi att sätta upp en liten konsolapp, skapa en DataBar Expanded Stacked‑streckkod, justera dess layout och spara resultatet som PNG‑filer – allt med **barcode generator c#**‑biblioteket.

Vi kommer att gå igenom allt du behöver veta: installera paketet, konfigurera kolumner och rader (ja, vi svarar på *how to set columns* och *how to set rows*), och slutligen hur du **create databar barcode**‑objekt som du kan lägga in i fakturor, biljetter eller vad som helst som behöver en maskinläsbar etikett. Inga externa dokument behövs; bara kopiera‑klistra, kör, och du kommer att se två PNG‑filer dyka upp i din mapp.

## Vad du behöver

- .NET 6.0 SDK eller senare (koden fungerar på .NET Core, .NET Framework och .NET 5+)
- Ett nytt konsolprojekt (`dotnet new console`) – du kan också använda Visual Studio om du föredrar ett UI.
- Aspose.BarCode for .NET NuGet‑paketet (biblioteket som driver **barcode generator c#**). Installera det med:

```bash
dotnet add package Aspose.BarCode
```

Det är allt. När paketet har återställts är du redo att köra.

## Barcode Generator C# – Så här sätter du upp projektet

Först, låt oss importera de nödvändiga namnområdena och skapa en hjälpfunktion som håller vår huvudrutin prydlig.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Varför den här strukturen fungerar

- **Separation of concerns** – varje hjälpfunktion fokuserar på en enskild konfiguration (kolumner vs. rader). Det gör koden lättare att läsa och återanvända.
- **Explicit parameters** – vi skickar `columns` eller `rows` som argument, så du kan anropa samma metod med vilket värde som helst utan att redigera kroppen.
- **Immediate feedback** – `Console.WriteLine` talar om exakt var filen hamnade, vilket är praktiskt när du kör programmet från en terminal.

## Hur du ställer in kolumner för DataBar Expanded Stacked

`DataBar.Columns`‑egenskapen är den kontroll som bestämmer hur många vertikala segment streckkoden ska innehålla. Standardvärdet är `4`, men du kan behöva `2` eller `6` beroende på hur mycket data du kodar eller scannerens krav. Här är ett snabbt kodexempel som isolerar logiken för att sätta kolumner:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** När du ökar antalet kolumner växer streckkodens totala bredd proportionellt. Om du planerar att bädda in bilden i en PDF eller en webbsida, se till att behållaren kan hantera den extra bredden, annars kan scannern läsa fel.

## Hur du ställer in rader för DataBar Expanded Stacked

Rader fungerar på samma sätt, men de påverkar streckkodens höjd. Standardantalet rader är `3`. Om din etikett har begränsat vertikalt utrymme kan du sänka det till `2`. Omvänt kan fler rader förbättra läsbarheten på lågupplösta skrivare.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** Att sätta rader till ett värde lägre än det minsta som krävs för den kodade datan kommer att orsaka ett undantag vid körning. Biblioteket kastar `ArgumentException` med ett tydligt meddelande, så du vet omedelbart om konfigurationen är ogiltig.

## Generera streckkodsbild – Spara som PNG

Båda hjälpfunktionerna ovan avslutas med ett anrop till `Save`. `BarCodeImageFormat.Png`‑enumet talar om för Aspose.BarCode att skriva ut en förlustfri PNG‑fil, vilket är idealiskt för de flesta scanningsscenario eftersom den bevarar skarpa kanter. Om du föredrar ett annat format (JPEG för webben, BMP för äldre system), byt bara enum‑värdet – inga andra kodändringar behövs.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

De genererade PNG‑filerna ser ut så här (föreställ dig bilden; alt‑texten nedan beskriver den):

> **Alt‑text för de genererade bilderna:** *DataBar Expanded Stacked‑streckkod med 4 kolumner (vänster) och 3 rader (höger), renderad i högkontrast svart på en transparent bakgrund.*

## Skapa DataBar‑streckkod – Fullt fungerande exempel

När vi sätter ihop allt, här är en kompakt version som du kan klistra in direkt i `Program.cs`. Den demonstrerar både kolumn- och radkonfiguration, samt en snabb kontroll att filerna finns efter sparandet.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Förväntad output

När du kör programmet (`dotnet run`) bör du se konsollinjer liknande:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Öppna de två PNG‑filerna i någon bildvisare; du kommer att märka att den vänstra filen har fyra vertikala moduler (kolumner) medan den högra filen är tre moduler hög (rader). Båda är perfekt läsbara med vilken standard‑DataBar‑läsare som helst.

## Vanliga fallgropar & hur du undviker dem

| Symtom | Trolig orsak | Lösning |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | Kolumner satta till 0 eller > 8 (biblioteket begränsar till 8). | Håll dig till värden mellan **1** och **8**. |
| Streckkoden blir suddig i PDF | PNG sparad med standard‑DPI (96) och sedan skalad. | Använd `generator.Parameters.ImageResolution = 300;` innan sparandet. |
| Scanner misslyckas med rad‑endast konfiguration | Rader ändrade men kolumner kvar på standard som inte matchar datalängden. | Justera både rader **och** kolumner tillsammans, eller låt biblioteket automatiskt bestämma storlek genom att utelämna manuella inställningar. |

## Nästa steg

Nu när du vet hur du **generate barcode image**, **set columns**, **set rows**, och **create databar barcode** med **barcode generator c#**, kan du:

- Bädda in PNG‑filerna i PDF‑dokument med `Aspose.PDF` eller `iTextSharp`.
- Byt till `EncodeTypes.DatabarLimited` om du behöver ett mindre fotavtryck.
- Experimentera med färger (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Lägg till QR‑koder eller andra symboler i samma projekt – Aspose.BarCode stödjer över 150 typer.

Om du stöter på problem, lämna en kommentar nedan eller kolla den officiella Aspose.BarCode‑dokumentationen (API‑referensen är omfattande och innehåller dussintals levande kodexempel). Lycka till med kodningen, och må dina scannrar aldrig missa ett streck!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa DotCode‑streckkodsbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Skapa streckkodsbild c# – konfigurera Codablock F‑rader & kolumner](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generera streckkodsbild – GS1‑kupong UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}