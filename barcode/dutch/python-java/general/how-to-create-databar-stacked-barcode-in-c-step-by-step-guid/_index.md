---
category: general
date: 2026-10-21
description: Maak snel een gestapelde Databar‑streepjescode met C#. Leer hoe je de
  X‑dimensie instelt, de beeldverhouding aanpast en PNG‑afbeeldingen opslaat in deze
  volledige tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: nl
lastmod: 2026-10-21
og_description: maak een databar gestapelde barcode in C# met Aspose.BarCode. Volg
  deze gids om de X‑dimensie in te stellen, de beeldverhouding te wijzigen en PNG‑bestanden
  te exporteren.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Maak een gestapelde Databar-barcode in C# – volledige programmeergids
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Hoe maak je een gestapelde Databar‑barcode in C# – stapsgewijze handleiding
url: /nl/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een databar stacked barcode in C# te maken – stap‑voor‑stap gids

Als je een **databar stacked barcode** moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe. Je ziet hoe je de X‑dimensie configureert, de beeldverhouding aanpast en de barcode opslaat als PNG‑bestanden.

Het genereren van een DataBar stacked barcode vereist geen complexe build‑pipeline. Deze tutorial behandelt alles wat je nodig hebt: vereiste pakketten, stap‑voor‑stap code‑uitleg en tips voor veelvoorkomende valkuilen. Aan het einde kun je meerdere barcode‑afbeeldingen met verschillende beeldverhoudingen in één methode produceren.

## Wat je nodig hebt

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een IDE die C# ondersteunt)  
* **Aspose.BarCode for .NET** NuGet‑pakket – de bibliotheek die `BarcodeGenerator` en `EncodeTypes` levert  

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan of voeg de code toe aan een bestaand project. Importeer de vereiste namespaces zodat de compiler de barcode‑klassen herkent.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Deze `using`‑statements maken `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` beschikbaar die later in het voorbeeld worden gebruikt.

## Stap 2: De output‑map definiëren

Kies een map waarin de gegenereerde PNG‑bestanden worden weggeschreven. Het gebruik van een absoluut of relatief pad werkt op dezelfde manier; het voorbeeld gebruikt een relatieve map genaamd `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Het programmatisch aanmaken van de map voorkomt runtime‑fouten wanneer de directory ontbreekt.

## Stap 3: De **create databar stacked barcode** generator initialiseren

Maak een `BarcodeGenerator`‑instance aan met `EncodeTypes.DatabarStackedOmniDirectional`. De voorbeelddata `(01)12345678901231` volgt het GS1‑128‑formaat dat vereist is voor DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Het generator‑object bevat alle parameters die van invloed zijn op het visuele uiterlijk van de barcode.

## Stap 4: De X‑dimensie instellen (pixelbreedte van de kleinste balk)

De X‑dimensie bepaalt de totale grootte van de barcode zonder de gecodeerde data te wijzigen. Een waarde van `2` pixels levert een duidelijk, scanbaar beeld voor de meeste schermresoluties.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Pas deze waarde aan als je een grotere of kleinere barcode nodig hebt; houd de verhouding tussen breedte en hoogte consistent.

## Stap 5: De beeldverhouding configureren en de eerste afbeelding opslaan

De beeldverhouding bepaalt de hoogte‑tot‑breedte‑relatie van een DataBar stacked barcode. Een beeldverhouding van `15` is een veelvoorkomende standaard die een compact beeld oplevert.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft een PNG‑bestand naar de eerder gedefinieerde map. De bestandsnaam geeft duidelijk de gebruikte beeldverhouding weer.

### Verwachte output voor beeldverhouding 15

De gegenereerde `DatabarAspectRatio15.png` ziet er vergelijkbaar uit met de illustratie hieronder.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Alt‑tekst:* `create databar stacked barcode image saved with aspect ratio 15`

## Stap 6: De beeldverhouding wijzigen en een tweede afbeelding opslaan

Je kunt dezelfde `BarcodeGenerator`‑instance hergebruiken om variaties te produceren. Het wijzigen van `AspectRatio` naar `30` verdubbelt de hoogte van elke balkstapel, wat nodig kan zijn voor hoge‑resolutie‑afdrukken.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Verwachte output voor beeldverhouding 30

De afbeelding `DatabarAspectRatio30.png` is hoger, behoudt dezelfde breedte en verhoogt de leesbaarheid voor scanners op afstand.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Alt‑tekst:* `create databar stacked barcode image saved with aspect ratio 30`

## Volledige broncode

Alle stappen samenvoegen resulteert in een zelfstandige applicatie die je direct kunt uitvoeren.

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
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Compileer en voer het programma uit. Na uitvoering bevat de `Barcodes`‑directory twee PNG‑bestanden, elk een **create databar stacked barcode** met een andere beeldverhouding.

## Pro‑tips en veelvoorkomende valkuilen

* **Pro tip:** Houd de X‑dimensie tussen 1 px en 4 px voor de meeste scherm‑gebaseerde toepassingen. Grotere waarden vergroten de bestandsgrootte zonder de scanbetrouwbaarheid te verbeteren.
* **Pitfall:** Het wijzigen van de `EncodeTypes`‑waarde nadat de generator is aangemaakt, werkt de interne codering niet bij. Specificeer altijd de juiste `EncodeTypes` in de constructor.
* **Pro tip:** Wanneer je meer dan twee beeldverhoudingen nodig hebt, loop dan over een array van gehele getallen en roep `Save` aan binnen de lus. Dit vermindert code‑duplicatie.
* **Pitfall:** Opslaan naar een pad zonder schrijfrechten veroorzaakt een `UnauthorizedAccessException`. Zorg ervoor dat de applicatie draait met de juiste bestandsysteem‑rechten.

## Conclusie

Je weet nu hoe je een **create databar stacked barcode** in C# kunt maken met Aspose.BarCode. De gids behandelde het opzetten van de omgeving, het configureren van de X‑dimensie, het aanpassen van de beeldverhouding en het opslaan van PNG‑bestanden. Met deze basis kun je extra variaties genereren, barcode‑creatie integreren in web‑API’s, of de afbeeldingen in PDF‑rapporten insluiten.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals best practices voor het scannen van **DataBar Stacked Omnidirectional**, het insluiten van barcodes in **ASP.NET Core**‑responses, of het genereren van **QR‑codes** met dezelfde bibliotheek. Experimenteer met verschillende `EncodeTypes` en beeldformaten om aan de behoeften van je applicatie te voldoen.

Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe databar PNG‑afbeeldingen te maken met C# en Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hoe kolommen in te stellen voor een Databar Expanded Stacked barcode – volledige C#‑gids](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode in C# – volledige gids](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}