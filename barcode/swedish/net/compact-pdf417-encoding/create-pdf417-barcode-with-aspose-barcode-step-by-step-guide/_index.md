---
category: general
date: 2026-08-25
description: Skapa PDF417‑streckkod med Aspose.BarCode i C#. Denna handledning förklarar
  hur du snabbt genererar PDF417‑streckkod med tydliga kodexempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: sv
lastmod: 2026-08-25
og_description: Skapa PDF417‑streckkod med Aspose.BarCode i C#. Lär dig hur du genererar
  PDF417‑streckkod med ett komplett, körbart exempel.
og_image_alt: Screenshot of a generated PDF417 barcode created with Aspose.BarCode
og_title: Skapa PDF417‑streckkod med Aspose.BarCode – snabbguide
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create PDF417 barcode using Aspose.BarCode in C#. This tutorial explains
    how to generate PDF417 barcode quickly with clear code examples.
  headline: Create PDF417 barcode with Aspose.BarCode – step-by-step guide
  type: TechArticle
tags:
- Aspose.BarCode
- PDF417
- C#
title: Skapa PDF417-streckkod med Aspose.BarCode – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod med Aspose.BarCode – steg‑för‑steg‑guide

Om du behöver **skapa PDF417-streckkod** i en .NET‑applikation visar den här guiden hur du genererar PDF417-streckkod med Aspose.BarCode. Du får se ett komplett, färdigt‑att‑köra‑exempel, förstå varför varje inställning är viktig, och lära dig hur du anpassar koden för olika scenarier.

Tutorialen täcker:

* Lägga till Aspose.BarCode‑paketet i ditt projekt  
* Konfigurera streckkodsgeneratorn (text, X‑dimension, kolumner)  
* Spara streckkoden som en PNG‑fil  
* Hantera Unicode‑tecken och vanliga fallgropar  

Ingen extern dokumentation behövs – allt du behöver finns nedan.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)  
* En aktuell version av **Aspose.BarCode for .NET** NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* En IDE eller editor du föredrar (Visual Studio, VS Code, Rider, etc.)

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt och importera de nödvändiga Aspose.BarCode‑namnrymderna.

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
            // The full barcode generation logic starts here.
```

*`Aspose.BarCode`* innehåller kärnklasserna, medan *`Aspose.BarCode.Generation`* tillhandahåller `BarcodeGenerator` som används för att skapa streckkoder.

## Steg 2: Skapa PDF417‑streckkodsgenerator med önskad text

Den första raden konstruerar en `BarcodeGenerator` för PDF417‑symbologi och tilldelar den data du vill koda.

```csharp
            // Step 2: Create a PDF417 barcode generator with the desired text
            // Unicode characters such as Å, ó, and © are supported out of the box.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Varför detta är viktigt:**  
PDF417 kan lagra upp till 1 850 tecken, vilket gör den lämplig för dokument, biljetter eller ID‑kort. Genom att skicka texten direkt till konstruktorn säkerställer du att data kodas korrekt innan några visuella inställningar appliceras.

## Steg 3: Konfigurera visuella parametrar (X‑dimension och kolumner)

Finjustering av utseendet förbättrar skanningspålitlighet och matchar layoutkrav.

```csharp
            // Step 3: Set the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 4: Define the number of columns for the PDF417 barcode
            // Fewer columns produce a taller barcode; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
```

* **X‑dimension** – Styr bredden på en enskild streckkodsmodule. Ett värde på `2` pixlar är en bra balans mellan läsbarhet och filstorlek för de flesta skärmar.  
* **Columns** – Bestämmer hur många datakolumner streckkoden ska ha. Justera detta värde baserat på mängden data och det utrymme som finns på målmediet.

## Steg 4: Spara streckkodsbilden

Välj ett bildformat som passar ditt efterföljande arbetsflöde. PNG bevarar förlustfri kvalitet, vilket är idealiskt för vidare bearbetning eller utskrift.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

