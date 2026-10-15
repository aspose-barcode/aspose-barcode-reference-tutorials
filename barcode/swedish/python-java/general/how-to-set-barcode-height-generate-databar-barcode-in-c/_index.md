---
category: general
date: 2026-10-12
description: Hur man ställer in streckkodshöjd och genererar en DataBar‑streckkod
  i C# med Aspose.BarCode. Följ en steg‑för‑steg‑guide med komplett kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: sv
lastmod: 2026-10-12
og_description: Hur man ställer in streckkodshöjd i C# och genererar en DataBar-streckkod
  med Aspose.BarCode. Lär dig hela koden, varför varje steg är viktigt och hur du
  ändrar streckkodshöjden.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Hur man ställer in streckkodshöjd och genererar DataBar‑streckkod i C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man ställer in streckkodshöjd, genererar DataBar‑streckkod i C#
url: /sv/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ställer du in streckkodshöjd, generera DataBar-streckkod i C#

Om du behöver **how to set barcode** dimensioner programatiskt, visar den här guiden de exakta stegen. Du kommer att lära dig hur du genererar en DataBar Omni‑directional streckkod, justerar dess höjd och sparar båda versionerna som PNG‑filer.

Att ändra en streckkods stapelhöjd är ett vanligt krav när du integrerar streckkoder i kvitton, produktetiketter eller mobila skärmar. Exemplet nedan använder Aspose.BarCode‑biblioteket, som stöder hela sortimentet av GS1 DataBar‑symbologier.

## Vad du kommer att uppnå

* **how to set barcode** höjd för en DataBar Omni‑directional streckkod  
* **generate barcode c#** kod som skapar två bilder med olika höjder  
* förstå **how to create databar** symboler och varför stapelhöjden är viktig  
* tillämpa **change barcode height** logik utan att återskapa generatorn  

Inga externa verktyg krävs förutom Aspose.BarCode NuGet‑paketet och en .NET 6+‑runtime.

## Förutsättningar

* .NET 6 SDK eller senare installerat  
* Visual Studio 2022 (eller någon C#‑redigerare)  
* Aspose.BarCode för .NET – installera via `dotnet add package Aspose.BarCode`  

> **Pro tip:** Använd den kostnadsfria provlicensen från Aspose om du inte har en kommersiell nyckel; API‑et fungerar på samma sätt.

## Steg 1: Installera Aspose.BarCode‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till namnutrymmet `Aspose.BarCode`, som innehåller klassen `BarcodeGenerator` som vi kommer att använda för att **generate barcode c#** bilder.

## Steg 2: Skapa en DataBar‑streckkodsgenerator

Den första konkreta åtgärden för **how to set barcode** parametrar är att instansiera `BarcodeGenerator` med önskad symbologi och datasträng.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Varför detta är viktigt:* `EncodeTypes.DatabarOmniDirectional` producerar en kompakt, omnidirektionell DataBar som kan skannas från vilken vinkel som helst—ideal för små etiketter.

## Steg 3: Ställ in vanliga streckkodparametrar (inklusive initial stapelhöjd)

Nu besvarar vi **how to set barcode** X‑dimension och stapelhöjd innan den första bilden sparas.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimensionen styr den totala bredden på varje stapel; en inställning på 2 pixel ger en läsbar, skarp bild på de flesta skärmar. Steget **change barcode height** senare kommer att återanvända samma generator, vilket sparar tid och minne.

## Steg 4: Spara den första streckkodsbilden (30‑pixel hög)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Filen `DatabarHeight30.png` innehåller nu en DataBar‑streckkod med en stapelhöjd på 30 pixel.

## Steg 5: Ändra endast stapelhöjden till 60 pixel

För att demonstrera **change barcode height** ändrar vi bara egenskapen `BarHeight`. Alla andra inställningar förblir oförändrade, vilket är det mest effektiva sättet att producera flera storlekar från en enda generator.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Steg 6: Spara den andra streckkodsbilden (60‑pixel hög)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Du har nu två PNG‑filer, var och en med olika stapelhöjd men identisk data och X‑dimension.

## Fullt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera‑klistra in i en ny konsolapplikation (`dotnet new console`) och köra omedelbart.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Förväntad output

När programmet körs skapas två filer i körbarhetens arbetskatalog:

* `DatabarHeight30.png` – en DataBar‑streckkod med 30‑pixel höga staplar.  
* `DatabarHeight60.png` – samma streckkod, men varje stapel är dubbelt så hög.

Båda bilderna kan öppnas i vilken bildvisare som helst eller bäddas in direkt i PDF‑filer, HTML‑sidor eller utskrivna etiketter.

## Varför justering av stapelhöjd är viktigt

* **Scanning reliability:** Vissa skannrar har problem med mycket korta staplar på lågupplöst media; en ökad höjd förbättrar upptäckten.  
* **Design constraints:** En mobilapp kan behöva en kompakt streckkod (30 px) medan ett utskrivet kvitto kan kräva en större (60 px).  
* **Regulatory compliance:** Vissa branscher kräver en minsta stapelhöjd för GS1 DataBar‑symboler.  

Genom att återanvända samma `BarcodeGenerator`‑instans undviker du overheaden av att åter‑parsa datasträngen, vilket är särskilt fördelaktigt i hög‑genomströmning miljöer.

## Vanliga variationer och kantfall

| Situation | Rekommenderad justering |
|-----------|--------------------------|
| Behöver en annan X‑dimension | Ändra `XDimension.Pixels` innan den första `Save`. |
| Vill ha en annan symbologi (t.ex. DataBar Stacked) | Använd `EncodeTypes.DatabarStacked` när du konstruerar `BarcodeGenerator`. |
| Måste bädda in streckkoden i en PDF | Använd `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` och lägg till strömmen i ett PDF‑bibliotek. |
| Kör på .NET Framework 4.6 | Samma kod fungerar; referera bara till rätt Aspose.BarCode‑assembly. |

## Pro tips för pålitlig streckkodsgenerering

* **Cache the generator** när du genererar många streckkoder med samma data men olika storlekar.  
* **

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}