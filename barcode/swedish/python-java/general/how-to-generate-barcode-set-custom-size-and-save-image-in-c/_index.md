---
category: general
date: 2026-09-13
description: Lär dig hur du genererar streckkod i C#, anpassar streckkodens storlek
  och sparar streckkodsbilden som PNG med Aspose.BarCode. Komplett steg‑för‑steg‑guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: sv
lastmod: 2026-09-13
og_description: Hur man genererar streckkod i C# med anpassad streckkodsstorlek och
  sparar streckkodsbilden som PNG. Följ den här kompletta guiden för Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Hur man genererar en streckkod, ställer in anpassad storlek och sparar bilden
  i C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Hur man genererar en streckkod med anpassad storlek och sparar bilden i C#
url: /sv/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här genererar du streckkod med anpassad storlek och sparar bild i C#

Om du behöver **how to generate barcode** i en .NET-applikation, visar den här handledningen en komplett lösning. Du kommer att se hur du justerar **custom barcode size** och **save barcode image**‑filer med bara några rader C#‑kod.

Att generera streckkoder är ett vanligt krav för lagersystem, fraktetiketter och kassasystem. I slutet av den här guiden kommer du att ha ett körbart program som skapar två DataBar‑Stacked‑Omnidirectional‑streckkoder, var och en med ett annat bildförhållande, och skriver dem till PNG‑filer på disk.

**Prerequisites**

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
- Visual Studio 2022 eller någon C#‑IDE
- Aspose.BarCode för .NET (gratis provversion eller licensierat NuGet‑paket)

---

## Så här genererar du streckkod med Aspose.BarCode

Aspose.BarCode‑biblioteket abstraherar de lågnivådetaljer som rör streckkodstandarder, så att du kan fokusera på de data du vill koda och det visuella utseende du behöver.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Varför varje rad är viktig

| Steg | Förklaring |
|------|------------|
| **1️⃣ Skapa en generator** | `EncodeTypes.DatabarStackedOmniDirectional`‑enumet talar om för Aspose vilken streckkodssymbolik som ska användas. Strängen `"(01)12345678901231"` följer GS1‑128‑dataformatet, där `(01)` är Application Identifier för ett GTIN. |
| **2️⃣ Ställ in X‑dimension** | `XDimension.Pixels` definierar bredden på en enskild streckkodmodul (det minsta strecket). Att ändra detta värde är det primära sättet att uppnå en **custom barcode size** utan att ändra de kodade data. |
| **3️⃣ Ställ in bildförhållande & spara** | `DataBar.AspectRatio` styr höjd‑till‑bredd‑förhållandet för DataBar‑symboler. Ett bildförhållande på 15 ger en relativt kort, bred streckkod, medan 30 gör den högre. `Save` skriver den visuella representationen till en PNG‑fil, vilket uppfyller kravet **save barcode image**. |
| **4️⃣ Ändra bildförhållande & spara igen** | Genom att återanvända samma generatorinstans kan du skapa flera bilder med olika visuella egenskaper samtidigt som datan förblir konstant. |

---

## Justera anpassad streckkodsstorlek utöver X‑dimension

Medan `XDimension.Pixels` sätter modulens bredd, kan du också finjustera streckkodens totala dimensioner genom att kombinera två egenskaper:

1. **`BarHeight`** – explicit höjd i pixlar.  
2. **`BarWidth`** – explicit bredd i pixlar (åsidosätter X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Proffstips:** När du skriver ut streckkoder, testa alltid den genererade bilden i den slutgiltiga utskriftsstorleken. En modulbredd på 2 px fungerar för skärmvisning, men utskrivna etiketter kräver ofta minst 4 px för att vara läsbara.

---

## Välja rätt bildformat för att spara streckkodsbilder

Aspose.BarCode stöder PNG, JPEG, BMP, GIF och TIFF. PNG är förlustfritt och bevarar skarpa kanter, vilket gör det till det säkraste valet för de flesta applikationer. Om du behöver en mindre fil för webbbruk fungerar JPEG med en kvalitetsinställning på 90 bra, men var medveten om att komprimeringsartefakter kan påverka skanningspålitligheten.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Fullständigt, körbart exempel

Nedan är ett fristående konsolprogram som du kan kopiera, klistra in och köra. Det demonstrerar **how to generate barcode**, modifierar **custom barcode size** och **save barcode image** i två olika format.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Förväntad utskrift i konsolen**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

De fyra bildfilerna kommer att visas i programmet


## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hur man genererar PDF417‑streckkod med Aspose – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}