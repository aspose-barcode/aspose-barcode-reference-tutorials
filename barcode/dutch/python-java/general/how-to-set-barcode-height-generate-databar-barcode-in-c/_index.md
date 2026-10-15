---
category: general
date: 2026-10-12
description: Hoe de barcodehoogte in te stellen en een DataBar-barcode te genereren
  in C# met Aspose.BarCode. Volg een stapsgewijze handleiding met volledige code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: nl
lastmod: 2026-10-12
og_description: Hoe de barcodehoogte in C# in te stellen en een DataBar-barcode te
  genereren met Aspose.BarCode. Leer de volledige code, waarom elke stap belangrijk
  is, en hoe je de barcodehoogte kunt wijzigen.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Hoe de barcodehoogte in te stellen en een DataBar-barcode te genereren in
  C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe de barcodehoogte in te stellen en een DataBar‑barcode te genereren in C#
url: /nl/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de barcodehoogte in te stellen, DataBar barcode genereren in C#

Als je programmatically **how to set barcode** afmetingen moet instellen, laat deze gids je de exacte stappen zien. Je leert hoe je een DataBar Omni‑directional barcode genereert, de hoogte aanpast, en beide versies opslaat als PNG‑bestanden.

Het wijzigen van de balkhoogte van een barcode is een veelvoorkomende eis wanneer je barcodes integreert in kassabonnen, productetiketten of mobiele schermen. Het onderstaande voorbeeld maakt gebruik van de Aspose.BarCode‑bibliotheek, die het volledige scala aan GS1 DataBar‑symbologieën ondersteunt.

## Wat je zult bereiken

* **how to set barcode** hoogte voor een DataBar Omni‑directional barcode  
* **generate barcode c#** code die twee afbeeldingen maakt met verschillende hoogtes  
* begrijp **how to create databar** symbolen en waarom de balkhoogte belangrijk is  
* pas **change barcode height** logica toe zonder de generator opnieuw te maken  

Er zijn geen externe tools vereist, behalve het Aspose.BarCode NuGet‑pakket en een .NET 6+ runtime.

## Vereisten

* .NET 6 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑editor)  
* Aspose.BarCode voor .NET – installeer via `dotnet add package Aspose.BarCode`  

> **Pro tip:** Gebruik de gratis proeflicentie van Aspose als je geen commerciële sleutel hebt; de API werkt op dezelfde manier.

## Stap 1: Installeer het Aspose.BarCode‑pakket

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode` namespace toe, die de `BarcodeGenerator`‑klasse bevat die we zullen gebruiken om **generate barcode c#** afbeeldingen te maken.

## Stap 2: Maak een DataBar barcode‑generator

De eerste concrete actie voor **how to set barcode** parameters is het instantieren van `BarcodeGenerator` met de gewenste symbologie en dataketen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Waarom dit belangrijk is:* `EncodeTypes.DatabarOmniDirectional` produceert een compacte, omnidirectionele DataBar die vanuit elke hoek gescand kan worden — ideaal voor kleine etiketten.

## Stap 3: Stel algemene barcode‑parameters in (inclusief de initiële balkhoogte)

Nu beantwoorden we **how to set barcode** X‑dimensie en balkhoogte voordat we de eerste afbeelding opslaan.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

De X‑dimensie bepaalt de totale breedte van elke balk; een instelling van 2 pixels levert een leesbare, scherpe afbeelding op op de meeste schermen. De **change barcode height** stap later zal dezelfde generator hergebruiken, waardoor tijd en geheugen bespaard worden.

## Stap 4: Sla de eerste barcode‑afbeelding op (30‑pixel hoogte)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Het bestand `DatabarHeight30.png` bevat nu een DataBar barcode met een balkhoogte van 30 pixels.

## Stap 5: Verander alleen de balkhoogte naar 60 pixels

Om **change barcode height** te demonstreren, wijzigen we alleen de `BarHeight`‑eigenschap. Alle andere instellingen blijven ongewijzigd, wat de meest efficiënte manier is om meerdere groottes te produceren vanuit één generator.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Stap 6: Sla de tweede barcode‑afbeelding op (60‑pixel hoogte)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Je hebt nu twee PNG‑bestanden, elk met een verschillende balkhoogte maar identieke data en X‑dimensie.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren‑plakken in een nieuwe console‑applicatie (`dotnet new console`) en direct kunt uitvoeren.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Verwachte output

Het uitvoeren van het programma produceert twee bestanden in de werkmap van het uitvoerbare bestand:

* `DatabarHeight30.png` – een DataBar barcode met 30‑pixel hoge balken.  
* `DatabarHeight60.png` – dezelfde barcode, maar elke balk is twee keer zo hoog.

Beide afbeeldingen kunnen geopend worden in elke afbeeldingsviewer of direct ingebed worden in PDF’s, HTML‑pagina’s of afgedrukte etiketten.

## Waarom het aanpassen van de balkhoogte belangrijk is

* **Scanning reliability:** Sommige scanners hebben moeite met zeer korte balken op media met lage resolutie; het verhogen van de hoogte verbetert de detectie.  
* **Design constraints:** Een mobiele app heeft mogelijk een compacte barcode nodig (30 px) terwijl een afgedrukte kassabon een grotere kan vereisen (60 px).  
* **Regulatory compliance:** Bepaalde sectoren verplichten een minimale balkhoogte voor GS1 DataBar‑symbolen.  

Door dezelfde `BarcodeGenerator`‑instantie te hergebruiken, vermijd je de overhead van het opnieuw parseren van de dataketen, wat vooral voordelig is in omgevingen met hoge doorvoersnelheden.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanbevolen aanpassing |
|----------|-----------------------|
| Een andere X‑dimensie nodig | Wijzig `XDimension.Pixels` vóór de eerste `Save`. |
| Een andere symbologie wensen (bijv. DataBar Stacked) | Gebruik `EncodeTypes.DatabarStacked` bij het construeren van `BarcodeGenerator`. |
| De barcode moet in een PDF worden ingebed | Gebruik `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` en voeg de stream toe aan een PDF‑bibliotheek. |
| Uitvoeren op .NET Framework 4.6 | Dezelfde code werkt; verwijs gewoon naar de juiste Aspose.BarCode‑assembly. |

## Pro‑tips voor betrouwbare barcode‑generatie

* **Cache de generator** wanneer je veel barcodes genereert met dezelfde data maar verschillende groottes.  
* **

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcodehoogte te genereren en aan te passen voor één-dimensionale Databar met Aspose.BarCode voor .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hoe databar PNG‑afbeeldingen te maken met C# en Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hoe barcode met aangepaste grootte te genereren en afbeelding op te slaan in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}