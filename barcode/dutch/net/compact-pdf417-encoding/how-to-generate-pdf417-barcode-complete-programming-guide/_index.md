---
category: general
date: 2026-07-18
description: Hoe PDF417‑barcode te genereren met UTF‑8‑codering. Leer de stappen voor
  barcode‑UTF8‑codering in C# voor robuuste gegevenscaptatie.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- barcode utf8 encoding
language: nl
lastmod: 2026-07-18
og_description: Hoe PDF417-barcode te genereren met UTF‑8-codering. Volg deze tutorial
  om snel Macro PDF417-barcodes in C# te maken.
og_image_alt: Screenshot of a generated PDF417 barcode with UTF‑8 characters
og_title: Hoe PDF417-barcode te genereren – Stapsgewijze C#-gids
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: How to generate PDF417 barcode with UTF‑8 encoding. Learn barcode UTF8
    encoding steps in C# for robust data capture.
  headline: How to Generate PDF417 Barcode – Complete Programming Guide
  type: TechArticle
tags:
- barcode
- pdf417
- utf8
title: Hoe PDF417-barcode te genereren – Complete programmeergids
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren – Complete programmeergids

Heb je je ooit afgevraagd **hoe je PDF417**-barcodes kunt genereren die Unicode‑tekens correct verwerken? Je bent niet de enige. In veel voorraad‑, ticket‑ of document‑volgsystemen heb je een Macro PDF417‑barcode nodig die **barcode UTF8‑codering** respecteert, anders worden speciale tekens onleesbaar.

In deze tutorial lopen we een praktisch C#‑voorbeeld stap voor stap door, van het opzetten van het project tot het opslaan van een PNG‑afbeelding die exact de door jou opgegeven tekens bevat. Geen vage verwijzingen—alleen een complete copy‑and‑paste‑oplossing die vandaag werkt.

## Wat je nodig hebt

- **.NET 6.0** of later (de code werkt ook op .NET Framework 4.7+).  
- Een IDE zoals Visual Studio 2022 (elke editor die C# kan compileren volstaat).  
- Een licentie of een gratis evaluatie van **Aspose.BarCode for .NET** – deze bibliotheek levert de `BarcodeGenerator`‑klasse die hieronder wordt gebruikt.  
- Basiskennis van C#‑syntaxis (als je vertrouwd bent met `using`‑statements, ben je klaar).

Dat is alles. Geen extra NuGet‑pakketten naast Aspose.BarCode.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open je terminal of de NuGet Package Manager Console en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Of, als je de UI verkiest, zoek naar *Aspose.BarCode* en klik op **Install**. Dit haalt alles binnen wat je nodig hebt, inclusief ondersteuning voor UTF‑8 ECI‑coderingen.

## Stap 2: Maak een eenvoudige console‑applicatie

Maak een nieuw console‑project (of voeg de code toe aan een bestaand project):

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Open nu `Program.cs`. We zullen de inhoud vervangen door het volledige voorbeeld hieronder.

## Stap 3: Schrijf de volledige PDF417‑generatiecode

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Initialise the generator for a Macro PDF417 barcode.
            // -----------------------------------------------------------------
            // The text contains accented characters, Chinese glyphs and Cyrillic.
            // Thanks to UTF‑8 ECI these symbols survive the encoding process.
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde© 伍01 街 компания"
            );

            // -----------------------------------------------------------------
            // 2️⃣  Basic appearance – make the modules 2 pixels wide.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣  PDF417‑specific tweaks – fewer columns for a compact image.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.Columns = 4;

            // -----------------------------------------------------------------
            // 4️⃣  Define Macro PDF417 metadata (file ID, segment ID, etc.).
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417FileName = "伍01";
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "街";
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417Sender = "компания";

            // -----------------------------------------------------------------
            // 5️⃣  Crucial part – tell the generator the text is UTF‑8 encoded.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417ECIEncoding = ECIEncodings.UTF8;

            // -----------------------------------------------------------------
            // 6️⃣  Save the barcode as a PNG file.
            // -----------------------------------------------------------------
            string outputPath = "MacroPdf417ECI.png";
            barcodeGen.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

### Waarom elk gedeelte belangrijk is

