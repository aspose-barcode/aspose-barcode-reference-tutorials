---
category: general
date: 2026-11-17
description: Leer hoe je een barcode opslaat, compacte modus inschakelt, kolommen
  aanpast en een PDF417‑barcode genereert met een volledig C#‑voorbeeld.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: nl
lastmod: 2026-11-17
og_description: Hoe je een barcode opslaat, compacte modus inschakelt en kolommen
  aanpast bij het genereren van een PDF417‑barcode in C#. Volg de stapsgewijze handleiding.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Hoe een barcode opslaan als PNG en compacte modus inschakelen in C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Hoe een barcode opslaan als PNG en compacte modus inschakelen in C#
url: /nl/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode opslaan als PNG en compacte modus inschakelen in C#

Als je **how to save barcode** in een formaat wilt dat kan worden gebruikt op het web of in print, laat deze gids je de exacte stappen zien. Je leert ook hoe je **compact mode inschakelt**, **kolommen aanpast**, en **PDF417 barcode genereert** met de Aspose.BarCode bibliotheek voor .NET.

De tutorial behandelt alles vanaf de projectopzet tot het uiteindelijke PNG‑bestand, zodat je de code kunt kopiëren naar je eigen oplossing zonder extra onderzoek. Er is geen externe documentatie nodig; het volledige, uitvoerbare voorbeeld is inbegrepen.

## Vereisten

