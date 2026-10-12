---
category: general
date: 2026-09-26
description: De barcodegenerator C#‑handleiding laat zien hoe je rijen en kolommen
  instelt bij het maken van Databar Expanded Stacked‑barcodes in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: nl
lastmod: 2026-09-26
og_description: barcode generator C#-tutorial legt uit hoe je rijen en kolommen instelt
  voor Databar Expanded Stacked‑barcodes, met volledige code en tips.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Barcodegenerator C# – stel rijen en kolommen stap voor stap in
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Hoe gebruik je barcodegenerator C# voor rijen en kolommen
url: /nl/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe gebruik je barcode generator C# voor rijen en kolommen

Als je een **barcode generator C#** nodig hebt die je de visuele lay-out van een Databar Expanded Stacked barcode laat beheren, biedt deze tutorial een complete, uitvoerbare oplossing. Je leert **hoe je rijen instelt** en **hoe je kolommen instelt** zodat de gegenereerde afbeelding exact overeenkomt met het ontwerp dat je nodig hebt.

Het programmatisch genereren van barcodes voelt vaak als raden welke eigenschap wat doet. Aan het einde van deze gids begrijp je de API, vermijd je veelvoorkomende valkuilen, en heb je een kant‑klaar code‑voorbeeld dat je in je eigen project kunt kopiëren.

## Vereisten

* .NET 6.0 of later geïnstalleerd (de code werkt ook met .NET Core en .NET Framework)  
* Een referentie naar de barcode‑generatiebibliotheek die `BarcodeGenerator` en `EncodeTypes` levert (bijvoorbeeld Aspose.BarCode, Dynamsoft, of een compatibele SDK)  
* Een IDE zoals Visual Studio of VS Code  
* Schrijfrechten voor een map waar de PNG‑bestanden worden opgeslagen  

Er zijn geen extra NuGet‑pakketten nodig, behalve de barcode‑SDK zelf.

## Barcode generator C# – rijen en kolommen instellen

De volgende secties lopen elke configuratiestap door. De code‑fragmenten zijn volledig en kunnen direct in de `Main`‑methode van een console‑applicatie geplakt worden.

### Stap 1: Maak een generator voor een Databar Expanded Stacked barcode

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Waarom dit belangrijk is:* Het instantieren van `BarcodeGenerator` is de eerste handeling die je uitvoert in elke **barcode generator C#** workflow. De constructor ontvangt het coderings‑type en de gegevensreeks die gecodeerd zal worden.

### Stap 2: Hoe kolommen in te stellen – configureer de barcode om 4 kolommen te gebruiken

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Het instellen van de eigenschap `Columns` wijzigt het aantal verticale modules dat de DataBar gebruikt. Een waarde van `4` creëert een dichtere, compactere barcode, wat handig is wanneer je beperkte horizontale ruimte hebt.

### Stap 3: Sla de barcode‑afbeelding op met de kolominstelling

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft de gegenereerde afbeelding naar de schijf. Controleer het uitvoerbestand om te bevestigen dat de vier‑koloms lay‑out zoals verwacht verschijnt.

![Barcode generator C# voorbeeld dat rijen‑ en kolominstellingen toont](./images/barcode-rows-columns.png)

*De afbeelding hierboven illustreert het resultaat van de kolomconfiguratie.*

### Stap 4: Herinitialiseer de generator voor een andere lay‑out

Wanneer je een aparte barcode met een andere visuele opstelling nodig hebt, maak je een nieuwe instantie in plaats van de vorige te hergebruiken. Dit garandeert dat eerdere instellingen (zoals kolommen) niet doorsluipen in de nieuwe configuratie.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Stap 5: Hoe rijen in te stellen – configureer de barcode om 3 rijen te gebruiken

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

De eigenschap `Rows` regelt de verticale stapeling van de DataBar‑modules. Een lay‑out met drie rijen is de standaard voor veel scanapparaten, maar je kunt deze verhogen voor een hogere gegevensdichtheid.

### Stap 6: Sla de barcode‑afbeelding op die de rij‑instelling bevat

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Open `DatabarRows3.png` om de drie‑rijen‑opstelling te zien. Als de barcode niet scanbaar is, controleer dan de waarden voor rijen/kolommen nogmaals tegen de specificaties van je scanner.

## Volledige broncode – klaar om te kopiëren

Hieronder staat het volledige programma dat alle bovenstaande stappen combineert. Vervang `YOUR_DIRECTORY` door een absoluut of relatief pad dat bestaat op jouw machine.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Verwachte output

Het uitvoeren van het programma genereert twee PNG‑bestanden:

| Bestandsnaam          | Lay‑out beschrijving                     |
|----------------------|-------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked met **4 kolommen** |
| `DatabarRows3.png`   | Databar Expanded Stacked met **3 rijen**    |

Beide afbeeldingen moeten scanbaar zijn met standaard barcode‑lezers die de Databar Expanded Stacked symbologie ondersteunen.

## Veelvoorkomende valkuilen en pro‑tips

| Valkuil                                                          | Waarom het gebeurt                                          | Oplossing / Tip |
|------------------------------------------------------------------|-------------------------------------------------------------|-----------------|
| Het gebruiken van dezelfde `BarcodeGenerator`‑instantie voor zowel rijen als kolommen | De SDK behoudt de vorige configuratie, waardoor het instellen van rijen na kolommen een onverwachte mix kan veroorzaken | Herinitialiseer de generator (zoals getoond in Stap 4) voordat je de andere dimensie wijzigt |
| Vergeten om `EncodeTypes` correct in te stellen                 | De SDK gebruikt standaard een andere symbologie, wat leidt tot een ongeldige barcode | Geef altijd `EncodeTypes.DatabarExpandedStacked` door wanneer je dit specifieke formaat nodig hebt |
| Opslaan naar een niet‑bestaande map                              | `Save` gooit een uitzondering als het pad ongeldig is       | Zorg ervoor dat `YOUR_DIRECTORY` bestaat of gebruik `Directory.CreateDirectory` vóór het aanroepen van `Save` |
| Waarden buiten het toegestane bereik gebruiken (bijv. 0 kolommen) | De SDK valideert het bereik en gooit `ArgumentOutOfRangeException` | Geldige kolomwaarden zijn 1‑4; geldige rijwaarden zijn 1‑3 voor deze symbologie |

### Pro‑tip

Als je veel barcodes moet genereren met variërende rijen en kolommen, wikkel dan de configuratielogica in een hulpfunctie:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Deze aanpak vermindert duplicatie en maakt de code makkelijker te onderhouden.

## Conclusie

Je hebt nu een duidelijk, end‑to‑end voorbeeld van het gebruik van een **barcode generator C#** om zowel het aantal rijen als het aantal kolommen in een Databar Expanded Stacked barcode te beheersen. Door de bovenstaande stappen te volgen, kun je precieze barcode‑afbeeldingen genereren die exact voldoen aan de lay‑outvereisten van je scanhardware.

Vanaf hier kun je verder verkennen:

* Andere `DataBar`‑eigenschappen aanpassen, zoals **AspectRatio** of **BarHeight**
* Andere symbologieën genereren (bijv. QR, Code128) met dezelfde `BarcodeGenerator`‑klasse
* De gegenereerde PNG in PDFs insluiten of direct vanuit C# afdrukken

Voel je vrij om te experimenteren met verschillende rij‑/kolomcombinaties, en deel je resultaten in de reacties. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe kolommen in te stellen voor een Databar Expanded Stacked barcode – volledige C# gids](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode gids – hoe te genereren en te dimensioneren in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator voorbeeld in C# – Kolommen, rijen instellen & afbeelding exporteren](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}