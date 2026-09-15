---
category: general
date: 2026-07-18
description: Leer hoe u barcode‑afbeeldingen kunt genereren met een .net barcode‑generator
  en eenvoudig de barcodehoogte kunt aanpassen voor GS1‑Databar Omni‑Directional‑symbolen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: nl
lastmod: 2026-07-18
og_description: .net barcode generator laat je snel barcode‑afbeeldingen maken. Deze
  gids laat zien hoe je een barcode genereert, de balkhoogte aanpast en PNG‑bestanden
  opslaat.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Pas de barcodehoogte aan met .net barcodegenerator
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET barcodegenerator – barcodehoogte wijzigen
url: /nl/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – barcodehoogte wijzigen

Heb je je ooit afgevraagd **hoe je barcode** afbeeldingen kunt genereren zonder een tiental externe tools te jongleren? In de .NET-wereld is er een verrassend eenvoudige manier om dit te doen, en het belangrijkste onderdeel is de **.net barcode generator**. Met slechts een paar regels C# kun je een GS1‑Databar Omni‑Directional symbool maken, de balkhoogte aanpassen en het resultaat opslaan als een PNG‑bestand.

Als je een voorraadbeheersysteem, een verzendetikettenprinter of een andere app bouwt die een scanbare code nodig heeft, brengt deze tutorial je in enkele minuten van nul naar een werkende barcode. We lopen de volledige code stap voor stap door, leggen uit waarom elke instelling belangrijk is, en laten zien hoe je de **barcodehoogte wijzigt** zonder de specificatie te breken.

## Wat je nodig hebt

