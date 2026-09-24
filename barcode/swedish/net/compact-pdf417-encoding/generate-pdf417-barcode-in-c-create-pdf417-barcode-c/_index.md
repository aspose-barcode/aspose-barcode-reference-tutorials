---
category: general
date: 2026-07-24
description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Lär dig hur du skapar
  PDF417‑streckkod i C# med kompakt läge på några minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: sv
lastmod: 2026-07-24
og_description: Generera PDF417‑streckkod i C# snabbt med Aspose.BarCode. Den här
  handledningen visar hur du skapar PDF417‑streckkod i C# i kompakt läge, inklusive
  installation, kod och verifiering.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Generera PDF417‑streckkod i C# – Snabb guide
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Generera PDF417‑streckkod i C# – Skapa PDF417‑streckkod i C#
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417‑streckkod i C# – Komplett programmeringsgenomgång

Har du någonsin funderat på hur man **genererar PDF417‑streckkod** i en C#‑applikation utan att rota runt i ändlösa forumtrådar? Du är inte ensam. Oavsett om du bygger ett biljettsystem, ett säkert ID‑kort eller bara behöver ett snabbt sätt att bädda in data i ett utskrivbart format, kan behärskning av PDF417‑formatet spara dig timmar av trial‑and‑error.

I den här guiden går vi igenom ett **komplett, färdigt exempel** som visar exakt hur du **skapar PDF417‑streckkod i C#** med det populära Aspose.BarCode‑biblioteket. Vi täcker allt från installation av NuGet‑paketet till justering av kompakt‑läget, så att du kan kopiera‑klistra koden och se resultatet omedelbart.

## Vad du kommer att lära dig

- Hur du sätter upp Aspose.BarCode‑biblioteket i ett .NET‑projekt.  
- De exakta C#‑satserna som behövs för att **generera PDF417‑streckkod** med anpassad text, modulstorlek och kolumnantal.  
- Varför det är viktigt att växla *Compact* (Truncate)-alternativet för tät data.  
- Hur du sparar streckkoden som PNG och verifierar resultatet.  

Ingen tidigare erfarenhet av streckkoder krävs; bara en grundläggande förståelse för C# och Visual Studio (eller någon annan IDE du föredrar). När du är klar har du en återanvändbar metod som du kan släppa in i vilket projekt som helst som behöver en PDF417‑bild.

## Förutsättningar

| Krav | Varför det är viktigt |
|------|-----------------------|
| .NET 6.0 eller senare (eller .NET Framework 4.7+) | Aspose.BarCode stödjer båda; nyare runtime ger bättre prestanda. |
| Visual Studio 2022 (eller VS Code med C#‑tillägg) | Ger IntelliSense och enkel felsökning. |
| Internetuppkoppling (för den första NuGet‑återställningen) | Biblioteket hämtas från NuGet.org. |
| Grundläggande C#‑kunskaper | Krävs för att förstå klassstrukturer och metodanrop. |

Om du redan har detta, toppen—låt oss dyka ner.

## Installera Aspose.BarCode NuGet‑paketet

Öppna din projektmapp i en terminal och kör:

```bash
dotnet add package Aspose.BarCode
```

Eller, i Visual Studio, högerklicka på **Dependencies → Manage NuGet Packages**, sök efter *Aspose.BarCode* och klicka på **Install**. Detta enkla kommando hämtar alla typer vi kommer att använda, inklusive `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`.

> **Pro tip:** Efter installationen, kör en clean och rebuild av lösningen för att säkerställa att assemblyn refereras korrekt.

## Generera PDF417‑streckkod – Setup och beroenden

Först och främst: vi behöver ett `using`‑block som importerar de relevanta namnutrymmena.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa namnrymden ger oss åtkomst till generator‑klassen och uppräkningen av streckkodstyper. Inget avancerat—bara tre rader, och vi är redo att börja skapa streckkoden.

## Skapa PDF417‑streckkod C# – Steg‑för‑steg‑implementation

Nedan finns ett **självständigt konsolprogram** som skapar en kompakt PDF417‑streckkod från strängen `"Åspóse.Barcóde©"` och sparar den som `CompactPdf417.png`. Byt gärna ut texten mot vad du än behöver; generatorn hanterar Unicode‑tecken direkt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Varför varje steg är viktigt

1. **Datadefinition** – PDF417 kan lagra upp till ~1850 tecken, men vi håller det kort för demonstrationen. Unicode‑stöd betyder att de accentuerade tecknen inte bryter något.  
2. **Generator‑konstruktion** – `EncodeTypes.Pdf417`‑enum‑värdet talar om för Aspose vilken symbologi som ska användas; byter du till `EncodeTypes.QR` får du en QR‑kod istället.  
3. **X‑dimension** – Detta styr bredden på varje modul (de små fyrkantiga delarna som utgör streckkoden). Ett värde på `2` pixlar ger en skarp bild som fortfarande är läsbar när den skrivs ut med 300 dpi.  
4. **PDF417‑alternativ** – `Columns` påverkar streckkodens bildförhållande; färre kolumner gör bilden högre, vilket kan vara användbart för kvitton. `Truncate` (även kallat *Compact mode*) tar bort start/stop‑mönster‑padding, minskar filstorleken utan att kompromissa med dataintegriteten.  
5. **Utskrifts‑sökväg** – Att använda `Environment.CurrentDirectory` säkerställer att bilden hamnar bredvid den körbara filen, vilket gör den lätt att hitta under utveckling.  
6. **Sparande** – `BarCodeImageFormat.Png` ger förlustfri kvalitet, perfekt för vidare bearbetning eller inbäddning i PDF‑filer.

Kör programmet (`dotnet run` eller tryck **F5** i Visual Studio). Efter några sekunder bör du se ett konsolmeddelande som bekräftar filens plats, och PNG‑filen kommer att dyka upp i din projektmapp.

![Generate PDF417 barcode example](generated-pdf417.png)

*Bildtext: generate pdf417 barcode example – PNG‑bild av en kompakt PDF417‑streckkod skapad med C#.*

## Konfigurera kompakt‑läge – c# barcode generator pdf417 Options

Om du behöver en större streckkod (kanske för avläsning på avstånd), justera egenskaperna `Columns` och `Rows`. Här är ett snabbt kodexempel som visar alternativa konfigurationer:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Vanlig fråga:** *Kommer inaktivering av Truncate att bryta befintliga läsare?*  
> Vanligtvis inte. De flesta moderna läsare förstår både full‑storlek och kompakt PDF417. Om du däremot riktar dig mot äldre hårdvara, låt `Truncate` vara `false`.

## Spara och verifiera – hur man genererar pdf417 barcode Output

Efter sparandet kan du öppna PNG‑filen i någon bildvisare. För att dubbelkolla att streckkoden kodar den avsedda datan, använd Asposes `BarCodeReader`:



> **Vanlig fråga:** *Kommer inaktivering av Truncate att bryta befintliga läsare?*  
> Vanligtvis inte. De flesta moderna läsare förstår både full‑storlek och kompakt PDF417. Om du däremot riktar dig mot äldre hårdvara, låt `Truncate` vara `false`.

## Vad du bör lära dig härnäst

De följande handledningarna täcker närliggande ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringssätt i dina egna projekt.

- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Lägg till streckkod i PDF med Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}