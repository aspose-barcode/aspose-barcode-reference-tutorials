---
category: general
date: 2026-10-28
description: Skapa streckkod från text i C# med Aspose.BarCode. Lär dig att generera
  PDF417‑streckkodsbild, ställa in kolumner, justera X‑dimension och aktivera kompakt
  läge.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: sv
lastmod: 2026-10-28
og_description: Skapa streckkod från text i C# med Aspose.BarCode. Denna handledning
  visar hur du genererar en PDF417-streckkodsbild, anpassar storlek, kolumner och
  kompakt läge.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Skapa en streckkod från text i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Hur man skapar streckkod från text i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod från text i C# med Aspose.BarCode

Om du behöver **skapa streckkod från text** i en .NET-applikation, ger den här guiden en färdig‑till‑körning‑lösning. Du kommer att se hur du **genererar PDF417‑streckkod**‑bilder, styr modulbredd, kolumnantal och aktiverar kompakt läge utan att lämna din IDE.

Handledningen täcker allt som krävs för att **generate barcode C#** kod, från bibliotekets installation till att spara den slutgiltiga PNG‑filen. I slutet kan du bädda in en hög‑densitet PDF417‑streckkod i rapporter, biljetter eller lageretiketter.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon editor som stöder .NET)  
* Internetåtkomst för att ladda ner Aspose.BarCode för .NET NuGet‑paketet  

Dessa komponenter räcker för att kompilera och köra exemplet på Windows, Linux eller macOS.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Biblioteket som driver streckkodsgenereringen är **Aspose.BarCode for .NET**. Installera det med .NET‑CLI:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till `Aspose.BarCode`‑namnrymden, som innehåller `BarcodeGenerator`‑klassen som används genom hela handledningen.

## Steg 2: Skapa ett konsolprojekt och lägg till koden

Skapa ett nytt konsolprojekt och ersätt den genererade `Program.cs` med följande kod. Programmet demonstrerar hur man **skapar streckkod från text** och sparar den som en **PDF417‑streckkodbild**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig

* **`EncodeTypes.Pdf417`** väljer PDF417‑symbologi, vilket är idealiskt för att koda stora mängder data i ett två‑dimensionellt format.  
* **`XDimension.Pixels = 2`** minskar modulbredden, vilket gör streckkoden tätare och mer lämplig för begränsat utrymme.  
* **`Pdf417.Columns = 3`** styr antalet vertikala datakolumner; ett lägre antal ger en högre men smalare streckkod.  
* **`Pdf417.Truncate = true`** aktiverar kompakt läge, vilket tar bort oanvända kolumner på högersidan. Detta är den viktigaste inställningen som förvandlar en vanlig PDF417 till en **kompakt PDF417‑streckkodbild**.

## Steg 3: Bygg och kör projektet

Kör följande kommandon i projektkatalogen:

```bash
dotnet build
dotnet run
```

När programmet är klart kommer du att se ett konsolmeddelande som bekräftar filens plats. Öppna `CompactPdf417.png` med någon bildvisare för att verifiera resultatet.

**Förväntat resultat** – en högkontrast‑PNG som visar en kompakt PDF417‑streckkod som kodar strängen `Åspóse.Barcóde©`. Skanning av bilden med en standard streckkodsläsare returnerar den ursprungliga texten, vilket bekräftar att **generate pdf417 barcode** lyckades.

## Steg 4: Anpassa streckkoden för olika scenarier

Även om exemplet använder ett fast kolumnantal och X‑dimension, kan du anpassa generatorn för andra krav:

| Scenario | Justering |
|----------|------------|
| Större datamängd | Öka `Pdf417.Columns` eller sätt `Pdf417.Rows` manuellt |
| Högre skanningspålitlighet | Höj `XDimension.Pixels` till 3 eller 4 |
| Annat bildformat | Byt ut `BarCodeImageFormat.Png` mot `Jpeg` eller `Bmp` |
| Transparent bakgrund | Sätt `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Dessa alternativ låter dig **generate barcode C#** lösningar som passar mobilappar, skrivbordsrapporter eller webbtjänster.

## Steg 5: Hantera kantfall och bästa praxis

* **Unicode‑stöd** – Generatorn kodar automatiskt Unicode‑tecken, men säkerställ att din källsträng är UTF‑8‑kodad om du läser den från en fil.  
* **Stor text** – PDF417 kan koda upp till 1 850 alfanumeriska tecken. Om du överskrider denna gräns kastar biblioteket ett undantag; dela upp data i flera streckkoder eller byt till en symbologi med högre kapacitet.  
* **Felhantering** – Omge genereringskoden med ett `try/catch`‑block för att fånga `BarCodeException` och ge ett vänligt felmeddelande.  
* **Prestanda** – Att generera många streckkoder i en loop gynnas av att återanvända en enda `BarcodeGenerator`‑instans och bara uppdatera `CodeText` mellan iterationer.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Fullständig källkodslista

Nedan är det kompletta, fristående programmet som du kan kopiera till `Program.cs`. Inga ytterligare filer krävs.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Att köra detta program skapar **pdf417 streckkodbilden** som visas i illustrationen nedan.

![Kompakt PDF417‑streckkod skapad från text med C#](/images/compact-pdf417.png){.img-fluid alt="exempel på att skapa streckkod från text som visar en kompakt PDF417‑streckkodbild"}

*Bildbeskrivning: PNG‑filen visar en kompakt PDF417‑streckkod som kodar strängen “Åspóse.Barcóde©”.*  

## Slutsats

Du vet nu hur du **skapar streckkod från text** i C# och producerar en **PDF417‑streckkodbild** med anpassade dimensioner och kompakt läge. Exemplet visar de väsentliga stegen för att **generate barcode C#**, hantera Unicode‑data och justera visuella parametrar för olika distributionsscenarier.

Nästa, utforska relaterade ämnen såsom **generate QR code in C#**, **add barcode to PDF documents**, eller **embed barcodes in ASP.NET Core APIs**. Var och en av dessa bygger på samma `BarcodeGenerator`‑grundprinciper som behandlats här.

Lycka till med kodningen, och njut av att integrera streckkoder i dina .NET‑lösningar!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera PDF417‑streckkod i C# – Skapa PDF417‑streckkod C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Hur man genererar PDF417‑streckkod med Aspose.BarCode i C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Hur man skapar PDF417‑streckkodbild i C# – komplett guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}