---
category: general
date: 2026-10-14
description: Leer hoe je pdf417 kunt genereren met Aspose.BarCode, aangepaste tekst
  kunt toevoegen, macro‑metadata, en het resultaat kunt exporteren als een PNG in
  een stapsgewijze C#‑tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Leer hoe je pdf417 kunt genereren met Aspose.BarCode. Deze gids toont
  stap voor stap hoe je aangepaste tekst kunt toevoegen, macro‑metadata, en de barcode
  kunt opslaan als een PNG‑afbeelding.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Hoe pdf417 te genereren – volledige C#-gids
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Hoe pdf417 te genereren – volledige C#-gids
url: /nl/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe pdf417 te genereren – volledige C# gids

Als je **pdf417 moet genereren** voor een MacroPdf417‑symbool, leidt deze tutorial je door het volledige proces. Je ziet hoe je macro‑specifieke opties configureert, aangepaste Unicode‑tekst embedt en de barcode opslaat als een PNG‑afbeelding. Aan het einde van de gids heb je een kant‑klaar C#‑fragment dat in elk .NET‑project kan worden geplaatst, of het nu een console‑app, een Windows‑service of een cloud‑gebaseerde micro‑service is.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.BarCode for .NET (ondersteunt meer dan 70 symbologieën).  
- **Kan ik Unicode‑tekens toevoegen?** Ja – de API ondersteunt volledig UTF‑8‑strings zoals `"Åspóse.Barcóde©"`.  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.BarCode‑licentie is vereist voor onbeperkt gebruik; een gratis evaluatie werkt voor testen.  
- **Welke .NET‑versies worden ondersteund?** .NET 6+, .NET 5, .NET Core 3.1 en .NET Framework 4.7+.  
- **Is PNG het beste formaat voor afdrukken?** PNG behoudt verliesvrije kwaliteit en is ideaal voor high‑resolution barcode‑afdrukken.

## Wat is pdf417?
`PDF417` is een gestapelde lineaire barcode die tot ongeveer 1 700 tekens per symbool kan coderen. Het wordt veel gebruikt voor vervoersbewijzen, identificatiekaarten en voorraadtracking omdat het grote hoeveelheden data kan opslaan in een compact, machinaal leesbaar formaat.

## Waarom Aspose.BarCode gebruiken voor pdf417‑generatie?
Aspose.BarCode ondersteunt **meer dan 70 barcode‑symbologieën**, verwerkt bestanden tot **2 GB** zonder het volledige document in het geheugen te laden, en garandeert **100 % naleving van ISO/IEC 15438**. In benchmark‑tests maakt de bibliotheek een volledige MacroPdf417‑barcode in minder dan **150 ms** op een typische ontwikkellaptop, waardoor hij snel genoeg is voor high‑throughput server‑scenario's.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* **.NET 6.0 of later** (de code werkt ook op .NET Framework 4.7+).  
* Een **geldige Aspose.BarCode voor .NET‑licentie** (de gratis proefversie werkt voor ontwikkeling).  
* **Visual Studio 2022** of een andere C#‑IDE naar keuze.  
* Basiskennis van C#‑syntaxis en object‑georiënteerde concepten.  

Er zijn geen extra NuGet‑pakketten vereist naast **Aspose.BarCode**.

## Hoe pdf417 te genereren met macro‑opties?

Laad de `BarcodeGenerator` met de `EncodeTypes.MacroPdf417`‑enum, stel de module‑grootte in, configureer macro‑velden en sla tenslotte de afbeelding op. De volgende stappen tonen de exacte volgorde die je moet volgen om veelvoorkomende valkuilen te vermijden.

### Stap 1: installeer het Aspose.BarCode NuGet‑pakket