`Save`‑metoden skriver bilden till den angivna sökvägen. Om du behöver ett annat format (JPEG, BMP, SVG) ersätter du `BarCodeImageFormat.Png` med motsvarande enum‑värde.

## Fullt, körbart exempel

Kopiera hela kodblocket nedan till `Program.cs` i ett nytt konsolprojekt, kör `dotnet run`, så hittar du `Pdf417Basic.png` i projektmappen.

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
            // Create a PDF417 barcode generator with Unicode text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Save as PNG
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Förväntad utdata

Att köra programmet skapar en PNG‑fil som liknar illustrationen nedan.

![Exempel på skapad PDF417-streckkod](https://example.com/images/pdf417-sample.png "Exempel på skapad PDF417-streckkod")

*Bilden visar en tydlig PDF417‑streckkod med tre kolumner och en modulbredd på 2 px.*

## Hur du genererar PDF417‑streckkod med anpassade datalängder

Om dina data överskrider standardkapaciteten kan du behöva justera ytterligare parametrar:

| Parameter | Rekommenderad inställning | Orsak |
|-----------|---------------------------|-------|
| `Pdf417.Rows` | `0` (auto) | Låt Aspose beräkna det optimala antalet rader. |
| `Pdf417.ErrorLevel` | `2` (default) | Högre nivåer ökar redundansen, vilket förbättrar skanningspålitlighet på skadat medium. |
| `Pdf417.SecurityLevel` | `0`–`8` | Använd endast när du behöver felkorrigering utöver standard. |

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 0;          // Auto‑calculate rows
generator.Parameters.Barcode.Pdf417.ErrorLevel = 2;   // Standard error correction
generator.Parameters.Barcode.Pdf417.SecurityLevel = 5; // Optional extra security
```

**Tips:** Testa alltid den genererade streckkoden med den avsedda skanningshårdvaran. Högre felnivåer kan göra bilden större, vilket kan påverka layoutbegränsningar.

## Vanliga fallgropar och hur du undviker dem

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Streckkoden blir suddig | Sparas som en lågupplöst PNG | Öka `XDimension.Pixels` eller exportera till SVG (`BarCodeImageFormat.Svg`) |
| Tecken ersätts av � | Indatasträngen är inte kodad som UTF‑8 | Se till att källfilen sparas med UTF‑8‑kodning (de flesta IDE:er använder detta som standard) |
| Skannern kan inte läsa streckkoden | För få kolumner för mängden data | Öka `Pdf417.Columns` eller låt Aspose automatiskt bestämma kolumner genom att utelämna inställningen |

## Skapa streckkod med Aspose – bortom PDF417

Aspose.BarCode stödjer många symbologier (QR, Code128, DataMatrix, etc.). Att byta till en annan typ kräver bara att du ändrar `EncodeTypes`‑enum‑värdet:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
qrGenerator.Save("QRCode.png", BarCodeImageFormat.Png);
```

Detta demonstrerar **create barcode with Aspose**‑mönstret: instansiera `BarcodeGenerator` med önskat `EncodeTypes`‑värde, konfigurera parametrar och anropa sedan `Save`.

## Slutsats

Du vet nu hur du **skapar PDF417-streckkod** i C# med Aspose.BarCode, från projektuppsättning till finjustering av visuella parametrar och hantering av Unicode‑data. Det kompletta, körbara exemplet kan anpassas för större datamängder, olika bildformat eller alternativa symbologier.

Nästa steg du kan utforska:

* **Hur du genererar PDF417‑streckkod** i ett webb‑API (ASP.NET Core) – användbart för on‑demand‑generering.  
* Inbädda streckkoden i ett PDF‑dokument med Aspose.PDF.  
* Använda `Pdf417.Rows` och `Pdf417.ErrorLevel` för att uppfylla specifika skanningsstandarder.

Känn dig fri att experimentera med kolumnantal, X‑dimension‑värden och utdataformat för att passa just ditt användningsfall. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar PDF417‑streckkod – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man läser streckkod från PDF i Java med Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}