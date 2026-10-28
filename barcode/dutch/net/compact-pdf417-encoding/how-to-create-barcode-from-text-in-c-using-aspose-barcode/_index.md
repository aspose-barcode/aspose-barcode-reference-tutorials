---
category: general
date: 2026-10-28
description: Maak een barcode van tekst in C# met Aspose.BarCode. Leer hoe je een
  PDF417‑barcode‑afbeelding genereert, kolommen instelt, de X‑dimensie aanpast en
  compacte modus inschakelt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: nl
lastmod: 2026-10-28
og_description: Maak een barcode van tekst in C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je een PDF417-barcodeafbeelding genereert, de grootte, kolommen en
  compacte modus aanpast.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Maak een barcode van tekst in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Hoe een barcode te maken van tekst in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te maken vanuit tekst in C# met Aspose.BarCode

Als je een **barcode vanuit tekst** moet maken in een .NET‑applicatie, biedt deze gids een kant‑klaar‑te‑run‑oplossing. Je ziet hoe je **PDF417‑barcode**‑afbeeldingen kunt genereren, de module‑breedte, kolom‑aantal kunt regelen en compacte modus kunt inschakelen zonder je IDE te verlaten.

De tutorial behandelt alles wat nodig is om **barcode C#**‑code te **genereren**, van de installatie van de bibliotheek tot het opslaan van het uiteindelijke PNG‑bestand. Aan het einde kun je een high‑density PDF417‑barcode in rapporten, tickets of voorraadlabels insluiten.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere editor die .NET ondersteunt)  
* Internettoegang om het Aspose.BarCode for .NET NuGet‑pakket te downloaden  

Deze items zijn voldoende om het voorbeeld te compileren en uit te voeren op Windows, Linux of macOS.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

De bibliotheek die de barcode‑generatie aandrijft is **Aspose.BarCode for .NET**. Installeer deze met de .NET‑CLI:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode` namespace toe, die de `BarcodeGenerator`‑klasse bevat die door de hele tutorial wordt gebruikt.

## Stap 2: Maak een console‑project en voeg de code toe

Maak een nieuw console‑project aan en vervang de gegenereerde `Program.cs` door de volgende code. Het programma laat zien hoe je **barcode vanuit tekst** maakt en opslaat als een **PDF417‑barcode‑afbeelding**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is

* **`EncodeTypes.Pdf417`** selecteert de PDF417‑symbologie, die ideaal is voor het coderen van grote hoeveelheden data in een twee‑dimensionaal formaat.  
* **`XDimension.Pixels = 2`** verkleint de module‑breedte, waardoor de barcode dichter wordt en beter geschikt is voor beperkte ruimte.  
* **`Pdf417.Columns = 3`** bepaalt het aantal verticale datakolommen; een lager aantal resulteert in een hogere maar smallere barcode.  
* **`Pdf417.Truncate = true`** activeert compacte modus, waarbij ongebruikte kolommen aan de rechterkant worden weggesneden. Dit is de belangrijkste instelling die een gewone PDF417 omzet in een **compacte PDF417‑barcode‑afbeelding**.  

## Stap 3: Bouw en voer het project uit

Voer de volgende commando's uit in de projectmap:

```bash
dotnet build
dotnet run
```

Wanneer het programma klaar is, zie je een console‑bericht dat de bestandslocatie bevestigt. Open `CompactPdf417.png` met een willekeurige afbeeldingsviewer om het resultaat te verifiëren.

**Verwachte output** – een hoog‑contrast PNG die een compacte PDF417‑barcode toont die de tekenreeks `Åspóse.Barcóde©` codeert. Het scannen van de afbeelding met een standaard barcode‑lezer geeft de oorspronkelijke tekst terug, wat bevestigt dat **generate pdf417 barcode** geslaagd is.

## Stap 4: De barcode aanpassen voor verschillende scenario's

Hoewel het voorbeeld een vast kolomaantal en X‑dimension gebruikt, kun je de generator aanpassen voor andere eisen:

| Scenario | Aanpassing |
|----------|------------|
| Grotere gegevenspayload | Verhoog `Pdf417.Columns` of stel `Pdf417.Rows` handmatig in |
| Betere scanbetrouwbaarheid | Verhoog `XDimension.Pixels` naar 3 of 4 |
| Ander afbeeldingsformaat | Vervang `BarCodeImageFormat.Png` door `Jpeg` of `Bmp` |
| Transparante achtergrond | Stel `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` in |

Deze opties stellen je in staat om **barcode C#**‑oplossingen te **genereren** die passen bij mobiele apps, desktop‑rapporten of webservices.

## Stap 5: Omgaan met randgevallen en best practices

* **Unicode‑ondersteuning** – De generator codeert Unicode‑tekens automatisch, maar zorg ervoor dat je bronreeks UTF‑8 gecodeerd is als je deze uit een bestand leest.  
* **Grote tekst** – PDF417 kan tot 1.850 alfanumerieke tekens coderen. Als je deze limiet overschrijdt, gooit de bibliotheek een uitzondering; splits de data over meerdere barcodes of schakel over naar een symbologie met hogere capaciteit.  
* **Foutafhandeling** – Plaats de generatiecode in een `try/catch`‑blok om `BarCodeException` op te vangen en een vriendelijke foutmelding te geven.  
* **Prestaties** – Het genereren van veel barcodes in een lus profiteert van het hergebruiken van één `BarcodeGenerator`‑instantie en alleen `CodeText` bijwerken tussen iteraties.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Volledige broncode

Hieronder staat het volledige, zelfstandige programma dat je kunt kopiëren naar `Program.cs`. Er zijn geen extra bestanden nodig.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Het uitvoeren van dit programma maakt de **pdf417‑barcode‑afbeelding** die hieronder wordt geïllustreerd.

![Compacte PDF417 barcode gemaakt vanuit tekst met C#](/images/compact-pdf417.png){.img-fluid alt="voorbeeld van barcode maken vanuit tekst dat een compacte PDF417‑barcode‑afbeelding toont"}

*Afbeeldingsbeschrijving: Het PNG‑bestand toont een compacte PDF417‑barcode die de tekenreeks “Åspóse.Barcóde©” codeert.*  

## Conclusie

Je weet nu hoe je **barcode vanuit tekst** in C# kunt **maken** en een **PDF417‑barcode‑afbeelding** kunt produceren met aangepaste afmetingen en compacte modus. Het voorbeeld laat de essentiële stappen zien om **barcode C#** te **genereren**, Unicode‑data te verwerken en visuele parameters aan te passen voor verschillende implementatiescenario's.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **generate QR code in C#**, **add barcode to PDF documents**, of **embed barcodes in ASP.NET Core APIs**. Elk van deze bouwt voort op dezelfde `BarcodeGenerator`‑fundamenten die hier behandeld worden.

Veel plezier met coderen, en geniet van het integreren van barcodes in je .NET‑oplossingen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [PDF417‑barcode genereren in C# – PDF417‑barcode maken in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Hoe PDF417‑barcode te genereren met Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Hoe PDF417‑barcode‑afbeelding te maken in C# – volledige gids](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}