---
category: general
date: 2026-10-08
description: Lär dig hur du skapar streckkodsbilder i C# och upptäck hur du justerar
  bildförhållandet för DataBar staplade omnidirektionella streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: sv
lastmod: 2026-10-08
og_description: Skapa streckkodbild i C# och lär dig hur du justerar bildförhållandet
  för DataBar staplade omni‑direktionella streckkoder med ett komplett kodexempel.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Skapa streckkodsbild i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man skapar en streckkodbild och justerar dess bildförhållande i C#
url: /sv/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du streckkodsbild och justerar dess bildförhållande i C#

Om du behöver **skapa streckkodsbild** programatiskt visar den här guiden en komplett, färdig‑att‑köra lösning. Du får se exakt **hur du justerar bildförhållandet** för en DataBar staplad omni‑riktad streckkod, ett krav som ofta förekommer i detaljhandel och logistik.

I den här handledningen lär du dig hur du:
* Initierar en Aspose.BarCode `BarcodeGenerator` för DataBar staplad omni‑riktad symbologi.  
* Ställer in X‑dimensionen (modulbredd) i pixlar för att kontrollera stapelns tjocklek.  
* Använder två olika bildförhållanden och sparar varje resultat som en PNG‑fil.  
* Verifierar resultatet och förstår varför bildförhållandet är viktigt.

Inga externa verktyg krävs—bara Aspose.BarCode för .NET-biblioteket och en .NET 6 (eller senare) utvecklingsmiljö.

## Så skapar du streckkodsbild med Aspose.BarCode

Det första steget är att skapa en instans av generatorn med önskad symbologi och datasträng. Enum‑värdet `EncodeTypes.DatabarStackedOmniDirectional` instruerar Aspose.BarCode att producera en DataBar staplad omni‑riktad streckkod, som är allmänt använd för GS1‑128‑applikationer.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Varför detta är viktigt:** `BarcodeGenerator`‑objektet är startpunkten för alla streckkodsskapande uppgifter. Genom att ange symbologin och rådata i förväg säkerställer du att den genererade bilden följer GS1‑standarden.

## Ställa in X‑dimensionen (modulbredd)

X‑dimensionen definierar bredden på den smalaste stapeln (modulen). En större X‑dimension ger en tjockare streckkod, vilket kan vara hjälpsamt för lågupplösta skrivare.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** Att justera X‑dimensionen är en del av den visuella fininställningen. Det påverkar inte den kodade datan, men det påverkar skanningspålitligheten på olika enheter.

## Så justerar du bildförhållandet – första versionen (15)

Bildförhållandet styr förhållandet mellan höjd och bredd för DataBar‑streckkoden. Egenskapen `DataBar.AspectRatio` accepterar heltalsvärden; större tal ger högre staplar.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** Ett bildförhållande på 15 är en vanlig standard för detaljhandels‑skannrar. Den resulterande PNG‑filen (`DatabarAspectRatio15.png`) får ett högre utseende, vilket kan förbättra skanningsframgång på handhållna enheter.

## Så justerar du bildförhållandet – andra versionen (30)

Du kan behöva en högre streckkod för specifika etikettformat. Att ändra bildförhållandet är så enkelt som att tilldela ett nytt heltalsvärde innan du anropar `Save` igen.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta är viktigt:** Genom att demonstrera **hur du justerar bildförhållandet** kan du generera flera streckkodsbilder från samma datakälla utan att återskapa generatorn. Detta minskar minnesanvändningen och påskyndar batch‑bearbetning.

### Förväntat resultat

Efter att programmet har körts hittar du två PNG‑filer i körkatalogen:

| Filnamn                     | Bildförhållande | Visuell beskrivning |
|-----------------------------|-----------------|---------------------|
| `DatabarAspectRatio15.png`  | 15              | Standardhöjd, lämplig för de flesta kassa‑skannrar. |
| `DatabarAspectRatio30.png`  | 30              | Högre staplar, användbar för stora etiketter eller lågupplösta skrivare. |

Båda bilderna innehåller samma kodade GTIN `(01)12345678901231`, men de visuella proportionerna skiljer sig beroende på det bildförhållande du har angett.

## Vanliga frågor och hantering av specialfall

### Vad gör jag om jag behöver en annan X‑dimension?

Du kan ändra `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` till vilket heltal som helst större än noll. För mycket högupplöst output (t.ex. 300 dpi) ger ett värde på 3‑4 pixlar ofta tydligare resultat.

### Hur väljer jag rätt bildförhållande?

Det optimala förhållandet beror på skanningsmiljön:
* **Låga etiketter** – använd ett mindre förhållande (t.ex. 10‑15) för att hålla streckkoden kompakt.
* **Stora fraktcontainrar** – ett högre förhållande (t.ex. 25‑35) förbättrar läsbarheten på avstånd.
* **Regulatoriska krav** – vissa standarder kräver en minsta höjd; konsultera GS1‑specifikationen för exakta siffror.

### Kan jag generera andra streckkodformat med samma kod?

Ja. Byt ut `EncodeTypes.DatabarStackedOmniDirectional` mot vilket annat `EncodeTypes`‑värde som helst (t.ex. `EncodeTypes.Code128`). Resten av koden—X‑dimension, bildförhållande (om tillämpligt) och sparande—förblir densamma.

### Vad gör jag om jag behöver skapa bilden i ett annat format?

`BarCodeImageFormat` stödjer PNG, JPEG, BMP, GIF och TIFF. Ändra bara det andra argumentet i `Save`, till exempel:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Proffstips: återanvänd generatorn för batch‑bearbetning

När du måste skapa dussintals streckkoder med samma visuella inställningar, skapa en instans av generatorn en gång, uppdatera bara `CodeText`‑egenskapen och anropa `Save` upprepade gånger. Detta undviker overheaden av att ständigt allokera interna buffertar.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Slutsats

Du vet nu hur du **skapar streckkodsbild** i C# med Aspose.BarCode och exakt **hur du justerar bildförhållandet** för DataBar staplade omni‑riktade symboler. Genom att kontrollera X‑dimensionen och bildförhållandet kan du producera streckkoder som uppfyller alla skannings‑ eller layoutkrav samtidigt som implementationen förblir enkel och underhållbar.

### Nästa steg

* Utforska andra symbologier såsom **Code128** eller **QR Code** genom att byta `EncodeTypes`‑värdet.  
* Kombinera streckkodsgenereringen med PDF‑skapande (t.ex. med Aspose.PDF) för att bädda in streckkoder direkt i fakturor.  
* Experimentera med dynamisk bildförhållande‑val baserat på etikettstorlek—detta utökar **hur du justerar bildförhållandet**‑mönstret till en fullfjädrad etikett‑designmotor.

Känn dig fri att anpassa exemplet, dela dina resultat eller ställa följdfrågor i kommentarerna. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar databar staplad streckkod i C# med Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Hur man skapar streckkodsbild med Aspose.Barcode i C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Hur man justerar streckkodsstorlek – Codablock F-aspektförhållande med Aspose.BarCode för .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}