---
category: general
date: 2026-08-25
description: Maak een RM4SCC‑barcode in C# met stap‑voor‑stap code en leer hoe je
  de barcodehoogte instelt voor precieze afmetingen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: nl
lastmod: 2026-08-25
og_description: Maak een RM4SCC-barcode in C# met Aspose.BarCode en leer hoe je de
  barcodehoogte instelt voor nauwkeurige controle in je .NET-toepassingen.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: RM4SCC-barcode maken in C# – gids voor het instellen van de barcodehoogte
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Maak RM4SCC-barcode in C# en stel de barcodehoogte in
url: /nl/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak RM4SCC barcode C# en stel barcodehoogte in

Maak snel een RM4SCC barcode C# met behulp van de Aspose.BarCode bibliotheek. Deze tutorial laat **zien hoe je de barcodehoogte instelt** en andere visuele eigenschappen aanpast zodat de barcode precies in je lay-out past.

Je ziet een compleet, kant‑klaar console‑programma dat drie PNG‑bestanden genereert:

* een Planet barcode met standaardhoogte (ter vergelijking)  
* een RM4SCC barcode met een handmatige hoogte van 100 px  
* een Planet barcode met lege (ongevulde) staven  

Het voorbeeld gaat ervan uit dat je Visual Studio 2022 (of een andere .NET 6+ IDE) en een geldige Aspose.BarCode for .NET‑licentie of evaluatiekopie hebt.

## Vereisten

| Vereiste | Reden |
|----------|-------|
| .NET 6 SDK (of later) | Levert de runtime voor de console‑applicatie |
| Aspose.BarCode for .NET NuGet‑pakket | Levert `BarcodeGenerator`, `EncodeTypes` en API's voor het exporteren van afbeeldingen |
| Basis C#‑kennis | Nodig om de codeflow te begrijpen |

Installeer het NuGet‑pakket met:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Als je de code zonder licentie uitvoert, bevatten de gegenereerde afbeeldingen een klein Aspose‑watermerk.

## Stap 1: Zet de projectstructuur op

Maak een nieuw console‑project en voeg de benodigde `using`‑directieven toe:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

De `using`‑statements geven je toegang tot de barcode‑generator‑klassen en de PNG‑formaat‑enum.

## Stap 2: Definieer de uitvoermap

Kies een map waarin de PNG‑bestanden worden opgeslagen. De map moet bestaan voordat je `Save` aanroept.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Het programmatic aanmaken van de directory voorkomt een *FileNotFoundException* wanneer de code op een nieuwe machine wordt uitgevoerd.

## Stap 3: Genereer een Planet barcode met de standaardhoogte (baseline)

De Planet barcode staat niet centraal in deze gids, maar biedt een visuele basislijn om te vergelijken met de handmatig geschaalde RM4SCC barcode.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Waarom dit belangrijk is:*  
`XDimension` bepaalt de breedte van één staaf. Door deze constant te houden en `BarHeight` te wijzigen, wordt het effect van de hoogte geïsoleerd.

## Stap 4: **Create RM4SCC barcode C#** – stel een handmatige hoogte in

Nu pakken we de primaire taak aan: **create RM4SCC barcode C#** en expliciet de hoogte ervan regelen.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Hoe stel je de barcodehoogte in

De `BarHeight`‑eigenschap bevindt zich onder `Parameters.Barcode`. Ze accepteert een `float`‑waarde die wordt uitgedrukt in **pixels**, **points** of **millimeters**, afhankelijk van de `Unit` die je kiest (`Pixels`, `Points`, `Millimeters`). In het voorbeeld gebruiken we `Pixels` omdat het uitvoerformaat PNG is.

Als je een hoogte in millimeters nodig hebt, schakel dan eerst de eenheid:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Stap 5: Genereer een Planet barcode met lege (ongevulde) staven

Deze stap demonstreert een andere handige eigenschap — `FilledBars`. Deze op `false` zetten creëert een “holle” barcode, wat handig kan zijn voor ontwerpdoeleinden.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Volledig, uitvoerbaar programma

Kopieer de volgende code naar `Program.cs`. Bouw en voer het project uit; drie PNG‑bestanden verschijnen in de map `GeneratedBarcodes`.



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een code128 barcode Java en stel je de balkhoogte in](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Hoe maak je een barcode‑quiet zone .NET voor Code 16K met Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hoe maak je een Aztec barcode met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}