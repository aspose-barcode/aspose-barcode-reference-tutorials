---
category: general
date: 2026-08-22
description: Hoe een barcode te genereren in C# met Aspose.BarCode. Leer stap voor
  stap een barcode‑afbeelding in C# te maken, de 2‑D‑component uit te schakelen en
  PNG‑bestanden op te slaan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: nl
lastmod: 2026-08-22
og_description: Hoe een barcode te genereren in C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je een barcode‑afbeelding maakt in C# met DataBar Expanded, de 2‑D‑component
  schakelt en PNG‑bestanden opslaat.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Hoe een barcode te genereren in C# – complete gids voor het maken van een
  barcode‑afbeelding in C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Hoe een barcode genereren in C# – barcode‑afbeelding maken in C# met DataBar
  Expanded
url: /nl/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcode te genereren in C# – barcode afbeelding c# maken met DataBar Expanded

Barcode genereren in C# is een veelvoorkomende vereiste wanneer je machine‑leesbare gegevens in je applicaties moet integreren. Deze gids laat zien hoe je een barcode afbeelding c# maakt met de Aspose.BarCode bibliotheek, het 2‑D composite‑component uitschakelt, en het resultaat opslaat als PNG‑bestanden.

Je ziet een compleet, uitvoerbaar programma, een uitleg van elke configuratie‑optie, en tips voor het aanpassen van de output. Geen externe documentatie is nodig—alleen de onderstaande code en een .NET‑ontwikkelomgeving.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een IDE die .NET ondersteunt)  
* Aspose.BarCode for .NET NuGet‑pakket (`Aspose.BarCode`)  

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

De bibliotheek levert de `BarcodeGenerator`‑klasse die door deze tutorial heen wordt gebruikt.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuwe console‑applicatie aan en importeer de benodigde namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

De `Aspose.BarCode.Generation` namespace bevat alle klassen die nodig zijn om barcodes te configureren en te renderen.

## Stap 2: De DataBar Expanded barcode‑generator initialiseren

De eerste functionele regel maakt een `BarcodeGenerator` voor de **DataBar Expanded**‑symbologie en levert de ruwe gegevensreeks. De gegevensreeks volgt het GS1 Application Identifier‑formaat `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Het aanmaken van de generator reserveert het interne bitmap‑canvas, zodat je grootte en uiterlijk kunt aanpassen vóór het renderen.

## Stap 3: Definieer de module‑breedte (X‑dimensie)

De X‑dimensie bepaalt de breedte van het kleinste barcode‑element. Het instellen in pixels geeft je precieze controle over de uiteindelijke afbeeldingsgrootte.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van `2` pixels werkt goed voor weergave op scherm; verhoog deze voor afdrukken met hogere resolutie.

## Stap 4: Het 2‑D composite‑component uitschakelen

DataBar Expanded kan optioneel een 2‑D component bevatten dat extra informatie draagt. Om een barcode **zonder** dit component te genereren, zet je de vlag op `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Het uitschakelen van het component vermindert de visuele complexiteit en levert een kleiner PNG‑bestand op.

## Stap 5: De barcode‑afbeelding opslaan zonder het 2‑D component

Kies een uitvoermap en schrijf de afbeelding naar schijf. De `BarCodeImageFormat.Png`‑enum zorgt voor een verliesvrij PNG‑bestand.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Na deze aanroep bevat `Databar2DComponentDisabled.png` een schone DataBar Expanded‑barcode.

## Stap 6: Het 2‑D composite‑component inschakelen

Als je de extra datalaag nodig hebt, schakel je de vlag opnieuw in. Dezelfde generator‑instantie kan hergebruikt worden, waardoor je een tweede object vermijdt.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Stap 7: De barcode‑afbeelding opslaan met het 2‑D component ingeschakeld

Render de tweede afbeelding met dezelfde instellingen, behalve de 2‑D vlag.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Nu toont `Databar2DComponentEnabled.png` de barcode met het extra 2‑D‑patroon.

## Volledige broncode

Kopieer de volledige code‑fragment hieronder naar `Program.cs` en voer het project uit. Het programma maakt beide PNG‑bestanden aan in de map die je opgeeft.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma geeft:

```
Barcode images generated successfully.
```

en maakt twee bestanden aan:

* `Databar2DComponentDisabled.png` – barcode zonder het 2‑D component  
* `Databar2DComponentEnabled.png` – barcode met het 2‑D component  

Open de PNG‑bestanden in een willekeurige afbeeldingsviewer om het visuele verschil te verifiëren.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing |
|-----------|------------|
| **Andere symbologie** | Vervang `EncodeTypes.DatabarExpanded` door een andere waarde, bijv. `EncodeTypes.Code128`. |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` naar 4 of 5, of stel `Resolution` in `barcodeGenerator.Parameters.Image` in. |
| **Andere afbeeldingsformaten** | Gebruik `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, of `BarCodeImageFormat.Svg`. |
| **Uitvoeren in een webapp** | Stream de afbeeldingsbytes direct naar de HTTP‑respons in plaats van op schijf op te slaan. |
| **Geheugenbeheer** | Plaats de generator in een `using`‑block als je .NET Framework target om onbeheerste resources vrij te geven. |

## Pro‑tips

* **Herbruik de generator** – Alleen de 2‑D vlag wijzigen voorkomt het opnieuw instantiëren van het object, wat CPU‑cycli bespaart.  
* **Valideer data** – GS1‑data moet voldoen aan de exacte lengte‑ en checksum‑regels; ongeldige invoer veroorzaakt een `ArgumentException`.  
* **Batchverwerking** – Loop over een collectie gegevensreeksen, schakel de 2‑D vlag naar behoefte, en sla elke afbeelding op met een unieke bestandsnaam.  

## Conclusie

Je weet nu hoe je een barcode in C# kunt genereren en een barcode afbeelding c# kunt maken met volledige controle over het 2‑D composite‑component. Het voorbeeld laat zien hoe je de generator initialiseert, de X‑dimensie configureert, het component schakelt, en PNG‑bestanden opslaat. Vanaf hier kun je andere symbologieën verkennen, de afbeeldingen in PDF’s embedden, of barcode‑generatie integreren in ASP.NET Core‑services.

--- 

*Volgende stappen*: probeer QR‑codes te genereren, experimenteer met verschillende afbeeldingsresoluties, of embed de gegenereerde PNG‑bestanden in een PDF met Aspose.PDF. Deze uitbreidingen bouwen voort op dezelfde `BarcodeGenerator`‑API en houden je workflow consistent.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hoe de barcode‑hoogte te genereren en aan te passen voor One‑Dimensional Databar met Aspose.BarCode voor .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}