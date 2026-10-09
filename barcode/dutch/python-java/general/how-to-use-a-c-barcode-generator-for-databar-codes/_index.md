---
category: general
date: 2026-09-23
description: c# barcodegenerator tutorial laat zien hoe je barcode‑afbeeldingen met
  aangepaste beeldverhoudingen kunt genereren met behulp van de Aspose.BarCode‑bibliotheek.
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
language: nl
lastmod: 2026-09-23
og_description: c# barcodegeneratorhandleiding leidt je stap voor stap door het genereren
  van barcode‑afbeeldingen, het aanpassen van beeldverhoudingen en het exporteren
  van PNG‑bestanden met Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Maak hoogwaardige barcodes met een C# barcodegenerator
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
title: Hoe een C# barcodegenerator te gebruiken voor DataBar-codes
url: /nl/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een C# barcode‑generator te gebruiken voor DataBar‑codes

Als je een **c# barcode generator** nodig hebt die DataBar stacked Omni‑Directional‑symbolen kan produceren, biedt deze gids een complete, kant‑klaar‑oplossing. Je ziet hoe je barcode‑afbeeldingen genereert, de X‑dimensie regelt en de beeldverhouding aanpast zonder de IDE te verlaten.

Barcodes genereren is een veelvoorkomende eis voor voorraadsystemen, verzendlabels en point‑of‑sale‑toepassingen. Aan het einde van deze tutorial kun je PNG‑bestanden maken met elke gewenste beeldverhouding, en begrijp je hoe je de code kunt aanpassen voor andere barcode‑typen.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑editor naar keuze)  
* Een NuGet‑referentie naar **Aspose.BarCode** – de bibliotheek die de `BarcodeGenerator`‑klasse aandrijft  

Je hebt geen aparte grafische bibliotheek nodig; Aspose.BarCode verwerkt de afbeeldingencodering intern.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van de bibliotheek toe aan je projectbestand, waardoor de `BarcodeGenerator`‑klasse beschikbaar wordt.

## Stap 2: Definieer de uitvoermap

Kies een map waarin de gegenereerde PNG‑bestanden worden opgeslagen. Een absoluut of relatief pad werkt op dezelfde manier, maar een relatief pad houdt het project draagbaar.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Het programmatic maken van de map voorkomt runtime‑fouten als de map ontbreekt.

## Stap 3: Instantieer de C# barcode‑generator met voorbeeldgegevens

De `BarcodeGenerator`‑constructor vereist twee argumenten: het barcode‑type en de gegevensreeks. Voor een DataBar stacked Omni‑Directional‑symbool gebruik je `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

De gegevensreeks volgt het GS1 Application Identifier‑formaat. De `EncodeTypes`‑enum bevat meer dan 150 barcode‑standaarden; je kunt overschakelen naar een ander type door de enum‑waarde te wijzigen.

## Stap 4: Stel de X‑dimensie (pixelgrootte) voor de barcode in

De X‑dimensie bepaalt de breedte van de smalste balk. Een pixelwaarde van 2 levert een scherp, high‑resolution‑beeld op dat geschikt is voor de meeste schermen.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Het aanpassen van de X‑dimensie is optioneel, maar geeft je fijne controle over de visuele dichtheid van de barcode.

## Stap 5: Genereer een barcode met een beeldverhouding van 15 en sla deze op als PNG

De `AspectRatio`‑eigenschap behoort tot het `DataBar`‑subobject. Het wijzigen van deze waarde strekt of comprimeert de barcode verticaal terwijl de gecodeerde data behouden blijft.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft de barcode naar het opgegeven bestandspad. De `BarCodeImageFormat.Png`‑enum zorgt voor verliesloze compressie.

![c# barcode generator output voorbeeld](generated_barcode_example.png)

*Afbeelding: barcode gegenereerd met een beeldverhouding van 15.*

## Stap 6: Verander de beeldverhouding naar 30 en genereer een tweede afbeelding

Het hergebruiken van dezelfde `BarcodeGenerator`‑instantie voorkomt het aanmaken van een nieuw object. Werk simpelweg de `AspectRatio` bij en roep opnieuw `Save` aan.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Nu heb je twee PNG‑bestanden die alleen verschillen in verticale schaal. Deze techniek is handig wanneer je dezelfde data moet weergeven voor verschillende labelgroottes.

## Veelvoorkomende variaties en randgevallen

### Overschakelen naar een ander barcode‑type

Als je een QR‑code, Code 128 of PDF417 nodig hebt, vervang je de enum‑waarde in de constructor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Alle andere configuratiestappen (X‑dimensie, opslaan) blijven identiek.

### Omgaan met niet‑ondersteunde tekens

De `BarcodeGenerator` valideert de invoerreeks tegen de geselecteerde symbologie. Het leveren van een illegaal teken veroorzaakt een `ArgumentException`. Plaats de creatie in een try‑catch‑blok om een vriendelijke foutmelding te geven:

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

### Exporteren naar andere afbeeldingsformaten

Aspose.BarCode ondersteunt BMP, JPEG, TIFF en SVG. Pas het tweede argument van `Save` dienovereenkomstig aan:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### High‑resolution output voor afdrukken

Bij afdrukken op high‑DPI‑printers, verhoog je de X‑dimensie en stel je eventueel de `Resolution`‑eigenschap in:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Deze instellingen produceren grotere bestanden maar behouden scherpe randen op fysieke media.

## Verwachte output

Het uitvoeren van het volledige programma maakt de volgende bestanden aan in `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – een DataBar‑code met standaardhoogte  
* `DatabarAspectRatio30.png` – een verticaal uitgerekte versie  

Beide afbeeldingen bevatten dezelfde gecodeerde GS1‑data, en je kunt ze verifiëren met elke barcode‑scanner‑app.

## Volledige broncode

Kopieer de code hieronder naar een nieuw console‑project (`dotnet new console`) en voer het uit. Het programma print statusberichten naar de console en schrijft de PNG‑bestanden naar schijf.

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

Het uitvoeren van het programma levert console‑output vergelijkbaar met:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusie

Je beschikt nu over een **c# barcode generator** die DataBar stacked Omni‑Directional‑symbolen kan maken, de X‑dimensie kan aanpassen en PNG‑bestanden met aangepaste beeldverhoudingen kan exporteren. Hetzelfde patroon werkt voor elke andere barcode‑symbologie die door Aspose.BarCode wordt ondersteund, waardoor het eenvoudig is om barcode‑creatie te integreren in voorraadsystemen, verzendprocessen of point‑of‑sale‑oplossingen.

Wil je verder verkennen, probeer dan:

* QR‑codes of PDF417‑symbolen genereren (`how to generate barcode` voor mobiele apps)  
* Exporteren naar SVG voor schaalbare web‑graphics  
* De gegenereerde afbeeldingen direct in PDF‑facturen embedden met Aspose.PDF  

Experimenteer met verschillende `AspectRatio`‑waarden, X‑dimensie‑groottes en uitvoerformaten om exact te voldoen aan je eisen.


## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}