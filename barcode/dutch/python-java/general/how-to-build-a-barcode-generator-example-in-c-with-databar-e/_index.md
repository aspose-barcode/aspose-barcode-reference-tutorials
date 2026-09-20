---
category: general
date: 2026-09-19
description: barcodegenerator‑voorbeeld in C# dat laat zien hoe je een barcode genereert
  in C# met Aspose.BarCode voor kolom‑ en rij‑indelingen
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: nl
lastmod: 2026-09-19
og_description: Barcode‑generatorvoorbeeld toont hoe je een barcode in C# kunt genereren
  met kolom‑ en rij‑indelingen met behulp van Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: barcodegenerator-voorbeeld – maak DataBar Expanded Stacked‑barcodes in C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcodegenerator-voorbeeld te bouwen in C# met DataBar Expanded Stacked
url: /nl/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator voorbeeld – maak DataBar Expanded Stacked barcodes in C#

Als je een **barcode generator example** nodig hebt die werkt in een .NET‑project, laat deze gids je precies zien hoe je barcode C# genereert met behulp van de Aspose.BarCode‑bibliotheek. Je ziet hoe je een DataBar Expanded Stacked‑barcode configureert voor zowel een kolom‑gebaseerde lay‑out als een rij‑gebaseerde lay‑out, en je krijgt kant‑klaar‑code die PNG‑afbeeldingen produceert.

De tutorial behandelt alles, van het installeren van het NuGet‑pakket tot het opslaan van de uiteindelijke afbeeldingen, zodat je de code kunt kopiëren naar je eigen oplossing zonder extra onderzoek.

## Wat je zult leren

* Hoe je Aspose.BarCode installeert en referentieert in een C#‑project.  
* Hoe je een **barcode generator example** maakt die een lange data‑string codeert.  
* Hoe je een 4‑kolom lay‑out en een 3‑rij lay‑out instelt voor hetzelfde barcode‑type.  
* Hoe je de gegenereerde afbeeldingen opslaat als PNG‑bestanden.  

Aan het einde van dit artikel heb je twee kant‑klaar PNG‑bestanden: `ExpandedStackedCols4.png` (vier kolommen) en `ExpandedStackedRows3.png` (drie rijen).

## Vereisten

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code, of elke C#‑IDE die je verkiest.  
* Internettoegang om het **Aspose.BarCode** NuGet‑pakket te downloaden.  

Er zijn geen extra externe services vereist.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van Aspose.BarCode toe aan je projectbestand. Nadat het pakket is hersteld, kun je de namespaces ervan refereren in je C#‑bronbestanden.

## Stap 2: Voeg de benodigde using‑directieven toe

Maak een nieuwe C#‑console‑applicatie (of voeg de code toe aan een bestaand project) en voeg de volgende `using`‑statements toe aan de bovenkant van het bestand:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Deze directieven geven je toegang tot de `BarcodeGenerator`‑klasse en de `EncodeTypes`‑enumeratie die worden gebruikt in het **barcode generator example**.

## Stap 3: Maak een barcode generator voorbeeld met een 4‑kolom lay‑out

Het eerste deel van het voorbeeld bouwt een DataBar Expanded Stacked‑barcode die een vier‑kolom indeling gebruikt. De onderstaande code volgt exact de stappen uit het oorspronkelijke fragment, maar voegt commentaren toe die uitleggen waarom elke regel nodig is.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Waarom dit werkt**

* `EncodeTypes.DatabarExpandedStacked` vertelt Aspose.BarCode om een DataBar Expanded Stacked‑symbool te genereren, wat geschikt is voor retail‑toepassingen.  
* Het instellen van `DataBar.Columns` op `4` dwingt de generator om het symbool in vier verticale secties te splitsen, waardoor de leesbaarheid op smalle etiketten verbetert.  
* `Save` schrijft de barcode naar schijf; het argument `BarCodeImageFormat.Png` zorgt voor verliesvrije beeldkwaliteit.  

Het uitvoeren van dit blok maakt `ExpandedStackedCols4.png` aan in de werkmap van de applicatie. Het bestand bevat een hoge‑resolutie barcode die door elke standaard DataBar‑lezer kan worden gescand.

