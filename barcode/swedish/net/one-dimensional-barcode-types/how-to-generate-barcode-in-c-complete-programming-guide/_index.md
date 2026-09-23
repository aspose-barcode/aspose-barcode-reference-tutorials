---
category: general
date: 2026-07-21
description: Hur man snabbt genererar streckkod i C#. Lär dig hur du ställer in dimensioner,
  ändrar kolumner och använder en streckkodsgenerator för PNG‑bilder i en steg‑för‑steg‑handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change columns
- barcode generator for png
language: sv
lastmod: 2026-07-21
og_description: Hur genererar man en streckkod i C#? Den här guiden visar hur du ställer
  in dimensioner, ändrar kolumner och exporterar en streckkodsgenerator till PNG med
  komplett kod.
og_image_alt: Screenshot of a MicroPDF417 barcode saved as a PNG file
og_title: Hur man genererar streckkod i C# – Fullständig guide för PNG-utdata
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode in C# quickly. Learn how to set dimensions,
    change columns, and use a barcode generator for PNG images in a step‑by‑step tutorial.
  headline: How to Generate Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn how to set dimensions,
    change columns, and use a barcode generator for PNG images in a step‑by‑step tutorial.
  name: How to Generate Barcode in C# – Complete Programming Guide
  steps:
  - name: Create a New Console Application
    text: 'Open a terminal and run:'
  - name: Add the Aspose.BarCode Dependency
    text: '```bash dotnet add package Aspose.BarCode ```'
  - name: Verifying the Barcode
    text: You can scan the PNG with any barcode scanner app (most smartphones have
      one built‑in). It should decode back to `Åspóse.Barcóde©`. If it doesn’t, double‑check
      that the image isn’t corrupted and that your scanner supports MicroPDF417.
  - name: Changing the Barcode Type
    text: 'If you need a classic **Code128** or a QR code, swap the `EncodeTypes`
      enum:'
  - name: Exporting to Other Formats
    text: 'Aspose supports JPEG, BMP, GIF, and TIFF:'
  - name: Dynamically Setting Dimensions
    text: 'Suppose you receive width/height from user input:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Hur man genererar streckkod i C# – Komplett programmeringsguide
url: /sv/net/one-dimensional-barcode-types/how-to-generate-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod i C# – Komplett programmeringsguide

Har du någonsin undrat **hur man genererar streckkod** i C# utan att kämpa med kryptiska bibliotek? Du är inte ensam. Oavsett om du behöver en liten lageretikett eller en elegant biljett‑QR, kan det vara en riktig tidsbesparing att skapa en streckkod programmässigt. I den här handledningen går vi igenom varje steg—**hur man ställer in dimensioner**, finjusterar layouten och slutligen exporterar en **streckkodsgenerator för PNG**‑bilder.

Vi kommer att använda det populära **Aspose.BarCode**‑biblioteket (gratisprovversionen fungerar utmärkt för testning). I slutet av den här guiden har du en färdig‑att‑köra konsolapp som genererar en skarp MicroPDF417‑streckkod i PNG, och du kommer att förstå hur du anpassar koden för andra format eller bildtyper.

## Förutsättningar

