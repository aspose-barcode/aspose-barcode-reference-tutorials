---
category: general
date: 2026-08-03
description: Barcode-generator C#-tutorial laat zien hoe je een barcode‑afbeelding
  genereert met Aspose.BarCode, kolommen en rijen instelt en PNG‑bestanden opslaat
  voor DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: nl
lastmod: 2026-08-03
og_description: Barcode generator C#-tutorial legt uit hoe je een barcode‑afbeelding
  genereert met Aspose.BarCode, DataBar Expanded Stacked‑kolommen en -rijen configureert
  en PNG‑bestanden opslaat.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Barcodegenerator C# – stapsgewijze handleiding voor het genereren van een
  barcode‑afbeelding
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcodegenerator C# – barcode‑afbeelding genereren
url: /nl/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – barcode‑afbeelding genereren

Als je een barcode generator C# nodig hebt die een barcode‑afbeelding kan genereren voor DataBar Expanded Stacked, leidt deze gids je door het volledige proces. Je leert hoe je kolom‑ en rij‑instellingen configureert, het resultaat opslaat als PNG, en de code aanpast voor andere symbologieën.

Barcode‑afbeeldingen programmatically genereren verwijdert handmatige stappen en zorgt voor consistentie in facturen, verzendetiketten en voorraad‑systemen. Deze tutorial behandelt alles wat je nodig hebt, van project‑opzet tot volledige broncode, zodat je het voorbeeld direct kunt uitvoeren.

## Prerequisites

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later geïnstalleerd  
* Een IDE zoals Visual Studio 2022 (elke editor die C# ondersteunt)  
* Een licentie voor **Aspose.BarCode for .NET** – de gratis evaluatie werkt voor testen  
* Basiskennis van C#‑syntaxis  

Als een van deze items ontbreekt, installeer dan de .NET SDK vanaf dotnet.microsoft.com en verkrijg het Aspose.BarCode NuGet‑pakket met:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a barcode generator C# project

Maak een nieuwe console‑applicatie aan en voeg de benodigde `using`‑directieven toe:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

De `BarcodeGenerator`‑klasse is de kern van de barcode generator C# API. Hij ontvangt het symbologie‑type en de te coderen tekst.

## Step 2: Generate a DataBar Expanded Stacked barcode and set columns

Het eerste voorbeeld maakt een barcode met vier kolommen. Het aanpassen van de `Columns`‑eigenschap verandert de visuele dichtheid van de DataBar Expanded Stacked‑symbologie.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Why this matters:** Het aantal kolommen beïnvloedt de hoeveelheid data die in een compacte ruimte kan worden opgeslagen. Een waarde van 4 produceert een bredere barcode die door de meeste scanners leesbaar blijft.

## Step 3: Generate a barcode with custom row count

Het tweede voorbeeld laat zien hoe je de verticale lay‑out kunt regelen door de `Rows`‑eigenschap in te stellen. Een configuratie met drie rijen is handig wanneer je een hogere barcode nodig hebt voor beperkte horizontale ruimte.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Why this matters:** Het aanpassen van rijen laat je de barcode in een smalle kolom passen terwijl de leesbaarheid behouden blijft. De barcode generator C# rekent automatisch de module‑grootte opnieuw uit om aan de specificatie te voldoen.

## Step 4: Full, runnable example

Hieronder staat een zelfstandig programma dat de vorige stappen combineert. Kopieer de code naar `Program.cs`, vervang `YOUR_DIRECTORY` door een bestaand map‑pad, en voer de applicatie uit.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Expected output

Wanneer je het programma uitvoert, verschijnen er twee PNG‑bestanden in de doelmap:

* **DatabarCols4.png** – een DataBar Expanded Stacked barcode met vier kolommen  
* **DatabarRows3.png** – dezelfde data gecodeerd in drie rijen  

Open de afbeeldingen met een willekeurige beeldviewer; ze tonen scherpe, scanbare barcodes die klaar zijn om afgedrukt of in PDF’s ingebed te worden.

## How to generate barcode image with custom dimensions

Als je een specifieke afbeeldingsgrootte nodig hebt, pas dan de `ImageHeight`‑ en `ImageWidth`‑eigenschappen aan vóór het aanroepen van `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Het wijzigen van de afmetingen beïnvloedt de gecodeerde data niet; het schaalt alleen de visuele weergave. Deze techniek is nuttig bij het integreren van barcodes in UI‑componenten met vaste lay‑out‑beperkingen.

## Common pitfalls and pro tips

* **Path separators:** Gebruik verbatim‑strings (`@"C:\Path\file.png"`) of `Path.Combine` om escape‑character problemen op Windows te vermijden.  
* **License enforcement:** Zonder een geldige licentie bevatten de gegenereerde afbeeldingen een watermerk. Pas je licentie vroeg in de applicatie toe:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Encoding limits:** DataBar Expanded Stacked ondersteunt tot 74 numerieke tekens. Het overschrijden van deze limiet veroorzaakt een uitzondering. Valideer de invoerlengte voordat je de generator maakt.  
* **Performance:** Het hergebruiken van één `BarcodeGenerator`‑instantie voor meerdere saves vermindert geheugenallocatie. Verander alleen de `Rows`‑ of `Columns`‑eigenschappen tussen saves als de te coderen tekst gelijk blijft.

## Next steps

Nu je barcode‑afbeeldingen kunt genereren met de barcode generator C#, kun je het volgende verkennen:

* **Different symbologies** – probeer `EncodeTypes.QR`, `EncodeTypes.Code128`, of `EncodeTypes.Pdf417`.  
* **Color customization** – stel `Parameters.Barcode.ForeColor` en `BackColor` in om bij je huisstijl te passen.  
* **Embedding in PDFs** – combineer de gegenereerde PNG met Aspose.PDF om afdrukbare documenten te maken.  

Deze uitbreidingen stellen je in staat een volledige barcode‑oplossing te bouwen voor voorraad, logistiek of detailhandel.

---


## What Should You Learn Next?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}