## Stap 4: Herinitialiseer de generator voor een andere lay‑out

Om een rij‑gebaseerde lay‑out te demonstreren, heb je een nieuwe `BarcodeGenerator`‑instantie nodig. Herinitialiseren garandeert dat de vorige kolominstelling de nieuwe configuratie niet beïnvloedt.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Stap 5: Configureer de barcode om een 3‑rij lay‑out te gebruiken

De DataBar‑API ondersteunt ook een rij‑indeling. Het instellen van de `Rows`‑eigenschap bepaalt hoeveel horizontale segmenten het symbool zal bevatten.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Waarom je rijen boven kolommen zou kunnen kiezen**

Rijen zijn nuttig wanneer de hoogte van het label beperkt is maar de breedte ruim is. Een drie‑rij lay‑out comprimeert de barcode verticaal terwijl de vereiste hoeveelheid data behouden blijft.

## Volledig bronbestand

Hieronder vind je een volledig, zelfstandig `Program.cs`‑bestand dat je direct kunt compileren en uitvoeren. Het bevat zowel de kolom‑ als de rij‑voorbeelden, zodat je met één uitvoering twee PNG‑bestanden krijgt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Verwachte output

Na het uitvoeren van het programma zie je twee console‑berichten die de bestandscreatie bevestigen:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Beide PNG‑bestanden tonen een DataBar Expanded Stacked‑barcode die de string `"Long data string"` codeert. Het scannen van een van beide afbeeldingen met een standaard barcode‑scanner geeft de oorspronkelijke data terug.

## Veelgestelde vragen en randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik het afbeeldingsformaat wijzigen?** | Ja. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Tiff` afhankelijk van je vereisten. |
| **Wat als de data‑string korter is?** | Het DataBar‑formaat past automatisch de symboolgrootte aan; je hoeft de lay‑outinstellingen niet te wijzigen. |
| **Hoe stel ik de barcode‑grootte (breedte/hoogte) in?** | Gebruik `generator.Parameters.Image.Width` en `generator.Parameters.Image.Height` vóór het aanroepen van `Save`. |
| **Is het mogelijk een mens‑leesbare bijschrift toe te voegen?** | Stel `generator.Parameters.Barcode.CodeText` in en schakel `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above` in. |
| **Welke .NET‑versies worden ondersteund?** | Aspose.BarCode ondersteunt .NET Standard 2.0, .NET 5/6, en .NET Framework 4.6.1+. |

Het behandelen van deze variaties maakt het **barcode generator example** robuust genoeg voor productiegebruik.

## Pro‑tips

* **Herbruik het generator‑object alleen wanneer de lay‑out gelijk blijft.** Een nieuwe instantie maken voor elke lay‑out, zoals getoond in Stappen 4‑5, voorkomt onbedoelde eigenschaps‑overdracht.  
* **Valideer de gegenereerde barcode** met `generator.Validate()` als je moet verzekeren dat deze voldoet aan ISO/GS1‑normen.  
* **Batchverwerking:** Plaats de kolom‑ en rij‑logica in een lus die over een lijst van lay‑outconfiguraties iterereert. Dit vermindert code‑duplicatie wanneer je veel variaties nodig hebt.

## Conclusie

Dit **barcode generator example** toont hoe je **generate barcode C#** code maakt die zowel een 4‑kolom als een 3‑rij DataBar Expanded Stacked‑barcode produceert. Je hebt nu een volledig, uitvoerbaar programma, inzicht in de belangrijkste eigenschappen (`Columns`, `Rows`), en praktische tips om de oplossing uit te breiden.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **customizing barcode colors**, **embedding barcodes in PDF documents**, of **generating QR codes with Aspose.BarCode**. Elk van deze onderwerpen bouwt voort op dezelfde API‑principes die hier behandeld zijn.

Voel je vrij om te experimenteren met verschillende data‑strings, afbeeldingsformaten en lay‑outcombinaties. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode Generator Voorbeeld in C# – Stel Kolommen, Rijen in & Exporteer Afbeelding](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Genereer Aspose.BarCode Databar barcode met .NET API – Rij‑ en Kolomconfiguratie](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator voorbeeld in C# – stel breedte en hoogte in](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}