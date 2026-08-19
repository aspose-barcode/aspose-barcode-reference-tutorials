---
category: general
date: 2026-08-19
description: Lär dig hur du genererar en streckkod‑PNG‑fil i C# och justerar dess
  höjd, med fokus på hur du skapar streckkodsbilder och enkelt ändrar streckkodens
  höjd.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: sv
lastmod: 2026-08-19
og_description: Skapa en streckkod‑PNG‑fil i C# och lär dig hur du genererar streckkods­bilder,
  justerar streckkodshöjden och ändrar streckkodshöjden för optimal skanning.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Skapa en streckkod PNG-fil i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Hur man skapar en streckkod PNG‑fil med justerbar höjd i C#
url: /sv/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du en streckkod PNG-fil med justerbar höjd i C#

Om du behöver skapa en **barcode PNG file** i C#, visar den här guiden exakt hur du gör. Du får se ett komplett, körbart exempel som demonstrerar **how to generate barcode**‑bilder och hur du **adjust barcode height** för olika användningsfall.

Att generera en streckkod PNG‑fil är ett vanligt krav för lagerhanteringssystem, kassasystem och alla applikationer som måste skriva ut eller visa maskinläsbara data. När du är klar med den här tutorialen kan du ändra streckkodens höjd, spara flera PNG‑filer och förstå hur höjden påverkar skanningspålitligheten.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* **Aspose.BarCode for .NET** NuGet‑paketet (kodexemplet använder detta bibliotek)  

Du kan lägga till paketet från kommandoraden:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Den fria utvärderingsversionen av Aspose.BarCode fungerar för utveckling och testning. För produktion, skaffa en licensnyckel.

## Installera streckkodsbiblioteket

Det första steget är att referera biblioteket i ditt projekt. Lägg till följande `using`‑direktiv högst upp i din C#‑fil:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa namnrymder ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`.

## Skapa streckkod PNG‑filen

Nu skapar vi en `BarcodeGenerator`‑instans som kommer att producera en **barcode PNG file**. Exemplet använder Databar OmniDirectional‑symbologi, men du kan ersätta `EncodeTypes.DatabarOmniDirectional` med vilken stödjande typ som helst.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Strängen `"(01)12345678901231"` följer GS1 Application Identifier‑formatet för ett 14‑siffrigt GTIN. Anpassa datan så att den matchar dina egna produktidentifierare.

## Ställ in X‑dimension (valfritt)

X‑dimensionen definierar bredden på en enskild streckkodmodul. Ett pixel‑baserat värde ger dig exakt kontroll över bildstorleken.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på `2` pixlar fungerar bra för de flesta skärmar. Öka det om du behöver en större streckkod vid utskrift.

## Justera streckkodshöjd och spara streckkod PNG‑filen

`BarHeight`‑egenskapen styr den vertikala storleken på staplarna. Genom att ändra detta värde kan du **adjust barcode height** utan att påverka den kodade datan.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Filen `DatabarBarHeight30Pixels.png` är nu en **barcode PNG file** som är 30 pixlar hög.  

För att **change barcode height** och skapa en andra bild, tilldela helt enkelt ett nytt värde och anropa `Save` igen:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Du har nu två PNG‑filer—en på 30 px och en på 60 px—som demonstrerar hur du **adjust barcode height** i farten.

### Varför stapelhöjden är viktig

* **Readability:** Skannrar förväntar sig en minsta höjd för pålitlig detektering. En för kort streckkod kan missas, särskilt med lågupplösta kameror.  
* **Aesthetics:** Att matcha streckkodshöjden med omgivande designelement ger ett renare UI.  
* **Print constraints:** Vissa etikettskrivare har fasta höjdluckor; genom att justera streckkodshöjden säkerställer du att den får plats.  

**Best practice:** Håll höjden som en multipel av X‑dimensionen (t.ex. 30 px när X‑dimensionen är 2 px) för att behålla proportionerna och undvika distortion.

## Komplett exempel

Nedan är det fullständiga, självständiga programmet som du kan klistra in i en konsolapplikation och köra direkt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Förväntad output**

När programmet körs skapas två filer i den körbara filens arbetskatalog:

* `DatabarBarHeight30Pixels.png` – en 30‑pixel‑hög streckkod PNG‑fil  
* `DatabarBarHeight60Pixels.png` – en 60‑pixel‑hög streckkod PNG‑fil  

Öppna någon av PNG‑filerna med en bildvisare; du kommer att se en tydlig Databar OmniDirectional‑streckkod redo för skanning.

## Edge cases and troubleshooting

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| Barcode appears blurry | X‑dimension too low for chosen height | Increase `XDimension.Pixels` (e.g., from 2 to 3) |
| Scanner fails on low‑height barcode | Height below scanner’s minimum | Set `BarHeight.Pixels` to at least 30 px (or per scanner specs) |
| PNG file is empty or corrupted | Output path invalid or write permission denied | Use an absolute path or ensure the app has write access |
| Need a different symbology | Current `EncodeTypes` not suitable | Replace `EncodeTypes.DatabarOmniDirectional` with another enum value (e.g., `EncodeTypes.Code128`) |

## Vanliga frågor

**Q: Kan jag generera andra bildformat (JPEG, BMP)?**  
A: Ja. Ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` osv.

**Q: Hur bäddar jag in PNG‑filen i en webbsida?**  
A: Servera den genererade PNG‑filen via en HTTP‑endpoint eller konvertera den till en Base64‑sträng och placera den i ett `<img>`‑tags `src`‑attribut.

**Q: Finns det ett sätt att sätta bakgrundsfärgen?**  
A: Använd `generator.Parameters.Image.BackgroundColor = Color.White;` (eller någon `System.Drawing.Color`).

## Slutsats

Du vet nu hur du **generate a barcode PNG file** i C# och exakt **adjust barcode height** för att möta skannings‑ eller designkrav. Genom att ändra `BarHeight.Pixels`‑egenskapen kan du **change barcode height** i farten och producera flera PNG‑tillgångar från en enda kodbas.

Nästa steg är att utforska andra anpassningsalternativ såsom förgrundsfärg, marginaler och att lägga till mänskligt läsbar text. Du kan också experimentera med olika symbologier (`EncodeTypes.Code128`, `EncodeTypes.QR`) för att bredda det datautbud du kan koda.

Lycka till med kodningen, och må dina streckkoder alltid skannas på första försöket!

## Vad bör du lära dig härnäst?

De följande tutorialerna behandlar närliggande ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}