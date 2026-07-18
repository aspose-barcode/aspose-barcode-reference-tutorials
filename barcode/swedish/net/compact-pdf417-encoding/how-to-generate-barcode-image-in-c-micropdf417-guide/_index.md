---
category: general
date: 2026-07-18
description: Lär dig hur du genererar en streckkodbild i C# med MicroPdf417‑formatet.
  Steg‑för‑steg‑inställning för dimensioner och sparande som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- micro pdf417 barcode
- BarcodeGenerator class
- set barcode dimensions
- save barcode as png
language: sv
lastmod: 2026-07-18
og_description: Hur genererar man en streckkodbild i C#? Följ den här guiden för att
  skapa en MicroPdf417-streckkod, justera dess storlek och exportera den som en PNG-fil.
og_image_alt: Screenshot of a MicroPdf417 barcode image generated in C#
og_title: Hur man genererar en streckkodsbild i C# – Komplett MicroPdf417-handledning
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  headline: How to Generate Barcode Image in C# – MicroPdf417 Guide
  type: TechArticle
- description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  name: How to Generate Barcode Image in C# – MicroPdf417 Guide
  steps:
  - name: Change Image Format
    text: 'You aren’t limited to PNG. Switch to JPEG or BMP by adjusting the second
      argument of `Save`:'
  - name: Increase DPI for Print
    text: 'For high‑resolution prints, bump the `Resolution` property:'
  - name: Add Quiet Zone (Margin)
    text: 'A quiet zone helps scanners differentiate the barcode from surrounding
      graphics:'
  - name: Encode Different Data Types
    text: 'MicroPdf417 works with numeric, alphanumeric, and binary data. If you need
      to embed a URL, just replace the text:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Hur man skapar en streckkodsbild i C# – MicroPdf417‑guide
url: /sv/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkodsbild i C# – MicroPdf417 Guide

Har du någonsin undrat **hur man genererar streckkodsbild** i C# utan att leta igenom ändlösa dokument? Du är inte ensam. Oavsett om du bygger ett biljettsystem, en produktkatalog eller bara behöver en snabb QR‑liknande kod, kan behärskning av streckkodsskapande spara dig tid och huvudvärk.

I den här handledningen går vi igenom de exakta stegen för att generera en **MicroPdf417 streckkodsbild** med hjälp av `BarcodeGenerator`‑klassen, justera dess dimensioner och spara resultatet som PNG. Inga onödiga utsvävningar – bara ett komplett, körbart exempel som du kan kopiera‑klistra in i ditt projekt redan idag.

## Vad du kommer att lära dig

- Ställ in `BarcodeGenerator` för MicroPdf417‑formatet  
- **Ställ in streckkodsdimensioner** som modulbredd och kolumnantal  
- **Spara streckkod som PNG** till en valfri mapp  
- Valfria justeringar för högupplöst output och felhantering  

Vid slutet kommer du kunna svara på frågan *“hur man genererar streckkodsbild”* med självförtroende, och du har en solid grund för att skapa andra streckkodstyper också.

---

## Förutsättningar

1. **.NET 6.0 eller senare** (koden fungerar även på .NET Framework 4.5+)  
2. En referens till **Aspose.BarCode**‑biblioteket (eller något bibliotek som tillhandahåller `BarcodeGenerator`). Du kan hämta det via NuGet:  

   ```bash
   dotnet add package Aspose.BarCode
   ```

3. En bra IDE – Visual Studio, Rider eller VS Code räcker.  
4. Skrivrättigheter till den katalog där du ska spara PNG‑filen.

> **Pro tip:** Om du använder ett annat streckkodsbibliotek kan klassnamnen skilja sig, men det övergripande flödet är detsamma.

## Steg 1: Skapa en MicroPdf417 streckkodsgenerator

Det första du behöver är en instans av `BarcodeGenerator` konfigurerad för **MicroPdf417 streckkod**‑formatet. Detta objekt är motorn som omvandlar din text till en visuell kod.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // Choose the MicroPdf417 format
    "Åspóse.Barcóde©");               // The data you want to encode
