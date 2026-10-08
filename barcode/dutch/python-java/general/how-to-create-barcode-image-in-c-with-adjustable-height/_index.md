---
category: general
date: 2026-09-07
description: Leer hoe je een barcode‑afbeelding maakt in C# en de hoogte, breedte
  en het formaat aanpast om snel barcode‑PNG‑bestanden te genereren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: nl
lastmod: 2026-09-07
og_description: Maak een barcode‑afbeelding in C# en leer hoe je de barcode‑afmetingen
  instelt, de barcode‑hoogte wijzigt en barcode‑PNG‑bestanden genereert voor elke
  toepassing.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Barcode‑afbeelding maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Hoe maak je een barcode‑afbeelding in C# met verstelbare hoogte
url: /nl/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding te maken in C# met verstelbare hoogte

Als je een barcode‑afbeelding in C# moet maken voor een point‑of‑sale‑systeem of een voorraadtracker, laat deze gids je de volledige workflow zien. Je ziet hoe je barcode‑parameters instelt, de barcode‑hoogte wijzigt en barcode‑PNG‑bestanden genereert die aan visuele eisen voldoen.

Het genereren van een barcode‑afbeelding is een veelvoorkomende taak bij het integreren van scan‑hardware, het afdrukken van etiketten of het bouwen van rapportage‑dashboards. Aan het einde van deze tutorial heb je een herbruikbare code‑snippet die je in staat stelt de X‑dimensie, hoogte en uitvoerformaat van de barcode aan te passen zonder je IDE te verlaten.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 (of later) geïnstalleerd – de code compileert met elke recente .NET SDK.
* Een referentie naar de **Aspose.BarCode**‑bibliotheek (beschikbaar via NuGet `Aspose.BarCode`).
* Basiskennis van C#‑console‑applicaties.

Deze vereisten zorgen ervoor dat het voorbeeld direct werkt op Windows, Linux of macOS.

## Stap 1: Het project opzetten en de bibliotheek importeren

Maak een nieuw console‑project aan en voeg het barcode‑pakket toe:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Open nu *Program.cs* en voeg de benodigde `using`‑directives toe:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Deze imports geven je toegang tot `BarcodeGenerator`, `EncodeTypes` en de image‑format‑enums die nodig zijn om **barcode‑afbeeldingen te maken**.

## Stap 2: De generator initialiseren met de gewenste symbologie

De eerste regel code maakt een `BarcodeGenerator` aan die weet welk barcode‑type moet worden gecodeerd. In dit voorbeeld gebruiken we de DataBar Omni‑Directional‑symbologie, maar je kunt `EncodeTypes.DatabarOmniDirectional` vervangen door elk ander type dat door Aspose.BarCode wordt ondersteund.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

De string `"(01)12345678901231"` volgt het GS1 Application Identifier‑formaat, dat veel retailers eisen. Het initialiseren van de generator is de basis voor elke **hoe barcode in te stellen**‑bewerking die volgt.

## Stap 3: Hoe barcode‑dimensies in te stellen – X‑dimensie en hoogte

### 3.1 De smalle balkbreedte aanpassen (X‑dimensie)

De X‑dimensie bepaalt de dikte van de smalste balk. Een waarde van **2 pixels** geeft een fijner uiterlijk, handig wanneer je een compact label nodig hebt.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 De barcode‑hoogte wijzigen voor visueel evenwicht

De balkhoogte bepaalt hoe hoog de barcode verschijnt. Hieronder tonen we twee veelvoorkomende hoogtes — 30 pixels voor een klein label en 60 pixels voor een groter visueel. Dit demonstreert **hoe barcode‑hoogte** programmatisch aan te passen.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Stap 4: Barcode‑PNG‑bestanden genereren met verschillende hoogtes

