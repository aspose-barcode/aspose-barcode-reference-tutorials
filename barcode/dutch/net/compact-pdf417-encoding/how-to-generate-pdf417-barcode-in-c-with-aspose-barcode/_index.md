---
category: general
date: 2026-11-27
description: Leer hoe je een PDF417‑barcode genereert in C# met Aspose.BarCode. Pas
  de afmetingen aan, stel het aantal kolommen in en sla op als PNG in een paar regels
  code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: nl
lastmod: 2026-11-27
og_description: Genereer PDF417‑barcode in C# direct. Deze tutorial laat zien hoe
  je de afmetingen, het aantal kolommen kunt configureren en het resultaat als PNG‑afbeelding
  kunt opslaan.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: PDF417-barcode genereren in C# – snelle gids met Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hoe PDF417-barcode te genereren in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren in C# met Aspose.BarCode

Als je een **PDF417-barcode** moet genereren in een .NET‑applicatie, laat deze gids je een beknopte, end‑to‑end oplossing zien. Je ziet hoe je de barcode maakt, de grootte nauwkeurig afstemt en het resultaat naar een PNG‑bestand schrijft — allemaal met de Aspose.BarCode‑bibliotheek.

Het genereren van een PDF417-barcode is gebruikelijk wanneer je grote hoeveelheden data moet coderen voor scanning op mobiele apparaten, instapkaarten of voorraadlabels. Aan het einde van deze tutorial heb je een kant‑klaar console‑programma dat een hoogwaardige PNG‑afbeelding produceert.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Een recente versie van **Aspose.BarCode for .NET** (het NuGet‑pakket `Aspose.BarCode`)  
* Een IDE of editor (Visual Studio, VS Code, Rider, enz.)  

De code werkt op Windows, Linux en macOS omdat Aspose.BarCode platform‑onafhankelijk is.

## Stap 1: Maak een nieuw console‑project

Open een terminal en voer uit:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Dit maakt een minimaal C#‑project met de naam **Pdf417Demo** en voegt de `Aspose.BarCode`‑dependency toe.

## Stap 2: Schrijf de barcode‑generatiecode

Open **Program.cs** en vervang de inhoud door het volgende:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Waarom elke regel belangrijk is

* **BarcodeGenerator** – de kernklasse die een barcode‑afbeelding maakt. Het doorgeven van `EncodeTypes.Pdf417` selecteert de PDF417‑symbologie.  
* **XDimension.Pixels** – bepaalt de kleinste balkbreedte. Lagere waarden verkleinen de afbeelding; hogere waarden verbeteren de leesbaarheid op scanners met lage resolutie.  
* **Pdf417.Columns** – regelt het aantal datakolommen. Meer kolommen geven een kortere maar hogere barcode; minder kolommen maken de barcode breder.  
* **ErrorCorrectionLevel** – hogere niveaus voegen redundante data toe, waardoor de barcode toleranter is voor beschadiging, ten koste van de grootte.  
* **Save(..., BarCodeImageFormat.Png)** – schrijft de afbeelding naar schijf in PNG‑formaat, een verliesvrije indeling die ideaal is voor verdere verwerking of inbedding in documenten.

## Stap 3: Bouw en voer het programma uit

Voer vanuit de terminal uit:

```bash
dotnet run
```

Je zou moeten zien:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Een bestand met de naam **Pdf417Basic.png** verschijnt in de projectmap. Het openen ervan toont een duidelijke PDF417‑barcode die de tekst *“Sample text for PDF417 barcode”* codeert.

![Gegenereerde PDF417-barcode opgeslagen als PNG‑bestand](pdf417-barcode-example.png "Gegenereerde PDF417-barcode in PNG‑formaat")

*Afbeeldings‑alt‑tekst: screenshot van een gegenereerde PDF417-barcode opgeslagen als PNG‑bestand, die het resultaat van de tutorial voor het genereren van een PDF417-barcode laat zien.*

## Stap 4: Veelvoorkomende variaties en randgevallen

### De gecodeerde data wijzigen

Vervang het tweede argument van `BarcodeGenerator` door een willekeurige UTF‑8‑string, bijvoorbeeld:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

De generator splitst de data automatisch over rijen en kolommen.

### Afbeeldingsgrootte aanpassen zonder kwaliteitsverlies

Als je een grotere afbeelding nodig hebt voor afdrukken, verhoog dan `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Zeer lange invoer verwerken

PDF417 kan tot 1 850 tekens coderen. Voor extreem lange strings kun je het aantal kolommen verhogen:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Als de inhoud de maximale capaciteit overschrijdt, gooit Aspose.BarCode een `ArgumentException`. Plaats de generatiecode in een try‑catch‑blok om een vriendelijke foutmelding weer te geven.

### Opslaan in andere formaten

Aspose.BarCode ondersteunt BMP, JPEG, TIFF en SVG. Verander het formaat als volgt:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Stap 5: Verifieer de barcode

Je kunt bevestigen dat de barcode geldig is door deze te scannen met een willekeurige PDF417‑lezerapp (bijv. smartphone‑camera‑apps die barcode‑scanning ondersteunen). De gedecodeerde tekst moet overeenkomen met de string die je aan de generator hebt doorgegeven.

Als het scannen mislukt:

* Zorg ervoor dat de afbeelding niet gecomprimeerd is (gebruik PNG of verliesvrije SVG).  
* Controleer of `ErrorCorrectionLevel` hoog genoeg is voor de beoogde omgeving.  
* Controleer of de barcode‑afmetingen passend zijn voor de resolutie van de scanner.

## Conclusie

Je weet nu hoe je **PDF417-barcode** kunt genereren in C# met Aspose.BarCode, de afmetingen kunt aanpassen, het aantal kolommen kunt instellen en het resultaat kunt exporteren als PNG‑afbeelding. Deze aanpak werkt voor een breed scala aan scenario's, van mobiel ticketing tot voorraadbeheer.

Vervolgens kun je verkennen:

* **Lezen** van een PDF417‑barcode met `BarCodeReader`.  
* Het genereren van andere symbologieën zoals QR‑Code of DataMatrix.  
* Het inbedden van de PNG in PDF’s, rapporten of webpagina’s.  

Voel je vrij om te experimenteren met verschillende fout‑correctieniveaus, afbeeldingsformaten en data‑payloads om aan de behoeften van je project te voldoen. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417-barcode te genereren in C# met Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Hoe PDF417-barcode te genereren en weer te geven als PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Hoe PDF417-barcode te genereren in C# en de barcode‑grootte in te stellen](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}