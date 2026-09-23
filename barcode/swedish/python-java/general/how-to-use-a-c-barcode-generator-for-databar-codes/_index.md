---
category: general
date: 2026-09-23
description: c#-barcodegeneratorhandledning visar hur man genererar streckkodsbilder
  med anpassade bildförhållanden med hjälp av Aspose.BarCode-biblioteket.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: sv
lastmod: 2026-09-23
og_description: c#‑barcodegeneratorguiden visar dig hur du genererar streckkodsbilder,
  justerar bildförhållanden och exporterar PNG‑filer med Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Skapa högkvalitativa streckkoder med en C#‑streckkodsgenerator
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Hur du använder en C#‑streckkodsgenerator för DataBar‑koder
url: /sv/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du använder en C#-streckkodsgenerator för DataBar-koder

Om du behöver en **c# barcode generator** som kan producera DataBar staplade Omni‑Directional‑symboler, ger den här guiden dig en komplett, färdig‑att‑köra lösning. Du kommer att se hur du genererar streckkods‑bilder, styr X‑dimensionen och ändrar bildförhållandet utan att lämna IDE:n.

Att generera streckkoder är ett vanligt krav för lagersystem, fraktetiketter och kassasystem. I slutet av den här handledningen kan du skapa PNG‑filer med vilket bildförhållande du vill, och du kommer att förstå hur du anpassar koden för andra streckkodstyper.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon C#‑redigerare du föredrar)  
* En NuGet‑referens till **Aspose.BarCode** – biblioteket som driver klassen `BarcodeGenerator`  

Du behöver inte ett separat grafikbibliotek; Aspose.BarCode hanterar bildkodning internt.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av biblioteket i din projektfil, vilket gör klassen `BarcodeGenerator` tillgänglig för användning.

## Steg 2: Definiera utdatamappen

Välj en mapp där de genererade PNG‑filerna ska sparas. Att använda en absolut eller relativ sökväg fungerar på samma sätt, men en relativ sökväg håller projektet portabelt.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Att skapa katalogen programatiskt förhindrar körningsfel om mappen saknas.

## Steg 3: Instansiera C#-streckkodsgeneratorn med exempeldata

Konstruktorn för `BarcodeGenerator` kräver två argument: streckkodstypen och datasträngen. För en DataBar staplad Omni‑Directional‑symbol använder du `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Datasträngen följer GS1 Application Identifier‑formatet. `EncodeTypes`‑enumet innehåller över 150 streckkodstandarder; du kan byta till en annan typ genom att ändra enum‑värdet.

## Steg 4: Ställ in X‑dimensionen (pixelstorlek) för streckkoden

X‑dimensionen styr bredden på den smalaste stapeln. Ett pixelvärde på 2 ger en skarp, högupplöst bild som passar de flesta skärmar.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att justera X‑dimensionen är valfritt, men det ger dig fin‑granulär kontroll över den visuella densiteten i streckkoden.

## Steg 5: Generera en streckkod med bildförhållandet 15 och spara den som PNG

`AspectRatio`‑egenskapen tillhör `DataBar`‑sub‑objektet. Att ändra detta värde sträcker eller komprimerar streckkoden vertikalt samtidigt som den kodade datan bevaras.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save`‑metoden skriver streckkoden till den angivna filsökvägen. `BarCodeImageFormat.Png`‑enumet säkerställer förlustfri komprimering.

![c# streckkodsgenerator exempel på utdata](generated_barcode_example.png)

*Bild: streckkod genererad med bildförhållandet 15.*

## Steg 6: Ändra bildförhållandet till 30 och generera en andra bild

Att återanvända samma `BarcodeGenerator`‑instans undviker att allokera ett nytt objekt. Uppdatera helt enkelt `AspectRatio` och anropa `Save` igen.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Nu har du två PNG‑filer som bara skiljer sig åt i vertikal skalning. Denna teknik är användbar när du behöver samma data renderad för olika etikettstorlekar.

## Vanliga variationer och kantfall

### Byta till en annan streckkodstyp

Om du behöver en QR‑kod, Code 128 eller PDF417, ersätt enum‑värdet i konstruktorn:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Alla andra konfigurationssteg (X‑dimension, sparande) förblir identiska.

### Hantera ej stödda tecken

`BarcodeGenerator` validerar inmatningssträngen mot den valda symboliken. Att ange ett otillåtet tecken kastar ett `ArgumentException`. Omge skapandet med ett try‑catch‑block för att ge ett vänligt felmeddelande:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exportera till andra bildformat

Aspose.BarCode stöder BMP, JPEG, TIFF och SVG. Ändra det andra argumentet i `Save` därefter:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Högupplöst utdata för utskrift

När du skriver ut på hög‑DPI‑skrivare, öka X‑dimensionen och sätt eventuellt `Resolution`‑egenskapen:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Dessa inställningar ger större filer men behåller skarpa kanter på fysiskt medium.

## Förväntad utdata

Att köra det kompletta programmet skapar följande filer i `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – en DataBar‑kod med standardhöjd  
* `DatabarAspectRatio30.png` – en vertikalt utdragen version  

Båda bilderna innehåller samma kodade GS1‑data, och du kan verifiera dem med någon streckkodsläsarapp.

## Fullständig källkod

Kopiera koden nedan till ett nytt konsolprojekt (`dotnet new console`) och kör det. Programmet skriver statusmeddelanden till konsolen och sparar PNG‑filerna på disk.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Att köra programmet ger konsolutdata liknande:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Slutsats

Du har nu en **c# barcode generator** som kan skapa DataBar staplade Omni‑Directional‑symboler, justera X‑dimensionen och exportera PNG‑filer med anpassade bildförhållanden. Samma mönster fungerar för alla andra streckkodssymboler som stöds av Aspose.BarCode, vilket gör det enkelt att integrera streckkodsskapande i lager-, frakt‑ eller kassasystem.

Om du vill utforska vidare, prova:

* Generera QR‑koder eller PDF417‑symboler (`how to generate barcode` för mobilappar)  
* Exportera till SVG för skalbara webb‑grafik  
* Bädda in de genererade bilderna direkt i PDF‑fakturor med Aspose.PDF  

Experimentera med olika `AspectRatio`‑värden, X‑dimension‑storlekar och utdataformat för att matcha exakt

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man justerar streckkodsstorlek – Codablock F bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}