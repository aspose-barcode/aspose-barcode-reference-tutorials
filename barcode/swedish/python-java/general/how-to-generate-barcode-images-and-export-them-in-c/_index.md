---
category: general
date: 2026-10-21
description: Lär dig hur du genererar streckkodsbilder i C# och hur du exporterar
  streckkodsfiler som PNG med Aspose.BarCode för snabba, pålitliga resultat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: sv
lastmod: 2026-10-21
og_description: Hur man genererar streckkodsbilder i C# och hur man exporterar streckkodsfiler
  som PNG. Följ den här kompletta handledningen för att skapa Planet- och RM4SCC-streckkoder
  med Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Hur du genererar streckkodsbilder och exporterar dem i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hur man genererar streckkodsbilder och exporterar dem i C#
url: /sv/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du streckkodsbilder och exporterar dem i C#

Om du behöver **how to generate barcode** bilder i en .NET‑applikation, visar den här guiden de exakta stegen för att skapa Planet‑ och RM4SCC‑streckkoder och sedan **how to export barcode** filer som PNG‑filer. Du får ett färdigt kodexempel, en beskrivning av varje inställning och tips för vanliga fallgropar.

Handledningen täcker:

* Lägga till Aspose.BarCode NuGet‑paketet
* Konfigurera modulbredd och valfri stapelhöjd
* Spara de genererade streckkoderna till disk
* Verifiera utdatafilerna

> **Förutsättning** – .NET 6+ SDK, Visual Studio 2022 (eller någon IDE), och en internetanslutning för att ladda ner Aspose.BarCode‑paketet.

## Vad du kommer att uppnå

I slutet av den här artikeln kommer du att kunna:

* Generera en **Planet**‑streckkod med automatisk stapelhöjd.
* Generera en **RM4SCC**‑streckkod med automatisk stapelhöjd.
* Åsidosätta standardhöjden och skapa en 100‑pixel‑hög streckkod.
* Exportera varje streckkod till en PNG‑fil i en mapp du väljer.

## Steg 1: Installera Aspose.BarCode

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet tillhandahåller klassen `BarcodeGenerator` och uppräkningen `EncodeTypes` som används i koden nedan.

## Steg 2: Ställ in utdatamappen

Skapa en mapp där PNG‑filerna ska lagras. Mappen kan vara absolut eller relativ till projektets rot.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Tips:** Att använda `Path.Combine` undviker hårdkodade sökvägsavgränsare och fungerar på Windows, macOS och Linux.

## Steg 3: Generera streckkoder med automatisk stapelhöjd

När du inte anger en stapelhöjd väljer Aspose.BarCode en storlek som passar den kodade datan. Följande kod skapar två streckkoder—Planet och RM4SCC—med en modulbredd på 4 pixel.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Varför detta fungerar:**  
* `EncodeTypes.Planet` och `EncodeTypes.RM4SCC` talar om för generatorn vilken symbolik som ska användas.  
* `XDimension.Pixels` definierar bredden på en enskild streckkodmodul; ett värde på 4 px ger en tydlig, läsbar bild.  
* Eftersom `BarHeight` inte är satt beräknar biblioteket den optimala höjden automatiskt.

## Steg 4: Generera streckkoder med en fast 100‑pixel stapelhöjd

Om din design kräver en specifik stapelhöjd kan du åsidosätta den automatiska beräkningen:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Varför du kan behöva en fast höjd:**  
Designspecifikationer för fraktetiketter anger ofta exakta stapeldimensioner för att säkerställa kompatibilitet med streckkodsläsare. Att sätta `BarHeight.Pixels` garanterar enhetlighet i alla genererade bilder.

## Steg 5: Verifiera de exporterade filerna

Efter att programmet har körts innehåller mappen `Barcodes` fyra PNG‑filer:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Öppna någon av dem med en bildvisare eller bädda in dem i en PDF för att bekräfta att de renderas korrekt. Om en scanner misslyckas med att läsa en streckkod, öka `XDimension.Pixels`‑värdet eller dubbelkolla inmatningssträngens längd.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Du bör se en output liknande:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Vanliga frågor och edge cases

| Fråga | Svar |
|----------|--------|
| **Kan jag exportera till andra format än PNG?** | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp`, `Gif` eller `Tiff`. |
| **Vad händer om min data innehåller tecken som inte tillåts av symboliken?** | Generatorn kastar `ArgumentException`. Validera inmatningen eller byt till en symbolik som stödjer teckenuppsättningen. |
| **Hur ändrar jag förgrunds‑/bakgrundsfärgerna?** | Sätt `Parameters.Barcode.ForeColor` och `Parameters.Barcode.BackColor` innan du anropar `Save`. |
| **Finns det ett sätt att generera streckkoder i minnet istället för att spara till disk?** | Anropa `GenerateBarCodeImage()` för att få ett `System.Drawing.Image`‑objekt, manipulera eller strömma det efter behov. |

## Proffstips: batch‑behandling

När du behöver skapa många streckkoder (t.ex. för en postlista) kan du omsluta genereringslogiken i en `foreach`‑loop:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Detta mönster skalar till tusentals streckkoder samtidigt som koden förblir koncis.

## Slutsats

Du vet nu **how to generate barcode** bilder i C# och **how to export barcode** filer som PNG med Aspose.BarCode. Det kompletta exemplet visar både automatisk och fast‑höjds‑generering för Planet‑ och RM4SCC‑symbolik, vilket ger dig en solid grund för alla streckkod‑relaterade projekt.

**Nästa steg**

* Utforska andra symboliker som Code128, QR eller DataMatrix.  
* Experimentera med färganpassning (`ForeColor`, `BackColor`).  
* Integrera de genererade PNG‑filerna i PDF‑fakturor eller fraktetiketter med ett PDF‑bibliotek.  

Lycka till med kodningen, och låt dina streckkoder skanna smidigt!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Skapa GS1‑streckkodsbilder i C# – Hur man snabbt genererar streckkod i C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [hur man genererar streckkodsbilder med Aspose.BarCode i C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}