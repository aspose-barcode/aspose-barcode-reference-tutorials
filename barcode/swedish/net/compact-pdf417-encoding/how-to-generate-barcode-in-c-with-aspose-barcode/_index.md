---
category: general
date: 2026-09-16
description: Lär dig hur du genererar streckkod och ställer in streckkodens storlek
  i C#. Steg‑för‑steg‑guide med Aspose.BarCode för att skapa en Micro PDF417‑bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: sv
lastmod: 2026-09-16
og_description: Hur man genererar streckkod i C# och ställer in streckkodsstorlek
  med Aspose.BarCode. Följ den här koncisa handledningen för att skapa en Micro PDF417
  PNG.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Hur man genererar streckkod i C# – komplett Aspose.BarCode-guide
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hur man genererar streckkod i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod i C# med Aspose.BarCode

Om du behöver veta **hur man genererar streckkod** i ett .NET‑projekt, guidar den här handledningen dig genom hela processen med hjälp av Aspose.BarCode‑biblioteket. Du får också lära dig hur du **ställer in streckkodsstorlek** så att bilden passar ditt UI eller dina utskriftskrav.

Guiden täcker allt från installation av NuGet‑paketet till konfiguration av en Micro PDF417‑symbol och sparande som en PNG‑fil. När du är klar har du ett körbart kodexempel som du kan klistra in i vilken C#‑konsol‑ eller webbapplikation som helst.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar även med .NET Framework 4.6+)
- Visual Studio 2022 eller någon IDE som stödjer C#
- Internetåtkomst för att ladda ner **Aspose.BarCode**‑NuGet‑paketet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Grundläggande kunskap om C#‑syntax

## Hur man genererar streckkod med Aspose.BarCode

Det första steget är att skapa en `BarcodeGenerator`‑instans som vet vilken symbologi som ska användas och vilken data som ska kodas.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Varför detta är viktigt:** `EncodeTypes.MicroPdf417` talar om för biblioteket att producera en kompakt PDF417‑variant, idealisk för små etiketter eller QR‑kod‑liknande fotavtryck. Strängen `"Micro data"` blir den mänskligt läsbara nyttolasten som bäddas in i streckkoden.

## Ställ in streckkodsstorlek och dimensioner

En läsbar streckkod måste ha rätt modul‑ (X)‑dimension och tillräckligt många kolumner för att rymma datan. Här **ställer du in streckkodsstorlek**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** styr bredden på den minsta stapeln (”modulen”). Ett värde på `2` pixlar fungerar bra för skärmvisning; öka det för högupplöst utskrift.
- **Pdf417.Columns** begränsar antalet vertikala kolumner. Micro PDF417‑formatet stödjer endast upp till 7 kolumner; `4` ger en balanserad storlek utan att offra datakapacitet.

> **Proffstips:** Om den genererade bilden ser för liten ut, höj `XDimension.Pixels` till `3` eller `4`. Om du har ont om UI‑utrymme kan du sänka den till `1`, men se till att skannern du planerar att använda fortfarande kan läsa symbolen.

## Spara streckkodsbilden

Efter att du har konfigurerat storleken instruerar du helt enkelt generatorn att skriva bilden till disk.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

`Save`‑metoden accepterar alla format som stöds av Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG är förlustfritt och bevarar de skarpa kanterna som behövs för pålitlig skanning.

**Förväntad output:** En fil med namnet `micro.png` kommer att skapas i projektets arbetskatalog. När du öppnar den ser du en liten, högkontrast Micro PDF417‑streckkod som är redo för testning med vilken standard‑scanner som helst.

## Komplett exempel

När alla delar sätts ihop får du ett självständigt program som du kan köra direkt.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Kör programmet (`dotnet run` från konsolen) så ser du bekräftelsemeddelandet. Den genererade PNG‑filen kan bäddas in i rapporter, skrivas ut på produktetiketter eller visas på en webbsida.

## Vanliga frågor och edge‑cases

| Fråga | Svar |
|---|---|
| **Kan jag generera andra streckkodstyper?** | Ja. Byt ut `EncodeTypes.MicroPdf417` mot vilket värde som helst från `EncodeTypes`‑enumet (t.ex. `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Vad gör jag om jag behöver en större bild?** | Öka `XDimension.Pixels` eller använd `generator.Parameters.Image.Width/Height` för att tvinga en specifik pixelstorlek. |
| **Stöder biblioteket transparenta bakgrunder?** | Sätt `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` innan du anropar `Save`. |
| **Hur läser jag tillbaka streckkoden?** | Använd `Aspose.BarCode.BarCodeReader` på den sparade bilden; den upptäcker automatiskt symbologin. |
| **Är PNG‑filen säker för utskrift?** | PNG är förlustfritt, men för CMYK‑utskrift kan du överväga att spara som TIFF (`BarCodeImageFormat.Tiff`). |

## Slutsats

Du vet nu **hur man genererar streckkod** i C# och hur man **ställer in streckkodsstorlek** med Aspose.BarCode. Det kompletta exemplet visar hur man skapar en Micro PDF417‑symbol, justerar dess dimensioner och exporterar en PNG‑fil. Med den här grunden kan du utforska andra symbologier, anpassa färger eller integrera streckkodsgenerering i ASP.NET Core‑tjänster.

### Nästa steg

- Prova att generera en QR‑kod (`EncodeTypes.QR`) och jämför modul‑storlekar.  
- Experimentera med `generator.Parameters.Image` för att lägga till marginaler eller ändra DPI för utskriftsklar output.  
- Kombinera streckkodsgenerering med **Aspose.PDF** för att bädda in bilden direkt i en PDF‑rapport.

Lycka till med kodningen, och njut av den flexibilitet som Aspose.BarCode ger dina .NET‑streckkodprojekt!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}