Open je project in Visual Studio en voer vervolgens het volgende commando uit in de Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode`‑namespace toe, die de `BarcodeGenerator`‑klasse bevat die in deze tutorial wordt gebruikt.

### Stap 2: maak een barcode‑generator voor MacroPdf417

`BarcodeGenerator` is de kernklasse die wordt gebruikt om barcodes te genereren in Aspose.BarCode.  
De eerste regel maakt een `BarcodeGenerator`‑instantie die zich richt op de **MacroPdf417**‑symbologie en de aangepaste tekst embedt die je wilt coderen.

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

`BarcodeGenerator` is de kernklasse van Aspose.BarCode voor het creëren van elke barcode; hij bevat alle coderingsopties en renderingsinstellingen.

### Stap 3: definieer de basis‑modulegrootte

`XDimension` stelt de breedte van een enkele module (pixel) in de barcode in.  
De module‑grootte bepaalt de visuele dichtheid van de barcode. Een pixelwaarde van `2` levert een scherpe afbeelding op die goed print op standaard labelprinters.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een hogere waarde maakt de barcode groter, terwijl een lagere waarde scanproblemen kan veroorzaken op apparaten met lage resolutie.

### Stap 4: configureer PDF417 macro‑specifieke lay‑outopties

`Columns` bepaalt het aantal datakolommen in de PDF417‑barcode.  
MacroPdf417 vereist verschillende extra parameters. Deze instellingen stellen je in staat de data over meerdere bestanden te verdelen, elk segment te identificeren en de integriteit te verifiëren.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

De eigenschap `Columns` beïnvloedt de breedte van de barcode, terwijl de macro‑velden (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) downstream‑systemen in staat stellen de oorspronkelijke data correct samen te stellen.

### Stap 5: voeg extra macro‑metadata toe

`MacroPdf417Terminator` geeft aan of het huidige segment het laatste is in een macro‑reeks.  
Aspose.BarCode laat je optionele macro‑velden embedden zoals checksum, bestandsgrootte, tijdstempel en afzender/ontvanger‑informatie. Deze velden zijn nuttig voor audit‑trails en foutdetectie.

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

De checksum beschermt tegen transmissiefouten, terwijl de tijdstempel en afzender‑velden context bieden voor downstream‑verwerking. Het instellen van `MacroPdf417Terminator` op `Set` signaleert dat dit het laatste segment in de macro‑reeks is.

### Stap 6: sla de barcode op als PNG‑afbeelding

`Save` schrijft de gegenereerde barcode‑afbeelding naar een bestand in het opgegeven formaat.  
Tot slot schrijf je de gegenereerde barcode naar schijf. PNG behoudt verliesvrije kwaliteit, wat ideaal is voor scanning.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Wanneer de code klaar is, bevat het bestand `ExtPDF417Meta.png` een high‑resolution MacroPdf417‑barcode die de aangepaste tekst en alle macro‑metadata codeert.

#### Verwachte output

Het openen van `ExtPDF417Meta.png` toont een verticaal georiënteerde barcode met duidelijk gedefinieerde rijen en kolommen. Het scannen van de afbeelding met een PDF417‑lezer levert de oorspronkelijke string **Åspóse.Barcóde©** en de macro‑velden die je hebt geconfigureerd (file ID, segment ID, checksum, enz.) terug.

## Hoe pdf417 te genereren zonder macro‑opties?

Om een standaard PDF417‑barcode te maken, hoef je alleen de symbologie in te stellen op `EncodeTypes.Pdf417`, de te coderen tekst op te geven, eventueel grootte‑parameters zoals `XDimension` en `Columns` aan te passen, en vervolgens `Save` aan te roepen. Deze aanpak laat alle macro‑specifieke eigenschappen weg, waardoor een enkel‑segment barcode ontstaat die geschikt is voor de meeste toepassingen.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Dit fragment toont **hoe pdf417 te genereren** snel wanneer macro‑functionaliteit niet nodig is. Het directe antwoord: maak een `BarcodeGenerator` met `EncodeTypes.Pdf417`, stel `CodeText` in, pas eventueel `XDimension` en `Columns` aan, en roep `Save` aan met het gewenste afbeeldingsformaat.

## Veelvoorkomende valkuilen en pro‑tips

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Barcode is te klein om te scannen | X‑dimension ingesteld op 1 pixel of kolommen te hoog | Gebruik minstens `2` pixels voor `XDimension` en houd kolommen tussen `3` en `9` voor typische labelgroottes |
| Unicode‑tekens verschijnen als � | Encoding‑mismatch in het projectbestand | Zorg ervoor dat het projectbestand is opgeslagen als UTF‑8 en dat het bronbestand de juiste BOM bevat |
| Macro‑velden worden genegeerd door de scanner | `MacroPdf417Terminator` niet ingesteld voor het laatste segment | Stel `MacroPdf417Terminator = Pdf417MacroTerminator.Set` in op het laatste segment |
| Afbeeldingsbestand is beschadigd | Uitvoerstroom niet correct gesloten | Gebruik de `using`‑statement (zoals getoond) om de generator correct vrij te geven |

## Volledig, uitvoerbaar voorbeeld

`BarcodeGenerator` is de klasse die de barcode‑afbeelding maakt.  
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

Het uitvoeren van het programma print een regel die ongeveer als volgt lijkt:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Open het bestand om de visuele output te verifiëren.

## Veelgestelde vragen

**V: Kan ik deze code gebruiken in een ASP.NET Core web‑API?**  
Ja. Dezelfde `BarcodeGenerator`‑klasse werkt in elke .NET‑runtime, inclusief ASP.NET Core, zolang de `Aspose.BarCode`‑assembly is verwezen.

**V: Ondersteunt Aspose.BarCode andere afbeeldingsformaten?**  
Absoluut. Je kunt opslaan naar PNG, JPEG, BMP, TIFF en zelfs SVG door de bijbehorende `BarCodeImageFormat`‑enumwaarde door te geven aan de `Save`‑methode.

**V: Hoe groot kan de gecodeerde data zijn?**  
Een enkele PDF417‑symbool kan tot 1 700 tekens bevatten; met MacroPdf417 kun je data over meerdere segmenten verdelen, waardoor praktisch onbeperkte lengte wordt ondersteund.

**V: Is er een manier om kleur toe te voegen aan de barcode?**  
Ja. Stel de `ForeColor`‑ en `BackColor`‑eigenschappen van de `BarcodeGenerator` in vóór het aanroepen van `Save` om gekleurde barcodes te maken.

**V: Wat als ik de barcode direct in een PDF moet insluiten?**  
Gebruik Aspose.PDF om de gegenereerde PNG‑ of SVG‑afbeelding in een PDF‑pagina te plaatsen, of gebruik de ingebouwde PDF‑exportfunctie van Aspose.BarCode.

## Conclusie

Je weet nu **hoe pdf417 te genereren** voor de MacroPdf417‑symbologie, aangepaste Unicode‑tekst te embedden, macro‑metadata te configureren en het resultaat als PNG‑afbeelding te exporteren. Hetzelfde patroon laat je een gewone PDF417‑barcode genereren wanneer macro‑opties niet nodig zijn, en je kunt de code aanpassen voor andere barcode‑formaten die door Aspose.BarCode worden ondersteund. Experimenteer met verschillende `XDimension`‑waarden, kolomtellingen en macro‑veldcombinaties om de barcode af te stemmen op jouw specifieke printer of scanner.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix barcode te genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Barcode genereren Java - Code‑tekst instellen met Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Laatst bijgewerkt:** 2026-10-14  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Macro Pdf417 barcode maken met Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Barcode‑grootte aanpassen C‑gids om Pdf417‑barcodes te genereren](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Barcode lezen van afbeelding C volledige gids met Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}