---
category: general
date: 2026-08-15
description: Läs streckkod från bild i C# med BarCodeReader. Lär dig hur du läser
  flera streckkoder i C#, läser PDF417‑streckkod och ser ett komplett C# BarCodeReader‑exempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: sv
lastmod: 2026-08-15
og_description: Läs streckkod från bild i C# med en steg‑för‑steg‑guide. Upptäck hur
  du läser flera streckkoder i C#, avkodar PDF417‑symboler och kör ett komplett C#
  BarCodeReader‑exempel.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Läs streckkod från bild i C# – BarCodeReader-handledning
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Läs streckkod från bild i C# – BarCodeReader-handledning
url: /sv/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs streckkod från bild i C# – BarCodeReader‑handledning

Om du behöver **läsa streckkod från bild** i en .NET‑applikation visar den här guiden exakt hur du gör det med `BarCodeReader`‑klassen. Du får också se hur du **läser flera streckkoder C#**, avkodar en PDF417‑symbol och får ett komplett **C# BarCodeReader‑exempel** som du kan kopiera in i ditt projekt.

Handledningen täcker varje steg—från att lägga till det nödvändiga NuGet‑paketet till att skriva ut utökade PDF417‑fält—så att du slutar med ett körbart konsolprogram. Ingen extern dokumentation behövs; all kod och alla förklaringar ingår.

## Vad du behöver

* .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
* Visual Studio 2022 eller någon C#‑kompatibel editor
* `Aspose.BarCode` NuGet‑paketet (eller motsvarande bibliotek som tillhandahåller `BarCodeReader`)
* En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`)

Att ha dessa förutsättningar säkerställer att exempelprogrammet kompileras utan ytterligare konfiguration.

## Läs streckkod från bild med BarCodeReader

Det första steget är att skapa en `BarCodeReader`‑instans som pekar på bildfilen och talar om för biblioteket vilken streckkodstyp som ska sökas.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Varför detta fungerar:**  
`BarCodeReader` öppnar bilden, skannar efter den angivna `DecodeType` och returnerar en samling av `BarCodeResult`‑objekt. Varje resultat innehåller den generiska streckkodsdata (`CodeTypeName`, `CodeText`) och, för Macro PDF417, ett `Extended.Pdf417`‑objekt som visar alla extra fält som definieras av standarden.

## Läs flera streckkoder C# i en enda bild

Ibland innehåller en bild mer än en streckkod (t.ex. en QR‑kod bredvid en PDF417). För att hantera det scenariot, utelämna helt enkelt den explicita `DecodeType` eller skicka `DecodeType.AllSupported` och loopa igenom resultaten.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Varför du behöver detta:**  
Att specificera `AllSupported` instruerar motorn att prova alla streckkodformat den känner till, vilket garanterar att du fångar varje symbol i bilden. Detta är den rekommenderade metoden när du inte kan förutsäga streckkodstyperna i förväg.

## Hur du läser PDF417‑streckkod med C#

Om du bara är intresserad av det klassiska PDF417‑formatet (utan macro), ändra `DecodeType` till `Pdf417`. Resten av koden förblir identisk, förutom att de utökade fälten inte är tillgängliga.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Varför detta är viktigt:**  
Klassisk PDF417 visar inte de macro‑specifika egenskaperna, så `Extended.Pdf417`‑blocket är onödigt. Att använda den exakta `DecodeType` snabbar också upp skanningen eftersom biblioteket hoppar över icke‑stödda algoritmer.

## Fullständigt C# BarCodeReader‑exempel du kan kopiera

Nedan är det kompletta programmet som kombinerar de tre scenarierna till ett enda, lätt‑att‑köra konsolprogram. Ersätt `YOUR_DIRECTORY/ExtPDF417Meta.png` med den faktiska sökvägen till din bild.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Förväntad utdata

När exempelbilden innehåller en Macro PDF417‑streckkod skriver konsolen ut något liknande:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Om bilden bara innehåller en vanlig PDF417 kommer “Macro PDF417”‑avsnittet att vara tomt, och “Classic PDF417”‑avsnittet kommer att visa den avkodade texten.

## Slutsats

Du vet nu hur du **läser streckkod från bild** i C# med `BarCodeReader`, hur du **läser flera streckkoder C#** i en enda fil, och de exakta stegen för att **läsa PDF417‑streckkod**—både macro‑ och klassiska varianter. Det fullständiga **C# BarCodeReader‑exemplet** är redo att klistras in i vilket .NET‑projekt som helst, och du kan utöka det för att hantera andra format eller integrera det i en större bild‑behandlingspipeline.

**Nästa steg**

* Utforska felhanteringsmönster såsom `try / catch` runt läsarblocket.  
* Experimentera med `ReaderParameters`‑objektet för att finjustera detekteringshastighet och noggrannhet.  
* Kombinera streckkodsläsning med bild‑förbehandlingsbibliotek (

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Läs DataMatrix‑streckkod C# – Generera DataMatrix‑läge (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Läs streckkod från bild – Mästra extrahering av streckkodsområde i Java med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}