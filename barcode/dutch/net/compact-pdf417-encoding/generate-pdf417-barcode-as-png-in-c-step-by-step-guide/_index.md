---
category: general
date: 2026-10-28
description: Genereer PDF417‑barcode in C# en exporteer deze als PNG‑afbeelding. Leer
  hoe je de lay‑out configureert, kolommen en rijen instelt, en het bestand opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: nl
lastmod: 2026-10-28
og_description: Genereer een PDF417‑barcode in C# en sla deze op als een PNG‑afbeelding.
  Volg deze volledige gids om de lay‑out te configureren, kolommen en rijen in te
  stellen en een barcode van hoge kwaliteit te produceren.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Genereer PDF417-barcode als PNG – C#-tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Genereer PDF417‑barcode als PNG in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-barcode genereren als PNG in C# – stapsgewijze handleiding

Als je een **PDF417-barcode** moet **genereren** in een .NET‑applicatie, laat deze gids je precies zien hoe je de barcode maakt en opslaat als een PNG‑afbeelding. Je leert hoe je de barcode‑lay‑out configureert, het aantal kolommen en rijen instelt, en een bestand produceert dat kan worden gebruikt in voorraadbeheer, ticketing of mobiele scanscenario's.

De tutorial behandelt alles, van het installeren van de benodigde bibliotheek tot het afhandelen van randgevallen zoals ongeldige lay‑outwaarden. Geen externe documentatie nodig—kopieer gewoon de code, voer deze uit, en je hebt een kant‑klaar barcode‑beeld.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Een C#‑ontwikkelomgeving (Visual Studio, VS Code of Rider)  
* Internettoegang om het **Aspose.BarCode for .NET** NuGet‑pakket te downloaden (de bibliotheek die in de voorbeelden wordt gebruikt)  

Deze vereisten zorgen ervoor dat de code compileert en draait zonder extra configuratie.

## Stap 1: Installeer de barcode‑bibliotheek

De eenvoudigste manier om **barcode‑generator PNG** functionaliteit te krijgen, is door het officiële Aspose.BarCode‑pakket te gebruiken. Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de bibliotheek en de afhankelijkheden toe aan je projectbestand. Nadat de installatie geslaagd is, kun je de klassen in je C#‑bronbestanden refereren.

## Stap 2: Maak een PDF417 barcode‑generator

Het aanmaken van het barcode‑object is de basis van het proces. Het volgende fragment bouwt een generator die de tekst `"Sample"` codeert met de PDF417‑symbologie.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Waarom deze stap belangrijk is* – De `BarcodeGenerator`‑klasse omvat alle instellingen die nodig zijn voor het renderen. Door `EncodeTypes.Pdf417` op te geven, vertel je de bibliotheek een **PDF417‑barcode** te produceren, een gestapelde lineaire code die ideaal is voor het opslaan van grote hoeveelheden data.

## Stap 3: PDF417‑kolommen en -rijen instellen

Een PDF417‑barcode kan worden aangepast door de matrix te wijzigen. De twee meest voorkomende parameters zijn **columns** (horizontale modules) en **rows** (verticale modules). Het regelen van deze waarden beïnvloedt de grootte en leesbaarheid van de barcode.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### PDF417‑barcode configureren voor specifieke afmetingen

* Gebruik waarden binnen de gedocumenteerde bereiken; getallen buiten het bereik veroorzaken een uitzondering.  
* Een hoger aantal kolommen comprimeert de barcode horizontaal, terwijl meer rijen de verticale hoogte vergroten.  
* Pas de lay‑out aan om te passen bij het doel‑printoppervlak of de scan‑afstand.

Als je een andere vorm nodig hebt, wijzig dan de cijfers overeenkomstig. De bibliotheek rekent automatisch de module‑grootte opnieuw uit om de barcode scanbaar te houden.

## Stap 4: PNG‑barcode genereren

Het opslaan van de barcode als PNG‑bestand is een één‑regelige bewerking zodra de generator volledig is geconfigureerd. PNG biedt verliesloze compressie, waardoor het ideaal is voor scherpe barcode‑afbeeldingen.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Waarom PNG* – De `BarCodeImageFormat.Png`‑enum vertelt de bibliotheek de barcode te renderen met het PNG‑formaat. Dit formaat behoudt scherpe randen, wat essentieel is voor barcodescanners die afhankelijk zijn van hoog‑contrast randen.

### Verwachte output

Het uitvoeren van het programma maakt een bestand genaamd **CustomLayout.png** aan in de werkmap van de applicatie. Het openen van het bestand toont een rechthoekige PDF417‑barcode met vier kolommen en negen rijen, die de tekenreeks `"Sample"` codeert.

![Generate PDF417 barcode as PNG](https://example.com/images/pdf417-custom.png "Generate PDF417 barcode as PNG")

*Afbeeldings‑alt‑tekst*: **PDF417-barcode genereren als PNG** – een barcode‑afbeelding geproduceerd door de tutorial‑code.

## Stap 5: Verifieer de barcode en los veelvoorkomende problemen op

Na het genereren van de afbeelding moet je controleren of een scanner of validatietool deze kan lezen. Hier zijn een paar snelle controles:

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Barcode is onscherp | Afbeelding is na generatie verkleind | Houd de originele PNG‑grootte; vermijd schalen in UI‑elementen |
| Scanner meldt “invalid data” | Kolommen/rijen buiten bereik of data te lang voor gekozen lay‑out | Verminder de hoeveelheid te coderen tekst of vergroot het aantal rijen/kolommen |
| PNG‑bestand is leeg | `generator.Save`‑pad wijst naar een niet‑bestaande map | Zorg dat de map bestaat of gebruik een absoluut pad |

**Pro tip:** Wanneer je een transparante achtergrond nodig hebt (bijv. om de barcode over een UI‑element te leggen), stel `generator.Parameters.Image.TransparentBackground = true;` in vóór het aanroepen van `Save`.

## Volledig werkend voorbeeld

Hieronder staat het complete programma dat je kunt kopiëren, plakken en uitvoeren zonder aanpassingen (behalve het uitvoerpad indien gewenst).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Het uitvoeren van het programma geeft een bevestigingsbericht weer en produceert `CustomLayout.png` in dezelfde map als het uitvoerbare bestand.

## Conclusie

Je weet nu hoe je een **PDF417‑barcode** in C# kunt **genereren**, de lay‑out kunt configureren met specifieke kolommen en rijen, en het resultaat kunt exporteren als een **PNG‑barcode**‑afbeelding. De stappen omvatten het installeren van de Aspose.BarCode‑bibliotheek, het initialiseren van de generator, het toepassen van aangepaste afmetingen, het opslaan van het bestand en het verifiëren van de output.

Vanaf hier kun je extra instellingen verkennen, zoals fout‑correctieniveau, barcode‑marges, of het direct inbedden van de afbeelding in een PDF‑rapport. Elk van die onderwerpen bouwt voort op het kernpatroon dat in deze gids wordt getoond, zodat je de oplossing kunt aanpassen aan elke .NET‑barcode‑generatiescenario.

---


## Wat kun je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}