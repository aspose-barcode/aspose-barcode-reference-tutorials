---
category: general
date: 2026-07-15
description: Generera PDF417‑streckkod snabbt med C#. Lär dig hur du genererar streckkod
  från text, justerar streckkodens storlek och ställer in anpassade streckkodsdimensioner
  på några minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: sv
lastmod: 2026-07-15
og_description: Generera PDF417-streckkod i C# omedelbart. Denna guide visar hur du
  genererar streckkod från text, justerar streckkodens storlek och använder anpassade
  streckkodsdimensioner.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Generera PDF417‑streckkod i C# – Fullständig programmeringshandledning
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Generera PDF417‑streckkod i C# – Komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod i C# – Komplett steg‑för‑steg‑guide

Har du någonsin behövt **generera PDF417 barcode** men varit osäker på vilka inställningar du ska justera? Du är inte ensam—många utvecklare stöter på samma problem när de först börjar arbeta med 2‑D-streckkoder. Den goda nyheten? Med några rader C# kan du omvandla vilken sträng som helst till en skannbar PDF417‑bild, kontrollera dess exakta storlek och till och med definiera en anpassad kolumn‑rad‑layout.

I den här handledningen går vi igenom hur man **genererar streckkod från text**, justerar streckkodens storlek och ställer in anpassade streckkodsdimensioner — allt med det populära Aspose.BarCode‑biblioteket. I slutet har du ett färdigt exempel som du kan lägga till i vilket .NET‑projekt som helst.

![Exempel på PDF417-streckkod](https://example.com/og-image.png "Exempel på PDF417-streckkod")

## Vad du kommer att bygga

- En PDF417-streckkod som kodar strängen `Åspóse.Barcóde©`.
- Precisionskontroll över X‑dimensionen (pixelbredden för varje modul).
- En anpassad layout med 4 kolumner och 9 rader.
- En PNG‑fil sparad på disk.

Inga externa tjänster, inga magiska trollstavar—bara ren C#‑kod som du kan kompilera direkt nu.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar även på .NET Framework 4.8).
- Visual Studio 2022 eller någon IDE som stödjer C#.
- Aspose.BarCode för .NET (gratis provversion eller licensierad version). Installera via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Det är allt—så snart paketet är refererat är du redo att köra.

## Steg 1 – Generera PDF417-streckkod med textdata

Det första vi behöver är en instans av `BarcodeGenerator` som vet att vi arbetar med PDF417‑symbologi och den exakta texten vi vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Varför detta är viktigt:**  
> `EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑2‑D‑formatet, medan det andra argumentet är **generera streckkod från text**‑payloaden. Allt du skickar här blir data som lagras i streckkodsmatrisen.

## Steg 2 – Justera streckkodens storlek (X‑dimension)

Om du någonsin har skrivit ut en streckkod som var för liten på ett kvitto, känner du frustrationen när skannern missar den. `XDimension`‑egenskapen styr bredden på en enskild modul (den minsta svarta eller vita fyrkanten) i pixlar.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Proffstips:**  
> Ett värde på 2 px fungerar bra för de flesta skärmvisningsscenarier. För högupplösta utskrifter kan du öka detta till 3 eller 4 px. Kom bara ihåg att större X‑dimensioner ökar den totala bildstorleken.

## Steg 3 – Ställ in anpassade streckkodsdimensioner (kolumner & rader)

PDF417 låter dig bestämma hur många kolumner och rader streckkoden ska uppta. Det är här **custom barcode dimensions** kommer in i bilden. Att ändra dessa värden kan hjälpa dig att passa streckkoden i ett trångt UI‑utrymme eller uppfylla en specifik etikettstorlek.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Vad händer under huven?**  
> Biblioteket omfördelar den kodade datan över det angivna rutnätet. Färre kolumner innebär högre streckkoder; fler rader gör dem kortare. Lek med siffrorna tills den visuella balansen känns rätt för din applikation.

## Steg 4 – Spara streckkodens bild

Nu när vi har konfigurerat allt ber vi helt enkelt generatorn att skriva en PNG‑fil. PNG är förlustfri, så skärpan i modulerna förblir intakt.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

När du kör programmet bör du se en fil på `C:\Barcodes\CustomLayout.png` som ser liknande ut som skärmdumpen ovan. Att skanna den med någon PDF417‑kompatibel läsare returnerar den ursprungliga strängen `Åspóse.Barcóde©`.

## Fullt fungerande exempel

Nedan är det kompletta programmet som du kan kopiera‑klistra in i en konsolapp. Det inkluderar alla using‑direktiv och felhantering du förväntar dig i produktionskod.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Förväntad utdata

Att köra koden skriver ut:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…och skapar en PNG som kan öppnas i vilken bildvisare som helst. Om du skannar den med en mobilapp (t.ex. “Barcode Scanner” på iOS/Android) bör den avkodade texten vara exakt **Åspóse.Barcóde©**.

## Vanliga frågor & kantfall

| Question | Answer |
|----------|--------|
| **Kan jag använda ett annat bildformat?** | Ja—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` eller `Svg` stöds alla. Ändra bara det andra argumentet till `Save`. |
| **Vad händer om min text innehåller Unicode‑tecken?** | Aspose.BarCode har fullt stöd för UTF‑8, så exemplet med `Å` och `©` fungerar direkt. |
| **Hur ändrar jag felkorrigeringsnivån?** | Använd `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (nivåer 0‑8). Högre nivåer ökar redundansen men också storleken. |
| **Jag behöver en transparent bakgrund—kan jag göra det?** | Ställ in `generator.Parameters.Barcode.Image.TransparentBackground = true;` innan du sparar. |
| **Finns det ett sätt att bädda in streckkoden direkt i en PDF?** | Absolut. Ersätt `Save`‑anropet med `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` så får du en en‑sides PDF som innehåller streckkoden. |

## Slutsats

Du vet nu hur du **genererar PDF417 barcode** i C# från vilken sträng som helst, **justerar streckkodens storlek**, och tillämpar **custom barcode dimensions** för att passa dina layoutbehov. Det fyrastegsflödet—initiera, storlek, layout, spara—täcker huvudarbetsflödet för de flesta 2‑D‑streckkodsscenarier.

Vad blir nästa steg? Prova att byta `EncodeTypes.Pdf417` mot `EncodeTypes.QR` eller `EncodeTypes.Code128` för att se hur API:et anpassar sig. Experimentera med olika `XDimension`‑värden, lek med kolumn‑/rad‑matrisen, eller bädda in bilden i en PDF‑rapport. Möjligheterna är praktiskt taget oändliga, och nu har du en solid grund att bygga vidare på.

Har du fler frågor, eller har du upptäckt ett smart knep när du lekt med PDF417? Lägg en kommentar nedan—låt oss hålla samtalet igång. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar Aztec-streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man genererar streckkod – En-dimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Generera DataMatrix-streckkod – Pro‑guide med Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}