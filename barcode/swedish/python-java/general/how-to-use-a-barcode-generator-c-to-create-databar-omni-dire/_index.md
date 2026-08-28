---
category: general
date: 2026-08-22
description: Barcode‑generator C#‑handledning visar hur man genererar streckkod‑PNG‑filer,
  skapar DataBar‑streckkoder och justerar streckkodens höjd på bara några steg.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: sv
lastmod: 2026-08-22
og_description: barcode generator C#-guiden går igenom hur du genererar barcode PNG,
  skapar DataBar‑streckkoder och justerar streckkodens höjd effektivt.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: Streckkodsgenerator C# – skapa DataBar‑streckkoder och justera höjden
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man använder en streckkodsgenerator i C# för att skapa DataBar‑omnidirektionella
  streckkoder
url: /sv/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder en barcode generator C# för att skapa DataBar Omni‑directional streckkoder

Om du behöver en **barcode generator C#** som kan producera högkvalitativa PNG‑bilder, så har den här guiden dig täckt. Du kommer att lära dig hur man genererar barcode PNG‑filer, skapar en DataBar Omni‑directional streckkod och justerar streckkodens höjd utan att lämna din IDE.

Att generera streckkoder programatiskt tar bort det manuella steget att använda en grafikredigerare. I slutet av den här tutorialen har du två PNG‑filer—en med 30‑pixel hög stapelhöjd och en annan med 60‑pixel hög stapelhöjd—klara för inkludering i fakturor, etiketter eller lagersystem.

**Prerequisites**

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
- En referens till `Aspose.BarCode` NuGet‑paketet (eller något bibliotek som exponerar ett liknande API)
- Grundläggande kunskap om C# och Visual Studio eller din föredragna IDE

---

## Steg 1: Ställ in barcode generator C#‑projektet

Att skapa en **barcode generator C#**‑instans är det första du gör. Konstruktorn tar två argument: streckkodstypen (`EncodeTypes.DatabarOmniDirectional`) och data‑payloaden. I det här exemplet följer payloaden GS1 Application Identifier‑formatet för en 14‑siffrig GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Varför detta är viktigt:** Enum‑värdet `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket att rendera en DataBar som kan läsas från vilken riktning som helst, vilket är idealiskt för små detaljhandelsetiketter.

---

## Steg 2: Definiera modulens dimension (X‑dimension)

X‑dimensionen styr bredden på en enskild barcode‑modul. Att sätta den till 2 pixlar ger en skarp, läsbar bild samtidigt som filstorleken hålls låg.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tips:** Om du behöver en kompaktare streckkod för begränsat utrymme, sänk värdet till 1 pixel, men testa läsbarheten med en scanner.

---

## Steg 3: Generera den första PNG‑filen med 30‑pixel stapelhöjd

Stapelhöjden bestämmer hur höga staplarna blir. En höjd på 30 pixel är en vanlig standard för vanliga etiketter.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Filen `DatabarBarHeight30Pixels.png` innehåller nu en **generate barcode PNG** som kan användas direkt i webbsidor eller skrivas ut på begäran.

---

## Steg 4: Justera streckkodens höjd till 60 pixlar och spara en andra PNG

Att ändra stapelhöjden är så enkelt som att tilldela ett nytt värde till samma egenskap. Detta demonstrerar **adjust barcode height**‑funktionen i generatorn.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Nu har du `DatabarBarHeight60Pixels.png`, vilket är idealiskt för större förpackningar där streckkoden måste läsas på avstånd.

**Förväntad output**

- `DatabarBarHeight30Pixels.png` – en kompakt DataBar Omni‑directional streckkod, 30 px hög.
- `DatabarBarHeight60Pixels.png` – samma streckkod, dubblerad i höjd för bättre synlighet.

Båda bilderna är PNG‑filer, bevarar förlustfri kvalitet och stödjer transparens om så behövs.

---

## Hur man genererar barcode PNG‑filer i olika format

Även om den här tutorialen fokuserar på PNG, accepterar `Save`‑metoden andra format såsom `Jpeg`, `Bmp` och `Svg`. För att **how to generate barcode**‑filer i ett annat format, ersätt helt enkelt `BarCodeImageFormat.Png` med det önskade enum‑värdet:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Att välja SVG är praktiskt när du behöver en vektorbild som kan skalas utan pixling.

---

## Vanliga fallgropar när du **create DataBar barcode** bilder

| Problem | Orsak | Åtgärd |
|-------|-------|-----|
| Barcode appears blurry | X‑dimension too low for the target resolution | Increase `XDimension.Pixels` to 3 or 4 |
| Scanner cannot read the code | Bar height too short for the scanner’s optics | Use a minimum of 30 pixels or follow the scanner’s specifications |
| Data string is rejected | Incorrect GS1 formatting | Ensure the string starts with the proper Application Identifier, e.g., `(01)` for GTIN‑14 |

Att åtgärda dessa punkter tidigt sparar tid när du integrerar streckkoder i produktionspipeline.

---

## Avancerat tips: Återanvänd samma generator för flera streckkoder

Om du behöver **generate barcode PNG**‑filer för en sats produkter, återanvänd samma `BarcodeGenerator`‑instans och uppdatera bara `CodeText`‑egenskapen:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Detta mönster minimerar overhead för objektinstansering och håller din kod koncis.

---

## Slutsats

Du har nu ett komplett **barcode generator C#**‑arbetsflöde som **creates DataBar barcodes**, **generates barcode PNG**‑filer, och låter dig **adjust barcode height** med en enda egenskapsändring. Exemplet täcker allt från projektuppsättning till hantering av edge cases, så att du kan integrera streckkodsskapande i vilken .NET‑applikation som helst med förtroende.

**Nästa steg**

- Utforska andra barcode‑symbologier (`EncodeTypes.QR`, `EncodeTypes.Code128`) för att bredda din lösning.
- Kombinera generatorn med ASP.NET Core för att leverera streckkoder i realtid via en API‑endpoint.
- Experimentera med färgalternativ (`generator.Parameters.Barcode.ForeColor`) för varumärkesändamål.

Lycka till med kodandet, och må dina skanningar alltid vara snabba!

## Vad bör du lära dig härnäst?

Följande tutorialer täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}