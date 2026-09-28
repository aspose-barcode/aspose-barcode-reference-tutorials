---
category: general
date: 2026-07-24
description: Barcode Generator C#-tutorial die laat zien hoe je een barcode‑afbeelding
  genereert, kolommen en rijen instelt en een Databar‑barcode maakt in slechts een
  paar regels code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: nl
lastmod: 2026-07-24
og_description: Barcode Generator C#-tutorial leidt je door het genereren van een
  barcode‑afbeelding, het configureren van kolommen en rijen, en het maken van een
  Databar‑barcode met duidelijke codevoorbeelden.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Barcode Generator C# – Maak DataBar gestapelde barcodes snel
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcodegenerator C# – Creëer DataBar Expanded Stacked‑afbeeldingen
url: /nl/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Complete gids voor DataBar Expanded Stacked

Heb je je ooit afgevraagd hoe je **barcode generator c#** kunt gebruiken om in enkele seconden scherpe, scanbare afbeeldingen te genereren? Misschien sta je naar een leeg project te staren, onzeker over waar de kolommen of rijen horen, of hoe je daadwerkelijk *generate barcode image* bestanden kunt maken zonder hoofdpijn. Nou, je bent op de juiste plek. In deze tutorial zetten we een kleine console‑app op, maken we een DataBar Expanded Stacked barcode, passen we de lay‑out aan en slaan we het resultaat op als PNG‑bestanden — allemaal met de **barcode generator c#** bibliotheek.

We behandelen alles wat je moet weten: het installeren van het pakket, het configureren van kolommen en rijen (ja, we beantwoorden *how to set columns* en *how to set rows*), en uiteindelijk hoe je **create databar barcode** objecten maakt die je in facturen, tickets of alles wat een machinaal leesbaar label nodig heeft, kunt plaatsen. Geen externe documentatie nodig; gewoon kopiëren‑plakken, uitvoeren, en je ziet twee PNG‑bestanden in je map verschijnen.

## Wat je nodig hebt

