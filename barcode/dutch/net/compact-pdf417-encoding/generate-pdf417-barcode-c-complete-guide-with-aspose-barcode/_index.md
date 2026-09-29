---
category: general
date: 2026-08-03
description: Genereer PDF417‑barcode C# met Aspose.BarCode. Leer stap voor stap hoe
  je Macro PDF417‑metadata toevoegt en opslaat als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: nl
lastmod: 2026-08-03
og_description: Genereer PDF417-barcode C# met Aspose.BarCode. Deze tutorial laat
  zien hoe je Macro PDF417-metadata kunt insluiten en het resultaat exporteert als
  een PNG-afbeelding.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: PDF417‑barcode genereren in C# – stap‑voor‑stap Aspose.BarCode‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: PDF417-barcode genereren in C# – volledige gids met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 barcode genereren C# – volledige gids

Als u **PDF417 barcode C#** moet genereren voor een logistiek of document‑beheersysteem, laat deze tutorial u precies zien hoe u dit doet met Aspose.BarCode. U ziet hoe u de barcode configureert, Macro PDF417‑metadata insluit, en het resultaat opslaat als een PNG‑afbeelding in slechts een paar regels code.

Het genereren van een PDF417 barcode in C# betekent vaak dat u extra informatie moet verwerken, zoals bestands‑identifiers, segmentnummers of tijdstempels. Deze gids behandelt die details, zodat u niet door verspreide documentatie hoeft te zoeken. Aan het einde van het artikel heeft u een kant‑klaar programma dat een conforme Macro PDF417 barcode‑afbeelding produceert.

## Wat u nodig heeft

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
- Aspose.BarCode voor .NET (v23.9 of nieuwer) – installeren via NuGet `Install-Package Aspose.BarCode`
- Een ontwikkelomgeving zoals Visual Studio 2022 of Visual Studio Code
- Basiskennis van C#‑syntaxis

> **Pro tip:** Gebruik de nieuwste versie van Aspose.BarCode om te profiteren van bugfixes en ondersteuning voor de nieuwste PDF417‑specificaties.

## Hoe PDF417 barcode C# genereren met Aspose.BarCode

Het proces bestaat uit vier logische stappen. Elke stap staat in een duidelijk code‑blok zodat u deze direct kunt kopiëren, plakken en uitvoeren.

### Stap 1: Maak een Macro PDF417 barcode‑generator

Instantieer eerst `BarcodeGenerator` met de `EncodeTypes.MacroPdf417`‑enum. De constructor accepteert ook de tekst die u wilt coderen – in dit voorbeeld gebruiken we een string met Unicode‑tekens om volledige breedte‑ondersteuning te demonstreren.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Waarom dit belangrijk is*: Het `MacroPdf417`‑type vertelt Aspose.BarCode om het symbool als een macro‑barcode te behandelen, die extra metadata op bestandsniveau kan dragen. Zonder deze vlag zouden de extra velden die u later instelt worden genegeerd.

### Stap 2: Pas de basisuiterlijk van de barcode aan

Definieer vervolgens de visuele grootte van de barcode. `XDimension.Pixels` bepaalt de breedte van één module (het kleinste zwart/witte vierkant), terwijl `Pdf417.Columns` de algehele vorm beïnvloedt door het aantal kolommen in te stellen.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Waarom dit belangrijk is*: Een kleinere `XDimension` levert een afbeelding met hogere resolutie op, wat nuttig is wanneer de barcode vanaf een scherm moet worden gescand. Het aanpassen van het aantal kolommen kan helpen de barcode in beperkte ruimte te passen zonder de gegevenscapaciteit te verminderen.

### Stap 3: Vul Macro PDF417 metadata in

Macro PDF417 stelt u in staat bestands‑niveau informatie in te sluiten waar veel back‑office systemen op vertrouwen (bijv. bestand‑ID, segment‑ID, tijdstempel). De volgende eigenschappen illustreren de meest voorkomende velden.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Waarom dit belangrijk is*: Elk veld correspondeert direct met een segment van de macro‑barcode‑specificatie. Bijvoorbeeld, `MacroPdf417FileID` identificeert het logische bestand uniek, terwijl `MacroPdf417SegmentsCount` de scanner vertelt hoeveel delen te verwachten. Het leveren van nauwkeurige metadata zorgt ervoor dat downstream‑systemen het oorspronkelijke document foutloos kunnen reconstrueren.

