---
category: general
date: 2026-08-15
description: Databar uitgebreide gestapelde barcodegeneratie in C#. Leer hoe je een
  barcode‑afbeelding genereert, kolommen en rijen instelt voor DataBar‑lay‑outs.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: nl
lastmod: 2026-08-15
og_description: Databar uitgebreide gestapelde barcodegeneratie in C#. Volg deze stap‑voor‑stap
  handleiding om barcode‑afbeeldingen te genereren, kolommen in te stellen en rijen
  efficiënt in te stellen.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – genereer barcode‑afbeelding in C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: barcode‑afbeelding genereren in C#'
url: /nl/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: barcodeafbeelding genereren in C#

Als je een **databar expanded stacked** barcode‑afbeelding in C# moet genereren, laat deze gids je precies zien **hoe je barcode**‑afbeeldingen maakt met aangepaste kolom‑ en rij‑indelingen. Je ziet hoe je kolommen instelt, hoe je rijen instelt en hoe je de resulterende afbeeldingen opslaat zonder de IDE te verlaten.

De tutorial behandelt:

* Het maken van een barcode‑generator voor de **databar expanded stacked** symbologie.  
* Het configureren van een 4‑koloms indeling en een 3‑rij indeling.  
* Het opslaan van elke configuratie als een PNG‑bestand.  
* Tips voor het omgaan met randgevallen zoals ongeldige kolomaantallen.

Er is geen externe documentatie nodig; het volledige, uitvoerbare voorbeeld is inbegrepen.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="databar expanded stacked barcode gegenereerd met C#" }

## Stappen voor het genereren van een databar expanded stacked barcode

### 1. Installeer de Aspose.BarCode‑bibliotheek

De code maakt gebruik van de **Aspose.BarCode for .NET**‑bibliotheek, die de `BarcodeGenerator`‑klasse levert. Installeer het NuGet‑pakket met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

Nadat het pakket is geïnstalleerd, voeg je de vereiste namespace toe aan de bovenkant van je bestand:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Maak een barcode‑generator voor **databar expanded stacked**

De generator is het startpunt voor alle barcode‑bewerkingen. Je moet de symbologie (`EncodeTypes.DatabarExpandedStacked`) en de te coderen tekst opgeven.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Waarom dit belangrijk is:* De `EncodeTypes`‑enum vertelt de bibliotheek welk barcode‑formaat moet worden geproduceerd. Het gebruik van **databar expanded stacked** zorgt ervoor dat de resulterende afbeelding voldoet aan de GS1 DataBar‑specificatie voor gestapelde indelingen.

### 3. Hoe kolommen instellen voor DataBar

De eigenschap `Columns` bepaalt hoeveel verticale modules er in de gestapelde barcode verschijnen. Geldige waarden zijn 2, 3 of 4. Het instellen van kolommen beïnvloedt de breedte van de barcode en de hoeveelheid data die kan worden opgeslagen.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** Als je een waarde buiten het toegestane bereik probeert toe te wijzen, gooit de bibliotheek een `ArgumentException`. Valideer altijd de invoer wanneer je kolomselectie aan gebruikers blootstelt.

### 4. Sla de 4‑koloms barcode‑afbeelding op

Het opslaan van de afbeelding produceert een bestand dat je kunt insluiten in rapporten, facturen of mobiele apps. De `Save`‑methode accepteert een bestandspad en een afbeeldingsformaat.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Wanneer het bestand is geschreven, kun je het met elke afbeeldingsviewer openen om te bevestigen dat het **databar expanded stacked**‑patroon correct wordt weergegeven.

### 5. Hoe rijen instellen voor DataBar

Rijen voegen een tweede dimensie toe aan de gestapelde indeling, waardoor meer data kan worden gecodeerd zonder de barcode breder te maken. De eigenschap `Rows` heeft standaard de waarde 1; je kunt deze verhogen tot maximaal 3 voor de expanded stacked‑variant.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Waarom rijen belangrijk zijn:** Het verhogen van het aantal rijen verkleint de totale breedte terwijl de gegevenscapaciteit behouden blijft, wat nuttig is voor smalle etiketten of beperkte schermruimte op mobiele apparaten.

### 6. Sla de 3‑rij barcode‑afbeelding op

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Je hebt nu twee PNG‑bestanden — één met een 4‑koloms indeling en één met een 3‑rij indeling — beide met de **databar expanded stacked**‑symbologie.

### 7. Volledig C#‑voorbeeld om een barcode‑afbeelding te genereren

Alle stappen samengevoegd leveren een zelfstandige applicatie die je kunt kopiëren naar een console‑applicatie:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Verwachte uitvoer**

Het uitvoeren van het programma geeft het volgende weer:

```
4‑column barcode saved.
3‑row barcode saved.
```

en maakt twee PNG‑bestanden aan in `YOUR_DIRECTORY`. Open de bestanden om te verifiëren dat elk een geldige **databar expanded stacked**‑barcode toont.

## Veelvoorkomende valkuilen en praktische tips

* **Bestandsmap bestaat** – `Save` maakt geen ontbrekende mappen aan. Zorg ervoor dat `YOUR_DIRECTORY` bestaat of gebruik `Directory.CreateDirectory` vóór het opslaan.
* **Kolomlimieten** – Waarden anders dan 2, 3 of 4 veroorzaken een uitzondering. Bescherm tegen gebruikersinvoerfouten met een eenvoudige bereikcontrole:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Rijlimieten** – De expanded stacked‑variant ondersteunt maximaal 3 rijen. Het instellen van `Rows` op 0 of een waarde groter dan 3 veroorzaakt eveneens een uitzondering.
* **Afbeeldingsformaat** – `BarCodeImageFormat.Png` levert verliesvrije kwaliteit, ideaal voor afdrukken. Gebruik `Jpeg` alleen wanneer bestandsgrootte een primaire zorg is.

## Volgende stappen

Nu je weet **hoe je barcode**‑afbeeldingen maakt met aangepaste kolom‑ en rij‑configuraties, kun je:

* De generator integreren in een web‑API om barcode‑afbeeldingen on‑demand te leveren.  
* De barcode combineren met PDF‑generatiebibliotheken om deze in facturen in te sluiten.  
* Experimenteren met andere DataBar‑varianten (`DatabarExpanded`, `DatabarLimited`) met hetzelfde `Parameters.Barcode.DataBar`‑object.

Voor diepere aanpassingen — zoals het wijzigen van de balkkleur, het toevoegen van mens‑leesbare tekst, of het toepassen van QR‑code‑overlays — raadpleeg de Aspose.BarCode‑documentatie over `BarcodeGenerator`‑eigenschappen.

---

Door deze gids te volgen heb je de **databar expanded stacked**‑workflow onder de knie, geleerd **hoe je kolommen instelt**, **hoe je rijen instelt**, en twee verschillende barcode‑afbeeldingen geproduceerd die klaar zijn voor productie. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}