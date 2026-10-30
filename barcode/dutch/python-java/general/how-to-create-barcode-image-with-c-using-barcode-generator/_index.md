---
category: general
date: 2026-10-28
description: Maak snel een barcode‑afbeelding in C#. Leer het gebruik van de barcode‑generator
  in C#, hoe je de pixelgrootte instelt en hoe je de beeldverhouding voor DataBar
  wijzigt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: nl
lastmod: 2026-10-28
og_description: Maak een barcode‑afbeelding in C# met een Barcode Generator. Volg
  deze gids om de pixelgrootte in te stellen, de beeldverhouding te wijzigen en DataBar‑barcodes
  te genereren.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Barcode‑afbeelding maken in C# – stapsgewijze handleiding
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Hoe een barcode-afbeelding te maken met C# met behulp van Barcode Generator
url: /nl/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding maken met C# met Barcode Generator

Als je een **barcode‑afbeelding** moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe. Je ziet een compleet, uitvoerbaar voorbeeld dat de Barcode Generator C#‑bibliotheek gebruikt om een DataBar stacked omnidirectional barcode te genereren, de pixelgrootte in te stellen en de beeldverhouding te wijzigen.

Barcodes programmatisch genereren verwijdert de noodzaak voor externe tools en stelt je in staat de afbeelding direct in te sluiten in PDF‑bestanden, rapporten of UI‑besturingselementen. In de onderstaande stappen behandelen we ook **hoe je de pixelgrootte instelt** en **hoe je de beeldverhouding wijzigt**, twee veelvoorkomende eisen wanneer je een scherpe, correct geschaalde barcode nodig hebt.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Een C#‑compatibele IDE (Visual Studio, Rider, of VS Code)  
* Het `BarcodeGenerator` NuGet‑pakket (bijv. `GroupDocs.Barcode` of `Aspose.Barcode`) geïnstalleerd in je project  

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tip:** Controleer of de pakketversie overeenkomt met je doel‑framework om runtime‑incompatibiliteiten te voorkomen.

## Barcode‑afbeelding maken met Barcode Generator C#

De eerste stap is om de generator te instantieren met het gewenste barcode‑type en de data. Het voorbeeld hieronder maakt een **DataBar stacked omnidirectional** barcode, die ideaal is voor retail‑scan‑scenario's.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Waarom elke regel belangrijk is

* **Instantiate `BarcodeGenerator`** – De constructor neemt een barcode‑symbool (`EncodeTypes.DatabarStackedOmniDirectional`) en de ruwe data‑string. Het kiezen van de juiste symbologie zorgt ervoor dat de scanner de code kan lezen.  
* **Set `XDimension.Pixels`** – Deze eigenschap bepaalt de breedte van het kleinste balk‑element. Een waarde van `2` produceert een fijnkorrelig beeld dat op de meeste schermen leesbaar blijft. Verhoog deze waarde als je een grotere barcode nodig hebt voor printers met lage resolutie.  
* **Configure `AspectRatio`** – De DataBar‑familie ondersteunt verschillende beeldverhoudingen die de hoogte‑tot‑breedte‑relatie beïnvloeden. Waarden `15` en `30` zijn gangbaar; `15` levert een kortere barcode op, terwijl `30` een hogere barcode oplevert.  
* **`Save` method** – Slaat de gegenereerde barcode op als een PNG‑bestand. Je kunt `BarCodeImageFormat.Png` vervangen door `Jpeg` of `Bmp` als je downstream‑systeem een ander formaat vereist.

## Hoe de pixelgrootte in te stellen voor verschillende render‑contexten

Pixelgrootte bepaalt de visuele dichtheid van de barcode. Als een barcode wordt weergegeven op een monitor met hoge DPI, kun je de pixelgrootte verhogen naar `3` of `4`. Omgekeerd, voor thermische printers met lage resolutie, vermindert een kleinere pixelgrootte (bijv. `1`) het inktverbruik.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Edge case:** Het instellen van de pixelgrootte te laag (< 1) veroorzaakt een `ArgumentOutOfRangeException`. Valideer de waarde altijd voordat je deze toewijst.

