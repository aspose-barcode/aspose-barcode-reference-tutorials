---
category: general
date: 2026-10-12
description: Lär dig att skapa micro PDF417‑streckkod och konvertera streckkoden till
  PNG med C#. Steg‑för‑steg‑guide med fullständig kod och tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: sv
lastmod: 2026-10-12
og_description: Skapa micro‑PDF417‑streckkod och konvertera streckkoden till PNG med
  C#. Följ den här kompletta guiden för att generera både standard‑ och GS1‑versioner.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Skapa micro PDF417‑streckkod och konvertera den till PNG – C#‑handledning
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hur man skapar en mikro‑PDF417‑streckkod och konverterar den till PNG i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar micro PDF417 streckkod och konverterar den till PNG i C#

Om du behöver **create micro PDF417 barcode** i en .NET-applikation visar den här handledningen exakt hur. Du får se ett komplett, körbart exempel som genererar både en standard Micro PDF417 streckkod och en GS1‑kompatibel version, och sedan **convert barcode to PNG** för efterföljande användning såsom utskrift eller webbvisning.

Att generera en streckkod är mer än att bara anropa en enda metod—att välja rätt modulg storlek, kolumnantal och kodningsformat avgör skanningspålitligheten. I slutet av den här guiden kommer du att förstå varför varje inställning är viktig och hur du justerar dem för dina egna projekt.

## Förutsättningar

| Krav | Anledning |
|------|-----------|
| .NET 6.0 SDK eller senare | Tillhandahåller runtime för C#-konsolappen |
| Visual Studio 2022 (eller någon C#-IDE) | Gör redigering och felsökning enklare |
| **Aspose.BarCode for .NET** NuGet-paket | Tillhandahåller klasserna `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat` |
| Skrivbehörighet till utdata-mappen | Krävs för `Save`-anrop som skapar PNG-filer |

Du kan lägga till Aspose.BarCode-paketet via CLI:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa ett minimalt konsolprojekt

Skapa ett nytt konsolprojekt och referera till streckkodsbiblioteket. Följande `Program.cs` innehåller all kod du behöver; inga externa filer krävs.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Varför varje rad är viktig

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Den första skapar en enkel Micro PDF417 streckkod, medan den andra följer GS1-standarder och inbäddar Application Identifiers (AIs). Välj baserat på om ditt efterföljande system förväntar sig GS1-data.
* **`XDimension.Pixels = 2`** – Styr modulbredden. Mindre värden ger en tätare bild men kan bli oläslig på lågupplösta skannrar. Två pixlar är en säker standard för de flesta etikettprinter.
* **`Pdf417.Columns = 4`** – Micro PDF417 låter dig begränsa antalet kolumner, vilket minskar den totala bredden. Fyra kolumner håller streckkoden kompakt utan att offra datakapaciteten för korta payloads.
* **`BarCodeImageFormat.Png`** – PNG bevarar förlustfri kvalitet, vilket är avgörande för streckkodens tydlighet. Därför **convert barcode to PNG** istället för JPEG.

## Steg 2: Kör programmet och verifiera resultatet

1. Bygg projektet: `dotnet build`.
2. Kör: `dotnet run`.

Du bör se konsolmeddelanden liknande:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Öppna de genererade PNG-filerna med någon bildvisare. Båda bilderna visar en skarp, högkontrast streckkod klar för skanning.

### Förväntat visuellt resultat

| Streckkodstyp | Utseende |
|---------------|----------|
| **Micro PDF417** | Litet rektangulärt mönster med 4 kolumner, läsbart av de flesta 2‑D streckkodsskannrar. |
| **GS1 Micro PDF417** | Samma storlek men kodar GS1 AIs; en scanner som förstår GS1 kommer att returnera GTIN och serienummer. |

Om en scanner misslyckas med att läsa bilden, försök öka `XDimension.Pixels` till **3** eller **4**, eller minska kolumnantalet för standard Micro PDF417.

## Vanliga fallgropar och hur du undviker dem

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Oskarp streckkod efter utskrift | Låga DPI-inställningar på skrivaren | Exportera PNG med 300 dpi eller högre, eller låt skrivardrivrutinen hantera skalning. |
| Scanner returnerar “invalid data” | Saknad eller felaktig GS1 AI-format | Säkerställ att varje AI är omsluten av parenteser och följer GS1-specifikationen (t.ex. `(01)` för GTIN‑14). |
| Bildfil skapades inte | Utdata-mappen saknar skrivbehörighet | Kör programmet med förhöjda rättigheter eller välj en mapp som `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Streckkoden för stor för etiketten | Standardkolumnantalet är för högt | Minska `Pdf417.Columns` (t.ex. till **3**) eller öka `XDimension` för att minska den totala storleken. |

## Utöka exemplet

* **Olika bildformat** – Ersätt `BarCodeImageFormat.Png` med `Jpeg` eller `Bmp` om ditt arbetsflöde kräver dem. PNG förblir det bästa valet för förlustfri kvalitet.
* **Dynamisk data** – Skicka användarinmatning eller databasvärden till `BarcodeGenerator`-konstruktorn för att skapa streckkoder i realtid.
* **Batchgenerering** – Inslå skaplogiken i en loop som läser rader från en CSV-fil och sparar varje streckkod med ett unikt filnamn.

## Slutsats

Du vet nu hur du **create micro PDF417 barcode** i C# och **convert barcode to PNG** för både standard- och GS1‑kompatibla scenarier. Den kompletta, körbara koden demonstrerar de väsentliga inställningarna—X-dimension, kolumnantal och kodningstyp—så att du kan anpassa lösningen till vilket .NET‑projekt som helst som behöver kompakt, högkvalitativ 2‑D streckkod.

*Nästa steg*: utforska andra symbologier som stöds av Aspose.BarCode (t.ex. QR, DataMatrix), experimentera med olika `XDimension`-värden för högupplöst utskrift, eller integrera de genererade PNG-filerna i ett webb‑API som levererar streckkoder på begäran.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar micro pdf417 streckkod i C# och sparar den som PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Skapa streckkod PNG i C# – fullständig guide till GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Generera Micro PDF417 streckkod i C# – Komplett guide](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}