---
category: general
date: 2026-07-18
description: Lär dig hur du genererar streckkodsbilder med en .net‑streckkodsgenerator
  och enkelt ändrar streckkodshöjden för GS1‑Databar Omni‑Directional‑symboler.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: sv
lastmod: 2026-07-18
og_description: .net streckkodsgenerator låter dig snabbt skapa streckkodsbilder.
  Den här guiden visar hur du genererar streckkoder, justerar stapelhöjden och sparar
  PNG‑filer.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Ändra streckkodshöjd med .net streckkodsgenerator
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .net streckkodsgenerator – ändra streckkodshöjd
url: /sv/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net streckkodsgenerator – ändra streckkodshöjd

Har du någonsin undrat **hur man genererar streckkod**‑bilder utan att jonglera med dussintals tredjepartsverktyg? I .NET‑världen finns ett förvånansvärt enkelt sätt att göra det, och nyckelkomponenten är **.net barcode generator**. Med bara några rader C# kan du skapa en GS1‑Databar Omni‑Directional‑symbol, justera stapelhöjden och spara resultatet som en PNG‑fil.

Om du bygger ett lagersystem, en fraktetikett‑skrivare eller någon app som behöver en läsbar kod, så tar den här handledningen dig från noll till en fungerande streckkod på några minuter. Vi går igenom hela koden, förklarar varför varje inställning är viktig och visar hur du **ändrar streckkodshöjden** utan att bryta specifikationen.

## Vad du behöver

- .NET 6.0 eller senare (API:et fungerar likadant på .NET Framework 4.7+)
- En referens till streckkodsbiblioteket (t.ex. Aspose.BarCode for .NET – samma klasser används av många kommersiella paket)
- En utvecklingsmiljö (Visual Studio, Rider eller VS Code med C#‑tillägget)
- En mapp där du har skrivrättigheter – handledningen sparar PNG‑filer där

Det är allt. Inga extra NuGet‑paket utöver själva streckkodsbiblioteket.

## Använda .net barcode generator för att ändra streckkodshöjd

Nedan är ett **komplett, körbart konsolprogram**. Klistra in det i ett nytt C#‑projekt, justera utdatamappen och tryck F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Varför varje rad är viktig

| Rad | Orsak |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Skapar en **.net barcode generator** med önskad symboltyp och datapayload. Enum‑värdet `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket att använda GS1‑Databar Omni‑Directional‑formatet. |
| `XDimension.Pixels = 2;` | X‑dimensionen är bredden på den tunnaste stapeln. Att sätta den till *2 pixlar* ger en skarp bild på de flesta skärmar samtidigt som filstorleken hålls låg. |
| `BarHeight.Pixels = 30;` | Detta är steget för **ändra streckkodshöjd** som bestämmer hur höga varje stapel blir. En höjd på 30 pixlar är ett bra standardvärde för små etiketter. |
| `generator.Save(...);` | Sparar streckkoden till en PNG‑fil. PNG är förlustfri, vilket betyder att skannrarna ser exakt det mönster du genererat. |
| `BarHeight.Pixels = 60;` | Här **ändrar vi streckkodshöjden** igen—denna gång till 60 pixlar. Biblioteket renderar automatiskt om symbolen med den nya dimensionen när du anropar `Save` en andra gång. |
| `Console.WriteLine(...);` | Ger dig snabb återkoppling att processen avslutades utan att kasta ett undantag. |

> **Proffstips:** Om du behöver högre upplösning för utskrift, byt `BarCodeImageFormat.Png` till `BarCodeImageFormat.Tiff` och öka `Resolution`‑egenskapen (t.ex. `generator.Parameters.ImageResolution = 300;`). Stapelhöjden respekteras fortfarande, den renderas bara med en finare DPI.

## Hur man genererar streckkodsbilder med olika inställningar

Kodsnutten ovan täcker grunderna, men verkliga scenarier kräver ofta extra justeringar:

### Justera X‑dimensionen för större utskrifter
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Att öka X‑dimensionen gör hela streckkoden större utan att ändra den kodade datan. Detta är praktiskt när du skriver ut på stora etiketter.

### Byta utdataformat
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG skalas oändligt, vilket är perfekt för webbaserade skannrar som behöver skarpa vektorer.

### Lägga till mänskligt läsbar text
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Att aktivera `CodeTextVisible` lägger till den råa datan under streckkoden, användbart för verifiering under testning.

## Vanliga fallgropar när du **ändrar streckkodshöjd**

1. **För låg höjd** – Vissa skannrar kräver en minsta stapelhöjd (ofta 10 mm i fysiska enheter). Om du sätter `BarHeight.Pixels` för lågt kan den genererade bilden bli oläslig på en riktig skanner. Testa alltid med din mål‑hardware.
2. **Ej matchande X‑dimension och höjd** – En enorm stapelhöjd ihop med en liten X‑dimension kan se utdragen ut och kan orsaka avkodningsfel. Sikta på ett balanserat förhållande (ungefär 3:1 till 5:1) om inte specifikationen säger annat.
3. **Glömmer att återställa parametrar** – Generatorn behåller tillstånd mellan sparningar. Om du ändrar `BarHeight` för en bild och sedan återanvänder samma instans för en annan streckkod, så kvarstår den tidigare höjden. Återställ antingen egenskapen eller skapa en ny `BarcodeGenerator` för varje unik streckkod.

## Fullt end‑to‑end‑exempel (inklusive NuGet‑installation)

Om du börjar från början, följ dessa steg för att få projektet att köras:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Ersätt den automatiskt genererade `Program.cs` med kodblocket som visades tidigare, **kom ihåg att ersätta `YOUR_DIRECTORY`** med något i stil med `Path.Combine(Environment.CurrentDirectory, "output")`. Sedan:

```bash
dotnet run
```

Du bör se två PNG‑filer i mappen `output`:

- `DatabarBarHeight30Pixels.png` – en kompakt streckkod på 30 pixlar i höjd.
- `DatabarBarHeight60Pixels.png` – en högre version på 60 pixlar.

Båda bilderna ser liknande ut, men den andra har märkbart längre staplar, vilket gör den lättare för lågupplösta skannrar att läsa.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output som visar olika stapelhöjder"}

## Sammanfattning & nästa steg

Vi har gått igenom hur man **genererar streckkod**‑bilder med en **.net barcode generator**, finjusterat egenskapen **ändra streckkodshöjd**, och sparat resultaten i PNG‑format. De viktigaste slutsatserna är:

- Instansiera generatorn med rätt `EncodeTypes`.
- Styr den visuella storleken via `XDimension` och `BarHeight`.
- Anropa `Save` efter varje ändring för att spara en ny bild.
- Justera upplösning, format,

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man skapar dotcode med utökad kodtext med Aspose.BarCode för .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}