### Stap 4: Sla de barcode‑afbeelding op als PNG

Roep tenslotte `Save` aan om de barcode naar schijf te schrijven. PNG is verliesvrij, waardoor het ideaal is voor scannen van hoge kwaliteit.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Waarom dit belangrijk is*: De `BarCodeImageFormat.Png`‑enum garandeert dat het uitvoerbestand exact de pixelgegevens bevat die u hebt geconfigureerd. Als u een vectorformaat nodig heeft voor schalen, vervang dan `Png` door `Svg` – Aspose.BarCode ondersteunt dat direct.

#### Verwachte output

Het uitvoeren van het volledige programma maakt een bestand aan met de naam **ExtPDF417Meta.png**. De afbeelding toont een dichte, meer‑rijige PDF417‑symbool dat de tekst “Åspóse.Barcóde©” en de door u opgegeven macro‑metadata bevat. Het scannen van de barcode met een PDF417‑compatibele lezer geeft de oorspronkelijke tekst terug plus een gestructureerd gegevensblok met de bestand‑ID, segment‑ID, tijdstempel en andere velden.

![Schermafbeelding van gegenereerde PDF417 barcode](/images/pdf417-example.png){: .center-image alt="voorbeeldoutput van PDF417 barcode genereren C#"}

## Volledige broncode (klaar om te kopiëren‑plakken)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Hoe het resultaat te verifiëren

1. Open `ExtPDF417Meta.png` in een willekeurige afbeeldingsviewer.  
2. Gebruik een PDF417‑scannerapp (bijv. *Zebra Scanner* of *BarCode Reader* op Android/iOS).  
3. Bevestig dat de gedecodeerde payload de oorspronkelijke tekst bevat en een JSON‑achtig blok met de macro‑velden die u hebt ingesteld.

## Veelgestelde vragen en afhandeling van randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik een vectorafbeelding genereren in plaats van PNG?** | Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Svg`. De rest van de code blijft ongewijzigd. |
| **Wat als mijn gegevens de standaardcapaciteit overschrijden?** | Verhoog `Pdf417.Columns` of stel `Pdf417.Rows` handmatig in. Grotere waarden staan meer codewoorden per segment toe. |
| **Wordt Unicode ondersteund in de gecodeerde tekst?** | Absoluut. Het voorbeeld gebruikt “Åspóse.Barcóde©”. Aspose.BarCode schakelt automatisch over naar UTF‑8‑codering wanneer nodig. |
| **Moet ik een licentie voor Aspose.BarCode aanschaffen?** | Voor productie moet u een licentie toepassen om het evaluatiewatermerk te vermijden. Roep `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` aan vóór het maken van de generator. |
| **Hoe ga ik om met fouten bij het opslaan van het bestand?** | Plaats de `Save`‑aanroep in een try/catch‑blok en log `IOException` of `BarCodeException` voor probleemoplossing. |

## Conclusie

U weet nu hoe u **PDF417 barcode C#** kunt genereren met Aspose.BarCode, volledige Macro PDF417‑metadata kunt insluiten, en het resultaat kunt exporteren als een PNG‑afbeelding van hoge kwaliteit. De stappen – het maken van de generator, het aanpassen van het uiterlijk, het vullen van metadata en het opslaan van de afbeelding – vormen een herbruikbaar patroon dat u kunt aanpassen voor facturen, verzendetiketten of elke situatie die rijke barcode‑gegevens vereist.

### Volgende stappen

- Experimenteer met andere barcode‑formaten (bijv. QR, Code128) door `EncodeTypes` te wijzigen.  
- Verken `Pdf417.ErrorCorrectionLevel` om de scanbetrouwbaarheid bij slecht licht te verbeteren.  
- Integreer de gegenereerde afbeelding in een PDF‑rapport met behulp van Aspose.PDF voor end‑to‑end documentautomatisering.  

Voel u vrij om de metadata‑velden aan te passen aan uw bedrijfsregels, en laat de barcode‑generatie een naadloos onderdeel worden van uw C#‑applicaties. Veel programmeerplezier!

## Wat moet u hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om u te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in uw eigen projecten te verkennen.

- [Hoe een barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Zo maakt u een barcode – Compact PDF417 met Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode bibliotheek – Barcode toevoegen aan PDF met Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}