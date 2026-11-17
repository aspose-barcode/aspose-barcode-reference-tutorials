---
category: general
date: 2026-11-17
description: Leer hoe je een PDF417‑barcode maakt in C# – een complete gids over hoe
  je een barcode genereert vanuit een string met behulp van een C#‑barcodegenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: nl
lastmod: 2026-11-17
og_description: Maak snel een PDF417-barcode in C#. Deze tutorial laat zien hoe je
  een barcode genereert vanuit een string met een C# barcodegenerator en bevat de
  volledige broncode.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: PDF417-barcode maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Hoe maak je een PDF417-barcode in C# met een barcodegenerator
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te maken in C# met een barcodegenerator

Als je een **PDF417-barcode wilt maken** in een .NET-toepassing, laat deze gids precies zien hoe je dat doet. Je leert **hoe je een barcode genereert** vanuit een gewone string, de symboolgrootte configureert en het resultaat opslaat als een PNG‑bestand — allemaal met behulp van een betrouwbare C# barcodegenerator.

Barcodes programmatisch genereren verwijdert handmatige stappen en garandeert consistente kwaliteit. In deze tutorial behandelen we alles, van projectopzet tot de uiteindelijke afbeelding, zodat je barcode‑creatie vandaag nog in elke C#‑oplossing kunt integreren.

## Vereisten

* .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
* Visual Studio 2022 (of een IDE die C# ondersteunt)
* Een licentie of gratis proefversie van **Aspose.BarCode for .NET** – de bibliotheek die in de voorbeelden wordt gebruikt
* Basiskennis van C#‑syntaxis

Er zijn geen extra pakketten nodig; het NuGet‑pakket `Aspose.BarCode` bevat alle klassen die je nodig hebt.

## Stap 1 – De C# barcodegenerator instellen

Het eerste wat je doet wanneer je een **PDF417-barcode maakt**, is een `BarcodeGenerator`‑object instantiëren. Dit object vertegenwoordigt de **c# barcodegenerator** die de codering, weergave en opslaan afhandelt.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Waarom dit belangrijk is*: De `EncodeTypes.Pdf417`‑enum vertelt de bibliotheek om de PDF417‑symbologie te gebruiken, dezelfde standaard die wordt gebruikt voor identificatiekaarten en transportlabels. De string `"(01)12345678901234"` is een **barcode genereren vanuit string**‑voorbeeld dat ook laat zien hoe je **GS1-barcode maken**‑gegevens maakt.

## Stap 2 – De X‑dimensie (modulebreedte) configureren

De X‑dimensie bepaalt de breedte van de kleinste balk (module). Een veelgebruikte waarde voor weergave op het scherm is 2 pixels.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Het expliciet instellen van de X‑dimensie voorkomt dat de generator zijn standaardwaarde gebruikt, waardoor een barcode kan ontstaan die voor sommige scanners te klein is.

## Stap 3 – Het aantal kolommen definiëren

PDF417 stelt je in staat het aantal kolommen aan te passen, wat zowel de vorm van de barcode als de gegevenscapaciteit beïnvloedt. Voor een compact label werken vier kolommen goed.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Als je een hogere barcode nodig hebt, verhoog dan het aantal kolommen; de bibliotheek berekent automatisch het benodigde aantal rijen.

## Stap 4 – De barcode opslaan als afbeelding

Exporteer tenslotte de barcode naar een PNG‑bestand. PNG behoudt scherpe randen en ondersteunt transparantie.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Het uitvoeren van het programma maakt `output/Gs1Pdf417.png`. Open het bestand in een willekeurige afbeeldingsviewer — je ziet een nette **PDF417 barcode** die de door jou opgegeven GS1‑gegevens codeert.

### Verwachte output

![Gegenereerde PDF417 barcode die de GTIN (01)12345678901234 toont](/images/pdf417-sample.png){: .center-image alt="Gegenereerde PDF417 barcode gemaakt met een C# barcodegenerator"}

*De bovenstaande afbeelding toont het resultaat van het volledige code‑voorbeeld. De barcode kan worden gescand door elke PDF417‑compatibele lezer.*

## Extra opties en veelvoorkomende variaties

### Het afbeeldingsformaat wijzigen

Als je JPEG of BMP verkiest, vervang dan eenvoudig `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp`. De rest van de code blijft identiek.

### Het foutcorrectieniveau aanpassen

PDF417 ondersteunt foutcorrectieniveaus 0‑8. Hogere niveaus verhogen de redundantie maar vergroten ook de barcode.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Andere GS1‑barcodes genereren

Dezelfde `BarcodeGenerator` kan **GS1‑barcode maken** voor andere symbologieën, zoals `EncodeTypes.Gs1DataMatrix` of `EncodeTypes.Gs1Qr`. Vervang gewoon de enum‑waarde:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Omgaan met lege of null‑gegevens

Wanneer je **barcode genereren vanuit string** uitvoert, valideer dan altijd de invoer:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Dit voorkomt runtime‑exceptions en zorgt ervoor dat de barcode voldoet aan de GS1‑opmaakregels.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren en plakken in een nieuw console‑project. Het bevat alle benodigde `using`‑directieven, map‑creatie en foutafhandeling.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Voer het programma uit** (`dotnet run`) en je vindt `Gs1Pdf417.png` in de *output*‑map. Scan het met een PDF417‑lezer om te verifiëren dat de GTIN `(01)12345678901234` correct is gecodeerd.

## Veelgestelde vragen

**Q: Kan ik deze code gebruiken op .NET Framework 4.6?**  
A: Ja. De Aspose.BarCode‑bibliotheek richt zich op .NET Standard 2.0, wat compatibel is met .NET Framework 4.6 en later.

**Q: Wat als ik een afbeelding met hogere resolutie nodig heb?**  
A: Stel de `Resolution`‑eigenschap in vóór het opslaan:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Is de barcode nog geldig zonder de GS1 Application Identifier?**  
A: Het wordt een standaard PDF417‑barcode, maar zal niet worden herkend als een GS1‑conform symbool. Voeg de `(01)`‑prefix toe wanneer je **GS1‑barcode maken**‑conformiteit nodig hebt.

## Conclusie

Je weet nu hoe je een **PDF417‑barcode maakt** in C# met behulp van een robuuste **c# barcodegenerator**. De tutorial behandelde:

* Het instantiëren van `BarcodeGenerator` met GS1‑gegevens  
* Het configureren van X‑dimensie en kolomtelling  
* Het opslaan van het resultaat als PNG‑afbeelding  
* Het uitbreiden van de oplossing met foutcorrectie, verschillende formaten en invoervalidatie  

Met deze basis kun je elke PDF417‑ of GS1‑barcode direct uit een string genereren, in rapporten insluiten of naar printers sturen. Verken de Aspose.BarCode‑API om kleuren toe te voegen, marges in te stellen of meerdere barcodes te combineren tot één afbeelding.

**Volgende stappen**: probeer een **GS1‑barcode maken** voor DataMatrix te genereren, experimenteer met dynamische kolom‑berekeningen, of integreer de generator in een ASP.NET Core‑webservice die barcode‑afbeeldingen op aanvraag retourneert.

Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417-barcode te genereren in C# – volledige gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Hoe micro PDF417-barcode te maken en PNG te genereren in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Hoe macro PDF417-barcode te maken in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}