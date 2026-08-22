---
category: general
date: 2026-08-22
description: Leer hoe je een micro‑PDF417‑barcode maakt in C# en een barcode‑PNG‑afbeelding
  genereert. Inclusief het instellen van de barcode‑afmetingen en het opslaan van
  het bestand.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: nl
lastmod: 2026-08-22
og_description: Maak een micro‑PDF417‑barcode in C# en exporteer deze als PNG. Volg
  deze gids om de afmetingen van de barcode in te stellen en snel een barcode‑afbeelding
  te genereren.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Creëer micro‑PDF417‑barcode in C# – volledige programmeertutorial
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Hoe maak je een micro PDF417‑barcode in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een micro PDF417 barcode in C# – stap‑voor‑stap gids

Als je een **micro PDF417 barcode** moet maken voor een ticketsysteem, inventarislabel of mobiele scan, laat deze tutorial je precies zien hoe. Je ziet het volledige C#‑programma dat een barcode‑PNG genereert, leert hoe je de barcode‑dimensies instelt en begrijpt elke configuratie‑optie.

Aan het einde van deze gids kun je een hoge‑resolutie barcode‑afbeelding genereren, de X‑dimensie aanpassen, het aantal kolommen kiezen en het resultaat opslaan als een PNG‑bestand — allemaal met een paar regels code.

## Wat je nodig hebt

- .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
- Visual Studio 2022 of een andere C#‑compatibele IDE
- Het **Aspose.BarCode for .NET** NuGet‑pakket (of een bibliotheek die `EncodeTypes.MicroPdf417` ondersteunt)
- Basiskennis van C#‑syntaxis

> **Pro tip:** De gratis community‑editie van Aspose.BarCode is voldoende voor ontwikkeling en testen. Voor productie moet je een licentie aanschaffen om evaluatiewatermerken te verwijderen.

## Stap 1: Installeer de barcode‑bibliotheek

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Dit voegt de `Aspose.BarCode`‑assembly toe, die de `BarcodeGenerator`‑klasse levert die wordt gebruikt om **barcode‑afbeeldingen in C#** te maken.

## Stap 2: Initialiseert de generator – maak micro PDF417 barcode

De eerste uitvoerbare regel maakt een `BarcodeGenerator`‑instantie aan die is geconfigureerd voor de Micro PDF417‑symbologie en levert de gegevens die je wilt coderen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Waarom dit belangrijk is*: De `EncodeTypes.MicroPdf417`‑enum vertelt de bibliotheek om de compacte versie van PDF417 te gebruiken, wat ideaal is voor kleine labels en mobiele schermen.

## Stap 3: Hoe barcode‑dimensies in C# in te stellen

Het fijn afstellen van de module‑breedte (X‑dimensie) bepaalt de visuele dichtheid van de barcode. Een kleinere waarde levert een scherper beeld op, terwijl een grotere waarde de barcode makkelijker maakt om op afstand te scannen.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Waarom je dimensies moet instellen**: Zonder de X‑dimensie aan te passen, kan de standaardwaarde een barcode opleveren die er wazig uitziet bij weergave op hoge DPI. Instellen op 2 pixels is een goede balans voor de meeste scherm‑gebaseerde scans.

## Stap 4: Kies het aantal kolommen – de breedte van de barcode regelen

Micro PDF417 staat tussen 1 en 4 kolommen toe. Meer kolommen comprimeren de gegevens horizontaal, waardoor de totale afbeeldingsbreedte afneemt.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Randgeval*: Als je 5 kolommen vraagt, gooit de bibliotheek een `ArgumentOutOfRangeException`. Blijf altijd binnen het gedocumenteerde bereik.

## Stap 5: Hoe een barcode‑PNG te genereren – de afbeelding opslaan

Nu kun je de gegenereerde barcode exporteren naar een PNG‑bestand. PNG behoudt verliesvrije kwaliteit, wat essentieel is voor betrouwbaar scannen.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Wanneer je het programma uitvoert, zie je een console‑bericht dat de bestandslocatie bevestigt. De resulterende `MicroPdf417.png` ziet er als volgt uit:

![Schermafbeelding die een gegenereerde micro PDF417 barcode toont, gemaakt met C#](micro-pdf417-example.png "Gegenereerde micro PDF417 barcode")

*Afbeeldings‑alt‑tekst*: **micro PDF417 barcode gegenereerd in C#** – toont de uiteindelijke output na het toepassen van de dimensies en kolominstellingen.

## Stap 6: Voer uit en controleer de output

1. Bouw het project: `dotnet build`.
2. Voer uit: `dotnet run`.
3. Open `MicroPdf417.png` op je bureaublad en scan het met een mobiele barcode‑scanner app.

Je zou de tekst **“Sample text”** gedecodeerd moeten zien. Als de scanner een fout meldt, controleer dan de X‑dimensie en het aantal kolommen – extreme waarden kunnen de barcode te dicht maken voor sommige apparaten.

## Veelvoorkomende variaties en probleemoplossing

| Situatie | Aanpassing |
|-----------|------------|
| **Een grotere barcode nodig voor printers met lage resolutie** | Increase `XDimension.Pixels` to 3 or 4. |
| **Een hogere barcode willen zonder de breedte te wijzigen** | Set `generator.Parameters.Barcode.Pdf417.Rows` (rows range 3‑90). |
| **Meerdere barcodes genereren in een lus** | Re‑use the same `BarcodeGenerator` instance and only change `CodeText` before each `Save`. |
| **Opslaan als JPEG in plaats van PNG** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. |
| **Uitvoeren op .NET Framework 4.7** | The same code works; just reference the appropriate `Aspose.BarCode.dll`. |

## Volledige broncode (uitvoerbaar)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Verwachte output** – een PNG‑bestand van 200 × 100 pixels met een scherpe Micro PDF417 barcode die decodeert naar “Sample text”.

## Conclusie

Je weet nu hoe je een **micro PDF417 barcode** in C# kunt **maken**, **barcode‑dimensies** kunt **instellen**, en een **barcode‑PNG**‑afbeelding kunt **genereren**. Het volledige voorbeeld toont elke vereiste stap — van bibliotheek‑installatie tot het opslaan van het uiteindelijke bestand — zodat je barcode‑generatie direct in je eigen applicaties kunt integreren.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **het maken van QR‑codes met Aspose.BarCode**, **kleuren aanpassen**, of **barcodes in PDF‑documenten insluiten**. Elk van deze bouwt voort op dezelfde `BarcodeGenerator`‑fundamenten die hier behandeld worden.

Voel je vrij om te experimenteren met verschillende gegevensreeksen, kolomaantallen en X‑dimensie‑waarden om aan je specifieke scan‑omgeving te voldoen. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een barcode – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe PDF417 barcode te genereren – Compact PDF417 codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe een Aztec barcode te maken met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}