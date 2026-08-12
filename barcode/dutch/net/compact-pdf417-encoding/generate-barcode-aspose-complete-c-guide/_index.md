---
category: general
date: 2026-08-12
description: Genereer barcode aspose met Aspose.BarCode en leer hoe je pdf417 met
  aangepaste tekst in een paar eenvoudige stappen kunt genereren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: nl
lastmod: 2026-08-12
og_description: Genereer barcode met Aspose.BarCode. Deze tutorial laat zien hoe je
  een PDF417 genereert met aangepaste tekst, macro‑metadata en het resultaat opslaat
  als PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Barcode genereren met Aspose – stap‑voor‑stap gids
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Barcode genereren met Aspose – volledige C#‑gids
url: /nl/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode genereren met Aspose – volledige C#-gids

Als je **barcode aspose genereren** voor een MacroPdf417‑symbool nodig hebt, leidt deze tutorial je door het volledige proces. Je ziet hoe je macro‑specifieke opties configureert, aangepaste tekst insluit en de barcode opslaat als een PNG‑afbeelding.

Het genereren van een barcode met Aspose.BarCode elimineert handmatige berekeningen en garandeert naleving van de PDF417‑specificatie. In de onderstaande stappen leer je ook **hoe je pdf417 genereert** met aangepaste metadata zoals bestand‑ID, segment‑aantal en tijdstempels. Aan het einde van de gids heb je een kant‑klaar code‑voorbeeld dat je in elk .NET‑project kunt gebruiken.

## Vereisten

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
* Een geldige Aspose.BarCode for .NET‑licentie (de gratis evaluatie werkt voor testen)
* Visual Studio 2022 of een andere C#‑IDE naar keuze
* Basiskennis van C#‑syntaxis en object‑georiënteerde concepten

Er zijn geen extra NuGet‑pakketten vereist naast **Aspose.BarCode**.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open je project in Visual Studio en voer vervolgens de volgende opdracht uit in de Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode`‑namespace toe, die de `BarcodeGenerator`‑klasse bevat die in deze tutorial overal wordt gebruikt.

## Stap 2: Maak een barcode‑generator voor MacroPdf417

De eerste regel maakt een `BarcodeGenerator`‑instantie aan die zich richt op de **MacroPdf417**‑symbologie en de aangepaste tekst die je wilt coderen, insluit.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Waarom dit belangrijk is*: De `EncodeTypes.MacroPdf417`‑enum vertelt Aspose om de barcode te behandelen als een macro‑enabled PDF417‑symbool, dat het splitsen van grote gegevens over meerdere segmenten ondersteunt. De string `"Åspóse.Barcóde©"` toont aan dat de generator Unicode‑tekens correct verwerkt.

## Stap 3: Definieer de basis‑modulegrootte

De modulegrootte bepaalt de visuele dichtheid van de barcode. Een pixelwaarde van `2` levert een scherp beeld op dat goed afdrukt op standaard labelprinters.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Het verhogen van de waarde maakt de barcode groter, terwijl het verlagen ervan scan‑problemen kan veroorzaken op apparaten met lage resolutie.

## Stap 4: Configureer PDF417 macro‑specifieke lay-outopties

MacroPdf417 vereist verschillende extra parameters. Deze instellingen stellen je in staat om de gegevens over meerdere bestanden te splitsen, elk segment te identificeren en de integriteit te verifiëren.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Waarom dit belangrijk is*: De eigenschap `Columns` beïnvloedt de breedte van de barcode, terwijl de macro‑velden (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) downstream‑systemen in staat stellen de oorspronkelijke gegevens correct opnieuw samen te stellen.

## Stap 5: Voeg extra macro‑metadata toe

Aspose.BarCode stelt je in staat optionele macro‑velden in te sluiten, zoals checksum, bestandsgrootte, tijdstempel en afzender/ontvanger‑informatie. Deze velden zijn nuttig voor audit‑trails en foutdetectie.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Waarom dit belangrijk is*: De checksum beschermt tegen transmissiefouten, terwijl de tijdstempel en afzender‑velden context bieden voor downstream‑verwerking. Het instellen van `MacroPdf417Terminator` op `Set` geeft aan dat dit het laatste segment in de macro‑reeks is.

## Stap 6: Sla de barcode op als PNG‑afbeelding

Schrijf tenslotte de gegenereerde barcode naar schijf. PNG behoudt verliesvrije kwaliteit, wat ideaal is voor scanning.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Wanneer de code klaar is, bevat het bestand `ExtPDF417Meta.png` een hoge‑resolutie MacroPdf417‑barcode die de aangepaste tekst en alle macro‑metadata codeert.

### Verwachte output

Het openen van `ExtPDF417Meta.png` toont een verticaal georiënteerde barcode met duidelijk gedefinieerde rijen en kolommen. Het scannen van de afbeelding met een willekeurige PDF417‑lezer geeft de oorspronkelijke string **Åspóse.Barcóde©** en de macro‑velden die je hebt geconfigureerd (bestand‑ID, segment‑ID, checksum, enz.) terug.

## Hoe pdf417 genereren zonder macro‑opties (alternatief scenario)

Als je alleen een standaard PDF417‑barcode nodig hebt, laat dan de macro‑eigenschappen weg en behoud de basisconfiguratie:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Dit fragment toont **hoe je pdf417 genereert** snel wanneer macro‑functionaliteit niet vereist is.

## Veelvoorkomende valkuilen en pro‑tips

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode is te klein om te scannen | X‑dimensie ingesteld op 1 pixel of kolommen te hoog | Gebruik minimaal `2` pixels voor `XDimension` en houd het aantal kolommen tussen `3` en `9` voor typische labelgroottes |
| Unicode‑tekens verschijnen als � | Codering mismatch in het projectbestand | Zorg ervoor dat het projectbestand is opgeslagen als UTF‑8 en dat het bronbestand de juiste BOM bevat |
| Macro‑velden worden genegeerd door de scanner | `MacroPdf417Terminator` niet ingesteld voor het laatste segment | Stel `MacroPdf417Terminator = Pdf417MacroTerminator.Set` in op het laatste segment |
| Afbeeldingsbestand is beschadigd | Uitvoer‑stream niet correct gesloten | Gebruik de `using`‑statement (zoals getoond) om de generator correct vrij te geven |

## Volledig, uitvoerbaar voorbeeld

Kopieer de volgende code naar een nieuwe console‑applicatie en voer deze uit. Het programma maakt de barcode, slaat deze op en print het uitvoerpad naar de console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Het uitvoeren van het programma print een regel die lijkt op:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Open het bestand om de visuele output te verifiëren.

## Conclusie

Je weet nu hoe je **barcode aspose genereert** voor de MacroPdf417‑symbologie, aangepaste Unicode‑tekst insluit, macro‑metadata configureert en het resultaat exporteert als een PNG‑afbeelding. Hetzelfde patroon stelt je in staat **hoe je pdf417 genereert** zonder macro‑opties, en je kunt de code aanpassen voor andere barcode‑formaten die door Aspose.BarCode worden ondersteund.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **barcode custom text maken** voor QR‑codes, het toevoegen van kleurfilters met `Color`‑parameters, of barcodes direct in PDF‑documenten insluiten met Aspose.PDF. Experimenteer met verschillende `XDimension`‑waarden en kolomaantallen om de barcode nauwkeurig af te stemmen op jouw specifieke printer of scanner.

Veel plezier met coderen, en geniet van de betrouwbaarheid die Aspose.BarCode biedt voor jouw .NET‑barcode‑oplossingen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix barcode genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Barcode genereren Java - Code‑tekst instellen met Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}