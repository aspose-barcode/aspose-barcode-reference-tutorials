---
category: general
date: 2026-10-02
description: Leer hoe u kolommen en rijen instelt in een C#‑barcodegenerator om DataBar‑barcodes
  te maken. Stapsgewijze handleiding met volledige code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: nl
lastmod: 2026-10-02
og_description: C# barcodegenerator gids – leer hoe je kolommen en rijen instelt om
  DataBar-barcodes te maken met volledige codevoorbeelden.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'C# barcodegenerator: stel kolommen en rijen in voor DataBar-barcodes'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Hoe een C#-barcodegenerator te gebruiken om DataBar-barcodes te maken met aangepaste
  kolommen en rijen
url: /nl/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een C# barcodegenerator te gebruiken om DataBar-barcodes te maken met aangepaste kolommen en rijen

Als je een **c# barcode generator** nodig hebt die DataBar-barcodes kan produceren met precieze kolom- en rijconfiguraties, laat deze tutorial je precies zien hoe. Je zult zien waarom het aanpassen van kolommen en rijen belangrijk is, en je krijgt een compleet, kant‑klaar voorbeeld dat zowel een 4‑koloms als een 3‑rij DataBar Expanded Stacked barcode maakt.

In de secties die volgen behandelen we:

* De vereisten voor het gebruik van de Aspose.BarCode for .NET bibliotheek.
* Hoe kolommen (`how to set columns`) en rijen (`how to set rows`) in te stellen op een DataBar barcode.
* Een volledig C# consoleprogramma dat je kunt kopiëren, compileren en uitvoeren.
* Verwachte outputbestanden en tips voor probleemoplossing.

Aan het einde van deze gids kun je **databar barcode** afbeeldingen maken die zijn afgestemd op je lay-outvereisten.

## Vereisten

Before you start, make sure you have:

| Vereiste | Reden |
|-------------|--------|
| .NET 6.0 SDK of later | Biedt de runtime voor de C# code. |
| Visual Studio 2022 (of een IDE die .NET ondersteunt) | Maakt projectcreatie en debugging gemakkelijker. |
| Aspose.BarCode for .NET NuGet-pakket | Levert de `BarcodeGenerator`-klasse die in de voorbeelden wordt gebruikt. |
| Schrijfrechten voor een map voor de output PNG‑bestanden | De generator schrijft de barcode‑afbeeldingen naar de schijf. |

Install the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Maak een basis DataBar Expanded Stacked barcode

De eerste stap is het instantieren van een **c# barcode generator** met het `EncodeTypes.DatabarExpandedStacked`-formaat. Dit formaat is een tweedimensionale DataBar barcode die tot 74 numerieke tekens kan coderen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

The constructor receives two arguments:

* `EncodeTypes.DatabarExpandedStacked` – geeft de bibliotheek aan welke symbologie te gebruiken.
* `"Databar Expanded Stacked long"` – de tekst die zal worden gecodeerd.

## Stap 2: Hoe kolommen in te stellen

Kolommen beïnvloeden de horizontale dichtheid van de DataBar barcode. Het verhogen van het aantal kolommen maakt de barcode breder, wat de scanbetrouwbaarheid op printers met lage resolutie kan verbeteren.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Waarom 4 kolommen?**  
Vier kolommen bieden een goede balans tussen grootte en leesbaarheid voor de meeste retailtoepassingen. Je kunt experimenteren met waarden van 1 tot 8; de bibliotheek past de modulebreedte automatisch aan.

## Stap 3: Sla de kolom‑geconfigureerde barcode op

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

De afbeelding wordt opgeslagen als een PNG‑bestand, wat de scherpe randen behoudt die nodig zijn voor barcode‑scanners.

## Stap 4: Maak een aparte generator voor rijconfiguratie

Rijconfiguratie werkt op dezelfde manier maar beïnvloedt de verticale dichtheid. Om het mengen van kolom‑ en rij‑instellingen te voorkomen, maken we een nieuwe generator‑instantie.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Stap 5: Hoe rijen in te stellen

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Wanneer meer rijen gebruiken?**  
Het toevoegen van rijen maakt de barcode hoger, wat nuttig kan zijn wanneer de afdrukruimte horizontaal beperkt is maar verticaal ruim (bijv. op een productetiket dat hoger is dan breed).

