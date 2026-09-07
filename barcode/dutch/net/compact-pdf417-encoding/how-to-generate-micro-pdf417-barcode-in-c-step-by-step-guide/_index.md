---
category: general
date: 2026-09-07
description: Leer hoe je een micro‑pdf417‑barcode genereert in C# met een compleet
  codevoorbeeld, afstemming van de X‑dimensie, kolomconfiguratie en PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: nl
lastmod: 2026-09-07
og_description: Genereer een micro‑pdf417‑barcode in C# met deze beknopte tutorial.
  Inclusief X‑dimensie‑instellingen, kolomkeuzes en PNG‑export voor direct gebruik.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Genereer micro PDF417-barcode in C# – volledige programmeergids
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Hoe een micro PDF417‑barcode te genereren in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een micro pdf417 barcode te genereren in C# – stap‑voor‑stap gids

Als je een **micro pdf417 barcode** moet genereren in een .NET‑applicatie, laat deze tutorial je een kant‑klaar werkende oplossing zien. Je ziet hoe je de X‑dimensie van de barcode configureert, het aantal kolommen kiest en het resultaat exporteert als een PNG‑afbeelding—alles met de Aspose.BarCode C#‑bibliotheek.

Het genereren van een micro pdf417 barcode is gebruikelijk wanneer je compacte gegevens moet coderen voor mobiele tickets, voorraadlabels of beveiligde documenten. Aan het einde van deze gids heb je een herbruikbaar code‑fragment dat je in elk C#‑project kunt plaatsen.