## Hoe de beeldverhouding te wijzigen zonder de generator opnieuw te maken

Het wijzigen van de beeldverhouding is een eenvoudige eigenschaps‑update; je hoeft **niet** de `BarcodeGenerator`‑instantie opnieuw te maken. Dit bespaart geheugen en verbetert de prestaties wanneer je meerdere afbeeldingen met verschillende vormen nodig hebt.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Als je meer dan twee verhoudingen nodig hebt, kun je door een array itereren:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Verwachte output

Het uitvoeren van het programma maakt twee PNG‑bestanden (of meer, als je de lus gebruikt). Open ze in een willekeurige afbeeldingsviewer; je zou een nette DataBar‑barcode moeten zien:

* **DatabarAspectRatio15.png** – korte, brede barcode geschikt voor smalle labelruimtes.  
* **DatabarAspectRatio30.png** – hogere barcode die de scan‑betrouwbaarheid verbetert op schuine scanners.

Beide afbeeldingen hebben dezelfde pixelgrootte (2 px per module) maar verschillen alleen in hoogte, wat **hoe je de beeldverhouding wijzigt** demonstreert terwijl andere parameters constant blijven.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Symptom | Cause | Fix |
|---------|-------|-----|
| Barcode ziet er wazig uit | `XDimension.Pixels` te laag ingesteld voor de uitvoerresolutie | Verhoog de pixelgrootte tot minimaal `2` voor schermweergave, `3` voor afdrukken |
| Scanner kan de code niet lezen | Verkeerde `EncodeTypes` voor het data‑formaat | Controleer of de GTIN‑14 data overeenkomt met de gekozen symbologie |
| `ArgumentOutOfRangeException` bij beeldverhouding | Ratio‑waarde wordt niet ondersteund door de bibliotheek (geldige reeks: 15‑30) | Gebruik alleen waarden die door de bibliotheek zijn gedocumenteerd, of vang de uitzondering op en val terug op een standaardwaarde |
| Bestand niet gevonden na `Save` | Relatief pad wijst naar een niet‑bestaande map | Gebruik een absoluut pad of zorg ervoor dat `Directory.CreateDirectory` eerst wordt aangeroepen |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Volgende stappen – de barcode‑workflow uitbreiden

Nu je een **barcode‑afbeelding** kunt maken, wil je misschien:

* **Embed the PNG into a PDF** using a library like `PdfSharp` or `iTextSharp`.  
* **Generate other symbologies** (QR, Code128, PDF417) by changing the `EncodeTypes` enum.  
* **Apply color transformations** by accessing `barcode.Parameters.Barcode.Image.Color`.  
* **Serve the image via an ASP.NET Core endpoint** for on‑the‑fly generation in web apps.

Elk van deze onderwerpen bouwt voort op dezelfde kernconcepten die in deze tutorial aan bod komen, zoals het gebruik van **barcode generator c#**, pixel‑size controle, en aspect‑ratio manipulatie.

## Conclusie

Je weet nu hoe je **barcode‑afbeelding** kunt **maken** in C# met een Barcode Generator, hoe je de pixelgrootte instelt, hoe je de beeldverhouding wijzigt, en hoe je DataBar‑barcodes efficiënt genereert. Het complete, uitvoerbare voorbeeld kan worden gekopieerd naar elk .NET‑project, aangepast voor andere symbologieën, en uitgebreid om te passen in real‑world workflows.

Voel je vrij om te experimenteren met verschillende `XDimension`‑waarden, beeldverhoudingen en uitvoerformaten. Als je tegen problemen aanloopt, raadpleeg dan opnieuw de tabel “Veelvoorkomende valkuilen” of bekijk de officiële documentatie van de bibliotheek voor diepere configuratie‑opties. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode‑afbeelding te maken en de beeldverhouding aan te passen in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Hoe een barcode met aangepaste grootte te genereren en afbeelding op te slaan in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Hoe een barcode‑generator C# te gebruiken om DataBar‑barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}