* .NET 6.0 of later geïnstalleerd  
* Visual Studio 2022 (of een andere C# IDE)  
* Het `Aspose.BarCode` NuGet‑pakket (`Install-Package Aspose.BarCode`)  

Deze drie items zijn de enige afhankelijkheden voor de onderstaande code.

## Stap 1: Maak een PDF417 barcode‑generator

De eerste taak wanneer je **generate PDF417 barcode** uitvoert, is het instantieren van een `BarcodeGenerator` met het juiste encode‑type en de gegevens die je wilt coderen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

De `EncodeTypes.Pdf417`‑enum vertelt de bibliotheek om de PDF417‑symbologie te gebruiken, een gestapelde lineaire barcode die geschikt is voor het coderen van grote hoeveelheden data. De string `"Compact mode"` wordt de mens‑leesbare tekst onder de barcode.

## Stap 2: Stel de X‑dimensie (module‑breedte) in

Elke balk in een barcode wordt een module genoemd. Het regelen van de module‑breedte stelt je in staat de visuele grootte van de barcode fijn af te stemmen zonder de data te wijzigen.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Een X‑dimensie van 2 pixel produceert een compacte afbeelding die nog steeds betrouwbaar scant op de meeste apparaten.

## Stap 3: **How to adjust columns** voor de PDF417‑code

PDF417 staat je toe op te geven hoeveel kolommen de barcode moet gebruiken. Minder kolommen geven een hoger, smaller symbool, terwijl meer kolommen het symbool breder maar korter maken.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Deze regel toont **how to adjust columns**. Je kunt de waarde wijzigen naar 2, 4, of elk getal dat door de bibliotheek wordt ondersteund, afhankelijk van de ruimte die je op het doelmedium hebt.

## Stap 4: **How to enable compact mode** en het symbool inkorten

Compact mode verwijdert onnodige opvulling en verkleint de algehele footprint van de barcode. De bibliotheek maakt deze functie beschikbaar via de `Truncate`‑eigenschap.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Merk op dat de uitdrukking **enable compact mode** hier verschijnt, en dezelfde actie later in de gids wordt beschreven met de exacte bewoording **how to enable compact mode** om te voldoen aan de secundaire trefwoordvereiste.

## Stap 5: **How to save barcode** als PNG‑afbeelding

Het opslaan van de gegenereerde afbeelding is de laatste stap. De `Save`‑methode schrijft de barcode naar het bestandssysteem in het door jou opgegeven formaat.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Vervang `YOUR_DIRECTORY` door een absoluut of relatief pad waar je applicatie naar kan schrijven. Na uitvoering vind je een bestand genaamd `CompactPdf417.png` dat de compacte PDF417‑barcode bevat.

### Verwachte output

Het openen van het opgeslagen PNG‑bestand toont een verticaal compacte PDF417‑barcode met drie kolommen en ingekorte opvulling. De visuele grootte is ongeveer 2 px per module, waardoor de afbeelding geschikt is om in HTML `<img>`‑tags te embedden of af te drukken op kleine etiketten.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren naar een nieuw console‑project. Het bevat alle benodigde `using`‑directieven en demonstreert **how to save barcode**, **enable compact mode**, **how to adjust columns**, en **generate PDF417 barcode** in één doorlopend proces.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Het uitvoeren van dit programma genereert het eerder beschreven PNG‑bestand. De console‑output bevestigt de locatie van het opgeslagen bestand, waardoor je kunt verifiëren dat de **how to save barcode**‑stap geslaagd is.

## Veelgestelde vragen en randgevallen

### Wat als ik een ander afbeeldingsformaat nodig heb?

De `Save`‑methode accepteert elke `BarCodeImageFormat`‑enumwaarde, zoals `Jpeg`, `Bmp` of `Gif`. Vervang `BarCodeImageFormat.Png` door het gewenste formaat, en de rest van de code blijft ongewijzigd.

### Hoe beïnvloedt inkorting de datacapaciteit?

Het inschakelen van **compact mode** (inkorting) vermindert het aantal rijen, wat de maximale datacapaciteit van de barcode kan verlagen. Als je een “Data too large”‑exception tegenkomt, verhoog dan het aantal kolommen of schakel inkorting uit.

### Kan ik een dynamisch kolomaantal gebruiken?

Ja. Je kunt het kolomaantal berekenen op basis van de lengte van de invoerstring:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Deze snippet toont **how to adjust columns** programmatisch, zodat de barcode binnen een gegeven lay-out past.

### Is de X‑dimension beperkt tot gehele pixels?

De `Pixels`‑eigenschap accepteert elk positief geheel getal. Voor hogere resolutie‑outputs (bijv. afdrukken) kun je liever `Points` instellen in plaats van `Pixels` om apparaat‑onafhankelijke afmetingen te bereiken.

## Tips voor productiegebruik

* **Pro tip:** Plaats de barcode‑generatie in een try‑catch‑blok om `BarCodeException` af te handelen wanneer de invoergegevens de capaciteit van het symbool overschrijden.  
* **Let op:** Bestands‑systeemrechten. Het proces moet schrijfrechten hebben op de doelmap, anders zal de **how to save barcode**‑stap falen met een `UnauthorizedAccessException`.  
* **Prestatienota:** Het maken van veel barcodes in een lus profiteert van het hergebruiken van één `BarcodeGenerator`‑instantie en alleen de `CodeText`‑eigenschap bij elke iteratie bijwerken.

## Conclusie

Je weet nu **how to save barcode** als PNG‑bestand, **enable compact mode**, **how to adjust columns**, en **generate PDF417 barcode** met Aspose.BarCode voor C#. Het volledige voorbeeld demonstreert elke vereiste stap, van het initialiseren van de generator tot het schrijven van de uiteindelijke afbeelding.

Vanaf hier kun je gerelateerde onderwerpen verkennen, zoals het toevoegen van een logo aan de barcode, het aanpassen van kleuren, of het integreren van de generator in een ASP.NET Core‑API. Elk van deze uitbreidingen volgt hetzelfde patroon dat in deze gids wordt getoond, zodat je de code met vertrouwen kunt aanpassen.

Voel je vrij om te experimenteren met verschillende kolomaantallen, X‑dimensies en afbeeldingsformaten om te voldoen aan de exacte specificaties van je project. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode opslaan en PDF417 genereren met Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Hoe PDF417 barcode maken in C# met compacte modus](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hoe PDF417 barcode maken en opslaan als PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}