---
category: general
date: 2026-08-19
description: Maak databar PNG‑bestanden in C# met Aspose.BarCode. Leer hoe je databar‑afbeeldingen
  genereert, databar‑parameters configureert en PNG‑uitvoer opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: nl
lastmod: 2026-08-19
og_description: Maak databar‑PNG‑bestanden in C# met Aspose.BarCode. Deze tutorial
  leidt je stap voor stap door het genereren van databar‑afbeeldingen, het configureren
  van databar‑parameters zoals X‑dimensie en beeldverhouding, en het opslaan van PNG‑bestanden
  van hoge kwaliteit voor afdrukken of webgebruik.
og_image_alt: create databar PNG example
og_title: Maak databar PNG‑afbeeldingen in C# – stap‑voor‑stap gids
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Hoe databar PNG-afbeeldingen te maken met C# en Aspose.BarCode
url: /nl/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe databar PNG‑afbeeldingen te maken met C# en Aspose.BarCode

Als je **databar PNG**‑bestanden moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe. Je ziet een volledig, uitvoerbaar voorbeeld dat gestapelde omnidirectionele DataBar‑codes genereert, belangrijke parameters configureert en twee PNG‑bestanden opslaat met verschillende beeldverhoudingen.

Het genereren van een DataBar‑afbeelding gaat niet alleen om het aanroepen van één methode. Je moet ook **databar‑parameters configureren** zoals de X‑dimensie (modulebreedte) en de beeldverhouding om te voldoen aan afdruk‑ of scan‑specificaties. Aan het einde van deze tutorial begrijp je **hoe je databar**‑grafieken genereert die betrouwbaar werken in praktijksituaties.

## Vereisten

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 of een andere C#‑compatibele IDE
- Een geldige licentie voor **Aspose.BarCode for .NET** (de gratis evaluatie werkt voor testen)
- Basiskennis van C#‑syntaxis

> **Pro tip:** Als je nog geen licentie hebt, kun je een tijdelijke evaluatiesleutel aanvragen via het Aspose‑portaal. De API werkt hetzelfde; alleen het watermerk verandert.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open je project in Visual Studio, klik met de rechtermuisknop op de oplossing en selecteer **Manage NuGet Packages**. Zoek naar `Aspose.BarCode` en installeer de nieuwste stabiele versie.

```bash
dotnet add package Aspose.BarCode
```

Deze opdracht voegt de `Aspose.BarCode`‑assembly toe aan je project en maakt de `BarcodeGenerator`‑klasse beschikbaar.

## Stap 2: Initialiseert de barcode‑generator voor een gestapelde omnidirectionele DataBar

De constructor van `BarcodeGenerator` ontvangt twee argumenten: het type barcode en de ruwe gegevensreeks. Voor een gestapelde omnidirectionele DataBar gebruik je `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Waarom dit belangrijk is:** De constante `EncodeTypes.DatabarStackedOmniDirectional` vertelt de bibliotheek een barcode te produceren die vanuit elke oriëntatie gelezen kan worden, wat ideaal is voor winkelrek‑labels.

## Stap 3: Configureer de X‑dimensie (modulebreedte) in pixels

De X‑dimensie bepaalt de grootte van het kleinste balk‑element. Instellen in pixels geeft je precieze controle over de uiteindelijke afbeeldingsgrootte.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van **2 pixels** is een goede balans tussen leesbaarheid en compactheid voor de meeste labelprinters. Pas deze waarde aan als je grotere of kleinere modules nodig hebt.

## Stap 4: Stel de eerste beeldverhouding in en sla de PNG op

De beeldverhouding beïnvloedt de hoogte van de gestapelde DataBar. Een beeldverhouding van **15** levert een relatief korte barcode op, terwijl **30** deze hoger maakt.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft de gegenereerde barcode naar een PNG‑bestand. PNG is lossless, waardoor de scherpe randen behouden blijven die barcode‑scanners nodig hebben.

## Stap 5: Verander de beeldverhouding en sla een tweede PNG op

Je kunt dezelfde `BarcodeGenerator`‑instantie hergebruiken om variaties te maken door simpelweg de beeldverhouding te wijzigen.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Nu heb je twee PNG‑bestanden — `DatabarAspectRatio15.png` en `DatabarAspectRatio30.png` — elk met een andere visuele dichtheid.

## Stap 6: Controleer de output

Open de gegenereerde PNG‑bestanden in een willekeurige afbeeldingsviewer. Je zou een schone, hoog‑contrast DataBar‑barcode moeten zien. Het scannen van de afbeeldingen met een smartphone‑barcode‑scanner bevestigt dat beide beeldverhoudingen decoderen naar de oorspronkelijke GTIN‑waarde `12345678901231`.

![create databar PNG example](databar_example.png)

*De afbeelding hierboven toont de twee PNG‑bestanden naast elkaar. De linker afbeelding gebruikt beeldverhouding 15, de rechter gebruikt beeldverhouding 30.*

## Veelvoorkomende variaties en randgevallen

| Scenario | Wat te wijzigen | Reden |
|----------|----------------|-------|
| **Andere data** | Vervang de string `(01)12345678901231` door een geldige GS1‑toepassingsidentificator en gegevens | Hiermee kun je product‑ID’s, serienummers, enz. coderen |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` naar 3 of 4 | Noodzakelijk wanneer de barcode op grote formaten wordt afgedrukt of van afstand wordt gescand |
| **Andere DataBar‑types** | Gebruik `EncodeTypes.DatabarStacked` of `EncodeTypes.DatabarExpanded` | Kies het type dat het beste past bij je label‑lay‑out |
| **Transparante achtergrond** | Geef `BarCodeImageFormat.Png` mee met `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Handig om de barcode over gekleurde labels te leggen |

> **Let op:** Het instellen van een X‑dimensie die te klein is (< 1 pixel) kan een barcode opleveren die er wazig uitziet na

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe de barcode‑hoogte te genereren en aan te passen voor één‑dimensionale Databar met Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Maak één‑dimensionale Databar GS1‑codering met Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Genereer Aspose.BarCode Databar barcode met .NET API – Rij‑ en kolomconfiguratie](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}