---
category: general
date: 2026-09-10
description: Maak snel een barcode‑afbeelding in C# met een barcodegenerator‑voorbeeld
  dat laat zien hoe je de afmetingen instelt en PNG‑bestanden opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: nl
lastmod: 2026-09-10
og_description: Maak een barcode‑afbeelding in C# met een beknopt barcode‑generatorvoorbeeld
  in C#. Leer de grootte, hoogte te configureren en PNG‑bestanden te exporteren in
  enkele minuten.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Barcode-afbeelding maken in C# – stap‑voor‑stap generatorvoorbeeld
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Maak barcode‑afbeelding C# met barcodegenerator‑voorbeeld
url: /nl/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak barcode afbeelding C# met barcode generator voorbeeld

Als je een **barcode afbeelding C#** moet maken voor productetikettering, voorraadbeheer of mobiel scannen, laat deze gids een volledige oplossing zien. Je ziet een **barcode generator voorbeeld C#** dat de modulebreedte, balkhoogte configureert en PNG‑bestanden opslaat in slechts een paar regels code.

De tutorial behandelt alles, van het installeren van de vereiste bibliotheek tot het uitvoeren van een kant‑klaar te compileren console‑programma. Aan het einde heb je twee barcode PNG‑bestanden—een met een balkhoogte van 30 pixel en een met een balkhoogte van 60 pixel—klaar voor gebruik in elke .NET‑applicatie.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Een ontwikkelomgeving zoals Visual Studio 2022 of VS Code  
* Het **Aspose.BarCode** NuGet‑pakket (de code gebruikt `BarcodeGenerator` uit deze bibliotheek)  

Je kunt het pakket toevoegen met het volgende CLI‑commando:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Zet het console‑project op

Maak een nieuw console‑project aan en verwijs naar de barcode‑bibliotheek.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Het commando maakt een `Program.cs`‑bestand aan waarin je de **barcode generator voorbeeld C#**‑code plaatst.

## Stap 2: Schrijf het volledige barcode‑generatieprogramma

Vervang de inhoud van `Program.cs` door het volledige, uitvoerbare voorbeeld hieronder. Het programma laat zien hoe je een **barcode afbeelding C#** maakt met aangepaste afmetingen en hoe je het resultaat opslaat als PNG‑bestanden.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Waarom elke regel belangrijk is

* **EncodeTypes.DatabarOmniDirectional** – selecteert de DataBar Omnidirectional‑symbool, die numerieke gegevens codeert en veel wordt gebruikt in de detailhandel.  
* **XDimension.Pixels = 2** – stelt de modulebreedte in; een kleinere waarde levert een compactere barcode op.  
* **BarHeight.Pixels** – bepaalt de visuele hoogte van de balken. Het aanpassen van deze waarde laat je barcodes maken die passen bij verschillende labelgroottes.  
* **Save‑methode** – schrijft de barcode naar een PNG‑bestand, een formaat dat scherpe randen behoudt en werkt met de meeste beeldbibliotheken.

## Stap 3: Bouw en voer het programma uit

Voer het volgende commando uit vanuit de projectmap:

```bash
dotnet run
```

Wanneer het programma klaar is, zie je twee PNG‑bestanden in de `output`‑submap:

* `DatabarBarHeight30Pixels.png` – 30‑pixel balkhoogte  
* `DatabarBarHeight60Pixels.png` – 60‑pixel balkhoogte  

Beide afbeeldingen bevatten dezelfde gecodeerde data maar verschillen in visuele hoogte, wat laat zien hoe het **barcode generator voorbeeld C#** kan worden aangepast voor verschillende labelvereisten.

## Stap 4: Verifieer de gegenereerde barcodes

Open de PNG‑bestanden met een willekeurige afbeeldingsviewer. Je zou een duidelijke, hoog‑contrast DataBar‑barcode moeten zien. Om te bevestigen dat de barcodes leesbaar zijn, kun je een mobiele scanner‑app gebruiken (bijv. ZXing‑gebaseerde apps) of een desktop‑bibliotheek zoals **Aspose.BarCode** in decode‑modus:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Als de output overeenkomt met `(01)12345678901231`, is de generatie geslaagd.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing | Code‑fragment |
|-----------|------------|--------------|
| **Andere symbologie** (bijv. QR, Code128) | Verander de `EncodeTypes`‑waarde | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Aangepast beeldformaat** (JPEG, BMP) | Gebruik een andere `BarCodeImageFormat`‑enum | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamische data** (gebruikerinvoer) | Vervang de hard‑gecodeerde string door een variabele | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Ongeldige datalengte** | Vang `ArgumentException` op die door de generator wordt gegooid | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Pro tip: valideer altijd de invoerlengte voor de gekozen symbologie; Aspose.BarCode gooit een uitzondering als de data niet aan de specificatie voldoet.

## Checklist voor probleemoplossing

* **Directory not found** – De `SaveBarcode`‑helper maakt de `output`‑map automatisch aan, maar zorg ervoor dat de applicatie schrijfrechten heeft.  
* **Unexpected image size** – Controleer dat `XDimension.Pixels` en `BarHeight.Pixels` zijn ingesteld vóór het aanroepen van `Save`. Het wijzigen van deze waarden na het opslaan heeft geen effect op reeds geschreven bestanden.  
* **Unreadable barcode** – Zorg ervoor dat de gecodeerde string het GS1‑formaat volgt bij het gebruik van DataBar‑symbologieën. Ontbrekende haakjes of onjuiste Application Identifiers veroorzaken decodeerfouten.

## Conclusie

Je weet nu hoe je een **barcode afbeelding C#** maakt met een praktisch **barcode generator voorbeeld C#**. Het volledige programma stelt de modulebreedte in, past de balkhoogte aan en slaat PNG‑bestanden op met minimale code. Vanaf hier kun je extra functies verkennen, zoals kleuraanpassing, multi‑page PDF‑export, of realtime generatie in ASP.NET Core web‑API's.

**Volgende stappen**

* Experimenteer met andere symbologieën (`EncodeTypes.Code128`, `EncodeTypes.QR`) om je scanopties uit te breiden.  
* Integreer de generator in een webservice die barcode‑afbeeldingen op aanvraag retourneert.  
* Combineer de barcode met productmetadata in een PDF‑factuur met behulp van Aspose.PDF.

Veel plezier met coderen, en geniet van de flexibiliteit die C# biedt voor het maken van barcode‑afbeeldingen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode Generator Voorbeeld in C# – Stel kolommen, rijen & exporteer afbeelding](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Maak barcode afbeelding C# – GS1 DataMatrix voorbeeld](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Voorbeeld – Bouw DataBar afbeelding in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}