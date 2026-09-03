---
category: general
date: 2026-07-15
description: Generera streckkod från text med Aspose.BarCode i C#. Lär dig hur du
  ändrar kolumnantal, sparar streckkodsbild och skapar Aspose‑streckkodslösningar
  snabbt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- how to change column count
- save barcode image
- create barcode aspose
language: sv
lastmod: 2026-07-15
og_description: Generera streckkod från text med Aspose.BarCode. Denna guide visar
  hur du ändrar kolumnantalet, sparar streckkodsbilden och skapar streckkod med Aspose
  i några rader kod.
og_image_alt: Generate barcode from text example – MicroPdf417 PNG output
og_title: Generera streckkod från text med Aspose.BarCode – Snabb C#‑genomgång
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  headline: Generate barcode from text using Aspose.BarCode – C# Guide
  type: TechArticle
- description: Generate barcode from text using Aspose.BarCode in C#. Learn how to
    change column count, save barcode image, and create barcode Aspose solutions fast.
  name: Generate barcode from text using Aspose.BarCode – C# Guide
  steps:
  - name: What if my text is longer than the default capacity?
    text: MicroPdf417 automatically switches to a multi‑row layout when the data exceeds
      the maximum per row. You can still control the column count, but the library
      may add extra rows behind the scenes. No extra code needed—just keep an eye
      on the resulting image dimensions.
  - name: How do I change the image format to JPEG or BMP?
    text: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` (or `Bmp`).
      Remember that JPEG introduces compression artifacts, which can affect scanning
      reliability. PNG is the safest default.
  - name: I’m seeing a watermark in the output—what’s wrong?
    text: That’s the evaluation version of Aspose.BarCode. To **create barcode Aspose**
      without watermarks, load a valid license file as shown in the commented line
      of Step 2.
  - name: Can I generate other symbologies (QR, Code128, etc.)?
    text: Absolutely. Just swap `EncodeTypes.MicroPdf417` with any other value from
      the `EncodeTypes` enum, e.g., `EncodeTypes.QR` or `EncodeTypes.Code128`. The
      rest of the code stays the same, which makes the approach highly reusable.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-processing
title: Generera streckkod från text med Aspose.BarCode – C#‑guide
url: /sv/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod från text med Aspose.BarCode – C# Guide

Att generera streckkod från text med Aspose.BarCode är förvånansvärt enkelt. I den här handledningen går vi igenom **hur man genererar streckkod**, justerar kolumnlayouten och slutligen **sparar streckkodsbild** som en PNG‑fil. Oavsett om du bygger ett biljettsystem, en lageretikett‑skrivare eller bara experimenterar med QR‑liknande koder, så kommer stegen nedan snabbt att leda dig dit.

## Vad du kommer att lära dig

- Skapa en streckkod från en godtycklig Unicode‑sträng (ja, även “Åspóse.Barcóde©” fungerar).
- Justera **column count** för MicroPdf417 för att passa smala eller breda etiketter.
- Spara resultatet på disk med rätt bildformat.
- Tips för att hantera specialtecken och vanliga fallgropar när du **create barcode Aspose**‑lösningar.

Inga externa verktyg, inga kommandorads‑hack—bara ren C# och Aspose.BarCode‑biblioteket.

## Förutsättningar

Innan vi dyker ner, se till att du har:

1. **.NET 6.0** eller senare installerat (koden fungerar även på .NET Framework 4.7+).
2. En **license** för Aspose.BarCode, eller så kan du börja med den kostnadsfria utvärderingsversionen.
3. En mapp du kan skriva till – vi kallar den `YOUR_DIRECTORY` i exemplen.

Om du saknar någon av dessa, hämta NuGet‑paketet nu:

```bash
dotnet add package Aspose.BarCode
```

Det är allt—inga extra DLL‑filer att kopiera manuellt.

## Steg 1 – Ställ in projektet och importerna

Först, skapa en konsolapp (eller klistra in koden i vilket C#‑projekt som helst). Det viktiga är att importera rätt namnrymder:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeImageFormat; // for the image format enum
```

Varför dessa using‑satser? `BarcodeGenerator` finns i `Aspose.BarCode.Generation`, medan `BarCodeImageFormat`‑enumen finns i `Aspose.BarCode`. Att hålla importerna organiserade gör den efterföljande koden lättläst som vanlig engelska.

## Steg 2 – Skapa Barcode‑generatorn (how to generate barcode)

Nu **genererar vi streckkod från text**. `EncodeTypes`‑enumen talar om för Aspose vilken symbologi som ska användas; här väljer vi `MicroPdf417` eftersom den hanterar långa strängar i ett kompakt rutnät.

