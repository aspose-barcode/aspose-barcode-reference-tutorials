---
category: general
date: 2026-08-03
description: Skapa streckkod‑PNG i C# och lär dig hur du ändrar bildförhållandet för
  DataBar‑bilder. Följ detta kompletta exempel med kod och tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: sv
lastmod: 2026-08-03
og_description: Skapa streckkod PNG i C# och se hur du ändrar bildförhållandet för
  DataBar‑streckkoder. Denna guide ger dig färdig‑körbar kod och praktiska tips.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Skapa streckkod PNG i C# – fullständigt exempel med kontroll av bildförhållande
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Skapa streckkod PNG i C# – steg‑för‑steg guide
url: /sv/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod PNG i C# – steg‑för‑steg guide

Om du behöver **skapa streckkod PNG** i C#, visar den här handledningen exakt hur du gör. Du kommer att generera en staplad omnidirektionell DataBar‑streckkod, spara den som en PNG‑fil och lära dig **hur du ändrar bildförhållandet** för att passa olika skanningsmiljöer.

Guiden täcker allt du behöver: nödvändiga paket, ett komplett, körbart program och förklaringar till varför varje inställning är viktig. I slutet kommer du att ha två PNG‑filer—en med ett bildförhållande på 15 och en annan med 30—klara för testning eller produktionsbruk.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 SDK eller senare installerat
- Visual Studio 2022 (eller någon C#‑IDE)
- En NuGet‑referens till **Aspose.BarCode** (biblioteket som tillhandahåller `BarcodeGenerator`)
- Skrivbehörighet till den katalog där PNG‑filerna kommer att sparas

Du kan lägga till Aspose.BarCode‑paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Ställ in projektet och importera namnrymder

Skapa en ny konsolapplikation och importera de namnrymder som krävs för streckkodsgenerering och fil‑I/O.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Varför detta är viktigt:** Att importera `Aspose.BarCode.Generation` ger dig åtkomst till `BarcodeGenerator`. Att hålla koden inom `Main` gör exemplet självständigt och enkelt att köra.

## Steg 2: Skapa en streckkodsgenerator för en staplad omnidirektionell DataBar

Instansiera `BarcodeGenerator` med typen `EncodeTypes.DatabarStackedOmniDirectional` och en exempel‑GS1‑128‑datatsträng.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Varför detta är viktigt:** Den valda kodningstypen producerar en högdensitets‑DataBar som kan läsas av de flesta moderna skannrar. Datatsträngen följer GS1 Application Identifier (01)-formatet, vilket är vanligt för produktidentifierare.

## Steg 3: Definiera X‑dimensionen (modulbredd) i pixlar

Ställ in modulbredden för att kontrollera streckkodens totala storlek utan att påverka läsbarheten.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** En X‑dimension på 2 pixlar ger en streckkod som varken är för liten för skannrar eller för stor för vanliga etikettutrymmen.

## Steg 4: Spara den första PNG‑filen med ett bildförhållande på 15

Justera DataBar‑bildförhållandet och spara sedan bilden som en PNG‑fil.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Varför detta är viktigt:** Bildförhållandet styr förhållandet mellan höjd och bredd för den staplade DataBar. Ett förhållande på 15 är en vanlig standard som balanserar läsbarhet och etikettens höjd.

## Steg 5: Ändra bildförhållandet till 30 och spara en andra PNG

Ändra samma generatorinstans för att använda ett större bildförhållande och spara sedan den andra bilden.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Varför detta är viktigt:** Att öka bildförhållandet sträcker streckkoden vertikalt, vilket kan förbättra skanningspålitligheten på lågupplösta enheter eller när etiketten skrivs ut på smalt material.

## Förväntat resultat

När programmet körs skapas två PNG‑filer:

| Fil                               | Bildförhållande | Ungefärliga dimensioner (pixlar) |
|------------------------------------|-----------------|---------------------------------|
| `DatabarAspectRatio15.png`         | 15              | 200 × 300 (bredd × höjd)         |
| `DatabarAspectRatio30.png`         | 30              | 200 × 600 (bredd × höjd)         |

Båda bilderna innehåller en tydlig, skannbar DataBar‑streckkod som kodar GS1‑identifieraren `(01)12345678901231`.

## Vanliga frågor och kantfall

### Hur ändrar man andra visuella egenskaper?

Du kan justera förgrundsfärg, bakgrundsfärg eller lägga till mänskligt läsbar text via objektet `generator.Parameters.Barcode`. Till exempel:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Vad gör jag om jag behöver ett annat bildformat?

Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif` efter behov. PNG förblir det bästa valet för förlustfria streckkods‑bilder.

### Påverkar bildförhållandet skanningshastigheten?

Högre bildförhållanden ökar streckkodens höjd, vilket kan förbättra skanningspålitligheten på enheter som har problem med korta staplade symboler. Däremot kan extremt höga streckkoder vara för stora för små etiketter, så testa med din mål‑hardware.

### Kan jag generera flera streckkoder i en loop?

Ja. Skapa en ny `BarcodeGenerator`‑instans för varje datatsträng eller återanvänd samma instans genom att uppdatera `CodeText` och `DataBar.AspectRatio`. Detta tillvägagångssätt minskar overheaden för objektallokering.

## Pro‑tips

- **Återanvänd generatorn**: Att bara ändra `CodeText` eller `AspectRatio` undviker att återinstansiera objektet, vilket snabbar upp batch‑bearbetning.
- **Validera resultatet**: Använd en handhållen scanner eller en mobilapp för att bekräfta att den genererade PNG‑filen läses korrekt innan du går i produktion.
- **Filnamngivning**: Inkludera bildförhållandet i filnamnet (som visas) för att hålla reda på variationer under testning.

## Slutsats

Du vet nu hur du **skapar streckkod PNG**‑filer i C# och exakt **hur du ändrar bildförhållandet** för staplade omnidirektionella DataBar‑symboler. Det kompletta exemplet demonstrerar initiering, inställning av X‑dimension, manipulation av bildförhållande och bildsparande—allt i ett enda körbart program.

Härifrån kan du utforska ytterligare streckkodstyper, experimentera med färger eller integrera generatorn i ett större rapporterings‑ eller lagersystem. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkod PNG – DataMatrix bildförhållande – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man anpassar streckkod – Codablock F bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}