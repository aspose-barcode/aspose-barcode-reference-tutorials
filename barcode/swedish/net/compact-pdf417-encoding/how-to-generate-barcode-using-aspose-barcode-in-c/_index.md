---
category: general
date: 2026-11-20
description: Lär dig hur du genererar streckkod med Aspose.Barcode i C#. Den här guiden
  visar dig hur du skapar en MicroPdf417‑streckkod och sparar den som en PNG‑bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: sv
lastmod: 2026-11-20
og_description: Hur man genererar en streckkod med Aspose.Barcode i C#. Följ den här
  kompletta handledningen för att skapa en MicroPdf417-streckkod och exportera den
  som PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Hur man genererar streckkod med Aspose.Barcode – steg‑för‑steg C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Hur man genererar streckkod med Aspose.Barcode i C#
url: /sv/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod med Aspose.Barcode i C#

Om du behöver **how to generate barcode** för en skrivbords- eller webbapplikation, erbjuder Aspose.Barcode ett enkelt API. Denna handledning visar exakt hur du genererar en MicroPdf417-streckkod, anpassar dess dimensioner och sparar resultatet som en PNG-fil. Du kommer också att se hur du **create barcode with Aspose** för andra format utan att lämna IDE:n.

Att generera en streckkod är ett vanligt krav för lagersystem, biljettplattformar och säkra dokumentarbetsflöden. I slutet av den här guiden har du ett körbart program som producerar en högkvalitativ streckkodsbild klar för utskrift eller inbäddning.

## Vad du behöver

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 (eller någon C#-redigerare)
* En giltig licens för Aspose.Barcode för .NET – den kostnadsfria provversionen fungerar för utveckling och testning
* Grundläggande kunskap om C#-syntax

Inga ytterligare NuGet‑paket krävs utöver `Aspose.Barcode`.

## Så genererar du streckkod med Aspose.Barcode

Följande avsnitt delar upp processen i separata steg. Varje steg förklarar **why** koden är nödvändig, inte bara **what** den gör.

### Steg 1: Installera Aspose.Barcode NuGet‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.Barcode
```

Detta kommando lägger till den senaste stabila versionen av Aspose.Barcode till din projektfil, vilket säkerställer att `BarcodeGenerator`‑klassen är tillgänglig vid kompilering.

**Why this matters:** Paketet innehåller kärnmotorn för rendering och en uppsättning fördefinierade `EncodeTypes`. Utan det kan kompilatorn inte lösa `BarcodeGenerator` eller `EncodeTypes`.

### Steg 2: Skapa en `BarcodeGenerator`‑instans för MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Why this matters:** Konstruktorn kopplar symbologin (`EncodeTypes.MicroPdf417`) till de råa data du vill koda. MicroPdf417 är idealisk när du behöver ett mindre fotavtryck än full PDF417 samtidigt som den stödjer alfanumeriska data.

### Steg 3: Justera X‑dimensionen (modulbredd)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** X‑dimensionen bestämmer storleken på varje streckkodscell. Ett värde som är för lågt ger en suddig bild; ett värde som är för högt gör streckkoden onödigt stor. Två pixlar är ett balanserat standardvärde för de flesta skärm‑ och utskrifts scenarier.

### Steg 4: Välj antal kolumner för PDF417‑komponenten

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Why this matters:** MicroPdf417 använder internt en PDF417‑komponent. Justering av kolumnantalet påverkar streckkodens bildförhållande och datakapacitet. Fyra kolumner ger en kompakt form samtidigt som läsbarheten bevaras.

### Steg 5: Spara streckkodsbilden

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Why this matters:** `Save` skriver den renderade streckkoden till disk. PNG är förlustfri, vilket behåller skarpa kanter som är viktiga för skannrar. Du kan ersätta `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` om ditt arbetsflöde kräver ett annat format.

### Fullständig källkod

Genom att samla alla steg får du en komplett, fristående konsolapplikation:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Kör programmet (`dotnet run`) så hittar du `MicroPdf417.png` på ditt skrivbord. När du öppnar filen visas en skarp MicroPdf417‑streckkod som kodar texten `"Åspóse.Barcóde©"`.

## Verifiera streckkoden

För att bekräfta att streckkoden genererades korrekt:

1. Öppna PNG-filen i någon bildvisare.
2. Använd en mobil streckkodsskannerapp som stödjer PDF417 eller MicroPdf417.
3. Skanna bilden; appen bör visa den ursprungliga texten, inklusive specialtecknen.

Om skannern misslyckas, kontrollera följande:

* **X‑dimension:** Värden under 1 px kan orsaka renderingsartefakter.
* **Column count:** Värden utanför 1‑4 utlöser ett undantag.
* **Character set:** Aspose.Barcode stödjer UTF‑8; se till att källfilen sparas med UTF‑8‑kodning.

## Vanliga variationer och kantfall

### Generera andra symbologier

Om du vill **create barcode with Aspose** för QR‑koder, Code128 eller UPC, ersätt `EncodeTypes.MicroPdf417` med rätt enum‑värde, t.ex.:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Alla andra konfigurationssteg (X‑dimension, sparande) förblir desamma.

### Ändra bildformat

Aspose.Barcode stödjer flera rasterformat. För att exportera som JPEG med 90 % kvalitet:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Hantera stora datapaket

MicroPdf417 kan lagra upp till 1 KB data. För större paket, byt till full `EncodeTypes.Pdf417` och justera `Rows` och `Columns` därefter.

### Unicode och specialtecken

Biblioteket kodar automatiskt Unicode‑strängar. Vissa äldre skannrar känner dock bara igen ASCII. Om du riktar dig mot sådana enheter, begränsa inmatningen till ASCII‑intervallet eller använd en annan symbologi som garanterar kompatibilitet.

## Pro‑tips för produktionsanvändning

* **Cache the generator** när du genererar många streckkoder med samma inställningar – det minskar overhead för objekt‑skapande.
* **Set `Resolution`** (`generator.Parameters.ImageResolution`) till 300 dpi för utskrift med hög kvalitet.
* **Enable error correction** för 2‑D‑streckkoder (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) för att förbättra skanningspålitlighet på skadade medier.
* **Wrap the save logic** i ett `try / catch`‑block för att hantera I/O‑undantag, särskilt vid skrivning till nätverksdelningar.

## Slutsats

Du vet nu **how to generate barcode** med Aspose.Barcode i C#. Handledningen täckte installation av NuGet‑paketet, skapande av en `BarcodeGenerator`, konfiguration av dimensioner och kolumner samt sparande av resultatet som en PNG‑bild. Med denna grund kan du **create barcode with Aspose** för vilken stödjande symbologi som helst, justera visuella parametrar och integrera streckkodsgenerering i större .NET‑lösningar.

Klar att utforska vidare? Prova att generera QR‑koder för URL‑förkortning, bädda in streckkoder i PDF‑rapporter med Aspose.PDF, eller automatisera batch‑generering av streckkoder för lagerhantering. Varje nytt scenario bygger på samma grundläggande koncept som demonstrerats här. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}