```csharp
// Step 2: Create a barcode generator for MicroPdf417 with the desired text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

// Optional: If you have a license, load it now to avoid the evaluation watermark
// generator.License = new License(); // generator.License.SetLicense("Aspose.Total.NET.lic");
```

Observera att strängen innehåller accentuerade tecken och en copyright‑symbol. Aspose.BarCode kodar automatiskt Unicode, så du behöver inte förbehandla texten.

## Steg 3 – Finjustera utseendet (how to change column count)

MicroPdf417 låter dig styra antalet kolumner, vilket direkt påverkar streckkodens bredd. En kompakt layout är bra för smala etiketter; en bredare layout förbättrar läsbarheten på stora utskrifter.

```csharp
// Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3b: Define the number of columns for the PDF417 layout (e.g., 4 columns)
generator.Parameters.Barcode.Pdf417.Columns = 4; // <-- how to change column count
```

Varför 2‑pixel‑moduler? Det ger en skarp bild utan att öka filstorleken. Känn dig fri att experimentera—värden mellan 1 och 4 fungerar vanligtvis bra. Om du någonsin behöver ett annat antal kolumner, ändra bara `Columns`‑egenskapen; Aspose räknar om layouten automatiskt.

## Steg 4 – Spara streckkodsbilden (save barcode image)

Med generatorn konfigurerad är vi redo att **save barcode image**. `Save`‑metoden accepterar en filsökväg och en bildformat‑enum. PNG är förlustfri, så streckkoden förblir skarp även efter skalning.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Ett snabbt tips: använd alltid en absolut sökväg eller säkerställ att arbetskatalogen är den du förväntar dig; annars kan filen hamna i bin‑mappen och du undrar varför du inte kan hitta den.

## Fullt fungerande exempel

När allt sätts ihop, här är ett självständigt program du kan kopiera‑klistra in i `Program.cs` och köra:

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
            // 1️⃣ Create the generator with Unicode text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // finer modules
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // how to change column count

            // 3️⃣ Choose output location
            string outputPath = @"C:\Temp\MicroPdf417.png";

            try
            {
                // 4️⃣ Persist the image (save barcode image)
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"✅ Barcode generated and saved to: {outputPath}");
            }
            catch (Exception ex)
            {
                // Pro tip: handle I/O errors gracefully
                Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
            }
        }
    }
}
```

**Förväntad output** (konsol):

```
✅ Barcode generated and saved to: C:\Temp\MicroPdf417.png
```

Och om du öppnar `MicroPdf417.png` kommer du att se en skarp MicroPdf417‑streckkod som kodar den ursprungliga strängen, komplett med de specialtecken vi matade in.

## Vanliga frågor & kantfall

### Vad händer om min text är längre än standardkapaciteten?

MicroPdf417 byter automatiskt till en flerradslayout när data överskrider max per rad. Du kan fortfarande styra antalet kolumner, men biblioteket kan lägga till extra rader i bakgrunden. Ingen extra kod behövs—håll bara ett öga på bildens dimensioner.

### Hur ändrar jag bildformatet till JPEG eller BMP?

Byt `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` (eller `Bmp`). Kom ihåg att JPEG introducerar komprimeringsartefakter, vilket kan påverka skanningspålitligheten. PNG är det säkraste standardalternativet.

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg);
```

### Jag ser ett vattenmärke i resultatet—vad är fel?

Det är utvärderingsversionen av Aspose.BarCode. För att **create barcode Aspose** utan vattenmärken, ladda en giltig licensfil som visas i den kommenterade raden i Steg 2.

### Kan jag generera andra symbologier (QR, Code128, etc.)?

Absolut. Byt bara `EncodeTypes.MicroPdf417` mot ett annat värde från `EncodeTypes`‑enum, t.ex. `EncodeTypes.QR` eller `EncodeTypes.Code128`. Resten av koden förblir densamma, vilket gör metoden mycket återanvändbar.

## Pro‑tips för produktionsklar streckkodsgenerering

- **Cache generatorn** om du skapar många streckkoder med samma inställningar; det minskar overhead för objekt‑skapande.
- **Validera inmatningssträngen** för längdbegränsningar specifika för den valda symbologin (Aspose kastar `ArgumentException` om den är för lång).
- **Använd `using`‑satser** eller `Dispose` generatorn när du är klar för att snabbt frigöra inhemska resurser.
- **Ställ in DPI** via `generator.Parameters.ImageResolution.DpiX/DpiY` om du behöver högupplösta utskrifter för stora etiketter.

## Slutsats

Du vet nu exakt **how to generate barcode from text** med Aspose.BarCode, hur du **change column count**, och det korrekta sättet att **save barcode image** som PNG. Det kompletta, körbara exemplet ovan visar ett rent, produktionsklart

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}