---
category: general
date: 2026-10-08
description: Genereer PDF417‑barcode in C# en leer hoe je PDF417‑afbeeldingen efficiënt
  kunt genereren met Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: nl
lastmod: 2026-10-08
og_description: Genereer PDF417‑barcode in C# met een stapsgewijze handleiding. Leer
  hoe je PDF417 kunt genereren en de barcode‑afbeelding als PNG kunt opslaan.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Genereer PDF417‑barcode en maak barcode‑afbeelding in C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Genereer PDF417‑barcode en maak barcode‑afbeelding C#
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417‑streepjescode genereren en barcode‑afbeelding maken C#

Als je **PDF417‑streepjescode** moet genereren in een .NET‑applicatie, laat deze tutorial je precies zien hoe je dat doet. Je ziet een volledig, uitvoerbaar voorbeeld dat een barcode maakt, de lay‑out aanpast en het resultaat opslaat als een PNG‑afbeelding.

Het genereren van een PDF417‑streepjescode is een veelvoorkomende eis voor verzendetiketten, instapkaarten en voorraad‑systemen. Aan het einde van deze gids kun je **hoe PDF417 te genereren** met fijne controle over grootte en lay‑out, en leer je ook **barcode‑image C#**‑bestanden te maken die in een UI kunnen worden weergegeven of naar een printer kunnen worden gestuurd.

## Vereisten

- .NET 6.0 of hoger (de code werkt ook met .NET Framework 4.7.2+)
- Visual Studio 2022 of een andere C#‑compatibele IDE
- Aspose.BarCode for .NET (gratis proefversie of gelicentieerde versie)  
  Installeer het via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Er is geen extra configuratie nodig; de bibliotheek verwerkt PNG‑codering intern.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project en voeg de benodigde `using`‑directieven toe. Dit blok bevat alles wat je nodig hebt om het voorbeeld te compileren.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Waarom deze stap belangrijk is*: Het importeren van de `Aspose.BarCode.Generation`‑namespace geeft je toegang tot `BarcodeGenerator`, `EncodeTypes` en de parameterobjecten die worden gebruikt om de barcode aan te passen.

## Stap 2: PDF417‑streepjescode genereren met de gewenste tekst

Binnen `Main` maak je een instantie van `BarcodeGenerator` met `EncodeTypes.Pdf417`. De constructor neemt het barcode‑type en de tekst die je wilt coderen.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Uitleg*: `EncodeTypes.Pdf417` vertelt de bibliotheek om een PDF417‑symbologie te produceren. De string `"Layout demo"` wordt de gegevens‑payload die in de barcode wordt gecodeerd.

## Stap 3: De barcode‑grootte fijn afstellen met X‑dimension

De X‑dimension bepaalt de breedte van één module (het kleinste zwart‑/wit‑vierkant). Instellen in pixels geeft precieze controle over de uiteindelijke afbeeldingsgrootte.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Waarom dit belangrijk is*: Een kleinere X‑dimension levert een compactere barcode op, wat handig is wanneer je beperkte ruimte hebt op een etiket of UI‑element.

## Stap 4: De PDF417‑lay‑out aanpassen (kolommen en rijen)

PDF417 staat je toe het aantal kolommen en rijen te specificeren. Het aanpassen van deze waarden verandert de aspect‑ratio van de barcode.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Uitleg*: Met 4 kolommen en 9 rijen wordt de barcode hoger dan breed, wat past bij veel ticket‑printformaten.

## Stap 5: De gegenereerde barcode opslaan als PNG‑afbeelding

Schrijf tenslotte de barcode naar een bestand. De `BarCodeImageFormat.Png`‑enum zorgt voor verliesloze compressie.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Wat er gebeurt*: `Save` maakt het afbeeldingsbestand op schijf aan. Je kunt `BarCodeImageFormat.Png` vervangen door `Jpeg` of `Bmp` als een ander formaat vereist is.

### Volledig voorbeeld in één blok

Hieronder staat het complete, kant‑klaar te draaien programma. Vervang `YOUR_DIRECTORY` door een daadwerkelijk mappad op jouw machine.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Voer het programma uit (`dotnet run`) en open de resulterende `LayoutPdf417.png`. Je zou een nette PDF417‑streepjescode moeten zien die de tekst *Layout demo* codeert.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Gegenereerde PDF417 barcode opgeslagen als PNG"}

*Verwacht resultaat*: Een PNG‑bestand van ongeveer 150 × 300 pixels (grootte varieert met de X‑dimension) met een scanbare PDF417‑streepjescode.

## Veelvoorkomende variaties en randgevallen

| Scenario | Hoe de code aan te passen |
|----------|---------------------------|
| **Andere gegevens‑payload** | Verander het tweede argument van `BarcodeGenerator` (`"Layout demo"` → elke string, tot 1 800 tekens). |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` (bijv. `4`) of stel `Resolution` in via `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Transparante achtergrond** | Gebruik `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Inbedden in een Windows Forms PictureBox** | In plaats van `Save`, roep `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);` aan. |
| **Foutafhandeling** | Plaats de generatiecode in een `try…catch`‑blok om `BarCodeException` af te vangen voor niet‑ondersteunde tekens. |

## Pro‑tips

- **Barcode valideren**: Na het opslaan kun je de PNG laden met een barcode‑scanner‑SDK om te controleren of de gegevens overeenkomen met de oorspronkelijke string.
- **Prestaties**: Het hergebruiken van één `BarcodeGenerator`‑instantie voor meerdere barcodes vermindert toewijzings‑overhead.
- **Beveiliging**: Als de gecodeerde gegevens gevoelige informatie bevatten, overweeg dan om ze te versleutelen voordat je ze aan de generator doorgeeft.

## Conclusie

Je weet nu hoe je **PDF417‑streepjescode** kunt **genereren in C#** en **barcode‑image C#**‑bestanden kunt maken die voldoen aan aangepaste lay‑out‑eisen. Het volledige voorbeeld toont het initialiseren van de generator, het afstemmen van grootte en lay‑out, en het opslaan van het resultaat als PNG. Vanaf hier kun je extra functies verkennen, zoals kleur‑aanpassing, logo‑inbedden, of batch‑generatie van meerdere barcodes voor massaproductie.

---

*Volgende stappen*:  
- Experimenteer met andere symbologieën (Code128, QR) met dezelfde `BarcodeGenerator`‑klasse.  
- Leer hoe je PDF417‑streepjescodes leest met Aspose.BarCode’s `BarCodeReader`.  
- Integreer de gegenereerde PNG in ASP.NET Core MVC‑views voor dynamische barcode‑rendering.


## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}