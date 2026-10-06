---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# låter dig lägga till makrodata och generera
  PDF417‑streckkoder utan ansträngning. Lär dig steg för steg hur du lägger till makrometadata
  och skapar en PDF417‑bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: sv
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# visar hur du lägger till makrometadata
  och genererar en PDF417‑streckkod med några få kodrader.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – lägg till makro och generera PDF417-streckkod
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Hur man använder Aspose Barcode Generator C# för en MacroPdf417‑streckkod
url: /sv/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder Aspose Barcode Generator C# för en MacroPdf417-streckkod

Om du behöver skapa en MacroPdf417-streckkod i C#, **Aspose Barcode Generator C#** tillhandahåller ett koncist API som hanterar både streckkodsbilden och den nödvändiga makro‑metadata. Den här handledningen visar exakt hur du lägger till makroinformation och genererar en PDF417‑streckkodsbild på bara några steg.

Du kommer att lära dig hur du konfigurerar visuella parametrar, bäddar in makrofält såsom fil‑ID och tidsstämpel, och sparar resultatet som en PNG. Inga externa verktyg krävs – bara Aspose.BarCode‑biblioteket och en .NET‑utvecklingsmiljö.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* Visual Studio 2022 (eller någon C#‑IDE)  
* En licensierad eller utvärderingskopi av **Aspose.BarCode for .NET**  

Koden fungerar på Windows, Linux och macOS eftersom biblioteket är plattformsoberoende.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Öppna ditt projekt i Visual Studio och kör sedan följande kommando i **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Detta lägger till `Aspose.BarCode`‑assemblyn och dess beroenden i ditt projekt.

## Steg 2: Skapa ett barcode‑generator‑objekt

Den första raden skapar ett `BarcodeGenerator`‑objekt för **MacroPdf417**‑symbologin och anger den text du vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Varför detta är viktigt*: Värdet `EncodeTypes.MacroPdf417` talar om för biblioteket att förvänta sig makrorelaterade fält, vilka du kommer att ange i nästa steg.

## Steg 3: Definiera visuell utformning

Du kan kontrollera storleken på varje modul (den minsta svarta eller vita fyrkanten) och antalet kolumner i PDF417‑matrisen. Att justera `XDimension` påverkar den övergripande bildupplösningen.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Att öka `Columns` minskar streckkodens höjd, medan en större `XDimension` gör bilden tydligare på hög‑DPI‑skärmar.

## Steg 4: Lägg till makro‑metadata (hur man lägger till makro)

MacroPdf417 kräver flera ytterligare fält som beskriver källfilen och dess segmentering. Följande egenskaper motsvarar direkt PDF417‑makrospecifikationerna:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Varför dessa fält*:  
* `MacroPdf417FileID` binder alla segment tillsammans och säkerställer att en scanner kan återmontera originaldokumentet.  
* `MacroPdf417SegmentID` och `MacroPdf417SegmentsCount` låter avkodaren veta ordningen och det totala antalet delar.  
* `MacroPdf417FileSize` och `MacroPdf417Checksum` ger integritetskontroller, vilket är värdefullt för stora dataöverföringar.

## Steg 5: Spara streckkodsbilden (hur man genererar pdf417)

Till sist skriver du streckkoden till disk. Metoden `Save` accepterar en filsökväg och ett bildformat. PNG bevarar de skarpa kanterna på streckkoden utan komprimeringsartefakter.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

När programmet körs hittar du **ExtPDF417Meta.png** i output‑mappen. När du öppnar bilden visas en ren MacroPdf417‑streckkod klar för utskrift eller inbäddning i en PDF.

### Förväntat resultat

| Filnamn            | Format | Dimensioner (ungefär) |
|--------------------|--------|------------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (varierar med `XDimension`) |

Att skanna bilden med en PDF417‑kompatibel läsare (t.ex. ZXing, Aspose.BarCode for .NET) returnerar den ursprungliga texten **“Åspóse.Barcóde©”** tillsammans med alla makrofält.

## Vanliga fallgropar och hur du undviker dem

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| **Felaktig `EncodeTypes`** | Att använda `EncodeTypes.Pdf417` istället för `EncodeTypes.MacroPdf417` inaktiverar makrofält. | Instansiera alltid generatorn med `EncodeTypes.MacroPdf417`. |
| **Saknade makrofält** | Vissa scanners ignorerar streckkoden om obligatoriska makrofält utelämnas. | Fyll i minst `FileID`, `SegmentID`, `SegmentsCount` och `Terminator`. |
| **För liten `XDimension`** | Ett värde under 1 pixel kan ge en oläslig streckkod på lågupplösta skärmar. | Behåll `XDimension` ≥ 2 pixel för de flesta skärm‑ och utskrifts scenarier. |
| **Filsökvägsfel** | Att ange en relativ sökväg som inte finns kastar ett undantag. | Använd `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` eller en absolut sökväg. |

## Fullständig källkod

Nedan är det kompletta, körbara exemplet som du kan kopiera in i ett nytt konsolprojekt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Kör programmet (`dotnet run`). Efter körning skriver konsolen ut ett lyckat meddelande och PNG‑filen visas i projektets output‑mapp.

## Nästa steg

* **Koda större data** – Öka `Columns` eller justera `Rows` (via `Pdf417.Rows`) för att rymma fler tecken.  
* **Bädda in i PDF** – Använd Aspose.PDF för att placera den genererade PNG‑filen i ett dokument.  
* **Skanningsverifiering** – Använd `Aspose.BarCode.Reader` för att avkoda streckkoden och bekräfta makrofält programatiskt.  

Att utforska dessa ämnen fördjupar din förståelse för **hur man genererar PDF417**‑streckkoder med rik makroinformation och förbereder dig för verkliga användningsfall som batch‑dokumentbehandling eller säker datautbyte.

---

*Lycklig kodning! Om du fann den här guiden användbar, överväg att dela den med kollegor eller ge ett stjärnmärke till Aspose.BarCode‑repo på GitHub.*

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig behärska ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar macro PDF417-streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hur man genererar PDF417-streckkod i C# med Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode‑exempel: generera Macro PDF417 i C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}