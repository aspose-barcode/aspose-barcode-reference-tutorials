---
category: general
date: 2026-10-04
description: Maak snel een PDF417-barcode in C#. Leer hoe je een PDF417-barcode genereert
  en hoe je de barcode-afbeelding opslaat als PNG met Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: PDF417-barcode maken in C# met Aspose.Barcode. Deze tutorial laat
  zien hoe je een compacte PDF417-barcode genereert, het uiterlijk configureert en
  opslaat als PNG-afbeelding voor mobiel scannen of labelafdrukken.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: PDF417-barcode maken in C# – volledige stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
- Aspose.Barcode
title: PDF417-barcode maken in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-barcode maken in C# – stapsgewijze handleiding

Als je een **PDF417-barcode** moet maken in een .NET‑applicatie, laat deze handleiding je precies zien hoe je een PDF417-barcode genereert en hoe je de barcode‑afbeelding opslaat als een PNG‑bestand. Je krijgt een compacte afbeelding die uitstekend werkt voor mobiel scannen, ticketsystemen of labelprinters.

## Snelle antwoorden
- **Welke bibliotheek verwerkt de PDF417‑generatie?** Aspose.Barcode for .NET.  
- **In welk formaat slaat het voorbeeld op?** PNG, met `BarCodeImageFormat.Png`.  
- **Hoeveel regels code zijn nodig?** Ongeveer 10 regels na het project opzetten.  
- **Kan ik grootte en inkorting aanpassen?** Ja – de eigenschappen `Columns`, `Rows` en `Truncate`.  
- **Is de code .NET‑6‑compatibel?** Ja, volledig, en hij werkt ook met .NET Framework 4.7+.

## Wat heb je nodig om een PDF417-barcode te maken in C#?
Om te beginnen heb je een recente .NET SDK, een IDE zoals Visual Studio 2022, en het **Aspose.Barcode for .NET** NuGet‑pakket nodig. Deze tools laten het voorbeeld compileren en uitvoeren zonder extra configuratie.