```

**Varför detta är viktigt:**  
`EncodeTypes.MicroPdf417` talar om för biblioteket att använda den kompakta PDF417‑varianten, vilket är perfekt för korta strängar och begränsat utrymme. Texten kan innehålla Unicode‑tecken, som visas ovan, så du är inte begränsad till ren ASCII.

## Steg 2: Ställ in streckkodsdimensioner

Nu när generatorn finns, vill du förmodligen kontrollera hur stor varje modul (den lilla fyrkanten) är och hur många kolumner streckkoden sträcker sig över. Här kommer nyckelordet **set barcode dimensions** in i bilden.

```csharp
// Step 2: Adjust appearance – module width and column count
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels
generator.Parameters.Barcode.Pdf417.Columns = 4;    // Number of columns (affects height)
```

- **`XDimension.Pixels`** – Större värden gör streckkoden lättare att skanna men ökar filstorleken.  
- **`Pdf417.Columns`** – Färre kolumner komprimerar streckkoden vertikalt; fler kolumner sträcker den horisontellt.

> **Observera:** Att sätta modulbredden för lågt (t.ex. 1 pixel) kan ge en suddig bild på hög‑DPI‑skärmar. Ett värde mellan 2‑4 pixlar fungerar bra för de flesta skrivare.

## Steg 3: Spara streckkodsbilden som PNG

Med generatorn konfigurerad är sista steget att skriva grafiken till disk. Detta uppfyller kravet **save barcode as png**.

```csharp
// Step 3: Export the barcode to a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Vad som händer under huven:**  
`Save` renderar streckkoden till en bitmap, kodar den som PNG (förlustfri komprimering) och skriver bytes till den angivna platsen. Om katalogen inte finns kommer `Save` att kasta ett undantag – så du kanske vill omsluta detta i ett `try/catch`‑block i produktionskod.

## Fullständigt fungerande exempel

Sätter vi ihop allt får du en självständig konsolapp som du kan köra direkt:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set dimensions
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 3️⃣ Define output path
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        // 4️⃣ Save as PNG
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

**Förväntad output:** En skarp `MicroPdf417.png`‑fil på ditt skrivbord som visar den kodade strängen `Åspóse.Barcóde©`. Öppna den med någon bildvisare för att verifiera att streckkoden är tydlig och läsbar.

## Avancerade alternativ (valfritt)

Om du vill utöka det grundläggande flödet, överväg dessa justeringar – var och en matchar ett sekundärt nyckelord från vår lista.

### Ändra bildformat

Du är inte begränsad till PNG. Byt till JPEG eller BMP genom att justera det andra argumentet i `Save`:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

### Öka DPI för utskrift

För högupplösta utskrifter, öka `Resolution`‑egenskapen:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

### Lägg till tyst zon (marginal)

En tyst zon hjälper skannrar att särskilja streckkoden från omgivande grafik:

```csharp
generator.Parameters.Barcode.QR.QrQuietZone = 4; // 4 modules of margin
```

### Koda olika datatyper

MicroPdf417 fungerar med numerisk, alfanumerisk och binär data. Om du behöver bädda in en URL, byt bara ut texten:

```csharp
generator.CodeText = "https://example.com";
```

## Vanliga fallgropar & hur man undviker dem

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|--------|
| Streckkoden blir suddig | `XDimension.Pixels` satt till 1 eller bild skalad efter sparning | Använd minst 2 pixlar och undvik efterbearbetningsskalning |
| Skannern kan inte läsa koden | För många kolumner för given datalängd | Minska `Pdf417.Columns` eller låt biblioteket auto‑siza (`Columns = 0`) |
| Unicode‑tecken visas som � | Biblioteksversion föråldrad eller saknar teckensnittsstöd | Uppdatera Aspose.BarCode till senaste versionen och säkerställ korrekt kodning |
| `Save` kastar `DirectoryNotFoundException` | Utdatamappen finns inte | Skapa katalogen i förväg eller använd `Path.Combine` med kända mappar |

## Testa din streckkod

Efter att bilden har genererats kan du verifiera den med någon streckkodsskanningsapp (de flesta smarttelefonkameror har nu inbyggda streckkodsläsare). Rikta kameran mot PNG‑filen på skärmen eller skriv ut den – om appen läser `Åspóse.Barcóde©` har du framgångsrikt svarat på **hur man genererar streckkodsbild**.

## Slutsats

Vi har gått igenom allt du behöver veta för att **hur man genererar streckkodsbild** med C# och MicroPdf417‑formatet:

1. **Skapa** en `BarcodeGenerator` med dina data.  
2. **Ställ in streckkodsdimensioner** för att kontrollera storlek och läsbarhet.  
3. **Spara streckkod som PNG** (eller något annat stödd format).  

Härifrån kan du experimentera med olika streckkodstyper, justera DPI för utskrift eller bädda in bilden direkt i PDF‑filer eller rapporter. Byggstenarna är desamma, så känn dig fri att byta `EncodeTypes.MicroPdf417` mot `EncodeTypes.QR` eller `EncodeTypes.Code128` och upprepa stegen.

Har du frågor om andra streckkodstandarder eller behöver hjälp med att finjustera utseendet? Lämna en kommentar nedan, och lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar Aztec-streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man genererar streckkod – Endimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Hur man genererar DataMatrix-streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}