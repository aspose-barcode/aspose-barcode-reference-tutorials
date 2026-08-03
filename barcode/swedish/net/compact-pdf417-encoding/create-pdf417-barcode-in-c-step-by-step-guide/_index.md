---
category: general
date: 2026-08-03
description: Skapa PDF417‑streckkod i C# snabbt. Lär dig hur du genererar PDF417‑streckkod
  och hur du sparar streckkodens bild som PNG med Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: sv
lastmod: 2026-08-03
og_description: Skapa PDF417-streckkod i C# med Aspose.Barcode. Följ den här guiden
  för att generera PDF417-streckkod och hur du sparar streckkodsbilden effektivt.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Skapa PDF417-streckkod i C# – komplett kodningshandledning
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Skapa PDF417‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod i C# – steg‑för‑steg‑guide

Om du behöver **skapa PDF417-streckkod** i en .NET-applikation visar den här guiden exakt hur du genererar PDF417-streckkod och hur du sparar streckkodsbilden. Du får en PNG-fil som kan användas i rapporter, biljetter eller mobila skanningsappar.

Handledningen täcker allt från projektuppsättning till den slutliga PNG-filen. Ingen extern dokumentation krävs; följ bara stegen och kör koden.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 eller någon IDE som stödjer C#
* Internetåtkomst för att installera **Aspose.Barcode for .NET** NuGet‑paketet

Dessa förutsättningar säkerställer att koden kompileras utan ytterligare konfiguration.

## Skapa PDF417-streckkod – projektuppsättning

1. Öppna en kommandoprompt och skapa ett nytt konsolprojekt:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Lägg till Aspose.Barcode‑biblioteket:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Öppna den genererade filen `Program.cs`. `using`‑satserna högst upp ger dig åtkomst till streckkodsklasserna:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Projektet är nu redo att **skapa PDF417-streckkod**.

## Hur man genererar PDF417-streckkod med Aspose.Barcode

Kärnan i streckkodsskapandet finns i klassen `BarcodeGenerator`. Du specificerar symbologin (`EncodeTypes.Pdf417`) och de data du vill koda.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Varför detta är viktigt

* **EncodeTypes.Pdf417** talar om för biblioteket att använda PDF417‑standarden, som stödjer stora datamängder och felkorrigering.
* Att tillhandahålla Unicode‑tecken visar att generatorn hanterar icke‑ASCII‑inmatning utan extra konfiguration.

## Hur man konfigurerar streckkodens utseende

Du kan styra storleken på varje modul, antalet kolumner och om streckkoden använder kompakt (trunkerad) läge. Dessa inställningar påverkar både läsbarhet och filstorlek.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Praktiskt tips

Om du behöver en högre streckkod för begränsat horisontellt utrymme, öka `Columns`. Att sätta `Truncate` till `true` minskar den totala höjden genom att ta bort tysta zoner, vilket är idealiskt för mobila skärmar.

## Hur man sparar streckkodsbild som PNG

Efter att ha konfigurerat generatorn, anropa `Save` med en filsökväg och önskat bildformat. Metoden skriver bilden direkt till disk.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Förväntat resultat

När programmet körs skapas `CompactPdf417.png` i projektmappen. När du öppnar filen visas en kompakt PDF417‑streckkod som kodar strängen *Åspóse.Barcóde©*. Bilden kan bäddas in i HTML, PDF‑rapporter eller skrivas ut på etiketter.

## Fullständig källkod

Nedan är det kompletta, körbara programmet. Kopiera det till `Program.cs` och kör `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verifiera resultatet

När programmet är klart kan du verifiera att filen finns med ett snabbt kommando:

```bash
dotnet run && ls -l CompactPdf417.png
```

Om filen visas har processen för att **skapa PDF417-streckkod** lyckats.

## Vanliga variationer och kantfall

| Situation | Justering |
|-----------|------------|
| **Längre datasträng** | Öka `Columns` eller sätt `Rows` för att rymma fler kodord. |
| **Annat bildformat** | Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif`. |
| **Högre upplösning** | Sätt `generator.Parameters.ImageResolution` innan `Save`. |
| **Bakgrundsfärg** | Använd `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Undantagshantering** | Omslut `generator.Save` med ett `try/catch`‑block för att fånga I/O‑fel. |

## Slutsats

Du vet nu hur du **skapar PDF417-streckkod** i C# med Aspose.Barcode, konfigurerar dess utseende och **sparar streckkodsbilden** som en PNG‑fil. Det kompletta exemplet visar varje nödvändigt steg, från projektuppsättning till verifiering, så att du kan integrera streckkodsgenerering i vilken .NET‑lösning som helst.

Nästa steg är att utforska relaterade ämnen som **hur man genererar QR‑koder**, **bädda in streckkoder i PDF‑dokument** eller **anpassa streckkodsfärger**. Alla dessa bygger på samma generator‑API, vilket låter dig utöka din applikations skanningsmöjligheter med minimal ansträngning. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}