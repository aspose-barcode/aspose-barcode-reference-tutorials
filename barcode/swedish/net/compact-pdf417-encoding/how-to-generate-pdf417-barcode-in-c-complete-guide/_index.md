---
category: general
date: 2026-09-26
description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Följ den här steg‑för‑steg‑handledningen
  för att konfigurera kolumner, aktivera kompakt läge och spara som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: sv
lastmod: 2026-09-26
og_description: Generera PDF417-streckkod i C# med Aspose.BarCode. Denna guide visar
  hur du ställer in kolumner, aktiverar kompakt läge och exporterar resultatet som
  en PNG-bild.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Generera PDF417‑streckkod i C# – steg‑för‑steg‑handledning
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Hur man genererar PDF417-streckkod i C# – komplett guide
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417-streckkod i C# – komplett guide

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här handledningen en färdig‑att‑köra lösning. Du får se hur du konfigurerar streckkodens storlek, kolumnantal och kompakt läge, och sedan sparar resultatet som en högkvalitativ PNG‑fil.

Att generera en streckkod är ett vanligt krav för lagersystem, biljettplattformar och dokumentkodning. I slutet av den här guiden har du ett fristående C#‑program som producerar en kompakt PDF417‑streckkod med hjälp av **pdf417 barcode generator C#**‑biblioteket från Aspose.

## Vad du behöver

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
- En giltig Aspose.BarCode för .NET-licens (den kostnadsfria utvärderingen fungerar för testning)
- En IDE eller redigerare såsom Visual Studio 2022, Rider eller VS Code
- Grundläggande kunskap om C#‑konsolprojekt

> **Proffstips:** Om du använder den kostnadsfria utvärderingen kommer den genererade bilden att innehålla ett litet Aspose‑vattenstämpel. En köpt licens tar bort vattenstämpeln och låser upp hela funktionsuppsättningen.

## Steg 1: Ställ in Aspose.BarCode‑biblioteket

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode‑NuGet‑paketet.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Paketet tillhandahåller klassen `BarcodeGenerator`, som är kärnan i **pdf417 barcode generator C#**‑arbetsflödet.

## Steg 2: Skriv det kompletta streckkodsgenereringsprogrammet

Öppna `Program.cs` och ersätt dess innehåll med följande kod. Programmet demonstrerar varje nödvändigt steg, från att initiera generatorn till att spara bilden.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig

| Rad | Syfte |
|------|---------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Instansierar en PDF417‑generator och sätter den kodade texten. PDF417 stödjer stora datamängder och Unicode, vilket gör den lämplig för komplexa identifierare. |
| `XDimension.Pixels = 2` | Styr den visuella densiteten. Mindre värden ger finare streck; större värden förbättrar läsbarheten på lågupplösta skärmar. |
| `Pdf417.Columns = 3` | Åsidosätter den automatiska kolumnberäkningen. Fasta kolumner är användbara när du måste passa streckkoden i ett fördefinierat utrymme. |
| `Pdf417.Truncate = true` | Aktiverar kompakt läge, vilket tar bort onödig utfyllnad och minskar den totala storleken. |
| `Save(..., BarCodeImageFormat.Png)` | Skriver streckkoden till en PNG‑fil, ett förlustfritt format som är idealiskt för vidare bearbetning eller inbäddning i PDF‑filer. |

## Steg 3: Kör programmet och verifiera resultatet

Bygg och kör projektet:

```bash
dotnet run
```

Du bör se ett konsolmeddelande som bekräftar filens plats, och en fil med namnet **CompactPdf417.png** kommer att visas i projektmappen.

![Genererad PDF417-streckkodsexempel](images/compact-pdf417.png){.img-responsive alt="Genererad PDF417-streckkodsexempel"}

*Bilden visar en kompakt PDF417‑streckkod som kodar strängen “Åspóse.Barcóde©”.*  

Om du öppnar PNG‑filen i en bildvisare kommer du att märka tre kolumner av staplade datablock, varje streck 2 pixlar brett. Att skanna streckkoden med en standard‑PDF417‑läsare returnerar den ursprungliga texten, vilket bekräftar att generatorn fungerar som förväntat.

## Vanliga fallgropar och hur du undviker dem

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Streckkoden blir suddig | XDimension är inställd för lågt för mål‑DPI | Öka `XDimension.Pixels` till 3 eller 4, eller rendera i högre upplösning med `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Unicode‑tecken försvinner | Indatasträngen är inte kodad som UTF‑8 | Se till att källfilen sparas med UTF‑8‑kodning; generatorn hanterar automatiskt Unicode när strängtypen är `string`. |
| Truncate kastar ett undantag | Datastorleken överskrider maxgränsen för det valda kolumnantalet | Antingen öka `Pdf417.Columns` eller sätt `Pdf417.Truncate = false` så att generatorn kan allokera tillräckligt med utrymme. |
| Licens tillämpas inte | Utvärderingsversionen lägger till en vattenstämpel | Applicera en giltig licensfil via `Aspose.BarCode.License` innan generatorn skapas. |

## Utöka lösningen

När du har det grundläggande **generate PDF417 barcode**‑flödet kan du utforska ytterligare funktioner:

- **Error correction level** – Justera `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` för att öka motståndskraften mot skador.
- **Color customization** – Använd `generator.Parameters.Barcode.ForegroundColor` och `BackgroundColor` för att matcha varumärkesriktlinjer.
- **Embedding in PDFs** – Kombinera Aspose.PDF med Aspose.BarCode för att placera streckkoden direkt i ett PDF‑dokument.
- **Batch generation** – Loopa över en samling identifierare för att producera flera PNG‑filer i ett enda körning.

Alla dessa alternativ är dokumenterade i Aspose.BarCode API‑referensen och följer samma mönster som demonstrerats ovan.

## Slutsats

Du vet nu hur du **genererar PDF417-streckkod** i C# med Aspose.BarCode, konfigurerar kolumner, aktiverar kompakt läge och exporterar resultatet som en PNG‑bild. Det kompletta exemplet körs direkt och kan anpassas för större projekt, såsom biljettssystem, lageretiketter eller säker dokumentkodning.

Nästa steg är att prova de avancerade inställningarna i **pdf417 barcode generator C#**, såsom felkorrigering och färganpassning, eller integrera streckkoden i en PDF‑rapport med Aspose.PDF. Experimentera med olika `XDimension`‑värden och kolumnantal för att hitta den optimala balansen mellan storlek och skanningspålitlighet för ditt specifika användningsfall. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera PDF417-streckkod i C# – komplett guide med kompakt layout](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Aspose barcode‑exempel: generera Macro PDF417 i C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Hur man sparar streckkod i C# – Generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}