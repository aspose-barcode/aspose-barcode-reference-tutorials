---
category: general
date: 2026-07-18
description: Skapa PDF417‑streckkod i C# med C# PDF417‑streckkodsgeneratorn. Följ
  en steg‑för‑steg‑handledning för att bygga utökad kodtext, ställa in utseendet och
  spara bilden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: sv
lastmod: 2026-07-18
og_description: Skapa PDF417-streckkod i C# omedelbart. Den här guiden visar hur du
  använder C# PDF417-streckkodsgeneratorn, konfigurerar utökat läge och exporterar
  en PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Skapa PDF417-streckkod i C# – Komplett genomgång av generatorn
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Skapa PDF417‑streckkod i C# – Guide för streckkodsgenerator
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod i C# – Barcode Generator Guide

Har du någonsin behövt **create PDF417 barcode** i en C#-applikation men varit osäker på var du ska börja? Du är inte ensam—många utvecklare stöter på samma problem när de först hanterar två‑dimensionella streckkoder. De goda nyheterna? Med den inbyggda **C# PDF417 barcode generator** kan du snabbt skapa en fullständigt funktionell streckkod med bara några få rader.

I den här handledningen går vi igenom hela processen: bygga en utökad kodtext som blandar olika teckensätt, konfigurera generatorn för rätt visuella stil, och slutligen spara streckkoden som en PNG‑fil. När du är klar har du ett färdigt kodexempel som du kan klistra in i vilket .NET‑projekt som helst, samt tips för att hantera kantfall som Unicode‑tecken eller anpassade modulbredder.

---

## Vad du’ll Need

Innan vi dyker ner, se till att du har följande på din maskin:

- **.NET 6.0** eller senare (exemplet fungerar även med .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (eller något kompatibelt bibliotek som exponerar `BarcodeGenerator`, `EncodeTypes.Pdf417`, osv.)
- En kodredigerare – Visual Studio, Rider eller till och med VS Code duger
- En mapp du kan skriva till, eftersom generatorn sparar PNG‑filen där

Det är allt—inga extra NuGet‑paket utöver själva streckkodsbiblioteket.

---

## Steg‑för‑steg‑guide för **create PDF417 barcode**

### 1. Install the barcode library

Öppna din terminal i projektmappen och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till `Aspose.BarCode`‑namnutrymmet, som innehåller `BarcodeGenerator`‑klassen som vi kommer att använda genom hela handledningen.

### 2. Build the extended codetext

PDF417 stödjer **extended encoding**, vilket låter dig blanda olika teckensätt i en enda streckkod. Nedan skapar vi tre segment:

- Ett Windows‑1251 (kyrilliskt) segment
- Ett UTF‑8‑segment som innehåller Unicode‑tecken (de japanska kanji‑tecknen för “dog” och “right”)
- Ett plain‑text‑segment

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Varför detta är viktigt:**  
Om du bara använder plain‑text är du begränsad till standard‑ASCII‑subsetet. Genom att explicit deklarera ECI‑segment (Extended Channel Interpretation) säkerställer du att skannrarna tolkar varje del korrekt, oavsett språk eller symboler.

### 3. Initialise the **C# PDF417 barcode generator**

Nu när vi har en giltig kodtextsträng, överlämnar vi den till generatorn. `using`‑satsen ser till att underliggande resurser frigörs automatiskt.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configure appearance and encoding mode

Standardinställningarna ger dig en liten streckkod som kan vara svår att läsa. Låt oss justera några parametrar:

- **X‑Dimension** – styr bredden på varje modul (pixelstorlek)
- **EncodeMode** – talar om för motorn att behandla indata som extended‑läge
- **TwoDDisplayText** – valfri mänskligt läsbar text som visas under streckkoden

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Pro tip:** Om du skriver ut streckkoden på en etikettskrivare, öka `XDimension` till 20 px eller mer; de flesta skannrar gillar lite extra utrymme.

### 5. Save the barcode image

Sist, skriv bilden till disk. Biblioteket stödjer PNG, JPEG, BMP och flera vektorformat—PNG är ett säkert standardval eftersom det bevarar skarpa kanter.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Se till att `YOUR_DIRECTORY` finns och är skrivbar. Efter att programmet har körts bör du se en fil som liknar skärmbilden nedan.

![Genererad PDF417-streckkod skapad med C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "Genererad PDF417-streckkod skapad med C# PDF417 barcode generator")

---

## Användning av **C# PDF417 barcode generator** – djupare genomgång

### Handling Unicode and special characters

När du matar in Unicode‑symboler direkt i en plain‑text‑streckkod kan generatorn falla tillbaka på en fallback‑kodning, vilket resulterar i förvrängd output. Genom att använda `AddECICodetext` talar du explicit till kodaren vilket teckensätt som ska tillämpas, vilket eliminerar gissningar. Om du någonsin behöver stödja **Arabic**, **Hebrew** eller **emoji**, välj bara rätt `ECIEncodings`‑värde.

### Adjusting error correction level

PDF417 erbjuder fyra felkorrigeringsnivåer (0‑8). Högre nivåer ökar motståndskraften men gör också streckkoden större. Justera den via:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Scaling for print vs. screen

För skärmvisning kan du behålla standard‑96 dpi. För högupplöst utskrift (300 dpi eller mer), sätt:

```csharp
generator.Parameters.ImageResolution = 300;
```

Det säkerställer att den sparade PNG‑filen behåller tillräcklig detaljrikedom för laserskrivare.

### Common pitfalls

- **Missing `using` directive** – Att glömma `using Aspose.BarCode.Encoding;` gör att `ECIEncodings` blir odefinierat.
- **Directory not found** – `Save`‑metoden skapar inte mellanmapp‑strukturer; skapa dem i förväg eller använd `Path.Combine` med `Environment.CurrentDirectory`.
- **Wrong encode mode** – Om du lämnar `EncodeMode` på `Pdf417EncodeMode.Auto` kan biblioteket behandla din extended kodtext som plain‑text och ta bort ECI‑markörerna.

---

## Full, Ready‑to‑Run Example

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man skapar dotcode extended codetext med Aspose.BarCode för .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Skapa streckkod bild c# – Konfigurera Codablock F rader & kolumner](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}