---
category: general
date: 2026-08-09
description: Genereer PDF417‑barcode in C# snel. Leer hoe je PDF417 kunt genereren
  met compacte modus, kolomcontrole en PNG‑output met de BarcodeGenerator‑API.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: nl
lastmod: 2026-08-09
og_description: Genereer PDF417-barcode in C# met een beknopt voorbeeld. Deze gids
  laat zien hoe je compacte modus configureert, kolommen instelt en het resultaat
  opslaat als een PNG-afbeelding.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Genereer PDF417‑barcode in C# – volledige tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: PDF417‑barcode genereren in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417‑barcode genereren in C# – stapsgewijze handleiding

Als je een **PDF417‑barcode** moet genereren in een .NET‑applicatie, laat deze tutorial precies zien hoe je dat doet. Je ziet een compleet, uitvoerbaar programma dat een compacte PDF417‑barcode maakt, de grootte aanpast en de afbeelding opslaat als een PNG‑bestand.

Het genereren van een PDF417‑barcode is een veelvoorkomende eis voor mobiel ticketing, voorraadtracking en documentbeveiliging. Deze gids behandelt de essentiële configuratie‑opties, legt uit waarom elke instelling belangrijk is, en geeft praktische tips voor gebruik in de praktijk.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Een C#‑IDE zoals Visual Studio 2022 of Visual Studio Code  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (versie 23.10 of nieuwer)  

Je kunt het pakket installeren met de volgende CLI‑opdracht:

```bash
dotnet add package Aspose.BarCode
```

De code hieronder gaat ervan uit dat het pakket is gerefereerd en dat je schrijfrechten hebt op de output‑map.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan en voeg de benodigde `using`‑directieven toe. Deze namespaces maken de `BarcodeGenerator`‑klasse en de enumeratie voor afbeeldingsformaten beschikbaar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Waarom dit belangrijk is:** Het importeren van de juiste namespaces zorgt ervoor dat de compiler de `BarcodeGenerator`‑type en de `BarCodeImageFormat`‑enum kan vinden. Het ontbreken van een namespace leidt tot een compilatiefout, waardoor het barcode‑generatieproces wordt onderbroken.

## Stap 2: De `BarcodeGenerator` initialiseren met PDF417‑codering

De constructor van `BarcodeGenerator` ontvangt twee argumenten: de barcode‑symbologie (`EncodeTypes.Pdf417`) en de tekst die je wilt coderen. PDF417 ondersteunt een breed scala aan tekens, inclusief Unicode‑symbolen.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Uitleg:**  
* `EncodeTypes.Pdf417` vertelt de bibliotheek om de PDF417‑standaard te gebruiken.  
* De voorbeeldtekst bevat accenten en een copyright‑symbool om Unicode‑verwerking te demonstreren.  

Als je alleen numerieke gegevens moet coderen, kun je een eenvoudige string zoals `"1234567890"` doorgeven.

## Stap 3: De X‑dimensie aanpassen voor fijnere resolutie

De X‑dimensie bepaalt de breedte van één barcode‑module (het kleinste zwarte of witte element). Een kleinere pixelwaarde levert een afbeelding met hogere resolutie op.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom aanpassen?** Een standaard X‑dimensie van 3–4 pixels kan een barcode opleveren die er grof uitziet op schermen met hoge DPI. Het verlagen naar **2 pixels** biedt een goede balans tussen leesbaarheid en bestandsgrootte, vooral wanneer je later compacte modus inschakelt.

## Stap 4: Het aantal kolommen configureren

PDF417 laat je bepalen hoeveel kolommen de barcode moet bevatten. Minder kolommen maken de barcode smaller maar hoger, terwijl meer kolommen een bredere, kortere barcode opleveren.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Praktische tip:** Voor mobiele tickets die binnen een smalle etiket moeten passen, werkt een kolomtelling van **3–5** goed. Verhoog het aantal als je veel data hebt en een kortere barcode wilt.

## Stap 5: Compacte modus inschakelen om lege rijen te verkorten

