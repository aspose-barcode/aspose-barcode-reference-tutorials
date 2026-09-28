---
category: general
date: 2026-07-18
description: Generera micro‑pdf417‑streckkod med Aspose.BarCode för .NET – steg‑för‑steg‑guide
  som täcker kolumner, rader och PNG‑utdata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: sv
lastmod: 2026-07-18
og_description: Skapa mikro‑pdf417‑streckkod omedelbart med Aspose.BarCode för .NET.
  Lär dig hur du styr kolumner, rader och sparar som PNG på några minuter.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Generera Micro PDF417-streckkod – Fullständig C#-handledning
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generera Micro PDF417‑streckkod i C# – Komplett guide
url: /sv/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera Micro PDF417-streckkod i C# – Komplett guide

Har du någonsin undrat hur man **genererar micro pdf417 barcode** direkt från din C#-applikation? Du är inte ensam. Oavsett om du märker inventarier, kodar korta URL:er eller bygger en anpassad skanningslösning, kan behärskning av denna lilla men kraftfulla 2‑D-kod spara dig mycket krångel.

I den här handledningen går vi igenom ett verkligt exempel med **Aspose.BarCode for .NET**, och visar dig hur du justerar kolumner, rader och modulstorlek, och sedan sparar resultatet till en PNG‑fil. När du är klar har du en färdigkörbar konsolapp som skapar tre olika streckkods‑bilder—ingen gåta kvar.

## Vad du behöver

- .NET 6 eller senare (koden fungerar även på .NET Framework 4.7+)
- Visual Studio 2022 (eller någon C#‑IDE du föredrar)
- NuGet‑paketet **Aspose.BarCode** (`Aspose.BarCode`)
- En skrivbar mapp på disken för utdata‑PNG‑filerna

Om du redan har dem, bra—låt oss dyka ner.

## Steg 1: Skapa projektet och installera Aspose.BarCode

Först, skapa ett nytt konsolprojekt:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Proffstips:** Kör `dotnet restore` efter att ha lagt till paketet för att säkerställa att alla beroenden är lösta.

Öppna nu `Program.cs`. Vi börjar med att importera de nödvändiga namnutrymmena:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Dessa två `using`‑satser ger oss åtkomst till `BarcodeGenerator`, `EncodeTypes` och bildformat‑enum som vi kommer att behöva senare.

## Steg 2: Initiera MicroPdf417‑generatorn

Kärnan i operationen är `BarcodeGenerator`‑objektet. Vi matar det med **MicroPdf417**‑kodningstypen och den text vi vill koda—i vårt fall ordet “ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Varför `MicroPdf417`? Jämfört med den fullstora PDF417 packar den mikroa versionen mer data i ett mindre utrymme, perfekt för etiketter med begränsat utrymme.

## Steg 3: Justera modulstorleken (X‑Dimension)

Modulstorleken bestämmer hur många pixlar varje liten ruta i streckkoden upptar. Ett värde på **2 pixlar** ger en skarp, läsbar bild utan att filstorleken blåser upp.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Obs:** Om du behöver en större streckkod för avlägsen skanning, öka detta tal till 3 eller 4.

## Steg 4: Generera streckkoder med olika kolumn-/radkonfigurationer

### 4.1 Två kolumner, automatiskt beräknade rader

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Sex rader, automatiskt beräknade kolumner

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Fyra kolumner × åtta rader (fullt specificerade)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Varje `Save`‑anrop skriver en PNG‑fil till projektets arbetskatalog. Du kan gärna ändra sökvägen (`"YOUR_DIRECTORY/..."`) till något som `Path.Combine(Environment.CurrentDirectory, "output")` om du föredrar en dedikerad mapp.

## Steg 5: Fullt fungerande exempel

Sätter vi ihop allt, här är det kompletta, kopiera‑och‑klistra‑klara programmet:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Förväntat resultat

När programmet körs skapas tre PNG‑filer:

| Filnamn | Ungefärliga dimensioner (px) | Visuell indikation |
|-----------|----------------------------|--------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Smal, högre streckkod |
| `MicroPdf417Rows6.png` | 120 × 180 | Bredare, kortare streckkod |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Något fyrkantig, balanserad layout |

Öppna någon av dem i en bildvisare—du kommer att se en skarp **Micro PDF417**‑streckkod redo för skanning.

## Vanliga frågor & specialfall

- **Vad händer om utdatamappen inte finns?**  
  Anropa `Directory.CreateDirectory(path)` innan den första `Save` för att undvika ett `DirectoryNotFoundException`.

- **Kan jag ändra bildformatet?**  
  Absolut. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` efter behov.

- **Finns det en gräns för textlängden?**  
  MicroPdf417 kan koda upp till 1 KB data, men praktiska gränser beror på valda rader/kolumner. Om du får ett fel, öka antalet rader eller kolumner.

- **Hur bäddar jag in streckkoden i en PDF?**  
  Använd Aspose.Pdf för att infoga den genererade PNG‑filen, eller byt till `BarCodeImageFormat.Pdf` för direkt PDF‑output.

## Proffstips för C#‑streckkodsgenerering

1. **Cacha generatorn** när du behöver många streckkoder med samma inställningar—endast texten behöver ändras, vilket sparar CPU‑cykler.  
2. **Finjustera felkorrigeringen** via `generator.Parameters.Barcode.Pdf417.ErrorLevel` om din skanningsmiljö är bullrig.  
3. **Testa med riktiga skannrar** tidigt. Vissa handhållna enheter har problem med mycket täta mikro‑streckkoder; justering av `XDimension` kan göra stor skillnad.

## Slutsats

Du vet nu hur du **genererar micro pdf417 barcode** med **Aspose.BarCode for .NET**, manipulerar **MicroPdf417‑kolumner** och **MicroPdf417‑rader**, och sparar resultatet som PNG‑filer—allt från en enda, prydlig C#‑konsolapp. Experimentera med olika modulstorlekar, felnivåer eller till och med färgoutput för att passa ditt projekts behov.

Nästa steg kan vara att utforska **C# barcode generation** för andra symboler som QR, Code128 eller DataMatrix, eller att bädda in bilderna direkt i PDF‑filer med Aspose.Pdf. Himlen är gränsen när du har grunderna på plats.

Lycklig kodning, och må dina skanningar alltid vara felfria!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Skapa DotCode‑streckkodsbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generera DataMatrix‑streckkod – Pro‑guide med Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}