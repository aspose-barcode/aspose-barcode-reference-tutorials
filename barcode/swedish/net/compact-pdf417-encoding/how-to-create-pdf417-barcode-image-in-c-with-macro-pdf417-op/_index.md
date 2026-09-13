---
category: general
date: 2026-09-13
description: Lär dig hur du skapar PDF417‑streckkodbild i C# med BarcodeGenerator
  och Macro PDF417‑alternativ. Steg‑för‑steg‑kod, tips och fullständigt exempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: sv
lastmod: 2026-09-13
og_description: Skapa en PDF417‑streckkodsbild i C# med BarcodeGenerator. Följ den
  här detaljerade handledningen för att konfigurera Macro PDF417‑alternativ och spara
  en PNG‑streckkod.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Skapa PDF417‑streckkodsbild i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Hur man skapar en PDF417‑streckkodsbild i C# med Macro PDF417‑alternativ
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417‑streckkodsbild i C# med Macro PDF417‑alternativ

Om du behöver **skapa PDF417‑streckkodsbild** i C#, visar den här guiden exakt hur du gör det med **BarcodeGenerator‑klassen**. Oavsett om du bygger ett dokumentspårningssystem eller kodar stora filer, täcker steg‑för‑steg‑instruktionerna nedan allt från att konfigurera Macro PDF417‑alternativ till att spara den slutgiltiga PNG‑filen.

Att generera en streckkod är enkelt när du förstår de viktigaste parametrarna. I den här handledningen kommer du att lära dig hur du:

* Initierar en `BarcodeGenerator` för **Macro PDF417**.  
* Justerar streckkodens modulstorlek (`XDimension`).  
* Konfigurerar segment‑specifika inställningar såsom fil‑ID, segment‑ID och kontrollsumma.  
* Sparar resultatet som ett **streckkodsbildformat** (PNG) som kan visas i vilket UI som helst.

Det enda förutsättningen är en .NET‑utvecklingsmiljö (Visual Studio 2022 eller senare) och Aspose.BarCode för .NET‑NuGet‑paketet, som tillhandahåller `BarcodeGenerator`‑API‑t som används i exemplen.

---

## Hur man skapar PDF417‑streckkodsbild i C# – översikt

Att skapa en PDF417‑streckkodsbild består av fyra logiska steg:

1. **Skapa generatorn** – instansiera `BarcodeGenerator` med `EncodeTypes.MacroPdf417` och den data du vill koda.  
2. **Definiera modulstorleken** – sätt `XDimension.Pixels` för att kontrollera den fysiska bredden på varje streckkodselement.  
3. **Konfigurera Macro PDF417‑alternativ** – ange kolumner, filidentifierare, segmentnummer och valfri kontrollsumma.  
4. **Spara streckkoden** – skriv den genererade bilden till disk med ett stödformat för **streckkodsbild** såsom PNG.

Varje steg förklaras i detalj nedan, med komplett, körbar C#‑kod.

---

## Steg 1: Initiera BarcodeGenerator för Macro PDF417

Den första raden skapar ett `BarcodeGenerator`‑objekt som vet att det måste producera en **Macro PDF417**‑streckkod. Konstruktorn tar två argument: kodningstypen och den råa datasträngen.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Varför detta är viktigt:**  
`EncodeTypes.MacroPdf417` talar om för biblioteket att behandla streckkoden som en multi‑segment‑behållare, vilket är avgörande när du behöver dela upp en stor fil i flera symboler. `BarcodeGenerator`‑instansen är disposable, så `using`‑blocket garanterar att alla ohanterade resurser frigörs efter att bilden har sparats.

---

## Steg 2: Ställ in streckkodens modulstorlek (XDimension)

`XDimension` styr pixelbredden på en enskild streckkodmodul (det minsta svarta eller vita strecket). Ett värde på **2 pixlar** ger en kompakt men läsbar bild.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktiskt tips:**  
Om din mål‑skrivare har låg DPI, öka pixelantalet (t.ex. `3` eller `4`) för att undvika utsmetning. Om du däremot visar på skärm kan du hålla det lågt för att minska filstorleken.

---

## Steg 3: Konfigurera Macro PDF417‑specifika alternativ

Macro PDF417 lägger till metadata som gör det möjligt för en scanner att återskapa den ursprungliga filen från flera streckkodsegment. De vanligaste alternativen är:

| Egenskap | Betydelse |
|----------|-----------|
| `Columns` | Antal kolumner i varje symbol (påverkar bredd). |
| `MacroPdf417FileID` | Unik identifierare för hela filen. |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 1). |
| `MacroPdf417SegmentsCount` | Totalt antal segment som utgör filen. |
| `MacroPdf417FileName` | Ursprungligt filnamn (valfritt, för visning). |
| `MacroPdf417Checksum` | Valfri 16‑bits kontrollsumma för integritetsverifiering. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Varför dessa inställningar är viktiga:**  
- **Columns** påverkar läsbarhet och bildens totala dimensioner.  
- **FileID** måste vara densamma i alla segment så att dekodern vet att de hör ihop.  
- **SegmentID** och **SegmentsCount** låter scannern sortera delarna korrekt.  
- **FileName** och **Checksum** är valfria men förbättrar användarupplevelsen och dataintegriteten.

**Edge case:** Om du genererar mer än 999 segment, överskrider `SegmentID`‑fältet sitt intervall; dela då upp datan i flera filer istället.

---

## Steg 4: Spara den genererade streckkoden som en PNG‑bild

Det sista steget skriver streckkoden till disk. `BarCodeImageFormat.Png` ger en förlustfri bild som fungerar på webb, skrivbord och mobila plattformar.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Alternativa format:**  
Du kan ersätta `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` om ditt efterföljande system kräver ett specifikt format. Tänk på att JPEG introducerar komprimeringsartefakter som kan minska skanningspålitligheten.

**Förväntad utdata:**  
Filen `MacroPdf417.png` kommer att innehålla en högkontrast‑, multi‑segment‑PDF417‑streckkod. När den öppnas bör den se liknande ut som illustrationen nedan.

![Create PDF417 barcode image example](image.png){: .align-center alt="Create PDF417 barcode image example generated by C# code"}

---

## Fullständig källkod – redo att kopiera och köra

Nedan är det kompletta, självständiga programmet. Det innehåller de nödvändiga `using`‑direktiven, `Main`‑metoden och kommentarer som förklarar varje icke‑uppenbar rad.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Kör programmet:**  

1. Skapa ett nytt .NET 6 (eller senare) konsolprojekt.  
2. Lägg till Aspose.BarCode‑NuGet‑paketet (`dotnet add package Aspose.BarCode`).  
3. Ersätt den genererade `Program.cs` med koden ovan.  
4. Anpassa `outputPath` till en mapp du har skrivbehörighet till.  
5. Bygg och kör – konsolen bekräftar bildens plats.

---

## Vanliga frågor & felsökning

| Fråga | Svar |
|-------|------|
| *Vad gör jag om streckkoden är för bred för min etikett?* | Minska `Columns` eller öka `XDimension.Pixels` för att balansera bredd och läsbarhet. |
| *Behöver jag ange en kontrollsumma?* | Kontrollsumman är valfri |

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [Skapa PDF417‑streckkod i C# – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Skapa PDF417‑streckkodmetadata i C# – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generera streckkod med text – Full PDF417 Macro‑guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}