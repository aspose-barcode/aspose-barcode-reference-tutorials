---
category: general
date: 2026-10-18
description: Lär dig hur du läser streckkoder från en bild i C# med Aspose.BarCode,
  inklusive extrahering av Macro PDF417‑metadata och komplett exempelprogram.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: sv
lastmod: 2026-10-18
og_description: Hur man läser streckkod från en bild med C# Aspose.BarCode. Följ den
  här steg‑för‑steg‑handledningen för att extrahera Macro PDF417-metadata och hantera
  vanliga scenarier.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Hur man läser streckkod från bild i C# – komplett guide för Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man läser streckkod från bild i C# med Aspose.BarCode
url: /sv/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser streckkod från bild i C# med Aspose.BarCode

Om du behöver **hur man läser streckkod från bild** i en .NET‑applikation visar den här guiden de exakta stegen med Aspose.BarCode. Oavsett om du bearbetar skannade dokument, kvitton eller lageretiketter kommer du att se hur du läser streckkoden, hämtar Macro PDF417‑metadata och hanterar vanliga kantfall.

Att läsa en streckkod från en bild är en rutinuppgift, men att extrahera de utökade Macro PDF417‑fälten lägger till ett lager av komplexitet. Denna handledning täcker hela arbetsflödet, från projektuppsättning till ett fullt körbart exempel, så att du kan kopiera‑klistra koden och se omedelbara resultat.

## Vad du kommer att lära dig

- Hur du konfigurerar Aspose.BarCode för C#‑projekt.  
- Det korrekta sättet att instansiera **C# barcode reader** för en Macro PDF417‑bild.  
- Hur du itererar över varje upptäckt streckkod och skriver ut grundläggande information.  
- Hur du får åtkomst till **Macro PDF417 metadata** såsom fil‑ID, segment‑ID och kontrollsumma.  
- Tips för att hantera saknad metadata, stora bilder och vanliga avkodningsfel.  

**Förutsättningar**

- .NET 6.0 (eller senare) installerat.  
- Grundläggande kunskap om C# och Visual Studio (vilken IDE som helst fungerar).  
- En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`).  

## Steg 1: Installera Aspose.BarCode

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet innehåller **BarCodeReader class**, som implementerar **C# barcode reader**‑funktionaliteten som behövs för den här handledningen.

## Steg 2: Ställ in utvecklingsmiljön

Skapa en ny konsolapplikation om du inte redan har en:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Lägg till `using`‑direktiven högst upp i `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Dessa namnrymder exponerar **BarCodeReader class** och `DecodeType`‑enumerationen som krävs för Macro PDF417‑avkodning.

## Steg 3: Initiera BarCodeReader för Macro PDF417

Kärnan i **hur man läser streckkod från bild** är att skapa en `BarCodeReader`‑instans som riktar in sig på den specifika `DecodeType`. För Macro PDF417 måste du skicka `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Varför detta är viktigt:**  
Genom att välja `DecodeType.MacroPdf417` talar du om för biblioteket att leta efter det utökade Macro PDF417‑formatet, som innehåller extra fält utöver de grundläggande streckkodsdata. Om du använder en generisk `DecodeType.Pdf417` skulle dessa extra fält ignoreras.

## Steg 4: Iterera över upptäckta streckkoder

En enda bild kan innehålla flera streckkoder. Metoden `ReadBarCodes()` returnerar en enumererbar samling av `BarCodeResult`‑objekt. Loopa igenom dem för att skriva ut varje streckkods grundläggande information:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` berättar exakt vilken streckkodssymbolik som används (t.ex. “MacroPdf417”), medan `CodeText` innehåller den avkodade strängen.

## Steg 5: Extrahera och visa Macro PDF417‑metadata

När streckkoden är en Macro PDF417 ger egenskapen `Extended.Pdf417` ett rikt urval av metadatafält. Åtkomst dem direkt som visas nedan:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Dessa fält ger dig allt du behöver för att återskapa den ursprungliga flerdelade filen, verifiera integriteten och koppla streckkoden till ett specifikt dokument eller avsändare.

### Förväntad konsolutdata

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Om bilden inte innehåller en Macro PDF417‑streckkod kommer `Extended.Pdf417`‑objektet att vara `null`. Skydda dig mot detta för att undvika `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Steg 6: Hantera vanliga fel och kantfall

### Stora bilder

Att läsa mycket stora bilder kan förbruka betydande minne. Använd `BarcodeReader`‑översättningen som accepterar `ReaderParameters` för att begränsa maximal bildstorlek:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Saknad eller korrupt metadata

Om någon av Macro‑fälten saknas returnerar motsvarande egenskap `null` eller `0`. Logga dessa fall och bestäm om streckkoden ska betraktas som ofullständig.

### Flera streckkodstyper i en bild

Om en bild kan innehålla andra streckkodformat kan du skicka en array av `DecodeType`‑värden:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Detta tillvägagångssätt håller logiken för **hur man läser streckkod från bild** flexibel utan att offra prestanda.

## Steg 7: Fullständig källkod

Nedan är det kompletta, färdiga programmet. Ersätt `YOUR_DIRECTORY/ExtPDF417Meta.png` med sökvägen till din egen bild.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Kör programmet med:

```bash
dotnet run
```

Du bör se streckkodstyp, avkodad text och alla tillgängliga Macro PDF417‑fält skrivna till konsolen.

## Slutsats

I den här handledningen lärde du dig **hur man läser streckkod från bild** med Aspose.BarCode för C#. Guiden täckte hur du konfigurerar **C# barcode reader**,

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Hur man skapar macro PDF417‑streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hur man läser PDF417‑streckkod i C# – komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}