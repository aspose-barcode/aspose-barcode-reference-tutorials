---
category: general
date: 2026-08-22
description: Leer hoe je een PDF417‑barcode genereert in C# met Aspose.BarCode, de
  barcodegrootte instelt, kolommen aanpast en compacte modus inschakelt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: nl
lastmod: 2026-08-22
og_description: Genereer PDF417-barcode in C# met Aspose.BarCode. Deze gids laat zien
  hoe u de barcodegrootte instelt, kolommen beheert en compacte modus inschakelt voor
  een kleinere afbeelding.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: PDF417-barcode genereren in C# – grootte, kolommen en compacte modus instellen
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Hoe PDF417-barcode te genereren in C# en de barcodegrootte in te stellen
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode te genereren in C# en de barcodegrootte in te stellen

Als je een **PDF417 barcode** moet **genereren** in een .NET‑applicatie, leidt deze gids je door het volledige proces. Je ziet precies **hoe je PDF417 kunt genereren** met Aspose.BarCode, de **barcodegrootte instelt**, en een compacte PNG produceert die in rapporten of mobiele apps kan worden ingebed.

Het maken van een barcode vereist geen aparte grafische editor. Aan het einde van deze tutorial heb je een volledig functionele C#‑methode die een PDF417‑afbeelding produceert met de exacte afmetingen die je nodig hebt, klaar voor verdere verwerking.

## Wat je zult leren

* Installeer en verwijs naar de Aspose.BarCode‑bibliotheek.
* Maak een PDF417 barcode‑generator en specificeer de te coderen tekst.
* **Stel de barcodegrootte in** door X‑dimensie en kolomaantal te configureren.
* Schakel de compacte (afgekorte) modus in om het symbool te verkleinen.
* Sla het resultaat op als een PNG‑bestand.
* Los veelvoorkomende problemen op, zoals onleesbare codes en te grote afbeeldingen.

### Vereisten

* .NET 6.0 of hoger (de API werkt ook met .NET Framework 4.6+).
* Basiskennis van C# en Visual Studio (of een andere C#‑IDE).
* Een geldige Aspose.BarCode‑licentie (de gratis evaluatie werkt voor testen).

> **Pro tip:** Als je van plan bent om veel barcodes in een lus te genereren, hergebruik dan één `BarcodeGenerator`‑instantie en wijzig alleen de `CodeText`‑eigenschap. Dit vermindert geheugenallocaties.

## PDF417 barcode genereren met Aspose.BarCode

De eerste stap is het instantieren van de `BarcodeGenerator` voor de PDF417‑symbologie. Dit object is het toegangspunt voor alle barcode‑bewerkingen.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Waarom dit belangrijk is*: `EncodeTypes.Pdf417` vertelt de bibliotheek om de PDF417‑standaard te gebruiken, die grote hoeveelheden data en foutcorrectie ondersteunt. De constructor accepteert ook direct de data die je wilt coderen, waardoor een aparte `CodeText`‑toewijzing later overbodig is.

## Barcodegrootte en kolomaantal instellen

PDF417‑symbolen bestaan uit rijen en kolommen van kleine rechthoekige modules. Door de modulebreedte (X‑dimensie) en het aantal kolommen te regelen, kun je de totale afmetingen nauwkeurig afstemmen.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Uitleg*:  
* **X‑dimensie** (`Pixels`) bepaalt hoe breed elke module is. Kleinere waarden geven een compactere barcode, terwijl grotere waarden de leesbaarheid op laag‑resolutie scanners vergroten.  
* **Kolommen** regelen de horizontale lay-out. Minder kolommen maken de barcode hoger; meer kolommen maken hem breder. Pas deze twee instellingen samen aan om de exacte **barcodegrootte** te bereiken die je nodig hebt.

## Compacte modus inschakelen voor een kleinere barcode