- .NET 6.0 SDK of later (de code werkt op .NET Core, .NET Framework en .NET 5+)
- Een nieuw console‑project (`dotnet new console`) – je kunt ook Visual Studio gebruiken als je een UI prefereert.
- Het Aspose.BarCode for .NET NuGet‑pakket (de bibliotheek die **barcode generator c#** aandrijft). Installeer het met:

```bash
dotnet add package Aspose.BarCode
```

Dat is alles. Zodra het pakket is hersteld, ben je klaar om te starten.

## Barcode Generator C# – Het project opzetten

Laten we eerst de benodigde namespaces importeren en een hulpfunctie maken die onze hoofd‑routine overzichtelijk houdt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Waarom deze structuur werkt

- **Separation of concerns** – elke helper richt zich op één configuratie (kolommen vs. rijen). Dit maakt de code makkelijker leesbaar en herbruikbaar.
- **Explicit parameters** – we geven `columns` of `rows` als argumenten door, zodat je dezelfde methode kunt aanroepen met elke waarde zonder de body aan te passen.
- **Immediate feedback** – `Console.WriteLine` vertelt je precies waar het bestand is opgeslagen, wat handig is wanneer je het programma vanuit een terminal uitvoert.

## Hoe kolommen instellen voor DataBar Expanded Stacked

De `DataBar.Columns`‑eigenschap is de instelling die bepaalt hoeveel verticale segmenten de barcode bevat. Standaard is `4`, maar je hebt misschien `2` of `6` nodig, afhankelijk van de hoeveelheid data die je codeert of de eisen van de scanner. Hier is een kort fragment dat de logica voor het instellen van kolommen isoleert:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** Wanneer je het aantal kolommen vergroot, groeit de totale breedte van de barcode evenredig. Als je van plan bent de afbeelding in een PDF of webpagina in te sluiten, zorg er dan voor dat de container de extra breedte kan opvangen, anders kan de scanner deze verkeerd lezen.

## Hoe rijen instellen voor DataBar Expanded Stacked

Rijen werken op dezelfde manier, maar ze beïnvloeden de hoogte van de barcode. Het standaard aantal rijen is `3`. Als je label beperkte verticale ruimte heeft, kun je het verlagen naar `2`. Omgekeerd kunnen meer rijen de leesbaarheid verbeteren op printers met lage resolutie.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Let op:** Het instellen van rijen op een waarde lager dan het minimum dat nodig is voor de gecodeerde data veroorzaakt een uitzondering tijdens runtime. De bibliotheek gooit een `ArgumentException` met een duidelijke boodschap, zodat je meteen weet of de configuratie ongeldig is.

## Barcode‑afbeelding genereren – Opslaan als PNG

Beide helpers hierboven eindigen met een aanroep van `Save`. De `BarCodeImageFormat.Png`‑enum vertelt Aspose.BarCode om een loss‑less PNG‑bestand te genereren, wat ideaal is voor de meeste scansituaties omdat het scherpe randen behoudt. Als je een ander formaat verkiest (JPEG voor web, BMP voor legacy‑systemen), vervang dan simpelweg de enum‑waarde — er zijn verder geen code‑aanpassingen nodig.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

De gegenereerde PNG‑bestanden zien er als volgt uit (stel je de afbeelding voor; de alt‑tekst hieronder beschrijft het):

> **Alt‑tekst voor de gegenereerde afbeeldingen:** *DataBar Expanded Stacked barcode met 4 kolommen (links) en 3 rijen (rechts), weergegeven in hoog‑contrast zwart op een transparante achtergrond.*

## DataBar barcode maken – Volledig werkend voorbeeld

Alles samenvoegend, hier is een compacte versie die je direct in `Program.cs` kunt plaatsen. Het demonstreert zowel kolom‑ als rij‑configuratie, plus een snelle controle dat de bestanden bestaan na het opslaan.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Verwachte output

Wanneer je het programma uitvoert (`dotnet run`), zie je console‑regels die lijken op:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Open de twee PNG‑bestanden in een willekeurige afbeeldingsviewer; je merkt dat het linkerde bestand vier verticale modules (kolommen) heeft, terwijl het rechter bestand drie modules hoog is (rijen). Beide zijn perfect scanbaar met elke standaard DataBar‑lezer.

## Veelvoorkomende valkuilen & hoe ze te vermijden

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | Kolommen ingesteld op 0 of > 8 (de bibliotheek beperkt tot 8). | Gebruik waarden tussen **1** en **8**. |
| Barcode appears blurry in PDF | PNG opgeslagen met standaard DPI (96) en vervolgens geschaald. | Gebruik `generator.Parameters.ImageResolution = 300;` vóór het opslaan. |
| Scanner fails on rows‑only configuration | Rijen aangepast maar kolommen op de standaardwaarde gelaten die niet overeenkomt met de datalengte. | Pas zowel rijen **als** kolommen samen aan, of laat de bibliotheek automatisch de grootte bepalen door handmatige instellingen weg te laten. |

## Volgende stappen

Nu je weet hoe je **generate barcode image**, **set columns**, **set rows**, en **create databar barcode** kunt doen met **barcode generator c#**, kun je:

- De PNG‑bestanden in PDFs insluiten met `Aspose.PDF` of `iTextSharp`.
- Overschakelen naar `EncodeTypes.DatabarLimited` als je een kleinere footprint nodig hebt.
- Experimenteren met kleuren (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- QR‑codes of andere symbologieën toevoegen in hetzelfde project — Aspose.BarCode ondersteunt meer dan 150 types.

Als je tegen problemen aanloopt, laat dan een reactie achter of raadpleeg de officiële Aspose.BarCode‑documentatie (de API‑referentie is uitgebreid en bevat tientallen live code‑voorbeelden). Veel plezier met coderen, en moge je scanners nooit een markering missen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak DotCode barcode afbeelding – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Maak barcode afbeelding c# – Configureer Codablock F rijen & kolommen](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Genereer barcode afbeelding – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}