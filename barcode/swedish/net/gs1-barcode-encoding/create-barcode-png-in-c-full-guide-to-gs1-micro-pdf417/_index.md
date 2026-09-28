---
category: general
date: 2026-08-12
description: Skapa streckkod‑PNG i C# snabbt med Aspose.BarCode. Lär dig hur du genererar
  PDF417‑streckkod i C# och behärskar streckkodsgeneratorns användning i en enda handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: sv
lastmod: 2026-08-12
og_description: Skapa streckkod PNG i C# med Aspose.BarCode. Denna handledning visar
  hur du genererar PDF417‑streckkod i C# och använder streckkodsgeneratorn effektivt.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Skapa streckkod PNG i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Skapa streckkod PNG i C# – fullständig guide till GS1 Micro PDF417
url: /sv/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod PNG i C# – fullständig guide till GS1 Micro PDF417

Om du behöver **create barcode PNG** i en .NET-applikation, visar den här guiden exakt hur du gör det. Du kommer att lära dig att generera en PDF417-streckkod i C# och se **barcode generator usage**-mönster som fungerar i produktion.

Att generera en streckkodsbild är ett vanligt krav för lagersystem, fraktetiketter och biljettplattformar. I slutet av den här handledningen kommer du att ha ett självständigt konsolprogram som skriver en PNG-fil som innehåller en GS1 Micro PDF417-streckkod, redo för vidare bearbetning.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat (koden fungerar också med .NET Framework 4.7.2+).
* En aktuell version av **Aspose.BarCode for .NET** NuGet-paketet. Installera det med  
  `dotnet add package Aspose.BarCode`.
* Grundläggande kunskap om C#-konsolprojekt.
* Skrivrättighet till en mapp där PNG-filen ska sparas.

Dessa krav håller exemplet lättviktigt samtidigt som det speglar en verklig miljö.

## Steg 1: Ställ in C#-projektet

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode-referensen:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

`dotnet`-CLI:n skapar en `Program.cs`-fil och återställer NuGet-paketet. Detta steg är avgörande för **barcode generator usage** eftersom biblioteket innehåller `BarcodeGenerator`-klassen som vi kommer att använda.

## Steg 2: Skriv den kompletta koden för streckkodsgenerering

Ersätt innehållet i `Program.cs` med följande kod. Den innehåller varje rad du behöver för att **create barcode PNG** från början till slut.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig

| Rad | Anledning |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Väljer den specifika PDF417-varianten som krävs för GS1-applikationer. |
| Data string `"(01)12345678901231(10)ABC123"` | Visar GS1 AI-syntaxen för ett GTIN (01) och ett partinummer (10). |
| `XDimension.Pixels = 2` | Styr streckkodens fysiska storlek; en vanlig standard för skärmvisning. |
| `ImageResolution = 300` | Ökar DPI, vilket säkerställer att PNG-filen ser skarp ut när den skrivs ut. |
| `BackgroundColor = Transparent` | Gör PNG-filen overlay‑vänlig för UI-sammansättning. |
| `Save(..., BarCodeImageFormat.Png)` | Sparar streckkoden som en PNG, vilket uppfyller målet **create barcode PNG**. |

## Steg 3: Kör programmet och verifiera resultatet

Kör konsolappen:

```bash
dotnet run
```

Du bör se bekräftelsemeddelandet och hitta `output.png` i projektmappen. När du öppnar filen visas en GS1 Micro PDF417-streckkod som kodar exempeldata.

![exempel på create barcode PNG som visar en GS1 Micro PDF417-kod](barcode-example.png)

*Alt text: exempel på create barcode PNG som visar en GS1 Micro PDF417-kod.*

### Förväntat visuellt resultat

PNG-filen innehåller en rektangulär streckkod med jämnt fördelade svarta moduler. När den skannas med en GS1‑kompatibel scanner returneras strängen `(01)12345678901231(10)ABC123`, vilket bekräftar att **generate PDF417 barcode C#** lyckades.

## Steg 4: Utforska vanliga variationer

### Ändra symbologin

Om du behöver en vanlig PDF417 istället för mikroversionen, ersätt kodningstypen:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Justera bildformat

Aspose.BarCode stöder många format. För att skapa en JPEG istället:

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Spara till en ström (användbart för webb‑API:er)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Dessa kodsnuttar illustrerar flexibel **barcode generator usage** utöver det grundläggande fil‑sparningsscenariot.

## Pro‑tips och fallgropar

* **Validate data length** – GS1 Micro PDF417 har en maximal datakapacitet; att överskrida den kastar ett undantag. Använd `generator.Parameters.Barcode.IsValidData(data)` för att förkontrollera.
* **Avoid tiny XDimension values** – värden under 1 pixel kan producera oläsliga streckkoder på lågupplösta enheter.
* **Set `QuietZone`** om du bäddar in PNG-filen i en större grafik; standard‑quiet‑zone säkerställer att skannrar kan lokalisera start‑/stopp‑mönstren.
* **Thread safety** – `BarcodeGenerator`‑instanser är inte trådsäkra. Skapa en ny generator per begäran i en webbtjänst.

## Slutsats

Du vet nu hur du **create barcode PNG**‑filer i C# med Aspose.BarCode, hur du **generate PDF417 barcode C#** med GS1 Micro‑varianten, och de väsentliga mönstren för effektiv **barcode generator usage**. Det kompletta, körbara exemplet kan läggas in i vilket .NET‑projekt som helst, och du kan utöka det med olika symbologier, bildformat eller ström‑utdata.

### Vad blir nästa steg?

* Utforska **barcode reader integration** för att automatiskt verifiera genererade bilder.  
* Experimentera med **custom colors** och **logo embedding** för varumärkesmedvetna streckkoder.  
* Granska Aspose.BarCode-dokumentationen för avancerade felkorrigeringsinställningar och flersidigt PDF417‑generering.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man sparar PNG med DataMatrix C40 med Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}