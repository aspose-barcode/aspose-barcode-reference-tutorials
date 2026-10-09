---
category: general
date: 2026-09-26
description: Leer hoe je een barcode maakt in C# met Aspose.BarCode. Deze stapsgewijze
  gids bevat een voorbeeld van een barcodegenerator en laat zien hoe je de balkhoogte
  kunt aanpassen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: nl
lastmod: 2026-09-26
og_description: Maak een barcode in C# met Aspose.BarCode. Volg deze gids om een barcode
  te genereren, de balkhoogte aan te passen en PNG-afbeeldingen op te slaan.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Barcode maken in C# met Aspose.BarCode – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hoe maak je een barcode in C# met Aspose.BarCode
url: /nl/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te maken in C# met Aspose.BarCode  

Als je snel **barcode c#**‑projecten wilt **maken**, biedt Aspose.BarCode een vloeiende API die het zware werk afhandelt. In deze tutorial zie je een compleet **barcode‑generatorvoorbeeld**, leer je **hoe je de balkhoogte aanpast**, en exporteer je het resultaat als PNG‑bestanden.  

Of je nu een kassasysteem voor de detailhandel bouwt, voorraadlabels genereert, of verzendetiketten automatiseert, de mogelijkheid om de visuele grootte van een barcode programmatisch te wijzigen is essentieel. Deze gids gaat uit van een basiskennis van C# en een ontwikkelomgeving zoals Visual Studio 2022.  

## Vereisten  

Zorg ervoor dat je het volgende hebt:  

