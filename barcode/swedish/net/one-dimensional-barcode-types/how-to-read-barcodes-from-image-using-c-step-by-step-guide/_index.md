---
category: general
date: 2026-11-14
description: Lär dig hur du läser streckkoder från en bild i C# med en komplett streckkodsläsarhandledning
  i C#. Inkluderar installation, fullständig kod och hantering av Macro PDF417‑fält.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: sv
lastmod: 2026-11-14
og_description: Läs streckkoder från bild i C# med den här streckkodsläsartutorialen
  c#. Få ett komplett fungerande exempel och lär dig att extrahera Macro PDF417‑data.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Läs streckkoder från en bild i C# – komplett handledning
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
title: Hur man läser streckkoder från bild med C# – steg‑för‑steg‑guide
url: /sv/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser streckkoder från bild med C# – steg‑för‑steg‑guide

Om du behöver **läsa streckkoder från bild** i en .NET‑applikation visar den här guiden exakt hur. I slutet av handledningen har du ett komplett, körbart program som extraherar både grundläggande streckkoddata och de Macro PDF417‑specifika fälten.

I den här **barcode reader tutorial c#** kommer vi att gå igenom projektuppsättning, det nödvändiga NuGet‑paketet och ett komplett kodexempel som fungerar med den senaste .NET 8 SDK. Inga externa tjänster behövs—allt körs lokalt.

## Vad du kommer att lära dig

- Hur du lägger till Aspose.BarCode (eller liknande) biblioteket i ett C#‑projekt.  
- Hur du skapar en `BarCodeReader` som riktar sig mot en specifik bildfil.  
- Hur du itererar genom alla upptäckta streckkoder och skriver ut deras typ, text och Macro PDF417‑metadata.  
- Tips för att hantera bilder med flera streckkoder eller olika avkodningstyper.

### Förutsättningar

- .NET 8 SDK (eller .NET 6+ om du föredrar) installerat.  
- Grundläggande kunskap om C#‑konsolapplikationer.  
- En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `MacroPdf417.png`).  

---

## Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal och kör:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Detta skapar en minimal konsolapp med namnet **BarcodeReaderDemo**. Projektfilen (`BarcodeReaderDemo.csproj`) kommer att användas i nästa steg.

## Steg 2: Installera biblioteket för streckkodsläsning

För den här handledningen använder vi **Aspose.BarCode for .NET**‑biblioteket eftersom det stödjer Macro PDF417 direkt ur lådan. Installera det via NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Varför detta bibliotek?** Det tillhandahåller en enda `BarCodeReader`‑klass, stödjer dussintals symbologier och exponerar `Extended`‑egenskapen som innehåller Macro PDF417‑fält.

## Steg 3: Skriv koden för streckkodsläsaren (barcode reader tutorial c#)

Byt ut innehållet i `Program.cs` mot följande kompletta exempel. Det demonstrerar **hur man läser streckkoder från bild** och skriver ut både generisk och Macro PDF417‑specifik information.

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

### Förklaring av varje steg

| Steg | Varför det är viktigt |
|------|-----------------------|
| **1️⃣ Definiera bildsökväg** | Läsaren fungerar med en filsökväg eller ström. Att använda en relativ sökväg gör exemplet enkelt att kopiera‑klistra. |
| **2️⃣ Skapa BarCodeReader** | Genom att skicka `DecodeType.MacroPdf417` begränsas skanningen till den symbologin, vilket förbättrar hastigheten och säkerställer att `Extended`‑fältens värden fylls i. |
| **3️⃣ Iterera resultat** | En bild kan innehålla flera streckkoder; `foreach`‑loopen garanterar att vi fångar dem alla. |
| **4️⃣ Generisk utskrift** | `CodeTypeName` och `CodeText` är de vanligaste informationsdelarna som utvecklare behöver. |
| **5️⃣ Macro PDF417‑fält** | Macro PDF417 inbäddar ytterligare data (fil‑ID, segment‑ID, segment‑antal). Att komma åt `result.Extended.Pdf417` ger dig dessa värden utan extra parsning. |
| **6️⃣ Valfria extra fält** | Biblioteket exponerar andra macro‑fält (t.ex. `MacroPdf417FileName`). Du kan utöka utskriften efter ditt användningsfall. |
| **7️⃣ Håll konsolen öppen** | Användbart när du kör från Visual Studio eller `dotnet run` för att se utskriften innan fönstret stängs. |

## Steg 4: Kör programmet och verifiera utskriften

Placera din `MacroPdf417.png`‑fil i mappen som refereras av `imagePath`. Kör sedan:

```bash
dotnet run
```

Typisk konsolutskrift ser ut så här:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Om bilden innehåller flera Macro PDF417‑symboler kommer programmet att lista varje uppsättning värden i följd.

## Vanliga variationer och kantfall

### Läsa andra symbologier

Om du behöver **läsa streckkoder från bild** som inte är Macro PDF417, ersätt `DecodeType.MacroPdf417` med en kommaseparerad lista, t.ex.:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

`Extended`‑egenskapen kommer att vara `null` för symbologier som inte tillhandahåller extra data, så kontrollera alltid `null` innan du använder den.

### Hantera stora bilder

Stora PNG‑ eller JPEG‑filer kan öka minnesanvändningen. För att hålla processen lättviktig kan du skala ner bilden innan du skickar den till `BarCodeReader`:

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

### Arbeta med strömmar istället för filsökvägar

När bilden kommer från en databas eller en webbförfrågan, skicka en `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Pro‑tips för en smidig streckkodsläsarupplevelse

- **Pro‑tips:** Ange alltid `DecodeType` till den smalaste uppsättningen av symbologier du förväntar dig. Detta minskar falska positiver och snabbar upp bearbetningen.  
- **Se upp för:** Bilder med låg kontrast eller hög kompression kan leda till missade avläsningar. Förprocessa bilden (justera ljusstyrka/kontrast) om du märker låg detekteringsgrad.  
- **Tips:** `BarCodeReader`‑klassen implementerar `IDisposable`; att använda ett `using`‑block garanterar att de inhemska resurserna frigörs omedelbart.  

---

## Slutsats

Du vet nu hur du **läser streckkoder från bild** i C# och extraherar både standard‑ och Macro PDF417‑specifik information. Denna **barcode reader tutorial c#** ger en komplett, fristående lösning som du kan lägga in i vilket .NET‑projekt som helst.

Från här kan du:

- Utforska andra avkodningstyper (QR, DataMatrix, Code128).  
- Integrera läsaren i ett ASP.NET Core‑API för att bearbeta uppladdningar i realtid.  
- Spara de extraherade macro‑fälten i en databas för senare aggregering.

Lycka till med kodandet, och känn dig fri att experimentera med olika bildkällor och streckkodformat!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man avkodar PDF417‑streckkoder i C# och läser streckkodsbilder i C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [Hur man läser streckkod från bild c# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}