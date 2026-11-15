---
category: general
date: 2026-11-14
description: C#‑handledning för streckkodsgenerator som visar hur man skapar DataBar
  Omnidirectional‑streckkoder, anger X‑dimension och justerar streckhöjden i pixlar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: sv
lastmod: 2026-11-14
og_description: Barcode‑generator C#‑handledning förklarar steg för steg hur man genererar
  en DataBar Omnidirectional‑streckkod, definierar XDimension i pixlar och ändrar
  stapelhöjden för PNG‑utdata.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Streckkodsgenerator C#‑handledning – skapa DataBar‑streckkoder
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Streckkodsgenerator C#‑handledning: DataBar omnidirektionell'
url: /sv/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

Om du letar efter en **barcode generator C# tutorial**, har du hamnat på rätt ställe. Denna guide visar hur du skapar en DataBar Omnidirectional‑streckkod, konfigurerar XDimension i pixlar och justerar stapelhöjden för att producera PNG‑bilder.

Du får ett komplett, körbart exempel som täcker allt från att initiera generatorn till att spara flera bilder med olika stapelhöjder. Ingen extern dokumentation behövs – kopiera bara koden, kör den, så har du två streckkodsfiler redo att användas.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* En referens till streckkodsbiblioteket som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat` (t.ex. Aspose.BarCode för .NET)  
* Grundläggande kunskap om C#‑syntax och Visual Studio eller din föredragna IDE  

> **Pro tip:** Om du använder Aspose.BarCode, lägg till NuGet‑paketet `Aspose.BarCode` i ditt projekt.

## Barcode generator C# tutorial – steg 1: skapa generatorn

Det första steget är att instansiera en `BarcodeGenerator` med kodningstypen `DatabarOmniDirectional` och den data du vill koda.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Varför detta är viktigt:* `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket att producera en streckkod som kan läsas från vilken riktning som helst, vilket är idealiskt för detaljhandelsförpackningar och logistik.

## Ställ in XDimension‑pixlar för streckkoden

X‑dimensionen definierar bredden på den minsta modulen (”pixeln”) i streckkoden. Att ange den i pixlar ger dig exakt kontroll över streckkodens visuella densitet.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Förklaring:* Ett värde på `2` pixlar ger en streckkod som är tillräckligt skarp för de flesta skannrar samtidigt som bildfilens storlek hålls rimlig.

## Justera stapelhöjd och spara bilder

Stapelhöjden bestämmer hur höga staplarna blir. Du kan generera flera bilder med olika höjder genom att ändra egenskapen `BarHeight.Pixels` och anropa `Save` igen.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png`‑enum‑värdet säkerställer att utdata blir en förlustfri PNG‑fil, vilket är det rekommenderade formatet för streckkodsgrafik eftersom det bevarar exakta dimensioner.

## Ändra stapelhöjd för att skapa flera bilder

Du behöver ofta samma streckkod i olika storlekar – till exempel en för en liten etikett och en annan för ett stort affisch. Ändra stapelhöjden och återanvänd samma generatorinstans:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* Om stapelhöjden sätts för lågt (t.ex. under 10 px) kan vissa skannrar ha svårt att läsa koden. Testa alltid de genererade bilderna med din mål‑skannerutrustning.

## Fullständig källkod

Nedan är hela programmet som du kan kopiera‑klistra in i ett nytt konsolprojekt. Det innehåller alla nödvändiga `using`‑direktiv och demonstrerar båda variationerna av stapelhöjd.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Kör programmet, ersätt `YOUR_DIRECTORY` med en giltig sökväg, så hittar du två PNG‑filer:

* `DatabarBarHeight30Pixels.png` – staplar 30 px höga  
* `DatabarBarHeight60Pixels.png` – staplar 60 px höga  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Vanliga frågor

| Fråga | Svar |
|----------|--------|
| **Kan jag ändra bildformatet?** | Ja. Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif` efter behov. PNG föredras för förlustfri kvalitet. |
| **Vad händer om jag behöver en annan XDimension?** | Justera `generator.Parameters.Barcode.XDimension.Pixels` till valfritt heltal. Större värden ökar streckkodens totala bredd. |
| **Är DataBar Omnidirectional lämplig för mobilskanning?** | Ja, förutsatt att den utskrivna storleken uppfyller skannarens minsta modulstorlek (vanligtvis 0,33 mm). Den pixel‑baserade XDimension hjälper dig att nå detta krav. |
| **Hur bäddar jag in streckkoden i en PDF?** | Efter att du sparat PNG‑filen, använd ett PDF‑bibliotek (t.ex. iTextSharp) för att infoga bilden på en PDF‑sida. |

## Slutsats

Denna **barcode generator C# tutorial** har visat hur du skapar en DataBar Omnidirectional‑streckkod, sätter XDimension i pixlar och genererar PNG‑filer med olika stapelhöjder. Du har nu ett återanvändbart kodexempel som du kan anpassa för alla C#‑projekt som kräver streckkodsgenerering.

### Vad blir nästa steg?

* Utforska andra `EncodeTypes` såsom `Code128` eller `QR` för att bredda ditt streckkodssortiment.  
* Kombinera de genererade PNG‑filerna med ett PDF‑genereringsbibliotek för att skapa utskrivbara fakturor.  
* Experimentera med `generator.Parameters.Barcode.Color` för att lägga till egna färger samtidigt som du håller dig inom skanningsspecifikationerna.

Känn dig fri att modifiera exemplet, prova ytterligare stapelhöjder eller byta ut utdataformatet. Lycka till med kodandet!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}