## Vereisten

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
* Visual Studio 2022 (of elke IDE die C# ondersteunt)
* Het **Aspose.BarCode for .NET** NuGet‑pakket (versie 23.9 of nieuwer)

Je kunt het pakket installeren via de opdrachtregel:

```bash
dotnet add package Aspose.BarCode
```

Er zijn geen extra afhankelijkheden vereist.

## Stap 1: Maak een barcode‑generator voor MicroPdf417

De eerste taak is om een `BarcodeGenerator` te instantieren met de enum‑waarde `EncodeTypes.MicroPdf417` en de tekst die je wilt coderen. De tekst kan Unicode‑tekens bevatten, die de bibliotheek automatisch verwerkt.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Waarom dit belangrijk is:**  
`EncodeTypes.MicroPdf417` vertelt de bibliotheek om de compacte MicroPdf417‑symbologie te gebruiken, die meer gegevens opslaat in een kleinere ruimte dan de volledige PDF417. Het meegeven van de tekst bij de constructie zorgt ervoor dat de generator precies weet wat er moet worden gecodeerd.

## Stap 2: Pas de X‑dimensie aan voor fijnere resolutie

De X‑dimensie (module‑breedte) bepaalt hoeveel pixels elke barcode‑kolom inneemt. Een waarde van **2 pixels** levert een hoge‑resolutie barcode op die leesbaar blijft voor de meeste scanners.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pro‑tip:**  
Als je richt op low‑resolution schermen of printers, verhoog de waarde naar 3‑4 pixels om onscherpe randen te voorkomen. Omgekeerd kun je voor high‑density labels de waarde verlagen naar 1 pixel, maar test het resultaat met je scanner.

## Stap 3: Kies het aantal kolommen

MicroPdf417 staat **1 tot 4 kolommen** toe. Meer kolommen geven een kortere barcode maar verminderen de fout‑correctiecapaciteit. Voor de meeste ticket‑scenario's bieden **4 kolommen** een compacte vorm met behoud van robuustheid.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Waarom je dit zou kunnen aanpassen:**  
Als de gecodeerde tekst langer is dan de standaardcapaciteit, verhoog dan het aantal kolommen om overflow‑fouten te voorkomen. Verlaag het wanneer je een smalle barcode nodig hebt voor beperkte ruimte.

## Stap 4: Definieer de output‑map en bestandsnaam

Selecteer een map waarin de gegenereerde afbeelding wordt opgeslagen. Het gebruik van `Path.Combine` garandeert correcte pad‑scheidingstekens op Windows, Linux en macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Afhandeling van randgevallen:**  
Als het mappad ongeldig is of de applicatie geen schrijfrechten heeft, gooit `Directory.CreateDirectory` een uitzondering. Plaats de opslaalogica in een `try/catch`‑blok voor productiecodel.

## Stap 5: Sla de barcode op als PNG‑afbeelding

Exporteer tenslotte de barcode naar een PNG‑bestand. PNG behoudt scherpe randen en ondersteunt transparantie, waardoor het ideaal is voor UI‑rendering of afdrukken.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Na uitvoering vind je **MicroPdf417.png** in de `Barcodes`‑map op je bureaublad. Het openen van het bestand toont een duidelijke, hoge‑resolutie micro pdf417 barcode klaar om te scannen.

### Verwachte output

De opgeslagen afbeelding ziet er vergelijkbaar uit met de illustratie hieronder (het daadwerkelijke patroon hangt af van de gecodeerde tekst).

![Generated micro pdf417 barcode saved as PNG](https://example.com/placeholder-micro-pdf417.png "Screenshot of a generated micro pdf417 barcode saved as a PNG file")

*Alt‑tekst:* micro pdf417 barcode gegenereerd en opgeslagen als PNG‑afbeelding

## Volledig, uitvoerbaar voorbeeld

Alle stappen samenvoegen levert een enkel, zelfstandig programma op:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Voer het programma uit (`dotnet run` vanuit de projectmap) en controleer of het PNG‑bestand verschijnt zoals verwacht.

## Veelgestelde vragen en probleemoplossing

| Vraag | Antwoord |
|----------|--------|
| **Kan ik de barcode genereren als JPEG in plaats van PNG?** | Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`. JPEG comprimeert de afbeelding maar kan artefacten introduceren die de leesbaarheid voor de scanner beïnvloeden. |
| **Wat als de tekst tekens bevat die niet worden ondersteund door MicroPdf417?** | MicroPdf417 ondersteunt het volledige Unicode‑bereik. Als je een `ArgumentException` krijgt, controleer dan of de string correct is gecodeerd (bijv. vermijd surrogate‑paren die de symboolcapaciteit overschrijden). |
| **Hoe wijzig ik de voorgrondkleur?** | Gebruik `generator.Parameters.Barcode.BarColor = Color.Blue;` vóór het aanroepen van `Save`. |
| **Is er een manier om de barcode direct in een PDF in te sluiten?** | Ja. Gebruik `generator.Save(stream, BarCodeImageFormat.Pdf);` of voeg de afbeelding toe aan een PDF‑document met een PDF‑bibliotheek zoals Aspose.PDF. |
| **Mijn scanner kan de barcode niet lezen—wat moet ik controleren?** | Zorg ervoor dat de X‑dimensie minimaal 2 pixels is voor de meeste scanners, controleer of het aantal kolommen binnen het bereik van de scanner valt, en bevestig dat de afgedrukte grootte voldoet aan de minimale modulegrootte van de scanner (meestal 0,5 mm). |

## Conclusie

Je weet nu hoe je een **micro pdf417 barcode** in C# van begin tot eind kunt **genereren**. De gids besprak het maken van de `BarcodeGenerator`, het configureren van de X‑dimensie en het aantal kolommen, het voorbereiden van een output‑pad, en het opslaan van het resultaat als PNG. Door de secundaire instellingen—zoals balkkleur, afbeeldingsformaat of fout‑correctieniveau—aan te passen, kun je de barcode afstemmen op elke toepassing, van mobiele tickets tot voorraadlabels.

### Volgende stappen

* Experimenteer met **barcode X‑dimensie** waarden om grootte en leesbaarheid in balans te brengen.  
* Verken andere symbologieën (bijv. `EncodeTypes.Pdf417`, `EncodeTypes.QR`) met hetzelfde generator‑patroon.  
* Integreer de gegenereerde PNG in een PDF‑rapport met **Aspose.PDF** of embed deze direct in een WinForms/WPF‑UI.  

Veel programmeerplezier, en geniet van de flexibiliteit die de Aspose.BarCode‑bibliotheek biedt voor barcode‑generatie in C#!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode Generator Tutorial: Hoe PDF417 Barcode te genereren in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Hoe Barcode op te slaan in C# – PDF417 Barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Hoe PDF417 Barcode te genereren – Complete programmeergids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}