* .NET 6.0 SDK of later geïnstalleerd.  
* Visual Studio 2022 (of een andere C#‑IDE).  
* Een actieve Aspose.BarCode‑licentie (de gratis proefversie volstaat voor leren).  

Je moet ook het Aspose.BarCode NuGet‑pakket aan je project toevoegen:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Als je van plan bent om veel barcodes in een lus te genereren, hergebruik dan één `BarcodeGenerator`‑instantie en wijzig alleen de parameters die veranderen. Dit vermindert geheugenallocaties en verbetert de prestaties.

## Hoe een barcode te maken in C# met Aspose.BarCode  

De volgende secties lopen stap voor stap door het **barcode‑generatorvoorbeeld**. De code staat op zichzelf; kopieer deze naar een nieuw console‑applicatieproject en voer het uit.

### Stap 1: Vereiste namespaces importeren  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Deze namespaces geven je toegang tot de `BarcodeGenerator`‑klasse en de `EncodeTypes`‑enumeratie.

### Stap 2: De barcode‑generator initialiseren  

We gaan een **Databar Omni‑Directional**‑symbool genereren dat een GTIN‑14‑waarde codeert. De constructor neemt de symbologie en de ruwe gegevensreeks.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

De waarde `EncodeTypes.DatabarOmniDirectional` vertelt Aspose.BarCode welke barcode‑standaard gebruikt moet worden. De gegevensreeks volgt het GS1 Application Identifier‑formaat, dat veel voorkomt bij retail‑barcodes.

### Stap 3: Algemene barcode‑parameters instellen  

Twee visuele parameters worden het vaakst aangepast: de X‑dimensie (de smalle balkbreedte) en de totale balkhoogte.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

De **X‑dimensie** bepaalt de dichtheid van de barcode, terwijl **BarHeight** de verticale grootte van elke balk bepaalt. Het aanpassen van **BarHeight** is precies wat je nodig hebt wanneer je de **barcode‑hoogte wilt wijzigen** voor verschillende afdrukmedia.

### Stap 4: De eerste afbeelding opslaan (30‑pixel hoogte)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft de gerenderde afbeelding naar schijf. De bestandsnaam geeft duidelijk de gebruikte hoogte aan, wat helpt bij het vergelijken van verschillende uitvoer.

### Stap 5: De balkhoogte wijzigen naar 60 pixels  

Nu laten we zien **hoe je de balkhoogte aanpast** tijdens runtime. Dezelfde `generator`‑instantie wordt hergebruikt; alleen de eigenschap `BarHeight` wordt gewijzigd.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Omdat de generator alle andere instellingen behoudt (symbologie, gegevens, X‑dimensie), is het enige visuele verschil tussen de twee PNG‑bestanden de verticale grootte van de balken.

### Volledige broncode  

Alles bij elkaar gebracht levert een beknopt, uitvoerbaar programma op:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Verwachte output**  

Het uitvoeren van het programma maakt twee PNG‑bestanden aan in de werkmap van de executable:

* `DatabarBarHeight30Pixels.png` – een barcode met een balkhoogte van 30 px.  
* `DatabarBarHeight60Pixels.png` – dezelfde barcode, maar elke balk is twee keer zo hoog.

Open de afbeeldingen in een viewer; je zult zien dat het algemene patroon identiek blijft terwijl de verticale dimensie verandert, wat bevestigt dat de **change barcode height**‑operatie geslaagd is.

## Geavanceerde variaties  

### Overschakelen naar een andere symbologie  

Als je een QR‑code in plaats van een Databar nodig hebt, vervang je de `EncodeTypes`‑waarde:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Alle andere parameterinstellingen (X‑dimensie, BarHeight) blijven van toepassing waar ze zinvol zijn.

### `BarHeight` in millimeters gebruiken  

Aspose.BarCode ondersteunt ook fysieke eenheden. Om een hoogte van 10 mm in te stellen:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Handig wanneer je barcodes genereert voor afdruklay-outs die exacte afmetingen vereisen.

### Fouten afhandelen  

Als de gegevensreeks niet voldoet aan de geselecteerde symbologie, gooit `BarcodeGenerator` een `ArgumentException`. Plaats de generatie‑logica in een try‑catch‑blok om een vriendelijke melding te geven:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Veelgestelde vragen beantwoord  

* **Heeft het wijzigen van BarHeight invloed op de scanbaarheid?**  
  De barcode blijft scanbaar zolang de X‑dimensie en de totale stille zone voldoen aan de specificaties van de symbologie. Het verhogen van de hoogte maakt de balken alleen langer; het vermindert nooit het contrast.

* **Kan ik verschillende hoogtes voor individuele balken instellen?**  
  Nee. De eigenschap `BarHeight` wordt uniform toegepast op het gehele symbool. Voor ontwerpen met variabele balkhoogtes zou je een aangepaste renderingsroutine buiten de scope van Aspose.BarCode moeten gebruiken.

* **Is PNG het beste formaat voor afdrukken?**  
  PNG behoudt verliesvrije pixeldata, waardoor het ideaal is voor weergave op schermen. Voor hoge‑resolutie‑printopdrachten kun je beter `BarCodeImageFormat.Tiff` of `Pdf` gebruiken om vectorinformatie te behouden.

## Conclusie  

Je weet nu hoe je **barcode c#**‑toepassingen maakt met Aspose.BarCode, een compleet **barcode‑generatorvoorbeeld** ziet, en begrijpt **hoe je de balkhoogte aanpast** om aan verschillende lay‑outvereisten te voldoen. Door dezelfde generator‑instantie te hergebruiken en alleen `BarHeight` te wijzigen, kun je efficiënt **barcode height wijzigen** zonder het hele object opnieuw op te bouwen.

Vanaf hier kun je verder verkennen:

* Andere symbologieën genereren (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exporteren naar SVG of PDF voor schaalbare graphics.  
* Barcodes direct in Word‑ of Excel‑documenten insluiten met Aspose.Words of Aspose.Cells.

Veel programmeerplezier, en geniet van de flexibiliteit die Aspose.BarCode biedt voor je C#‑barcodeprojecten!


## Wat moet je hierna leren?  


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑aanpakken in je eigen projecten te verkennen.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}