### 4.1 Het eerste beeld opslaan (30 px hoogte)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 De hoogte verhogen en een tweede beeld opslaan

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Deze twee `Save`‑aanroepen illustreren **barcode‑PNG genereren** met verschillende afmetingen terwijl dezelfde generator‑instantie wordt hergebruikt. Het afbeeldingsformaat wordt expliciet op PNG gezet, wat verliesvrije kwaliteit behoudt — ideaal voor afdrukken of weergave op scherm.

## Stap 5: Volledig, uitvoerbaar voorbeeld

Alles samenvoegen levert een enkele `Main`‑methode op die je kunt kopiëren naar elk C#‑console‑project:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Het uitvoeren van dit programma produceert twee PNG‑bestanden in de output‑map van het project:

* `DatabarBarHeight30Pixels.png` – een compacte barcode van 30 px.
* `DatabarBarHeight60Pixels.png` – een grotere barcode van 60 px.

Beide bestanden bevatten een **barcode‑afbeelding maken** die in HTML kan worden ingebed, op etiketten kan worden afgedrukt of naar een mobiele app kan worden gestuurd voor scanning.

## Veelgestelde vragen en edge‑case handling

| Vraag | Antwoord |
|----------|--------|
| **Wat als ik een ander afbeeldingsformaat nodig heb?** | Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`, `Bmp` of `Gif`. De bibliotheek handelt de conversie automatisch af. |
| **Kan ik de voor‑/achtergrondkleuren wijzigen?** | Ja. Gebruik `generator.Parameters.Barcode.ForeColor` en `BackColor` om `System.Drawing.Color`‑waarden in te stellen vóór het aanroepen van `Save`. |
| **Hoe een barcode genereren zonder een bestand op schijf?** | Roep `generator.GenerateBarCodeImage()` aan om een `System.Drawing.Image`‑object te verkrijgen, en stream dit direct naar een response of database. |
| **Wat als de data‑string de limiet van de symbologie overschrijdt?** | De generator gooit een `ArgumentException`. Valideer de invoerlengte of trunkeer volgens de specificatie van de symbologie. |
| **Is er een manier om meerdere barcodes in batch te verwerken?** | Plaats de stappen in een `foreach`‑lus die `generator.CodeText` en `BarHeight` voor elk item bijwerkt, en roep vervolgens `Save` aan met een unieke bestandsnaam. |

Het behandelen van deze scenario's maakt de tutorial **hoe barcode‑hoogte aan te passen** robuust voor real‑world projecten.

## Pro‑tips voor betrouwbare barcode‑generatie

* **Cache de generator** wanneer je veel barcodes van hetzelfde type maakt; het hergebruiken van het object vermindert allocatie‑overhead.
* **Stel `Resolution` in** (`generator.Parameters.ImageResolution.Dpi`) als je PNG‑bestanden met hoge resolutie nodig hebt voor afdrukken.
* **Valideer GS1‑data** voordat je deze toewijst aan `CodeText` om coderingsfouten te voorkomen die scan‑fouten kunnen veroorzaken.
* **Test op echte scanners** na het wijzigen van hoogte of X‑dimensie — sommige oudere apparaten hebben minimale afmetingen nodig.

## Conclusie

Je weet nu hoe je **barcode‑afbeelding maakt** in C#, **hoe je barcode‑dimensies instelt**, **hoe je barcode‑hoogte aanpast**, en **barcode‑PNG genereert** voor elke visuele eis. Door `XDimension` en `BarHeight` te tweaken kun je compacte of grote barcodes produceren zonder de onderliggende data te wijzigen.

Vervolgens kun je gerelateerde onderwerpen verkennen zoals **barcode‑hoogte dynamisch aanpassen** op basis van gebruikersinvoer, barcodes in PDF‑rapporten embedden met Aspose.PDF, of overschakelen naar QR‑code‑generatie met `EncodeTypes.QR`. Experimenteer met verschillende symbologieën en uitvoerformaten om barcode‑creatie in C# volledig onder de knie te krijgen.


## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}