- **Stap 1** maakt een *Macro* PDF417‑object aan. De “Macro”‑variant laat je een grote payload over meerdere barcodes verdelen terwijl de volgorde behouden blijft.  
- **Stap 2** stelt `XDimension` in op 2 pixels – een gangbare grootte die leesbaarheid op schermen en printers in balans brengt.  
- **Stap 3** verlaagt het aantal kolommen tot 4, waardoor een compactere barcode ontstaat die nog steeds op de meeste labelformaten past.  
- **Stap 4** vult de macro‑specifieke velden (`FileID`, `SegmentID`, etc.) in. Deze zijn optioneel maar illustreren hoe metadata in te sluiten.  
- **Stap 5** is het hart van **barcode UTF8‑codering**. Zonder deze regel zou de bibliotheek standaard ISO‑8859‑1 gebruiken, waardoor niet‑ASCII‑tekens worden vervormd.  
- **Stap 6** schrijft de afbeelding naar schijf; PNG behoudt de scherpe randen van de barcode‑modules.

## Stap 4: Voer het programma uit en controleer de output

Voer vanuit de projectmap uit:

```bash
dotnet run
```

Je zou moeten zien:

```
✅ Barcode saved to MacroPdf417ECI.png
```

Open `MacroPdf417ECI.png` met een willekeurige afbeeldingsviewer. De barcode zal de tekenreeks **Åspóse.Barcóde© 伍01 街 компания** en de macro‑metadata die je hebt gedefinieerd bevatten. Het scannen met een PDF417‑compatibele scanner (of een smartphone‑app die Macro PDF417 ondersteunt) zal de originele Unicode‑tekst teruggeven, wat bewijst dat **barcode UTF8‑codering** naar behoren werkt.

### Verwacht visueel resultaat

> ![Gegenereerde PDF417 barcode](/images/pdf417-utf8-example.png "Gegenereerde PDF417 barcode met UTF‑8 tekens")

*Afbeeldings‑alt‑tekst:* **Gegenereerde PDF417 barcode met UTF‑8 tekens** (bevat het primaire zoekwoord voor toegankelijkheid).

## Veelvoorkomende valkuilen & pro‑tips

- **Valkuil:** Het vergeten instellen van `MacroPdf417ECIEncoding`. De barcode wordt nog steeds gegenereerd, maar elk teken buiten ASCII wordt een vraagteken of een onjuiste glyph.  
- **Pro‑tip:** Als je van plan bent de barcode in een PDF in te sluiten, gebruik dan `BarCodeImageFormat.Pdf` in plaats van PNG – Aspose embedt de vectorafbeelding direct, waardoor deze scherp blijft op elk zoomniveau.  
- **Valkuil:** Een bestandsnaam gebruiken met ongeldige tekens op Windows (bijv. `:` of `*`). Het voorbeeld gebruikt een eenvoudige naam, maar reinig altijd door de gebruiker opgegeven strings voordat je ze doorgeeft aan `Save`.  
- **Pro‑tip:** Bij het genereren van veel barcodes in een lus, hergebruik een enkele `BarcodeGenerator`‑instantie en wijzig alleen de `CodeText`‑eigenschap; dit vermindert de toewijzings‑overhead.

## Hoe PDF417 te genereren – Samenvatting

- **Installeer** Aspose.BarCode via NuGet.  
- **Instantieer** `BarcodeGenerator` met `EncodeTypes.MacroPdf417`.  
- **Configureer** het uiterlijk (`XDimension`, `Columns`).  
- **Stel** macro‑metadata in indien nodig.  
- **Schakel** `MacroPdf417ECIEncoding = ECIEncodings.UTF8` in om Unicode te verwerken.  
- **Sla** de afbeelding op in het gewenste formaat.

Dat is het volledige antwoord op **hoe je PDF417**‑barcodes kunt genereren die **barcode UTF8‑codering** respecteren.

## Wat is het volgende?

Nu je een werkende macro‑barcode hebt, kun je het volgende verkennen:

- **Afbeeldingen of logo’s toevoegen** aan de achtergrond van de barcode (zie Aspose’s `BackgroundImage`‑eigenschap).  
- **Een reeks gesegmenteerde barcodes genereren** voor grote dataladingen (verhoog `MacroPdf417FileID` en `SegmentID`).  
- **De barcode in een PDF‑rapport embedden** met `Aspose.Pdf` voor end‑to‑end documentautomatisering.  

Voel je vrij te experimenteren met verschillende `Columns`, `Rows`, of zelfs over te schakelen naar de standaard (niet‑macro) PDF417 als je geen segmentatie nodig hebt. Het kernidee—het instellen van de UTF‑8 ECI‑codering—blijft hetzelfde.

Veel programmeerplezier, en moge je scans altijd perfect zijn!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417‑barcodes te genereren – Compact PDF417‑codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix‑barcodes (ECC 200) te genereren met Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}