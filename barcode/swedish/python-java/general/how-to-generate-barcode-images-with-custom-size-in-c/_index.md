---
category: general
date: 2026-08-22
description: Hur man snabbt genererar en streckkod och lär sig hur man ändrar streckkodens
  storlek när man exporterar streckkodsbilden som PNG med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: sv
lastmod: 2026-08-22
og_description: Hur du genererar en streckkod i C# och enkelt ändrar streckkodens
  storlek innan du exporterar streckkodsbilden som PNG. Följ den här kompletta guiden.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Hur man genererar streckkodsbilder med anpassad storlek i C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man genererar streckkodsbilder med anpassad storlek i C#
url: /sv/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkodsbilder med anpassad storlek i C#

Om du behöver **how to generate barcode** för postautomatisering, lagerhantering eller evenemangsbiljetter, visar den här guiden en komplett, färdigkörbar lösning i C#. Du kommer också att lära dig **how to change barcode size** och **export barcode image**-filer i PNG-format utan att lämna din IDE.

Vi kommer att använda Aspose.BarCode-biblioteket eftersom det stödjer OneCode-symbologi, låter dig kontrollera dimensioner pixel‑för‑pixel och hanterar bildexport med ett enda metodanrop. I slutet av handledningen kommer du att ha fyra PNG-filer—varje fil representerar en OneCode-streckkod med ett olika antal siffror.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+)
- Visual Studio 2022 (eller någon C#-redigerare du föredrar)
- En NuGet-referens till **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Grundläggande kunskap om C#-syntax

> **Pro tip:** Om du utvärderar biblioteket erbjuder Aspose en gratis 30‑dagars provperiod som inkluderar alla streckkods‑funktioner.

## Steg 1: Skapa ett minimalt konsolprojekt

Skapa en ny konsolapplikation och lägg till Aspose.BarCode-paketet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Den genererade `Program.cs` kommer att innehålla hela streckkodsgenereringslogiken.

## Steg 2: How to generate barcode – skapa en återanvändbar metod

Nedan är en självständig metod som tar emot datasträngen, önskat filnamn och valfria storleksparametrar. Denna metod demonstrerar **how to generate barcode**-kärnmönstret.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Varför denna metod är viktig

- **Encapsulation:** Alla storleksrelaterade inställningar finns på ett ställe, vilket gör det enkelt att anropa metoden med olika dimensioner.
- **Reusability:** Du kan återanvända samma metod för vilken OneCode-stränglängd som helst, vilket är viktigt eftersom OneCode endast accepterar 20‑31 siffror.
- **Clarity:** Kommentarer märkta med emojis guidar läsarna genom de tre logiska faserna—initialisering, storleksändring och export.

## Steg 3: Ändra streckkodsstorlek för olika krav

Ibland förväntar sig en scanner en högre streckkod, eller så kräver en utskriftslayout en smalare modul. `XDimension.Pixels`-egenskapen styr bredden på en enskild streckkodmodul, medan `BarHeight.Pixels` anger den totala höjden.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Viktiga punkter när du ändrar storlek:**

- **Minimum X‑dimension:** 1 pixel är tekniskt tillåtet, men de flesta scanners behöver minst 2 pixel för pålitlig läsning.
- **Maximum height:** Det finns ingen hård gräns, men mycket höga streckkoder kan överskrida utskriftsområdet på standardetiketter.
- **Aspect ratio:** Håll förhållandet mellan höjd och modulbredd balanserat (≈12‑15 × modulbredd) för att undvika förvrängning.

## Steg 4: Exportera streckkodsbilder i andra format (valfritt)

`Save`-metoden accepterar flera `BarCodeImageFormat`-värden: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Om du behöver ett förlustfritt vektorformat kan du exportera till `Svg` istället.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Att exportera som PNG är det vanligaste valet eftersom det bevarar skarpa kanter och är brett stödjat av webbläsare och utskriftsprocesser.

## Förväntat resultat

När programmet körs skapas fyra PNG-filer i projektmappen:

- `PostalOneCodeBarcode20Digits.png` – 20‑siffrig OneCode-streckkod
- `PostalOneCodeBarcode25Digits.png` – 25‑siffrig OneCode-streckkod
- `PostalOneCodeBarcode29Digits.png` – 29‑siffrig OneCode-streckkod
- `PostalOneCodeBarcode31Digits.png` – 31‑siffrig OneCode-streckkod

Varje bild kommer att se liknande ut som platshållaren nedan (den faktiska grafiken beror på de numeriska data du angav).

![How to generate barcode example](https://example.com/placeholder.png "How to generate barcode example")

*Bildens alt‑text innehåller huvudnyckelordet för tillgänglighet och SEO.*

## Vanliga frågor och edge cases

| Question | Answer |
|----------|--------|
| **Vad händer om datasträngen är kortare än 20 siffror?** | OneCode kräver minst 20 siffror. Fyll på strängen med inledande nollor eller använd en annan symbologi (t.ex. Code128). |
| **Kan jag generera streckkoder i en flertrådad miljö?** | Ja. `BarcodeGenerator` är inte trådsäker, så skapa en separat generator per tråd. |
| **Hur sätter jag en bakgrundsfärg?** | Använd `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` innan du anropar `Save`. |
| **Finns det ett sätt att bädda in bilden direkt i en HTML‑sida?** | Spara bilden till en `MemoryStream`, konvertera till Base64 och bädda in med `<img src="data:image/png;base64,..." />`. |

## Slutsats

Du vet nu hur du **how to generate barcode** bilder i C# med Aspose.BarCode, hur du **change barcode size** genom att justera X‑dimension och stapelhöjd, och hur du **export barcode image**-filer i PNG (eller andra) format. Den återanvändbara `GenerateOneCode`-metoden låter dig skapa vilken OneCode-streckkod som helst mellan 20 och 31 siffror med en enda kodrad.

Från och med nu kan du:

- Experimentera med andra symbologier (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Integrera generatorn i ett web‑API som returnerar streckkodsbilder på begäran.
- Kombinera PNG‑utdata med ett PDF‑bibliotek för att bädda in streckkoder i fraktetiketter.

Lycka till med kodningen, och dela gärna dina egna varianter i kommentarerna!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix-streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hur man genererar Aztec-streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}