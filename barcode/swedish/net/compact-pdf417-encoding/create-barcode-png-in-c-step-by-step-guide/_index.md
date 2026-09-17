---
category: general
date: 2026-07-18
description: Skapa streckkod‑PNG i C# snabbt. Lär dig hur du justerar kolumner, aktiverar
  länkar och genererar PDF417 med en C#‑streckkodsgenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to adjust columns
- c# barcode generator
- how to generate pdf417
- how to enable linking
language: sv
lastmod: 2026-07-18
og_description: Skapa streckkod‑PNG i C# och lär dig hur du justerar kolumner, aktiverar
  länkar och genererar PDF417 med en C#‑streckkodsgenerator. Följ den här koncisa
  guiden.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Skapa streckkod PNG i C# – Komplett programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create barcode PNG in C# quickly. Learn how to adjust columns, enable
    linking, and generate PDF417 with a C# barcode generator.
  headline: Create barcode PNG in C# – Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Skapa streckkod PNG i C# – Steg‑för‑steg guide
url: /sv/net/compact-pdf417-encoding/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod PNG i C# – Komplett programmeringsgenomgång

Har du någonsin undrat hur man **skapar streckkod PNG**-filer från C# utan att rycka ur håret? Du är inte ensam. Oavsett om du behöver en GS1‑Micro‑PDF417 för en fraktetikett eller en enkel QR‑kod för en marknadsföringsflygblad, så gör behärskning av **c# barcode generator** hela processen till en barnlek.

I den här handledningen går vi igenom allt du behöver för att **skapa streckkod PNG**-bilder, från att installera rätt NuGet‑paket till att justera kolumnantal och aktivera länkning. I slutet kommer du att veta **hur man justerar kolumner**, **hur man aktiverar länkning**, och **hur man genererar PDF417** i några få snygga kodrader.

## Vad du kommer att lära dig

- Skapa ett C#‑projekt med ett streckkodsgenereringsbibliotek.  
- Använd en **c# barcode generator** för att bygga en GS1‑Micro‑PDF417‑streckkod.  
- Tillämpa **how to adjust columns** för att kontrollera streckkodens densitet.  
- Aktivera den speciella länkfunktionaliteten (**how to enable linking**).  
- Spara resultatet som en högkvalitativ **create barcode PNG**‑fil.  

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar på .NET Core och .NET Framework).  
- Grundläggande kunskap om C#‑syntax – om du kan skriva en `foreach` är du klar.  
- Visual Studio 2022, VS Code eller någon IDE du föredrar.  
- Internetåtkomst för att hämta streckkodsbiblioteket från NuGet (vi använder *Aspose.BarCode* i exemplet).

Inga externa konfigurationsfiler behövs; allt finns i koden vi kommer att skriva tillsammans.

## Steg 1: Lägg till streckkodsbiblioteket (c# barcode generator)

Öppna din terminal (eller Package Manager Console) och kör:

```bash
dotnet add package Aspose.BarCode
```

Det enda kommandot hämtar en robust **c# barcode generator** som kan hantera PDF417, QR, Code128 och mycket mer. Biblioteket underhålls aktivt (v24.9 i juli 2026) och fungerar på flera plattformar, så du blir inte låst till Windows.

## Steg 2: Definiera utdatamappen

Innan vi genererar något behöver vi en plats att lägga bilden. Att hårdkoda en sökväg fungerar för ett demo, men du kan senare ersätta den med ett konfigurationsvärde.

```csharp
// Step 2: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

Lägg märke till hur vi använder `Path.Combine` för säkerhet—inga magiska strängar som går sönder på Linux. Detta steg är viktigt eftersom ett försök att **create barcode PNG** utan en giltig mapp kastar ett körningsfel.

## Steg 3: Initiera GS1‑Micro‑PDF417‑generatorn (how to generate pdf417)

Nu blir det roligt. Vi skapar en **c# barcode generator**‑instans och matar den med den råa datasträngen.

```csharp
// Step 3: Initialise the GS1‑Micro‑PDF417 generator
var generator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

`EncodeTypes.GS1MicroPdf417`‑flaggan talar om för biblioteket att vi vill ha en PDF417‑variant som följer GS1‑standarderna. Datasträngen följer Application Identifier‑formatet: `(01)` för GTIN och `(240)` för en intern företagskod. Om du behöver en vanlig PDF417, byt bara enum‑värdet till `EncodeTypes.Pdf417`—det är **how to generate pdf417** i en annan variant.

## Steg 4: Justera streckkodslayouten (how to adjust columns & how to enable linking)

Två inställningar orsakar ofta förvirring: kolumnantalet och länkflaggan. Låt oss avmystifiera dem.

