---
category: general
date: 2026-09-29
description: Skapa GS1‑streckkod i C# och generera streckkod‑PNG‑bilder med BarcodeGenerator.
  Följ en steg‑för‑steg‑guide för att exportera streckkodsbilden effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: sv
lastmod: 2026-09-29
og_description: Skapa GS1-streckkod i C# och generera streckkod PNG-filer med BarcodeGenerator.
  Följ den här kompletta guiden för att snabbt exportera streckkodsbilder.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Skapa GS1-streckkod i C# – exportera som PNG på några minuter
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Skapa GS1-streckkod i C# och exportera den som PNG
url: /sv/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa GS1‑streckkod i C# och exportera den som PNG

Om du behöver **create barcode GS1** i en .NET‑applikation visar den här guiden exakt hur du gör det. Du kommer att se en koncis lösning som genererar en streckkod‑PNG‑bild och exporterar streckkodsbilden till disk, allt med Aspose.BarCode `BarcodeGenerator`‑klassen.

Att generera en GS1‑streckkod är ett vanligt krav för lager, frakt och kassasystem. I slutet av den här handledningen kommer du att kunna skriva ett litet C#‑program som skapar en GS1‑kompatibel MicroPDF417‑streckkod och sparar den som en högkvalitativ PNG‑fil.

## Förutsättningar

Innan du börjar, se till att du har:

* **.NET 6** (eller någon senare .NET‑version) installerad.  
* **Visual Studio 2022** eller någon IDE som stödjer C#.  
* **Aspose.BarCode for .NET** NuGet‑paketet (`Aspose.BarCode`) – det tillhandahåller `BarcodeGenerator`‑API:t som används i exemplen.  
* Grundläggande kunskap om C#‑syntax.

> **Pro tip:** Använd den kostnadsfria community‑editionen av Aspose.BarCode när du experimenterar; den fullständiga versionen tar bort eventuella utvärderingsvattenstämplar.

## Steg 1 – Skapa GS1‑streckkod med BarcodeGenerator

Det första du behöver göra är att instansiera `BarcodeGenerator` för *MicroPDF417*‑formatet och mata in en GS1‑datat sträng. GS1 Application Identifiers (AIs) omsluts av parenteser, t.ex. `(01)` för GTIN‑14 och `(21)` för ett serienummer.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Varför detta är viktigt:**  
`EncodeTypes.MicroPdf417` behandlar automatiskt indata som GS1‑data när strängen innehåller giltiga AIs. Detta säkerställer att den genererade streckkoden följer GS1‑specifikationen utan extra konfiguration.

## Steg 2 – Ställ in streckkodens dimensioner för optimal storlek

En streckkods visuella storlek styrs av dess **X‑dimension** (bredden på en enskild modul). Genom att justera `XDimension.Pixels` kan du finjustera den slutliga bildstorleken samtidigt som läsbarheten bevaras.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Hur man genererar streckkod‑PNG** – X‑dimensionen påverkar inte den kodade datan; den ändrar endast de fysiska dimensionerna på den genererade bilden. Om du behöver en större streckkod för högupplöst utskrift, öka detta värde (t.ex. `3` eller `4`).

## Steg 3 – Generera streckkod‑PNG och exportera streckkodsbilden

Nu kan du rendera streckkoden och skriva den till en PNG‑fil. `Save`‑metoden tar målsökvägen och det önskade bildformatet.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Vad som händer under huven:**  
`BarcodeGenerator.Save` rasteriserar streckkoden till en bitmap, applicerar den X‑dimension du angav tidigare och kodar bitmapen som en PNG‑fil. Den resulterande filen kan användas direkt i webbsidor, skrivas ut på etiketter eller bäddas in i PDF‑dokument.

## Fullständigt källkodsexempel

Nedan finns en komplett, fristående konsolapplikation som du kan kopiera, klistra in och köra. Den demonstrerar **how to generate barcode PNG**‑filer, **export barcode image**, och innehåller grundläggande felhantering.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Förväntat resultat

När du kör programmet bör du se:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Att öppna PNG‑filen visar en tydlig **GS1 MicroPDF417**‑streckkod som kodar GTIN‑14 `12345678901234` och serienumret `ABC123`. Att skanna den med någon GS1‑kompatibel scanner returnerar den ursprungliga datasträngen.

## Vanliga fallgropar och bästa praxis

| Problem | Varför det händer | Hur man undviker det |
|---------|-------------------|----------------------|
| **Felaktig AI‑formatering** | Saknade parenteser eller fel ordning gör att streckkoden inte blir GS1. | Omslut alltid varje AI med parenteser, t.ex. `(01)`. |
| **För liten X‑dimension** | Streckkoden blir oläslig på lågupplösta enheter. | Håll `XDimension.Pixels` ≥ 2 för de flesta skrivare; öka för hög‑DPI‑utskrift. |
| **Utdatamappen finns inte** | `Save` kastar `DirectoryNotFoundException`. | Använd `Directory.CreateDirectory` innan du anropar `Save`. |
| **Fel EncodeType används** | Vissa typer (t.ex. `Code128`) stödjer inte GS1‑data automatiskt. | Välj `EncodeTypes.MicroPdf417` eller någon annan GS1‑kompatibel typ. |
| **Saknar NuGet‑referens** | Kompileringfel som `The type or namespace name 'Aspose' could not be found`. | Installera `Aspose.BarCode`‑paketet via NuGet. |

## Utöka exemplet

* **Olika bildformat** – Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Gif` eller `Bmp` om du behöver ett annat format.  
* **Högupplöst output** – Ställ in `generator.Parameters.ImageResolution.DpiX` och `DpiY` innan du sparar.  
* **Bädda in i PDF** – Använd `Aspose.Pdf` för att placera PNG‑filen i en PDF‑faktura eller etikett.

## Slutsats

Du vet nu hur du **create barcode GS1** i C# med Aspose.BarCode `BarcodeGenerator`, **generate barcode PNG** och **export barcode image** till filsystemet. Guiden täckte varje steg – från att initiera generatorn med GS1‑data, justera X‑dimensionen, till att spara den slutliga PNG‑filen – samtidigt som vanliga fel adresserades och utökade idéer presenterades.

Känn dig fri att experimentera med andra GS1 Application Identifiers, olika streckkodssymboler eller högupplösta bilder. När du behärskar dessa grunder blir generering av kompatibla streckkoder för lager, frakt eller detaljhandel en rutinmässig del av din .NET‑verktygslåda.

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}