---
category: general
date: 2026-07-21
description: Genereer snel barcodes in C# met Aspose.BarCode. Leer hoe je een DataBar-barcode
  maakt, de barcodegrootte aanpast en de barcode-afbeelding exporteert in slechts
  een paar stappen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: nl
lastmod: 2026-07-21
og_description: Genereer barcode C# met Aspose.BarCode. Maak DataBar-barcode, pas
  de grootte aan en exporteer de afbeelding direct.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Barcode genereren in C# – DataBar-barcodes bouwen met aangepaste grootte
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Barcode genereren C# – DataBar‑barcode maken
url: /nl/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode genereren C# – DataBar barcode maken

Op zoek naar **barcode genereren C#** zonder eindeloos door documentatie te ploeteren? Je bent op de juiste plek. In deze gids lopen we stap voor stap door het maken van een **DataBar barcode**, het aanpassen van de afmetingen, en uiteindelijk **het exporteren van de barcode‑afbeelding**—allemaal met een handvol C#‑regels.

Stel je voor dat je een compact productlabel nodig hebt dat op een klein schap‑etiket past. Een DataBar Expanded Stacked‑symbool doet precies dat, en met Aspose.BarCode kun je precies bepalen hoeveel kolommen of rijen het gebruikt. Klaar? Laten we beginnen.

## Wat je gaat bereiken

- **Een DataBar barcode** (de “expanded stacked” variant) van nul af aan maken.  
- **De barcode‑grootte** aanpassen door kolommen of rijen direct in te stellen.  
- **De barcode‑dimensies** on‑the‑fly wijzigen zonder de generator opnieuw op te bouwen.  
- **De barcode‑afbeelding** exporteren naar PNG (of elk formaat dat Aspose ondersteunt).  

Geen externe services, geen rommelige configuraties—alleen nette, uitvoerbare C#‑code.

## Voorwaarden

- .NET 6.0 of hoger (de code werkt ook op .NET Framework 4.7+).  
- Een geldige Aspose.BarCode for .NET‑licentie (of je kunt de trial‑modus gebruiken).  
- Een IDE naar keuze—Visual Studio, Rider, of VS Code volstaat.  

Als je het NuGet‑pakket nog niet hebt geïnstalleerd, voer dan uit:

```bash
dotnet add package Aspose.BarCode
```

Dat is alles—geen andere afhankelijkheden.

## Stap 1: De barcode‑generator instellen (Hoe **barcode genereren C#**)

Eerst hebben we een `BarcodeGenerator`‑instantie nodig die wijst naar de **DataBar Expanded Stacked**‑symbologie. Dit object is de motor die later de afbeelding maakt.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Waarom dit belangrijk is*: De `EncodeTypes.DatabarExpandedStacked`‑enum vertelt Aspose dat we de gestapelde versie willen, wat ideaal is voor smalle ruimtes. De tekst die we doorgeven wordt de gecodeerde waarde; je kunt deze vervangen door elke numerieke string die jouw applicatie nodig heeft.

## Stap 2: **Barcode‑grootte aanpassen** – kolommen instellen

DataBar‑barcodes laten je de visuele dichtheid beïnvloeden door het aantal **kolommen** *of* **rijen** op te geven. Laten we beginnen met kolommen. Het aantal rijen wordt automatisch berekend om de barcode geldig te houden.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Pro tip*: Kolommen bepalen de breedte van de barcode. Meer kolommen → bredere barcode, wat de scanbetrouwbaarheid op laag‑resolutieprinters kan verbeteren.

## Stap 3: **Barcode‑afbeelding exporteren** met de kolominstelling

Nu schrijven we de afbeelding naar schijf. Je kunt PNG, JPEG, BMP, of zelfs SVG kiezen. Hier gebruiken we PNG voor een scherpe, verliesvrije output.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Verwacht resultaat** – Open `DatabarCols4.png` en je ziet een netjes gestapelde DataBar met vier kolommen. Het lijkt op een dichte stapel verticale strepen, perfect voor een klein label.

## Stap 4: **Barcode‑dimensies wijzigen** – rijen instellen

Soms heb je een hogere barcode nodig in plaats van een bredere. Schakel over naar rij‑controle; Aspose rekent de kolommen automatisch opnieuw.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Waarom overschakelen?* Rijen bepalen de hoogte van de barcode. Meer rijen maken het symbool hoger, wat handig kan zijn wanneer je verticale ruimte hebt maar beperkte breedte.

## Stap 5: **Barcode‑afbeelding exporteren** met de rij‑instelling

Sla de tweede variant op. Merk op dat de bestandsnaam de wijziging weergeeft; je kunt beide afbeeldingen ook behouden voor vergelijking.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Resultaat** – `DatabarRows3.png` toont nu een hogere versie van dezelfde data, nog steeds perfect scanbaar.

## Volledig werkend voorbeeld

Alles bij elkaar, hier een zelfstandige console‑app die je kunt kopiëren‑plakken en direct kunt uitvoeren:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Voer het programma uit en open vervolgens de twee PNG‑bestanden. Je hebt nu **barcode genereren C#**, **barcode‑grootte aanpassen**, **barcode‑dimensies wijzigen**, en **barcode‑afbeelding exporteren**—alles in minder dan een minuut.

## Veelgestelde vragen & randgevallen

- **Wat als ik een ander afbeeldingsformaat nodig heb?**  
  Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp`, `Gif` of `Svg`. De API handelt de conversie automatisch af.

- **Kan ik zowel rijen als kolommen tegelijk wijzigen?**  
  Technisch kun je beide instellen, maar Aspose geeft prioriteit aan de laatst aangepaste eigenschap. Het is veiliger om *één* dimensie in te stellen en de bibliotheek de andere laten berekenen voor een geldige DataBar.

- **Hoe pas ik een voor‑/achtergrondkleur toe?**  
  Gebruik `barcodeGen.Parameters.Barcode.ForegroundColor` en `BackgroundColor`. Voorbeeld:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is er een limiet voor de grootte van de te coderen data?**  
  DataBar Expanded Stacked ondersteunt tot 74 numerieke tekens (of 30 alfanumerieke). Overschrijding leidt tot een uitzondering.

## Volgende stappen

Nu je de basis van **databar barcode maken** onder de knie hebt, kun je overwegen:

- **Tekstannotaties** onder de barcode toevoegen (`barcodeGen.Parameters.CaptionAbove.Text`).  
- De PNG direct in een PDF embedden met Aspose.PDF.  
- Barcodes in bulk genereren door over een CSV met product‑ID’s te itereren.

Al deze onderwerpen bouwen voort op hetzelfde `BarcodeGenerator`‑object, zodat je niet opnieuw hoeft te beginnen.

---

**Conclusie**: je weet nu hoe je **barcode genereren C#**, **barcode‑grootte aanpassen**, **barcode‑dimensies wijzigen**, en **barcode‑afbeelding exporteren** met Aspose.BarCode. Speel met de kolom‑/rij‑waarden, wissel afbeeldingsformaten, en integreer de code in je voorraad‑ of POS‑systeem. Veel programmeerplezier!

## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementaties in je eigen projecten te verkennen.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}