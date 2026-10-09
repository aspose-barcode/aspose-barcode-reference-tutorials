---
category: general
date: 2026-10-08
description: Leer hoe je barcode‑afbeeldingen kunt aanpassen met een C# barcode‑generatorvoorbeeld,
  waarbij je de balkhoogte van 30 px naar 60 px wijzigt in slechts een paar regels
  code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: nl
lastmod: 2026-10-08
og_description: Hoe je een barcode snel kunt aanpassen met een C# barcode-generator
  voorbeeld. Pas de balkhoogte aan, sla PNG‑bestanden op en vermijd veelvoorkomende
  valkuilen.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Hoe de grootte van een barcode aan te passen in C# – stap‑voor‑stap generatorvoorbeeld
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Hoe een barcode te schalen met een barcodegenerator‑voorbeeld in C#
url: /nl/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te verkleinen met een barcode‑generator voorbeeld in C#

Als je **barcode‑afbeeldingen wilt verkleinen** in een .NET‑project, laat deze gids de volledige oplossing zien. Je ziet een beknopt **barcode generator voorbeeld C#** dat de balkhoogte van 30 px naar 60 px wijzigt en elke versie opslaat als een PNG‑bestand.

Het verkleinen van een barcode is vaak nodig wanneer dezelfde gegevens op kassabonnen, etiketten of productpagina’s in verschillende visuele schalen moeten verschijnen. In plaats van de rasterafbeelding met een externe editor te bewerken, kun je de afmetingen van de barcode programmatisch aanpassen, waardoor de gegevensintegriteit behouden blijft.

In deze tutorial leer je:

* Een DataBar Omni‑Directional barcode‑generator opzetten.  
* De X‑dimensie‑ en balkhoogte‑parameters aanpassen.  
* Twee afbeeldingen met verschillende hoogtes opslaan.  
* Begrijpen waarom het wijzigen van de balkhoogte werkt en op welke randgevallen je moet letten.

