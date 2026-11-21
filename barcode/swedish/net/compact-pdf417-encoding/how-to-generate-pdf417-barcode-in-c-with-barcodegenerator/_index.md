---
category: general
date: 2026-11-20
description: Lär dig hur du genererar PDF417‑streckkod i C# med BarcodeGenerator.
  Denna steg‑för‑steg‑guide täcker X‑dimension, kolumninställningar och PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: sv
lastmod: 2026-11-20
og_description: Generera PDF417‑streckkod i C# snabbt. Följ den här guiden för att
  ange dimensioner, kolumner och exportera streckkoden som en PNG‑bild.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Generera PDF417‑streckkod i C# – komplett steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Hur man genererar PDF417‑streckkod i C# med BarcodeGenerator
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417-streckkod i C# med BarcodeGenerator

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här guiden exakt hur du gör det. Du kommer att se ett komplett, körbart exempel som ställer in X‑Dimension, väljer antalet kolumner och sparar resultatet som en PNG‑bild.

Att generera en PDF417-streckkod är vanligt när du måste koda mycket data—t.ex. ett körkort, ett boardingkort eller ett lagerregister—till en kompakt, maskinläsbar bild. I den här tutorialen använder vi **BarcodeGenerator**-klassen från Aspose.BarCode-biblioteket, men koncepten gäller för alla bibliotek som stödjer PDF417.

I slutet av den här artikeln kommer du att kunna:

* Initiera en `BarcodeGenerator` för PDF417‑kodning.  
* Justera modulstorleken med **set XDimension pixels**.  
* Styr layouten med **configure PDF417 columns**.  
* **Save barcode as PNG** för användning i webbsidor, mobilappar eller tryckt material.  

> **Förutsättningar**  
> * .NET 6.0 eller senare (koden fungerar även med .NET Framework 4.7+).  
> * En referens till **Aspose.BarCode** NuGet‑paketet (`Install-Package Aspose.BarCode`).  
> * Grundläggande kunskap om C# och Visual Studio (eller någon IDE du föredrar).

---

## Så genererar du PDF417-streckkod i C#

Kärnan i lösningen är en kort fyrstegsprocess. Varje steg är inbäddat i en dedikerad metod så att du kan återanvända logiken i större projekt.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Varför dessa fyra steg är viktiga

1. **Initialize the generator** – `BarcodeGenerator` kopplar den valda symbologin (`EncodeTypes.Pdf417`) till den data du vill koda. Utan detta objekt kan du inte komma åt någon ytterligare konfiguration.  
2. **Set X‑Dimension** – PDF417 är byggt av små rektangulära moduler. Att ändra `XDimension.Pixels` låter dig kontrollera streckkodens visuella densitet, vilket är avgörande för läsbarhet på lågupplösta skärmar eller skrivare.  
3. **Configure columns** – PDF417 kan ordna sina kodord i ett variabelt antal kolumner. Färre kolumner ger en högre streckkod, medan fler kolumner gör den kortare. Justera detta för att passa utrymmet där bilden ska placeras.  
4. **Save as PNG** – PNG är ett förlustfritt format som bevarar de skarpa kanterna som krävs för exakt avläsning. Du kan också välja JPEG eller BMP, men PNG är det säkraste standardalternativet.

---

## Konfigurera streckkodsdimensioner (X‑Dimension)

Steget **set XDimension pixels** påverkar direkt hur skannrar tolkar streckkoden. Om modulen är för liten kan lågkvalitativa kameror missa enskilda staplar; om den är för stor kan streckkoden bli onödigt stor.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Testa den genererade bilden i den avsedda utskriftsstorleken. För högdensitetsutskrift (300 dpi eller mer) fungerar ett värde på `1` eller `2` bra. För skärmvisning vid 96 dpi ger `2`–`3` en tydlig visuell bild.

---

## Ställ in PDF417‑kolumner

Steget **configure PDF417 columns** låter dig bestämma streckkodens form.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### När du ska ändra kolumnantalet

| Kolumner | Resulterande form | Typiskt användningsområde |
|----------|-------------------|---------------------------|
| 1–3      | Hög, smal         | Etiketter med begränsad bredd |
| 4–9      | Balanserad        | Allmän scanning |
| 10+      | Bred, kort        | Stora skyltar eller webbgrafik |

Om din datapayload överstiger standardkapaciteten lägger biblioteket automatiskt till extra rader, men du kan fortfarande påverka bildförhållandet genom att justera kolumnantalet.

---

## Exportera streckkod till PNG

Att spara streckkoden som en PNG‑bild är enkelt:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Varför PNG?**  
* Förlustfri komprimering bevarar de skarpa kanterna som behövs för streckkodsläsare.  
* PNG stödjer transparens, vilket kan vara användbart om du senare lägger streckkoden över en färgad bakgrund.

Om du behöver ett annat format, ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Svg`—API‑et hanterar konverteringen automatiskt.

---

## Vanliga fallgropar och felsökning

| Problem | Trolig orsak | Åtgärd |
|---------|--------------|--------|
| Streckkoden blir suddig | X‑Dimension för liten för utskriftsupplösningen | Öka `XDimension.Pixels` till 3 eller 4. |
| Skannern kan inte läsa koden | Unicode‑tecken stöds inte av det valda teckensnittet | Se till att bibliotekets teckensnitt stödjer tecknen, eller ersätt dem med ASCII‑ekvivalenter. |
| Utdatafilen skapades inte | Ogiltig sökväg eller saknade skrivbehörigheter | Använd en absolut sökväg och verifiera mappens skrivbehörighet. |
| För många rader, streckkoden blir hög | Kolumnantalet för lågt för datalängden | Öka `Pdf417.Columns` till ett högre tal (t.ex. 6). |

---

## Fullständigt fungerande exempel – sammanfattning

Nedan är **det kompletta programmet** som du kan kopiera‑klistra in i ett nytt konsolprojekt. Ingen extra kod krävs utöver `using`‑satserna och Aspose.BarCode‑paketet.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Förväntad output:** En fil med namnet `Pdf417Basic.png` som innehåller en tydlig PDF417‑streckkod som kodar strängen `Åspóse.Barcóde©`. När den öppnas ska bilden visa en serie staplade rektangulära staplar med en högre densitet på vänstra sidan (på grund av den tre‑kolumniga layouten).

---

## Slutsats

Du vet nu hur du **genererar PDF417-streckkod** i C# med `BarcodeGenerator`‑klassen. Tutorialen täckte initiering av generatorn, **set XDimension pixels**, **configure PDF417 columns**, och **save barcode as PNG**—de väsentliga stegen för ett produktionsklart streckkodssflöde.

Härifrån kan du:

* Experimentera med olika `EncodeTypes` (t.ex. QR, Code128).  
* Lägg till felkorrigeringsnivåer via `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Rendera streckkoden direkt till en `MemoryStream` för webb‑API:er.

Känn dig fri att anpassa koden till ditt eget projekt, och dela dina resultat i kommentarerna eller på Stack Overflow med taggen `#pdf417`. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande tutorials täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera PDF417-streckkod som PNG i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Hur man genererar PDF417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man genererar PDF417-streckkod i C# med anpassade dimensioner](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}