## Stap 6: Sla de rij‑geconfigureerde barcode op

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Beide PNG‑bestanden (`DatabarCols4.png` en `DatabarRows3.png`) verschijnen in de map `C:\Barcodes`.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat een zelfstandige console‑applicatie die elke stap hierboven beschrijft. Kopieer de code naar een nieuw .NET console‑project en voer het uit.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Wat de code doet

| Sectie | Doel |
|---------|---------|
| **Namespace imports** | Haalt `Aspose.BarCode` en `Aspose.BarCode.Generation` binnen. |
| **Output directory** | Centraliseert het pad zodat je slechts één regel hoeft aan te passen als je de map verplaatst. |
| **Column generator** | Toont **how to set columns** op een `c# barcode generator`. |
| **Row generator** | Toont **how to set rows** op een `c# barcode generator`. |
| **Save calls** | Schrijft de PNG‑bestanden naar de schijf, waardoor ze klaar zijn voor scanning of opname in rapporten. |
| **Console output** | Biedt directe feedback, nuttig tijdens ontwikkeling. |

## Verwachte output

After running the program you should see two PNG files:

* **DatabarCols4.png** – een bredere barcode die vier kolommen weergeeft.
* **DatabarRows3.png** – een hogere barcode die drie rijen weergeeft.

Beide afbeeldingen bevatten de tekst *“Databar Expanded Stacked long”* gecodeerd in de DataBar Expanded Stacked symbologie. Je kunt ze openen in elke afbeeldingsviewer of aan een barcode‑scanner voeren om de leesbaarheid te verifiëren.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Reden | Oplossing |
|-------|--------|-----|
| **File‑access exception** | De outputmap bestaat niet of je hebt geen schrijfrechten. | Maak de map handmatig aan of voer het programma uit met verhoogde rechten. |
| **Incorrect column/row values** | De bibliotheek accepteert alleen waarden 1‑8 voor kolommen en 1‑4 voor rijen. | Valideer de waarden vóór toewijzing, bijv. `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | De gegenereerde afbeelding is te klein voor de resolutie van de scanner. | Verhoog de `ImageHeight` of `ImageWidth` via `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | De gecodeerde tekst overschrijdt de maximale lengte voor de gekozen DataBar‑variant. | Gebruik een kortere string of schakel over naar `EncodeTypes.DatabarExpanded` als je meer capaciteit nodig hebt. |

## Pro‑tips

* **Cache de generator** – Als je veel barcodes moet maken met dezelfde kolom‑/rij‑instellingen, hergebruik dan dezelfde `BarcodeGenerator`‑instantie en wijzig alleen de `CodeText`‑eigenschap.
* **Batchverwerking** – Loop over een collectie product‑identifiers, stel `generator.CodeText` in binnen de lus, en roep `Save` aan met een unieke bestandsnaam per iteratie.
* **Prestaties** – Voor scenario's met hoog volume, schakel anti‑aliasing uit (`generator.Parameters.Image.AntiAlias = false`) om de beeldgeneratie te versnellen zonder de scan‑kwaliteit te beïnvloeden.

## Volgende stappen

Nu je weet **how to set columns** en **how to set rows** met een **c# barcode generator**, wil je misschien verkennen:

* **Human‑readable tekst toevoegen** onder de barcode (`generator.Parameters.Barcode.CodeTextLocation`).
* **Kleuren wijzigen** (`generator.Parameters.Image.ForegroundColor` en `BackgroundColor`).
* **Andere DataBar‑varianten genereren** zoals `DatabarLimited` of `DatabarExpanded`.
* **Barcodes insluiten in PDF‑rapporten** met behulp van Aspose.PDF.

Elk van deze onderwerpen bouwt voort op de hier behandelde basis en helpt je rijkere, productie‑klare barcode‑oplossingen te creëren.

---

*Happy coding! Als je tegen problemen aanloopt, laat dan gerust een reactie achter of raadpleeg de Aspose.BarCode‑documentatie voor meer API‑details.*

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode‑kolommen en -rijen in te stellen met C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator‑voorbeeld in C# – Kolommen, rijen instellen & afbeelding exporteren](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Hoe een barcode‑generator C# te gebruiken om DataBar‑barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}