> **Voorwaarde** – Je beschikt over een .NET‑ontwikkelomgeving (Visual Studio 2022 of nieuwer) en de barcode‑bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` levert. De code werkt met de nieuwste versie van de bibliotheek vanaf oktober 2026.

## Voorvereisten voor het barcode‑generator voorbeeld C#

Voordat je begint, zorg dat je het volgende hebt:

| Item | Reden |
|------|-------|
| .NET 6.0 SDK of nieuwer | Biedt de runtime en taalfeatures die in het voorbeeld worden gebruikt. |
| Barcode‑bibliotheek (bijv. Aspose.BarCode, Dynamsoft, of een andere bibliotheek die `BarcodeGenerator` exposeert) | Levert de `EncodeTypes.DatabarOmniDirectional`‑enum en methoden voor afbeeldingsexport. |
| Een map waar je naar kunt schrijven (bijv. `C:\Temp\Barcodes\`) | Het voorbeeld slaat PNG‑bestanden op in deze locatie. |
| Basiskennis van C# | De tutorial gaat uit van bekendheid met klassen, eigenschappen en string‑interpolatie. |

Installeer de bibliotheek via NuGet als je dat nog niet hebt gedaan:

```bash
dotnet add package Aspose.BarCode
```

Vervang de pakketnaam door de naam die je daadwerkelijk gebruikt; de getoonde API‑structuur is gebruikelijk voor de meeste barcode‑SDK’s.

## Hoe een barcode te verkleinen – stap 1: maak de generator

De eerste stap is het instantieren van een `BarcodeGenerator` met de gewenste symbologie en gegevenspayload. In dit voorbeeld genereren we een **DataBar Omni‑Directional** barcode die een GTIN‑14‑waarde codeert.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Waarom dit belangrijk is:** De `EncodeTypes.DatabarOmniDirectional`‑enum vertelt de bibliotheek welke barcode‑standaard moet worden gebruikt. De gegevensreeks volgt de GS1 Application Identifier `(01)` voor een 14‑cijferige GTIN, waardoor de barcode voldoet aan wereldwijde handelsnormen.

## Hoe een barcode te verkleinen – stap 2: definieer de module‑breedte en initiële balkhoogte

De visuele grootte van een barcode hangt af van twee parameters:

* **X‑dimensie** – de breedte van de kleinste balk (module). Gemeten in pixels of millimetres.  
* **Balkhoogte** – de verticale lengte van de balken.

Deze waarden vóór het opslaan instellen garandeert dat de gerenderde afbeelding overeenkomt met de afmetingen die je nodig hebt.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Uitleg:** Een X‑dimensie van 2 px levert een compacte barcode die nog steeds betrouwbaar scant. De hoogte van 30 px is een veelgebruikt standaard voor kleine etiketten. Je kunt de X‑dimensie onafhankelijk van de hoogte aanpassen als je een dichtere of meer uitgelijnde structuur nodig hebt.

## Hoe een barcode te verkleinen – stap 3: sla de eerste afbeelding op (30 px hoogte)

Exporteer nu de barcode naar een PNG‑bestand. De `Save`‑methode accepteert een bestandspad en een afbeeldingsformaat‑enum.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultaat:** `DatabarBarHeight30Pixels.png` bevat een barcode van 30 px hoogte. Je kunt het bestand in elke afbeeldingsviewer openen om de afmetingen te verifiëren.

## Hoe een barcode te verkleinen – stap 4: wijzig de balkhoogte naar 60 px

Om een grotere versie te maken, wijzig je eenvoudig de `BarHeight`‑eigenschap. De generator hergebruikt dezelfde gegevens en X‑dimensie, zodat het patroon van de barcode identiek blijft — alleen de visuele grootte verandert.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Waarom dit werkt:** De barcode‑renderengine berekent de geometrie van elke balk op aanvraag. Het bijwerken van de hoogte‑eigenschap vóór de volgende `Save`‑aanroep veroorzaakt een nieuwe rasterisatie met de nieuwe afmetingen.

## Hoe een barcode te verkleinen – stap 5: sla de tweede afbeelding op (60 px hoogte)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Je hebt nu twee PNG‑bestanden, één klein (30 px) en één groter (60 px), klaar voor gebruik op verschillende etiketgroottes.

## Volledige broncode voor het barcode‑generator voorbeeld C#

Hieronder staat het complete, uitvoerbare programma. Kopieer het naar een nieuw console‑project om direct te testen.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Verwachte uitvoer in de console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Na het uitvoeren, open de twee PNG‑bestanden om het visuele verschil te zien. Beide barcodes coderen dezelfde GTIN‑14‑waarde en scannen identiek, ongeacht de hoogte.

## Waarom het aanpassen van de balkhoogte veilig is voor scanning

Barcode‑scanners lezen het patroon van lichte en donkere modules, niet het absolute pixel‑aantal. Zolang de **X‑dimensie** binnen de toleranties van de scanner blijft (meestal 0,5 mm tot 2 mm in fysieke eenheden), heeft het wijzigen van de hoogte geen invloed op de leesbaarheid. De bibliotheek schaalt de modules automatisch, waarbij de vereiste stille zones en uitlijningspatronen behouden blijven.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Valkuil | Oplossing |
|---------|-----------|
| **Doelmap bestaat niet** | Roep `Directory.CreateDirectory(outputPath)` aan vóór het opslaan. |
| **Onjuiste X‑dimensie waardoor scans wazig worden** | Houd `XDimension.Pixels` tussen 1 px en 4 px voor de meeste printers; test met een fysieke scanner. |
| **Een rasterformaat gebruiken voor zeer grote barcodes** | Schakel over naar `BarCodeImageFormat.Svg` voor onbeperkte schaalbaarheid zonder pixelatie. |
| **Vergeten `BarHeight` te resetten vóór de tweede opslag** | Zorg dat je de nieuwe hoogte **toekent** vóór het opnieuw aanroepen van `Save`. |

## Pro‑tip: genereer meerdere groottes in een lus

Als je een reeks hoogtes nodig hebt (bijv. 30 px, 45 px, 60 px), vermindert een eenvoudige `foreach`‑lus de duplicatie:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Dit patroon schaalt goed voor batchverwerking van productcatalogi.

## Randgevallen: verschillende afbeeldingsformaten en DPI‑instellingen

* **SVG‑output** – Gebruik `BarCodeImageFormat.Svg` om een vectorbestand te produceren dat zonder kwaliteitsverlies kan worden geschaald.  
* **High‑DPI PNG** – Stel `generator.Parameters.Image.DpiX` en `DpiY` in op 300 of 600 voor afdruk‑klare afbeeldingen; de balkhoogte wordt nog steeds in pixels gemeten, dus verhoog deze evenredig.  
* **Niet‑standaard symbologieën** – Sommige barcode‑typen (bijv. QR‑Code) hebben een aparte `Size`‑eigenschap in plaats van `BarHeight`. Raadpleeg de documentatie van de bibliotheek voor die gevallen.

## Testen van de verkleinde barcode

1. Open elk PNG‑bestand in een afbeeldingsviewer en controleer de pixelafmetingen (bijv. 150 × 30 px vs. 150 × 60 px).  
2. Print de afbeeldingen op 100 % schaal.  
3. Scan met een handscanner of een mobiele app. De gedecodeerde gegevens moeten zijn


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementaties in je eigen projecten te verkennen.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}