```csharp
// Step 4a: Adjust the number of columns – this is how to adjust columns
generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns gives a compact barcode

// Step 4b: Enable linking between macro and micro PDF417 – this is how to enable linking
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

- **How to adjust columns**: `Columns`‑egenskapen styr horisontell densitet. Färre kolumner gör streckkoden högre men bredare; fler kolumner komprimerar den vertikalt. Vi valde `4` eftersom det balanserar läsbarhet på en 2‑tumsetikett med en rimlig filstorlek.  
- **How to enable linking**: Att sätta `IsLinked = true` knyter ihop macro‑ (full‑size) och micro‑ (tiny) versionerna, vilket vissa skannrar kräver för hierarkisk dataextraktion.

Om du hoppar över dessa två rader får du fortfarande en streckkod, men den kanske inte uppfyller dina specifikationer. Tro mig, jag har spenderat timmar på att felsöka felaktiga kolumnantal.

## Steg 5: Finjustera modulbredden (X‑Dimension)

Även om det inte är ett huvudnyckelord, så kombineras justering av modulbredd ofta med kolumnjusteringar.

```csharp
// Step 5: Set X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

En pixel‑bred modul på `2` ger en skarp bild som skalar bra när du senare bäddar in den i PDF‑filer eller skriver ut den på termiska skrivare.

## Steg 6: Spara bilden – Äntligen **create barcode PNG**

All den här förberedelsen kulminerar i en enda rad som faktiskt skriver filen till disk.

```csharp
// Step 6: Save the generated barcode as a PNG – the core of create barcode png
string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
generator.Save(filePath, BarCodeImageFormat.Png);
Console.WriteLine($"✅ Barcode PNG saved to: {filePath}");
```

`BarCodeImageFormat.Png`‑enum garanterar förlustfri kompression, perfekt för efterföljande bearbetning (t.ex. att föra in PNG‑filen i en PDF eller ett HTML‑`<img>`‑element). Denna rad är hjärtat i **create barcode PNG**—utan den skulle du aldrig se resultatet.

## Fullt fungerande exempel

När vi sätter ihop allt, här är en fristående konsolapp som du kan kopiera och köra:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Define the output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // 2️⃣ Create a GS1‑Micro‑PDF417 barcode generator (how to generate pdf417)
        var generator = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(01)12345678901231(240)ABCD123456789012345");

        // 3️⃣ Adjust X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 4️⃣ How to adjust columns – set column count
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 5️⃣ How to enable linking – link macro and micro versions
        generator.Parameters.Barcode.Pdf417.IsLinked = true;

        // 6️⃣ Save as PNG – the moment we finally create barcode png
        string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Successfully created barcode PNG at: {filePath}");
    }
}
```

### Förväntad utdata

När du kör programmet skriver konsolen ut något liknande:

```
✅ Successfully created barcode PNG at: C:\YourProject\Barcodes\GS1MicroPdf417_906_907.png
```

Öppna filen, så ser du en ren, skannbar GS1‑Micro‑PDF417‑bild—precis vad du behövde för att **create barcode PNG** i ditt logistikflöde.

## Vanliga fallgropar & proffstips

- **Fallgrop:** Glömmer `Directory.CreateDirectory`. Appen kraschar med `DirectoryNotFoundException`.  
  **Tips:** Se alltid till att utdatamappen finns innan du sparar.

- **Fallgrop:** Använder fel `EncodeTypes`. `EncodeTypes.Pdf417` ger dig en vanlig PDF417, *inte* mikro‑versionen.  
  **Tips:** Dubbelkolla enum‑värdet när du behöver en GS1‑Micro‑streckkod.

- **Fallgrop:** Sätter `Columns` till ett värde utanför det tillåtna intervallet (1‑30).  
  **Tips:** Håll dig till 2‑10 för de flesta etikettstorlekar; annars kastar biblioteket ett `ArgumentOutOfRangeException`.

- **Proffstips:** Om du behöver en transparent bakgrund, lägg till  
  ```csharp
  generator.Parameters.Barcode.BackgroundColor = Color.Transparent;
  ```  
  innan du sparar. Detta får PNG‑filen att smälta sömlöst in i UI‑element.

- **Proffstips:** För batch‑bearbetning, omslut genereringslogiken i en `foreach`‑loop och variera datasträngen per iteration. Det är ett enkelt sätt att **create barcode PNG**‑filer i bulk.

## Utöka exemplet

Nu när du behärskar grunderna, överväg att utforska dessa relaterade ämnen:

- **How to generate QR codes** med samma `BarcodeGenerator` (byt bara `EncodeTypes.QR`).  
- **Adding human‑readable text** under streckkoden via `generator.Parameters.Barcode.BarHeight`.  
- **Exporting to SVG** (`BarCodeImageFormat.Svg`) för vektorbaserad webbgrafik.  
- **Integrating with ASP.NET Core** för att leverera streckkodsbilder i realtid (`FileStreamResult`).  

Alla dessa scenarier återanvänder det grundmönster vi gick igenom: initiera generatorn, justera parametrar, och **create barcode PNG** (eller ett annat format) med ett enda `Save`‑anrop.

## Slutsats

Vi har gått igenom ett komplett, produktionsklart sätt att **create barcode PNG**‑filer i C#. Genom att följa stegen vet du nu **how to adjust columns**, **how to enable linking**, och **how to generate PDF**.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}