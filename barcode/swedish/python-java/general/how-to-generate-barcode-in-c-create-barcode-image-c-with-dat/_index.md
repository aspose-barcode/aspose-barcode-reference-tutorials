---
category: general
date: 2026-08-22
description: Hur man genererar streckkod i C# med Aspose.BarCode. Lär dig skapa streckkodsbild
  i C# steg för steg, inaktivera 2‑D‑komponenten och spara PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: sv
lastmod: 2026-08-22
og_description: Hur man genererar streckkod i C# med Aspose.BarCode. Denna handledning
  visar hur du skapar en streckkodsbild i C# med DataBar Expanded, aktiverar 2‑D‑komponenten
  och sparar PNG‑filer.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Hur man genererar streckkod i C# – komplett guide för att skapa streckkodsbild
  i C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Hur man genererar streckkod i C# – skapa streckkodsbild i C# med DataBar Expanded
url: /sv/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod i C# – skapa streckkodsbild c# med DataBar Expanded

Att generera streckkod i C# är ett vanligt krav när du behöver bädda in maskinläsbara data i dina applikationer. Denna guide visar hur du skapar streckkodsbild c# med Aspose.BarCode‑biblioteket, inaktiverar den 2‑D‑kompositkomponenten och sparar resultatet som PNG‑filer.

Du kommer att se ett komplett, körbart program, en förklaring av varje konfigurationsalternativ samt tips för att anpassa utskriften. Ingen extern dokumentation krävs – bara koden nedan och en .NET‑utvecklingsmiljö.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* Aspose.BarCode för .NET NuGet‑paket (`Aspose.BarCode`)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

Biblioteket tillhandahåller klassen `BarcodeGenerator` som används genom hela denna handledning.

## Steg 1: Ställ in projektet och importera namnrymder

Skapa en ny konsolapplikation och importera de nödvändiga namnrymderna:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation`‑namnrymden innehåller alla klasser som behövs för att konfigurera och rendera streckkoder.

## Steg 2: Initiera DataBar Expanded‑streckkodsgeneratorn

Den första funktionella raden skapar en `BarcodeGenerator` för **DataBar Expanded**‑symbologin och tillhandahåller den råa datasträngen. Datasträngen följer GS1 Application Identifier‑formatet `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Att skapa generatorn allokerar den interna bitmap‑canvasen, så du kan justera storlek och utseende innan rendering.

## Steg 3: Definiera modulbredden (X‑dimension)

X‑dimensionen styr bredden på det minsta streckkodselementet. Genom att ange den i pixlar får du exakt kontroll över den slutliga bildstorleken.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på `2` pixlar fungerar bra för skärmvisning; öka det för högupplösta utskrifter.

## Steg 4: Inaktivera den 2‑D‑kompositkomponenten

DataBar Expanded kan valfritt inkludera en 2‑D‑komponent som bär ytterligare information. För att generera en streckkod **utan** denna komponent, sätt flaggan till `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Att inaktivera komponenten minskar den visuella komplexiteten och ger en mindre PNG‑fil.

## Steg 5: Spara streckkodsbilden utan 2‑D‑komponenten

Välj en utmatningskatalog och skriv bilden till disk. `BarCodeImageFormat.Png`‑enumet säkerställer en förlustfri PNG‑fil.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Efter detta anrop innehåller `Databar2DComponentDisabled.png` en ren DataBar Expanded‑streckkod.

## Steg 6: Aktivera den 2‑D‑kompositkomponenten

Om du behöver det extra datalagret, återaktivera flaggan. Samma generatorinstans kan återanvändas, vilket undviker att skapa ett andra objekt.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Steg 7: Spara streckkodsbilden med 2‑D‑komponenten aktiverad

Rendera den andra bilden med samma inställningar, förutom 2‑D‑flaggan.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Nu visar `Databar2DComponentEnabled.png` streckkoden med det extra 2‑D‑mönstret.

## Fullständig källkod

Kopiera hela kodsnutten nedan till `Program.cs` och kör projektet. Programmet skapar båda PNG‑filerna i den mapp du anger.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Förväntad utskrift

När programmet körs skrivs:

```
Barcode images generated successfully.
```

och skapar två filer:

* `Databar2DComponentDisabled.png` – streckkod utan 2‑D‑komponenten  
* `Databar2DComponentEnabled.png` – streckkod med 2‑D‑komponenten  

Öppna PNG‑filerna i någon bildvisare för att verifiera den visuella skillnaden.

## Vanliga variationer och kantfall

| Situation | Justering |
|-----------|------------|
| **Olika symbologi** | Byt ut `EncodeTypes.DatabarExpanded` mot ett annat värde, t.ex. `EncodeTypes.Code128`. |
| **Högre upplösning** | Öka `XDimension.Pixels` till 4 eller 5, eller sätt `Resolution` i `barcodeGenerator.Parameters.Image`. |
| **Andra bildformat** | Använd `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` eller `BarCodeImageFormat.Svg`. |
| **Kör i en webbapp** | Strömma bildbytarna direkt till HTTP‑svaret istället för att spara till disk. |
| **Minneshantering** | Omge generatorn med ett `using`‑block om du riktar dig mot .NET Framework för att säkerställa att ohanterade resurser frigörs. |

## Proffstips

* **Återanvänd generatorn** – Genom att bara ändra 2‑D‑flaggan undviker du att skapa ett nytt objekt, vilket sparar CPU‑cykler.  
* **Validera data** – GS1‑data måste följa exakt längd‑ och kontrollsummaregel; ogiltig inmatning kastar `ArgumentException`.  
* **Batch‑behandling** – Loopa över en samling datasträngar, växla 2‑D‑flaggan vid behov och spara varje bild med ett unikt filnamn.  

## Slutsats

Du vet nu hur du genererar streckkod i C# och skapar streckkodsbild c# med full kontroll över den 2‑D‑kompositkomponenten. Exemplet visar hur man initierar generatorn, konfigurerar X‑dimensionen, växlar komponenten och sparar PNG‑filer. Härifrån kan du utforska andra symbologier, bädda in bilderna i PDF‑filer eller integrera streckkodsgenerering i ASP.NET Core‑tjänster.

--- 

*Nästa steg*: prova att generera QR‑koder, experimentera med olika bildupplösningar eller bädda in de genererade PNG‑filerna i en PDF med Aspose.PDF. Dessa tillägg bygger på samma `BarcodeGenerator`‑API och håller ditt arbetsflöde konsekvent.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}