- .NET 6.0 SDK of later (werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 of een andere C#‑compatible editor
- Internettoegang om het Aspose.Barcode NuGet‑pakket te downloaden

## Hoe stel je een .NET‑project in voor PDF417‑barcode‑generatie?
Maak een nieuw console‑project, voeg het Aspose.Barcode‑pakket toe, en open het gegenereerde `Program.cs`. Dit bereidt een schone werkomgeving voor waarin je de barcode‑generator kunt instantieren en het uitvoerbestand kunt schrijven.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Hoe kun je een PDF417-barcode genereren met Aspose.Barcode?
`BarcodeGenerator` is de Aspose.Barcode‑klasse die barcode‑afbeeldingen maakt van opgegeven data en symbologie. Je specificeert de PDF417‑symbologie, levert de te coderen tekst, en past eventueel grootte‑ of foutcorrectie‑instellingen aan.

```bash
   dotnet add package Aspose.Barcode
   ```

### Waarom dit belangrijk is
* **EncodeTypes.Pdf417** vertelt de bibliotheek om de PDF417‑standaard te gebruiken, die grote gegevenspayloads en foutcorrectie ondersteunt.
* Het leveren van Unicode‑tekens bewijst dat de generator niet‑ASCII‑invoer aankan zonder extra configuratie.

## Hoe configureer je het uiterlijk van een PDF417-barcode?
Je kunt de module‑grootte, het aantal kolommen en of de barcode een compacte (ingekorte) modus gebruikt, regelen. Deze instellingen beïnvloeden direct de leesbaarheid op kleine schermen en de totale bestandsgrootte van de PNG‑afbeelding.

`generator.Parameters.Barcode.XDimension` bepaalt de breedte van één module, terwijl `Columns` en `Rows` de matrixafmetingen definiëren. Het instellen van `Truncate` op `true` verwijdert de stille zones voor een compactere afbeelding.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Praktische tip
Als je een hogere barcode nodig hebt voor beperkte horizontale ruimte, verhoog dan `Columns`. Het instellen van `Truncate` op `true` verkleint de totale hoogte door stille zones te verwijderen, wat ideaal is voor mobiele schermen.

## Hoe sla je de barcode‑afbeelding op als PNG?
`Save` is een methode van `BarcodeGenerator` die de gegenereerde afbeelding naar een bestand schrijft. Geef een bestandspad en `BarCodeImageFormat.Png` door om in één stap een PNG‑afbeelding te maken.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Verwacht resultaat
Het uitvoeren van het programma maakt `CompactPdf417.png` aan in de projectmap. Het openen van het bestand toont een compacte PDF417‑barcode die de string *Åspóse.Barcóde©* codeert. De afbeelding kan worden ingebed in HTML, PDF‑rapporten, of afgedrukt op labels.

## Hoe kun je het gegenereerde barcode‑bestand verifiëren?
Na afloop van het programma kun je met een snelle opdracht controleren of het bestand bestaat. Deze eenvoudige controle bevestigt dat de generatie‑ en opslaan‑stappen zonder fouten zijn voltooid.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Als het bestand verschijnt, is het **PDF417‑barcode‑maken**‑proces geslaagd.

## Wat zijn veelvoorkomende variaties en randgevallen bij het genereren van PDF417‑barcodes?
Verschillende scenario's kunnen aanpassingen van de generatorinstellingen vereisen. Hieronder een snelle referentietabel die laat zien hoe je typische variaties kunt afhandelen.

| Situatie | Aanpassing |
|-----------|------------|
| **Langere gegevensreeks** | Verhoog `Columns` of stel `Rows` in om meer codewoorden te kunnen verwerken. |
| **Ander afbeeldingsformaat** | Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif`. |
| **Hogere resolutie** | Stel `generator.Parameters.ImageResolution` in vóór `Save`. |
| **Achtergrondkleur** | Gebruik `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Foutafhandeling** | Omring `generator.Save` met een `try/catch`‑blok om I/O‑fouten op te vangen. |

Deze variaties laten je de barcode afstemmen op specifieke apparaten of merkrichtlijnen.

## Wat is de volgende stap na het maken van de barcode?
Nu je een PDF417‑barcode kunt genereren en opslaan, kun je gerelateerde mogelijkheden verkennen, zoals het genereren van QR‑codes, het insluiten van barcodes in PDF‑documenten, of het aanpassen van kleuren voor merkaanpassing. Al deze functionaliteiten gebruiken dezelfde `BarcodeGenerator`‑API, zodat je het voorbeeld met minimale inspanning kunt uitbreiden.

## Gerelateerde handleidingen
- [Hoe een barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix‑barcodes (ECC 200) genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Hoe een Aztec‑barcode genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Veelgestelde vragen

**V: Kan ik deze code gebruiken in een webapplicatie?**  
Ja. Dezelfde `BarcodeGenerator`‑klasse werkt in ASP.NET-, MVC- of Blazor‑projecten; zorg er alleen voor dat de server schrijfrechten heeft voor de doelmap.

**V: Ondersteunt Aspose.Barcode andere 2‑D‑symbologieën?**  
Zeker. Meer dan 30 2‑D‑barkodetypen worden ondersteund, waaronder QR, DataMatrix en Aztec.

**V: Hoe groot kan een barcode zijn?**  
PDF417 kan tot 1.850 tekens coderen in één symbool; je kunt data ook over meerdere rijen verdelen door `Rows` en `Columns` aan te passen.

**V: Is een licentie vereist voor productiegebruik?**  
Ja. Er is een gratis proefversie beschikbaar voor evaluatie, maar een commerciële licentie is nodig voor productie.

**V: Welke .NET‑versies zijn compatibel?**  
Aspose.Barcode ondersteunt .NET Framework 4.5+, .NET Core 3.1+ en .NET 5/6/7.

**Laatst bijgewerkt:** 2026-10-04  
**Getest met:** Aspose.Barcode 24.11 for .NET  
**Auteur:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}