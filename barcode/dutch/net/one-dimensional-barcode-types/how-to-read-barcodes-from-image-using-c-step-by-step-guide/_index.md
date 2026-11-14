---
category: general
date: 2026-11-14
description: Leer hoe je barcodes uit een afbeelding kunt lezen in C# met een volledige
  barcode‑lezer tutorial C#. Inclusief installatie, volledige code en het verwerken
  van Macro PDF417‑velden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: nl
lastmod: 2026-11-14
og_description: Lees barcodes van een afbeelding in C# met deze barcodelezer‑tutorial
  c#. Krijg een volledig werkend voorbeeld en leer hoe je Macro PDF417‑gegevens kunt
  extraheren.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Barcodes lezen uit afbeelding in C# – volledige tutorial
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Hoe barcodes uit een afbeelding lezen met C# – stap‑voor‑stap gids
url: /nl/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcodes uit een afbeelding lezen met C# – stapsgewijze handleiding

Als je **barcodes uit een afbeelding wilt lezen** in een .NET‑applicatie, laat deze gids je precies zien hoe. Aan het einde van de tutorial heb je een compleet, uitvoerbaar programma dat zowel de basis‑barcode‑gegevens als de Macro PDF417‑specifieke velden extraheert.

In deze **barcode reader tutorial c#** behandelen we het project‑setup, het benodigde NuGet‑pakket, en een volledige code‑voorbeeld dat werkt met de nieuwste .NET 8 SDK. Er zijn geen externe services nodig—alles draait lokaal.

## Wat je zult leren

- Hoe je de Aspose.BarCode (of een vergelijkbare) bibliotheek toevoegt aan een C#‑project.  
- Hoe je een `BarCodeReader` maakt die zich richt op een specifiek afbeeldingsbestand.  
- Hoe je door alle gedetecteerde barcodes itereren en hun type, tekst en Macro PDF417‑metadata weergeeft.  
- Tips voor het omgaan met afbeeldingen met meerdere barcodes of verschillende decodeertypen.

### Vereisten

- .NET 8 SDK (of .NET 6+ als je dat verkiest) geïnstalleerd.  
- Basiskennis van C# console‑applicaties.  
- Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (bijv. `MacroPdf417.png`).  

---

## Stap 1: Een nieuw console‑project opzetten

Open een terminal en voer uit:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Dit maakt een minimale console‑app met de naam **BarcodeReaderDemo**. Het project‑bestand (`BarcodeReaderDemo.csproj`) wordt in de volgende stap gebruikt.

## Stap 2: Installeer de barcode‑lezen bibliotheek

Voor deze tutorial gebruiken we de **Aspose.BarCode for .NET** bibliotheek omdat deze Macro PDF417 direct ondersteunt. Installeer deze via NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Waarom deze bibliotheek?** Het biedt een enkele `BarCodeReader`‑klasse, ondersteunt tientallen symbologieën, en maakt de `Extended`‑eigenschap beschikbaar die Macro PDF417‑velden bevat.

## Stap 3: Schrijf de barcode‑lezer code (barcode reader tutorial c#)

Vervang de inhoud van `Program.cs` door het volgende volledige voorbeeld. Het demonstreert **hoe barcodes uit een afbeelding te lezen** en print zowel generieke als Macro PDF417‑specifieke informatie.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Uitleg van elke stap

| Stap | Waarom het belangrijk is |
|------|--------------------------|
| **1️⃣ Define image path** | De lezer werkt met een bestands‑pad of stream. Het gebruik van een relatief pad maakt het voorbeeld eenvoudig te kopiëren‑plakken. |
| **2️⃣ Create BarCodeReader** | Het doorgeven van `DecodeType.MacroPdf417` beperkt de scan tot die symbologie, wat de snelheid verbetert en ervoor zorgt dat de `Extended`‑velden worden gevuld. |
| **3️⃣ Iterate results** | Een afbeelding kan meerdere barcodes bevatten; de `foreach`‑lus garandeert dat we ze allemaal vastleggen. |
| **4️⃣ Generic output** | `CodeTypeName` en `CodeText` zijn de meest voorkomende informatie die ontwikkelaars nodig hebben. |
| **5️⃣ Macro PDF417 fields** | Macro PDF417 voegt extra gegevens toe (bestand‑ID, segment‑ID, aantal segmenten). Toegang tot `result.Extended.Pdf417` levert deze waarden zonder extra parsing. |
| **6️⃣ Optional extra fields** | De bibliotheek biedt andere macro‑velden (bijv. `MacroPdf417FileName`). Je kunt de output uitbreiden zoals jouw use‑case vereist. |
| **7️⃣ Keep console open** | Handig bij het uitvoeren vanuit Visual Studio of `dotnet run` om de output te zien voordat het venster sluit. |

## Stap 4: Voer het programma uit en controleer de output

Plaats je `MacroPdf417.png`‑bestand in de map die wordt aangeduid door `imagePath`. Voer vervolgens uit:

```bash
dotnet run
```

Typische console‑output ziet er als volgt uit:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Als de afbeelding meerdere Macro PDF417‑symbolen bevat, zal het programma elke set waarden opeenvolgend weergeven.

## Veelvoorkomende variaties en randgevallen

### Andere symbologieën lezen

Als je **barcodes uit een afbeelding wilt lezen** die geen Macro PDF417 zijn, vervang je `DecodeType.MacroPdf417` door een door komma’s gescheiden lijst, bijvoorbeeld:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

De `Extended`‑eigenschap zal `null` zijn voor symbologieën die geen extra data leveren, controleer dus altijd op `null` voordat je er toegang toe krijgt.

### Grote afbeeldingen verwerken

Grote PNG‑ of JPEG‑bestanden kunnen het geheugenverbruik verhogen. Om het proces lichtgewicht te houden, kun je de afbeelding verkleinen voordat je deze aan `BarCodeReader` doorgeeft:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Werken met streams in plaats van bestands‑paden

Wanneer de afbeelding uit een database of een web‑request komt, geef je een `Stream` door:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Pro‑tips voor een soepele barcode‑lezer ervaring

- **Pro tip:** Stel `DecodeType` altijd in op de kleinste set symbologieën die je verwacht. Dit vermindert valse positieven en versnelt de verwerking.  
- **Let op:** Afbeeldingen met laag contrast of zware compressie kunnen gemiste lezingen veroorzaken. Pre‑process de afbeelding (pas helderheid/contrast aan) als je lage detectieratio's merkt.  
- **Tip:** De `BarCodeReader`‑klasse implementeert `IDisposable`; het gebruik van een `using`‑blok garandeert dat de native resources tijdig worden vrijgegeven.  

---

## Conclusie

Je weet nu hoe je **barcodes uit een afbeelding kunt lezen** in C# en zowel standaard als Macro PDF417‑specifieke informatie kunt extraheren. Deze **barcode reader tutorial c#** biedt een complete, zelfstandige oplossing die je in elk .NET‑project kunt gebruiken.

Vanaf hier kun je:

- Andere decodeertypen verkennen (QR, DataMatrix, Code128).  
- De lezer integreren in een ASP.NET Core API om uploads direct te verwerken.  
- De geëxtraheerde macro‑velden opslaan in een database voor latere aggregatie.

Veel programmeerplezier, en voel je vrij om te experimenteren met verschillende afbeeldingsbronnen en barcode‑formaten!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 barcodes te decoderen in C# en barcode‑afbeelding te lezen C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [Hoe barcode van afbeelding te lezen c# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Barcode van afbeelding lezen C# – complete gids met Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}