- .NET 6.0 SDK (eller någon nyare .NET‑version)
- Visual Studio 2022 (eller VS Code med C#‑tillägg)
- Aspose.BarCode för .NET NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Grundläggande kunskap om C#‑konsolprojekt (ingen djup expertis krävs)

> **Tips:** Om du föredrar en annan IDE, förblir stegen desamma—justera bara kommandot för projektet.

## Projektuppsättning

### Steg 1: Skapa en ny konsolapplikation

Öppna en terminal och kör:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Det här skapar en minimal `Program.cs`‑fil och en `.csproj` som riktar sig mot .NET 6.0.

### Steg 2: Lägg till Aspose.BarCode‑beroendet

```bash
dotnet add package Aspose.BarCode
```

Paketet tar med alla klasser vi behöver: `BarcodeGenerator`, `EncodeTypes` och bildformat‑enumar.

## Implementering av streckkodsgeneratorn

Nedan är den **kompletta, körbara koden**. Kopiera den till `Program.cs`, ersätt `YOUR_DIRECTORY` med en absolut eller relativ sökväg som du har skrivbehörighet till, och kör `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the text you want to encode.
            //    Using characters with accents demonstrates Unicode support.
            string barcodeText = "Åspóse.Barcóde©";

            // 2️⃣ Create the generator for MicroPDF417 (compact version of PDF417).
            //    This is the core of “how to generate barcode”.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, barcodeText);

            // 3️⃣ Adjust visual properties.
            //    • How to set dimensions? – we tweak XDimension (module width).
            //    • How to change columns? – we set the Columns property (max 4 for MicroPDF417).
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // finer detail
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // layout control

            // 4️⃣ Choose the output folder.
            //    For safety, we resolve a full path relative to the project directory.
            string outputPath = System.IO.Path.Combine(
                AppContext.BaseDirectory, "MicroPdf417.png");

            // 5️⃣ Save as PNG – this fulfills “barcode generator for png”.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to: {outputPath}");
        }
    }
}
```

#### Varför dessa inställningar är viktiga

- **XDimension** bestämmer bredden på varje liten stapel (modul). Att sätta den till `2` pixlar ger en skarpare bild utan att öka filstorleken.
- **Pdf417.Columns** styr hur många kolumner data delas upp i. MicroPDF417 har ett tak på 4; färre kolumner gör streckkoden högre, fler kolumner gör den bredare. Anpassa efter din etikettstorlek.
- **BarCodeImageFormat.Png** erbjuder förlustfri komprimering, idealisk för utskrift eller inbäddning i PDF‑filer.

## Köra exemplet

1. Bygg och kör projektet:

   ```bash
   dotnet run
   ```

2. Efter körning ser du ett konsolmeddelande med den fullständiga sökvägen till `MicroPdf417.png`. Öppna filen—din streckkod bör se ut ungefär så här:

![Skärmdump av genererad MicroPDF417‑streckkod PNG](https://example.com/placeholder.png "MicroPDF417‑streckkod sparad som PNG")  
*Bildtext: Skärmdump av en MicroPDF417‑streckkod sparad som en PNG‑fil.*

> **Obs:** Placeholder‑URL:en är bara för illustration. Ersätt den med en faktisk bild‑URL om du hostar en.

### Verifiera streckkoden

Du kan skanna PNG‑filen med någon streckkodsläsarapp (de flesta smartphones har en inbyggd). Den bör avkoda tillbaka till `Åspóse.Barcóde©`. Om den inte gör det, dubbelkolla att bilden inte är skadad och att din läsare stödjer MicroPDF417.

## Anpassa generatorn

### Ändra streckkodstypen

Om du behöver en klassisk **Code128** eller en QR‑kod, byt ut `EncodeTypes`‑enum:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Code128, barcodeText);
```

Alla andra parameteranrop förblir desamma, men vissa egenskaper (som `Pdf417.Columns`) blir irrelevanta—Aspose ignorerar dem smidigt.

### Exportera till andra format

Aspose stödjer JPEG, BMP, GIF och TIFF:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

JPEG minskar filstorleken ytterligare men introducerar komprimeringsartefakter—använd den bara när du är okej med en liten förlust av skärpa.

### Dynamiskt ställa in dimensioner

Anta att du får bredd/höjd från användarinmatning:

```csharp
int userPixels = int.Parse(Console.ReadLine() ?? "3");
generator.Parameters.Barcode.XDimension.Pixels = userPixels;
```

Validera alltid indata (minst 1 pixel, högst kanske 10) för att undvika oläsliga streckkoder.

## Vanliga fallgropar & pro‑tips

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Streckkoden ser suddig ut | XDimension för låg eller sparad med låg DPI | Öka `XDimension.Pixels` eller exportera med högre DPI (`generator.Save(..., BarCodeImageFormat.Png, 300)` ) |
| Läsaren kan inte läsa | För många kolumner för den givna bildbredden | Minska `Pdf417.Columns` eller förstora utdata‑bilden |
| Unicode‑tecken blir � | Fel kodning eller äldre biblioteks‑version | Se till att du använder Aspose.BarCode 23.9+ som fullt stödjer Unicode |
| Fil‑inte‑hittad‑fel | Utdatamappen finns inte | Använd `Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!)` innan du sparar |

**Pro‑tips:** När du genererar många streckkoder i en batch, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara `CodeText`‑egenskapen. Detta minskar objektallokering och snabbar upp bearbetningen.

## Fullständigt end‑to‑end‑exempel (batch‑läge)

Nedan är ett utökat kodsnutt som läser en CSV med produktkoder och skapar en PNG för var och en. Det demonstrerar skalbarhet och förstärker konceptet “hur man genererar streckkod”.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class BatchGenerator
{
    static void Main()
    {
        string csvPath = "products.csv"; // format: Id,BarcodeText
        string outputDir = Path.Combine(AppContext.BaseDirectory, "BatchOutput");
        Directory.CreateDirectory(outputDir);

        foreach (var line in File.ReadLines(csvPath))
        {
            var parts = line.Split(',');
            if (parts.Length != 2) continue; // skip malformed rows

            string id = parts[0];
            string text = parts[1];

            var gen = new BarcodeGenerator(EncodeTypes.MicroPdf417, text);
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            gen.Parameters.Barcode.Pdf417.Columns = 4;

            string fileName = Path.Combine(outputDir, $"barcode_{id}.png");
            gen.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

Kör den efter att du skapat en enkel `products.csv`:

```
001,ABC123
002,XYZ789
003,Åspóse.Barcóde©
```

## Slutsats

Vi har gått igenom **hur man genererar streckkod** i C# från grunden, utforskat **hur man ställer in dimensioner**, lärt **hur man ändrar kolumner**, och slutligen exporterat resultatet med en **streckkodsgenerator för PNG**. Den kompletta, kopiera‑och‑klistra‑klara koden ovan fungerar direkt, och förklaringarna svarar både på “vad” och “varför” bakom varje inställning.

Nästa steg kan vara att:

- Experimentera med andra `EncodeTypes` (QR, DataMatrix, Code128) – utmärkt för mobilappar.
- Integrera generatorn i ett ASP.NET Core‑API så att din webbtjänst kan returnera streckkoder på begäran.
- Fördjupa dig i Asposes avancerade styling (färger, ramar, inbäddade logotyper) för varumärkesändamål.

Har du frågor om ett specifikt streckkodformat eller bildkrav? Lämna en kommentar, och lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod – En-dimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}