Compacte modus verwijdert onnodige rijen uit de barcode‑matrix, waardoor de totale afbeeldingsgrootte wordt verkleind zonder verlies van gecodeerde data.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Wanneer te gebruiken:** Als je barcodes genereert voor opslag of netwerkoverdracht, kan compacte modus het PNG‑bestand tot wel 30 % verkleinen. Sommige oudere scanners ondersteunen echter geen verkorte PDF417; test dit met je doelhardware.

## Stap 6: De barcode opslaan als PNG‑afbeelding

Kies een output‑pad en roep `Save` aan. De enumeratie `BarCodeImageFormat.Png` produceert een verliesvrije afbeelding die voor de meeste toepassingen geschikt is.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Resultaatverificatie:** Open het PNG‑bestand in een willekeurige afbeeldingsviewer. Je zou een dichte, hoog‑contrasterende barcode moeten zien die overeenkomt met de voorbeeldtekst. Het scannen van de afbeelding met een PDF417‑lezer (bijv. ZXing of een smartphone‑app) geeft de oorspronkelijke string `"Åspóse.Barcóde©"` terug.

![Generated PDF417 barcode image saved as PNG](compact-pdf417.png "Generated PDF417 barcode in C#")

*De bovenstaande afbeelding toont de uiteindelijke output van de code uit de tutorial.*

## Volledig, uitvoerbaar voorbeeld

Alle onderdelen samengevoegd, hier is een compleet console‑programma dat je kunt kopiëren, plakken en uitvoeren.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma geeft:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Het bestand `CompactPdf417.png` bevat een compacte PDF417‑barcode die de opgegeven Unicode‑string codeert. Het scannen van de afbeelding met een standaard PDF417‑lezer levert exact dezelfde tekst op.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing | Reden |
|-----------|------------|--------|
| **Langere gegevenspayload** (bijv. > 150 tekens) | Verhoog `generator.Parameters.Barcode.Pdf417.Columns` naar 6‑8 | Meer kolommen voorkomen dat de barcode te hoog wordt. |
| **Transparante achtergrond nodig** | Gebruik `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Een transparante PNG integreert beter in UI‑overlays. |
| **JPEG genereren voor web** | Verander het formaat naar `BarCodeImageFormat.Jpeg` en stel eventueel `ImageQuality` in | JPEG verkleint de bestandsgrootte ten koste van verliesvrije kwaliteit. |
| **Null‑ of lege invoer verwerken** | Controleer de invoer vóór het aanmaken van de generator: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Voorkomt runtime‑exceptions en zorgt voor betekenisvolle barcodes. |

## Tips voor productiegebruik

* **Exception handling:** Plaats de generatie‑logica in een `try/catch`‑blok om fouten zoals onvoldoende schijfruimte of ongeldige parameters te loggen.  
* **Performance:** Hergebruik een enkele `BarcodeGenerator`‑instantie bij het genereren van veel barcodes met dezelfde instellingen; werk alleen de `CodeText`‑eigenschap bij tussen opslagen.  
* **Beveiliging:** Wanneer de gecodeerde tekst gevoelige informatie bevat, overweeg dan om deze te versleutelen vóór het doorgeven aan de generator en te ontsleutelen na het scannen.  

## Conclusie

Je weet nu hoe je een **PDF417‑barcode** kunt genereren in C# met de Aspose.BarCode‑bibliotheek, compacte modus kunt configureren, het aantal kolommen kunt regelen en het resultaat als PNG‑afbeelding kunt exporteren. Deze tutorial heeft elke stap behandeld, van projectopzet tot het omgaan met randgevallen, en biedt een kant‑en‑klaar oplossing voor barcode‑gedreven toepassingen.

Verken vervolgens gerelateerde onderwerpen zoals **QR‑codes maken in C#**, **batch‑barcode‑generatie**, en **barcode‑scannen integreren in mobiele apps**. Elk van deze bouwt voort op dezelfde `BarcodeGenerator`‑fundamenten die je nu beheerst.

Happy coding!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}