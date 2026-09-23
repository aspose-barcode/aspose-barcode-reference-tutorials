---
category: general
date: 2026-08-03
description: Läs PDF417‑streckkod från en bild med C# BarCodeReader – ett komplett
  streckkodsläsareexempel som också visar hur man läser flera streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: sv
lastmod: 2026-08-03
og_description: Läs PDF417‑streckkod snabbt med ett C# BarCodeReader‑exempel. Följ
  den här steg‑för‑steg‑guiden för att avkoda macro PDF417 och läsa flera streckkoder
  från en bild.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Läs PDF417-streckkod i C# – komplett exempel på streckkodsläsare
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Läs PDF417‑streckkod i C# – exempel på streckkodsläsare
url: /sv/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs PDF417-streckkod i C# – exempel på streckkodsläsare

Om du behöver läsa PDF417-streckkoddata från en bild visar den här guiden hur du gör det med **BarCodeReader**-klassen i C#. Du kommer att lära dig ett exempel på streckkodsläsare som även hanterar macro PDF417 och kan läsa flera streckkoder i en enda bild.

Att arbeta med streckkoder innebär ofta att hantera olika bildkällor, varierande ljusförhållanden och ibland sammansatta data såsom macro PDF417-segment. Denna handledning täcker allt du behöver för att avkoda en PDF417-streckkod, extrahera dess utökade fält och bearbeta flera streckkoder från samma bild. I slutet har du ett körbart konsolprogram som läser streckkoder från en bildfil och skriver ut detaljerad information till konsolen.

## Vad du behöver

* .NET 6.0 SDK eller senare installerat  
* En nyare version av **Aspose.BarCode for .NET** NuGet-paketet (eller något kompatibelt bibliotek som tillhandahåller `BarCodeReader` och `DecodeType.MacroPdf417`)  
* En bildfil som innehåller en PDF417- eller macro PDF417-streckkod (exemplet använder `ExtPDF417Meta.png`)  
* En kodredigerare eller IDE, till exempel Visual Studio 2022  

Inga ytterligare tjänster eller externa API:er krävs.

## Inställning av projektet för streckkodsläsning

1. **Skapa ett nytt konsolprojekt**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Lägg till streckkodsbiblioteket**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Kopiera streckkodsbilden**  

   Placera `ExtPDF417Meta.png` (eller någon bild som innehåller en PDF417-streckkod) i projektmappen.  
   För den här handledningen antar vi att filen finns på `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projektet är nu redo att kompileras och köra streckkodsläsar‑exemplet.

## Hur man läser PDF417-streckkod med BarCodeReader

Kärnan i lösningen är ett `using`-block som skapar en `BarCodeReader`-instans, specificerar `DecodeType.MacroPdf417` och itererar över varje upptäckt streckkod. Följande kod är ett komplett, fristående program som du kan klistra in i `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Varför detta fungerar**:  

* `DecodeType.MacroPdf417` talar om för läsaren att leta efter macro‑utökningen av PDF417, som innehåller ytterligare metadata såsom fil‑ID, segmentantal och tidsstämplar.  
* `using`‑satsen garanterar att ohanterade resurser (filhandtag, inhemska avkodningsbuffertar) frigörs omedelbart.  
* `foreach`‑loopen bearbetar automatiskt **alla** streckkoder som bilden innehåller, vilket uppfyller kravet på *läsa flera streckkoder*.

När du kör programmet (`dotnet run`) bör du se en utskrift som liknar följande:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Om bilden innehåller mer än en PDF417-streckkod skriver loopen ut ett separat block för varje streckkod, vilket demonstrerar hur man **läser flera streckkoder** från en enda bild.

## Läsa flera streckkoder från en bild

Samma `BarCodeReader`‑instans kan avkoda flera streckkodstyper samtidigt. För att bredda omfånget från endast macro PDF417 till vilken PDF417 som helst (eller till och med QR, Code128, etc.), justera `DecodeType`‑flaggan:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* är en bitmask, så du kan kombinera ett godtyckligt antal stödda format. Denna flexibilitet gör kodsnutten till ett **exempel på streckkodsläsare** som fungerar för en mängd olika användningsfall, såsom skanning av produktetiketter, biljetter eller ID‑kort.

## Att komma åt macro PDF417-fält på ett säkert sätt

Macro PDF417 lägger till en rik uppsättning utökade egenskaper. Dock innehåller inte varje streckkod alla fält. Att komma åt en saknad egenskap kan kasta ett `NullReferenceException`. Det säkraste tillvägagångssättet är att verifiera varje egenskap innan den skrivs ut:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Varför detta är viktigt*: I verkliga implementationer kan du få vanliga PDF417-streckkoder som saknar macro‑data. Den defensiva kontrollen säkerställer att din applikation fortsätter att köra utan att krascha.

## Vanliga fallgropar och bästa praxis

| Problem | Varför det händer | Rekommenderad åtgärd |
|-------|----------------|-----------------|
| Bildvägen är felaktig | `BarCodeReader` kastar ett file‑not‑found‑undantag innan någon avkodning sker | Använd `Path.Combine` och validera att filen finns med `File.Exists` |
| Lågupplöst bild | Avkodaren kan inte lokalisera streckkodens kanter, vilket resulterar i noll upptäckter | Tillhandahåll en minsta upplösning på 300 dpi för pålitliga resultat |
| Streckkod roterad > 45° | Många bibliotek antar vertikal orientering | Aktivera `reader.RecognitionOptions.RotateImage = true` om bilden är roterad |

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser DataMatrix-streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Läs DataMatrix-streckkod C# – Generera DataMatrix-läge (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Läs streckkod från bild – Mästra extrahering av streckkodsområden i Java med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}