PDF417 bevat een “compacte” (of afgekorte) modus die onnodige opvulling verwijdert en de totale voetafdruk verkleint. Dit is vooral handig wanneer je beperkte schermruimte hebt.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Waarom truncatie inschakelen?*  
Wanneer `Truncate` `true` is, laat de generator het stop‑patroon en enkele fout‑correctie‑codewoorden weg die niet nodig zijn voor de meeste scansituaties. De resulterende afbeelding is ongeveer 15‑20 % kleiner zonder de gegevensintegriteit voor typische gebruikssituaties op te offeren.

## De barcode opslaan als PNG‑afbeelding

Na het configureren van grootte en modus, schrijf je de barcode naar schijf. PNG is verliesvrij, waardoor de module‑randen scherp blijven.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Het bestand `CompactPdf417.png` zal een scherpe PDF417‑symbool bevatten dat overeenkomt met de afmetingen die je in de vorige stappen hebt ingesteld.

### Verwachte output

Het openen van de opgeslagen PNG moet een verticaal georiënteerde PDF417‑barcode tonen die bestaat uit drie kolommen, elke module 2 px breed, en een totale grootte van ongeveer **120 × 240 px** (breedte × hoogte). Het scannen van de afbeelding met een standaard PDF417‑lezer geeft de oorspronkelijke tekst “Sample text for PDF417” terug.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Barcode is onleesbaar | X‑dimensie te klein voor de scanner | Verhoog `XDimension.Pixels` naar 3 of 4 |
| Afbeelding is te breed voor de UI | Te veel kolommen ingesteld | Verminder `Pdf417.Columns` of schakel `Truncate` in |
| Exception `ArgumentOutOfRangeException` | Negatieve of nul kolomtelling | Zorg ervoor dat `Columns` een positief geheel getal is (minimum 1) |
| PNG‑bestand is leeg | Uitvoerpad bestaat niet of heeft geen schrijfrechten | Controleer of de map bestaat en de applicatie schrijfrechten heeft |

> **Pro tip:** Gebruik `barcodeGenerator.ValidateParameters()` vóór het aanroepen van `Save()` om configuratiefouten vroegtijdig te detecteren.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat een zelfstandige console‑applicatie die alle bovenstaande stappen bevat. Kopieer deze naar een nieuw C#‑project, herstel het Aspose.BarCode‑NuGet‑pakket, en voer het uit om het resultaat te zien.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Het uitvoeren van het programma** genereert `CompactPdf417.png` in de werkmap van het uitvoerbare bestand. Scan de afbeelding met een mobiele app (bijv. “Barcode Scanner”) om te verifiëren dat de gecodeerde tekst overeenkomt met de bronstring.

## Volgende stappen en gerelateerde onderwerpen

* **Verhoog foutcorrectieniveau** – pas `Pdf417.ErrorLevel` aan voor omgevingen met ruisvolle scans.  
* **Verander oriëntatie** – stel `Pdf417.Rotate` in op `RotationAngle.Rotate90` als je een horizontale lay-out nodig hebt.  
* **Barcode in een PDF insluiten** – combineer Aspose.PDF met Aspose.BarCode om de afbeelding direct in een document te plaatsen.  
* **Andere 2‑D barcodes genereren** – dezelfde `BarcodeGenerator`‑klasse ondersteunt DataMatrix, QR en Aztec‑codes; vervang gewoon `EncodeTypes.Pdf417` door de gewenste symbologie.

Door de **PDF417 barcode‑generatietechnieken** onder de knie te krijgen, kun je ticketing, voorraadlabeling en veilige gegevensoverdracht automatiseren in een breed scala aan .NET‑applicaties.

## Conclusie

Je weet nu hoe je een **PDF417 barcode** in C# kunt **genereren**, nauwkeurig de **barcodegrootte** kunt **instellen**, kolommen kunt configureren, compacte modus kunt inschakelen en het resultaat als PNG kunt opslaan. Pas deze instellingen toe om aan elke UI‑beperking of scan‑vereiste te voldoen, en breid de aanpak uit naar andere barcode‑formaten indien nodig. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 Barcode te genereren – Compacte PDF417‑codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe een Barcode te maken – Compacte PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix Barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}