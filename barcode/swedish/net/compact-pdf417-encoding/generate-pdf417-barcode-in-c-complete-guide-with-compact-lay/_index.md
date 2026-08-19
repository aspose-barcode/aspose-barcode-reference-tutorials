---
category: general
date: 2026-08-19
description: Generera PDF417‑streckkod i C# snabbt. Lär dig hur du genererar PDF417‑streckkod
  i C# med Aspose.BarCode i kompakt läge och anpassade inställningar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: sv
lastmod: 2026-08-19
og_description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Denna handledning
  visar hur du genererar PDF417‑streckkod i C# i kompakt läge, ställer in X‑dimension
  och sparar som PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Generera PDF417-streckkod i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generera PDF417-streckkod i C# – komplett guide med kompakt layout
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod i C# – komplett guide

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här handledningen exakt hur du gör det. Du får se ett koncist, produktionsklart exempel som skapar en kompakt PDF417-streckkod, anpassar X‑dimensionen och sparar resultatet som en PNG‑bild.

Att generera en PDF417-streckkod är vanligt när du måste koda stora mängder data — såsom biljettinformation, fraktmanifest eller identitetshandlingar — i ett maskinläsbart format. Att använda Aspose.BarCode gör processen enkel, och koden fungerar med .NET 6+ eller .NET Framework 4.7.2 och senare.

I den här guiden kommer du att:

* Installera Aspose.BarCode NuGet‑paketet.
* Skriva ett fristående C#‑program som **genererar PDF417-streckkod** med ett litet kolumnantal och kompakt (avkortat) läge.
* Justera stapelbredden (X‑dimension) för skarpare återgivning.
* Spara streckkoden som en PNG‑fil.
* Utforska variationer, kantfall och bästa‑praxis‑tips.

## Förutsättningar

Innan du börjar, se till att du har:

* Visual Studio 2022 (eller någon C#‑IDE) med .NET 6 SDK installerat.
* Internetåtkomst för att ladda ner **Aspose.BarCode**‑paketet från NuGet.
* Skrivbehörighet till en mapp där PNG‑filen ska sparas.

Inga ytterligare bibliotek behövs; Aspose.BarCode hanterar bildkodning internt.

## Steg 1: Lägg till Aspose.BarCode‑paketet

Öppna ditt projekt i Visual Studio, högerklicka på lösningen och välj **Manage NuGet Packages**. Sök efter `Aspose.BarCode` och installera den senaste stabila versionen.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Håll paketet uppdaterat. Nya versioner innehåller ofta prestandaförbättringar och stöd för de senaste .NET‑runtime‑versionerna.

## Steg 2: Skapa en minimal konsolapplikation

Skapa ett nytt C#‑konsolprojekt om du inte redan har ett:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Ersätt innehållet i `Program.cs` med hela exemplet nedan. Detta program demonstrerar **hur man genererar PDF417-streckkod i C#** från början till slut.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig

* **`EncodeTypes.Pdf417`** – väljer PDF417‑symbologi, som stödjer upp till ~1,1 KB data.
* **`XDimension.Pixels = 2`** – anger grundbredden på staplarna. Mindre värden gör streckkoden tunnare; större värden förbättrar läsbarheten på lågupplösta enheter.
* **`Pdf417.Columns = 3`** – begränsar antalet kolumner, vilket tvingar generatorn att använda fler rader, vilket ger en högre men smalare streckkod.
* **`Pdf417.Truncate = true`** – aktiverar kompakt läge, tar bort stoppmönstret och minskar bilden utan att förlora dataintegritet.
* **`Save(..., BarCodeImageFormat.Png)`** – skriver en PNG‑fil. Du kan också välja `Jpeg`, `Bmp` eller `Svg` beroende på efterföljande behov.

Kör programmet:

```bash
dotnet run
```

Du bör se konsolutdata som bekräftar filens plats, och mappen kommer att innehålla `CompactPdf417.png`. När du öppnar PNG‑filen visas en tydlig, kompakt PDF417‑streckkod som kodar Unicode‑strängen.

## Steg 3: Verifiera streckkoden (valfritt men rekommenderat)

För att säkerställa att streckkoden är läsbar kan du använda någon standard‑PDF417‑skannerapp på en smartphone eller ett desktop‑avkodarbibliotek. Den kodade texten bör exakt matcha den ursprungliga `data`‑strängen, inklusive specialtecken.

Om du stöter på avkodningsproblem:

* Öka `XDimension` till 3 eller 4 pixlar.
* Minska antalet kolumner (t.ex. sätt `Columns = 2`).
* Inaktivera `Truncate` (`Truncate = false`) för att lägga till stoppmönstret.

Dessa justeringar byter storlek mot läsbarhet, vilket är användbart för lågupplösta skrivare eller skannrar.

## Steg 4: Utforska vanliga variationer

### 4️⃣ Generera en högdensitets‑PDF417 för utskrift

Om du behöver en streckkod som får plats på en liten etikett, öka kolumnantalet och sänk X‑dimensionen:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Ändra utdataformatet till SVG för vektorskalning

SVG‑utdata skalar utan kvalitetsförlust, perfekt för responsiva webbplatser.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Koda binär data (t.ex. en byte‑array)

Om du behöver bädda in binära nyttolaster, konvertera dem först till en Base64‑sträng:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Streckkoden bär nu den binära informationen, och avkodaren måste vända Base64‑steget.

## Vanliga frågor

| Fråga | Svar |
|----------|--------|
| **Kan jag generera PDF417 utan Aspose?** | Ja, andra bibliotek som ZXing.Net eller Dynamsoft finns, men Aspose.BarCode erbjuder rikare layoutkontroll (kolumner, avkortning) och bättre Unicode‑hantering. |
| **Vad är maximal datalängd?** | PDF417 kan koda upp till 1 108 byte (≈ 1 KB) binär data. Om du överskrider detta, överväg att dela upp data över flera streckkoder. |
| **Är kompakt läge standardkompatibelt?** | Avkortad PDF417 är en del av ISO/IEC 15438‑specifikationen och är brett stödjande, men verifiera att din målskanner explicit stödjer den. |
| **Hur ändrar jag bakgrundsfärgen?** | Sätt `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` och `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` innan du sparar. |

## Slutsats

Du vet nu **hur man genererar PDF417-streckkod i C#** med Aspose.BarCode, hur man finjusterar X‑dimensionen, aktiverar kompakt läge och exporterar resultatet som en PNG‑bild. Det kompletta, körbara exemplet kan kopieras in i vilket .NET‑projekt som helst, och de visade variationerna låter dig anpassa streckkoden för utskrift, webb eller binära nyttolastsscenarier.

Kommande steg du kan utforska:

* Integrera streckkodsgenereringen i ett ASP.NET Core‑API som returnerar bilden på begäran.
* Kombinera PDF417 med QR‑koder på samma etikett för dubbel‑formatsskanning.
* Använd Aspose.BarCode `Reader`‑klassen för att avkoda den genererade bilden och verifiera data programatiskt.

Lycka till med kodningen, och njut av den flexibilitet som **generera PDF417-streckkod**‑lösningar ger dina applikationer!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar streckkodsbild med anpassning av extra utrymme med Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}