- .NET 6.0 of later (the API works the same on .NET Framework 4.7+)
- Een referentie naar de barcode‑bibliotheek (bijvoorbeeld, Aspose.BarCode for .NET – dezelfde klassen worden gebruikt door veel commerciële kits)
- Een ontwikkelomgeving (Visual Studio, Rider, of VS Code met de C#‑extensie)
- Een map waarin je schrijfrechten hebt – de tutorial slaat daar PNG‑bestanden op

Dat is alles. Geen extra NuGet‑pakketten naast de barcode‑bibliotheek zelf.

## De .net barcode generator gebruiken om de barcodehoogte te wijzigen

Hieronder staat een **volledig, uitvoerbaar console‑programma**. Plak het in een nieuw C#‑project, pas de uitvoermap aan, en druk op F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Waarom elke regel belangrijk is

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instantieert de **.net barcode generator** met de gewenste symbologie en gegevenspayload. De `EncodeTypes.DatabarOmniDirectional`‑enum geeft de bibliotheek aan om het GS1‑Databar Omni‑Directional‑formaat te gebruiken. |
| `XDimension.Pixels = 2;` | De X‑dimensie is de breedte van de dunste balk. Instellen op *2 pixels* levert een scherp beeld op de meeste monitoren en houdt de bestandsgrootte klein. |
| `BarHeight.Pixels = 30;` | Dit is de **barcodehoogte wijzigen** stap die bepaalt hoe hoog elke balk wordt. Een hoogte van 30 pixels is een goede standaard voor kleine etiketten. |
| `generator.Save(...);` | Slaat de barcode op als een PNG‑bestand. PNG is verliesvrij, wat betekent dat scanners het exacte patroon zien dat je hebt gegenereerd. |
| `BarHeight.Pixels = 60;` | Hier **wijzigen we de barcodehoogte** opnieuw—dit keer naar 60 pixels. De bibliotheek rendert het symbool automatisch opnieuw met de nieuwe afmeting wanneer je `Save` een tweede keer aanroept. |
| `Console.WriteLine(...);` | Geeft je snelle feedback dat het proces is voltooid zonder een uitzondering te werpen. |

> **Pro tip:** Als je een hogere resolutie‑output nodig hebt voor afdrukken, schakel `BarCodeImageFormat.Png` over naar `BarCodeImageFormat.Tiff` en verhoog de `Resolution`‑eigenschap (bijv. `generator.Parameters.ImageResolution = 300;`). De balkhoogte blijft gerespecteerd, alleen gerenderd met een fijnere DPI.

## Hoe barcode‑afbeeldingen te genereren met verschillende instellingen

De bovenstaande code behandelt de basis, maar real‑world scenario's vereisen vaak extra aanpassingen:

### X‑dimensie aanpassen voor grotere afdrukken
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Het verhogen van de X‑dimensie maakt de hele barcode groter zonder de gecodeerde data te wijzigen. Dit is handig bij het afdrukken op grote etiketten.

### Uitvoerformaten wisselen
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG schaalt oneindig, wat perfect is voor web‑gebaseerde scanners die scherpe vectoren nodig hebben.

### Menselijk leesbare tekst toevoegen
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Het inschakelen van `CodeTextVisible` voegt de ruwe data onder de barcode toe, handig voor verificatie tijdens het testen.

## Veelvoorkomende valkuilen wanneer je **barcodehoogte wijzigt**

1. **Hoogte te klein** – Sommige scanners vereisen een minimale balkhoogte (vaak 10 mm in fysieke eenheden). Als je `BarHeight.Pixels` te laag instelt, kan de gegenereerde afbeelding onleesbaar zijn voor een echte scanner. Test altijd met je doelhardware.
2. **Niet‑overeenkomende X‑dimensie en hoogte** – Een enorme balkhoogte gecombineerd met een kleine X‑dimensie kan er uitgerekt uitzien en kan decodeerfouten veroorzaken. Streef naar een gebalanceerde verhouding (ongeveer 3:1 tot 5:1) tenzij de specificatie iets anders aangeeft.
3. **Vergeten parameters te resetten** – De generator behoudt de staat tussen opslagen. Als je `BarHeight` voor één afbeelding wijzigt en vervolgens dezelfde instantie opnieuw gebruikt voor een andere barcode, blijft de vorige hoogte behouden. Reset de eigenschap of maak een nieuwe `BarcodeGenerator` aan voor elke afzonderlijke barcode.

## Volledig end‑to‑end voorbeeld (inclusief NuGet‑installatie)

Als je vanaf nul begint, volg dan deze stappen om het project werkend te krijgen:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Vervang de automatisch gegenereerde `Program.cs` door het eerder getoonde code‑blok, **vergeet niet `YOUR_DIRECTORY`** te vervangen door iets als `Path.Combine(Environment.CurrentDirectory, "output")`. Vervolgens:

```bash
dotnet run
```

Je zou twee PNG‑bestanden in de `output`‑map moeten zien:

- `DatabarBarHeight30Pixels.png` – een compacte barcode van 30 pixels hoog.
- `DatabarBarHeight60Pixels.png` – een hogere versie van 60 pixels.

Beide afbeeldingen zien er vergelijkbaar uit, maar de tweede heeft merkbaar langere balken, waardoor het makkelijker is voor scanners met lage resolutie om te lezen.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output die verschillende balkhoogtes toont"}

## Samenvatting & volgende stappen

We hebben behandeld hoe je **barcode** afbeeldingen kunt **genereren** met een **.net barcode generator**, de **barcodehoogte wijzigen** eigenschap fijn afgesteld, en de resultaten opgeslagen in PNG‑formaat. De belangrijkste punten zijn:

- Instantieer de generator met de juiste `EncodeTypes`.
- Regel de visuele grootte via `XDimension` en `BarHeight`.
- Roep `Save` aan na elke wijziging om een nieuwe afbeelding op te slaan.
- Pas resolutie, formaat, ...

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een Aztec barcode te genereren met aangepaste aspectratio met Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hoe een dotcode met uitgebreide codetext te maken met Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Hoe DataMatrix barcodes (ECC 200) te genereren met Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}