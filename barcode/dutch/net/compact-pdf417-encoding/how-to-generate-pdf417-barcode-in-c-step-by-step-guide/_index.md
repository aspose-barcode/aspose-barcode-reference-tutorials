---
category: general
date: 2026-09-10
description: Genereer PDF417‑barcode in C# snel. Leer hoe je PDF417 kunt genereren
  en hoe je de barcode‑grootte kunt aanpassen met Aspose.BarCode in slechts een paar
  regels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: nl
lastmod: 2026-09-10
og_description: Genereer direct een PDF417‑barcode in C#. Deze tutorial laat zien
  hoe je PDF417 genereert en hoe je de barcodegrootte aanpast met Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: PDF417-barcode genereren in C# – volledige programmeergids
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hoe PDF417‑barcode te genereren in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode te genereren in C# – stapsgewijze handleiding

Als u een **PDF417 barcode wilt genereren** in een .NET‑applicatie, laat deze gids u precies zien hoe u dat doet. U ziet een beknopt, kant‑klaar voorbeeld dat een PDF417 barcode maakt, u de grootte laat regelen, en het resultaat opslaat als een PNG‑afbeelding.

Het genereren van een PDF417 barcode is een veelvoorkomende eis voor voorraadsystemen, instapkaarten en documenttracking. In deze tutorial behandelen we ook **hoe u de barcode‑grootte kunt wijzigen** zodat de code zich aanpast aan verschillende afdruk‑ of schermweergave‑behoeften.

## Vereisten

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.6+)
* Visual Studio 2022 of een C#‑IDE
* Het **Aspose.BarCode for .NET** NuGet‑pakket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Basiskennis van C# console‑applicaties

## Projectconfiguratie

1. Maak een nieuw console‑project aan:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Voeg de Aspose.BarCode‑referentie toe (zie vereisten).  

3. Open `Program.cs` en vervang de inhoud door het volledige voorbeeld hieronder.

## Stap 1: PDF417 barcode genereren

De eerste stap is het aanmaken van een `BarcodeGenerator`‑instantie geconfigureerd voor de **PDF417**‑symbologie. Dit object is het toegangspunt voor alle barcode‑bewerkingen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Waarom dit belangrijk is* – De `EncodeTypes.Pdf417`‑enumwaarde vertelt Aspose.BarCode om de PDF417‑standaard te gebruiken, terwijl het tweede argument de te coderen data levert. De generator bevat nu een volledig barcode‑object dat u kunt aanpassen voordat u opslaat.

## Stap 2: Hoe de barcode‑grootte (module‑grootte) te wijzigen

PDF417‑barcodes bestaan uit kleine vierkante modules. Het aanpassen van de module‑grootte verandert de totale afmetingen van de afbeelding zonder de gecodeerde data te wijzigen.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Waarom dit belangrijk is* – Een grotere `XDimension` levert een grotere barcode die geschikt is voor hoge‑resolutie‑afdrukken; een kleinere waarde is beter voor weergave op het scherm. De standaardwaarde is meestal 1 px, wat er krap kan uitzien op moderne monitoren.

## Stap 3: Layout configureren – kolommen en rijen

PDF417 stelt u in staat het aantal kolommen en rijen te definiëren, wat zowel de vorm van de barcode als de fout‑correctiecapaciteit beïnvloedt.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Waarom dit belangrijk is* – Meer kolommen maken de barcode breder, terwijl meer rijen de barcode hoger maken. Pas deze waarden aan om te passen in de beschikbare ruimte in uw UI of afgedrukte label.

## Stap 4: De barcode‑afbeelding opslaan

Tot slot schrijft u de barcode naar een bestand. Hier gebruiken we PNG omdat het scherpe randen behoudt en transparantie ondersteunt.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Het uitvoeren van het programma maakt `LayoutPdf417.png` aan in de output‑map van het project. De afbeelding ziet er als volgt uit:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="voorbeeld van gegenereerde PDF417 barcode met 4 kolommen en 9 rijen"}

*Tip*: Als u een ander afbeeldingsformaat nodig heeft (JPEG, BMP, TIFF), vervang `BarCodeImageFormat.Png` door de juiste enum‑waarde.

## Hoe PDF417 te genereren – alternatieve gegevensbronnen

De bovenstaande code gebruikt een hard‑gecodeerde string "Layout test". In real‑world scenario's haalt u vaak gegevens uit een database, een bestand of gebruikersinvoer.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

De rest van de stappen (grootte, layout, opslaan) blijven ongewijzigd. Dit toont **hoe PDF417 te genereren** vanuit dynamische bronnen zonder extra complexiteit.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Barcode ziet er wazig uit | `XDimension` is te laag ingesteld voor de uitvoerresolutie | Verhoog `XDimension.Pixels` of sla op als een vectorformaat zoals SVG (`BarCodeImageFormat.Svg`) |
| Tekst past niet in de gekozen layout | Te veel tekens voor de geselecteerde rijen/kolommen | Verminder het aantal rijen/kolommen of splits de data over meerdere barcodes |
| Afbeeldingsbestand niet aangemaakt | Uitvoermap bestaat niet of er ontbreken schrijfrechten | Zorg ervoor dat de map bestaat (`Directory.CreateDirectory`) en dat de app met de juiste rechten draait |

## De barcode verifiëren

Na het genereren van de afbeelding kunt u deze verifiëren met elke PDF417‑scanner‑app (mobiele telefoons hebben gratis scanners) of de ingebouwde Aspose.BarCode‑lezer:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Als de output overeenkomt met de oorspronkelijke tekst, is het **PDF417 barcode genereren**‑proces geslaagd.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat u kunt kopiëren‑plakken in `Program.cs`. Het bevat alle using‑directives, foutafhandeling en commentaren.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Het uitvoeren van dit programma geeft het volgende weer:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

U heeft nu een **volledige, zelfstandige oplossing** voor het genereren van PDF417‑barcodes en het regelen van hun grootte.

## Conclusie

In deze tutorial heeft u geleerd hoe u **PDF417 barcode kunt genereren** in C# met Aspose.BarCode, hoe u **de barcode‑grootte kunt wijzigen** door de X‑dimensie aan te passen, en hoe u kolommen en rijen kunt configureren voor layout‑controle. U heeft ook gezien hoe u het resultaat programmatisch kunt verifiëren en hoe u de code kunt aanpassen voor dynamische gegevens.

Vervolgens kunt u verkennen:

* **Hoe PDF417 te genereren** met fout‑correctieniveau afstemming (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exporteren naar **vectorformaten** (SVG, EPS) voor onbeperkte schaalvergroting
* De barcode insluiten in een PDF‑document met **Aspose.PDF**

Experimenteer met verschillende module‑groottes en layout‑opties om te passen bij uw specifieke UI‑ of afdrukvereisten. Veel programmeerplezier!

## Wat moet u hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om u te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in uw eigen projecten te verkennen.

- [Hoe PDF417 Barcode te genereren met Aspose – Complete gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [barcode grootte aanpassen – C# gids om PDF417 barcodes te genereren](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Hoe Barcode op te slaan in C# – PDF417 Barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}