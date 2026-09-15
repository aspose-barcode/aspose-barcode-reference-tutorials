---
category: general
date: 2026-07-27
description: Maak een omnidirectionele barcode‑afbeelding met Aspose.BarCode. Leer
  hoe u een barcode genereert met Aspose, de beeldverhouding aanpast en PNG‑bestanden
  opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: nl
lastmod: 2026-07-27
og_description: Maak een omnidirectionele barcode‑afbeelding met Aspose. Volg deze
  gids om een barcode te genereren met Aspose, pas de beeldverhoudingen aan en exporteer
  PNG‑bestanden.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Maak een omnidirectionele barcode‑afbeelding met Aspose – Stap voor stap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Maak een omnidirectionele barcode‑afbeelding met Aspose – volledige gids
url: /nl/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Omnidirectionele Barcode Afbeelding met Aspose – Volledige Gids

Heb je ooit een **omnidirectionele barcode afbeelding** moeten maken, maar wist je niet welke bibliotheek je moest kiezen? Je bent niet de enige. In veel logistieke en retailprojecten is het DataBar Stacked Omnidirectional‑formaat de geheime saus voor compacte, hoge‑dichtheid codering.  

Het goede nieuws? Met **Aspose.BarCode** kun je die barcode genereren in een handvol regels, de beeldverhouding aanpassen en de PNG direct op schijf wegschrijven. Hieronder zie je precies hoe je **barcode met Aspose genereert**, waarom elke instelling belangrijk is en waar je op moet letten wanneer je de beeldverhouding wijzigt.

---

## Wat Deze Tutorial Behandelt

We lopen de volledige levenscyclus door:

1. Het instellen van de output‑map.
2. Het instantieren van een DataBar Stacked Omnidirectional‑generator.
3. Het configureren van pixelafmetingen en beeldverhoudingen.
4. Het opslaan van de barcode als PNG‑bestanden.
5. Het uitbreiden van het voorbeeld voor andere formaten en randgevallen.

Aan het einde heb je een kant‑klaar C#‑console‑applicatie die twee verschillende barcode‑afbeeldingen produceert. Geen externe tools, alleen pure Aspose‑code.

**Prerequisites**

- .NET 6.0 SDK of later (de code werkt ook op .NET Framework 4.7.2).
- Aspose.BarCode for .NET NuGet‑pakket (`Install-Package Aspose.BarCode`).
- Een map op schijf waar de afbeeldingen geschreven kunnen worden.

Als je deze al hebt, laten we beginnen.

---

## Stap 1: Bereid de Output‑Map Voor

Allereerst moet je het programma vertellen waar de PNG‑bestanden moeten worden opgeslagen. Een hard‑gecodeerd pad werkt voor een demo, maar in productie lees je dit waarschijnlijk uit een configuratie.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Waarom dit belangrijk is:* `Directory.CreateDirectory` is idempotent; het gooit geen fout als de map al bestaat, waardoor je een try‑catch‑blok kunt besparen.

---

## Stap 2: Maak een DataBar Stacked Omnidirectional‑Generator

Nu starten we de generator met het specifieke encode‑type en voorbeelddata. De string `"(01)12345678901231"` volgt de GS1 Application Identifier‑syntaxis voor een 14‑cijferige GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Uitleg:* `EncodeTypes.DatabarStackedOmniDirectional` vertelt Aspose om de omnidirectionele variant te gebruiken, die vanuit elke richting leesbaar is – perfect voor kleine etiketten die mogelijk gedraaid worden.

---

## Stap 3: Stel Algemene Barcode‑Parameters In

Voordat we iets renderen, definiëren we de kleinste elementgrootte (X‑Dimension). Een waarde van **2 pixels** levert een scherp beeld zonder het bestand te laten groeien.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tip:* Als je een hogere resolutie nodig hebt voor afdrukken, verhoog dit naar 3 of 4. Houd er wel rekening mee dat grotere X‑Dimensions zowel breedte als hoogte evenredig vergroten.

---

## Stap 4: Genereer en Sla Op met Beeldverhouding 15

De DataBar‑familie laat je de **beeldverhouding** aanpassen, die de hoogte‑tot‑breedte‑relatie bepaalt. Een beeldverhouding van **15** is een veelgebruikt standaard voor omnidirectionele barcodes.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Wat je zult zien:* Een relatief hoge barcode die nog steeds comfortabel op een 2 × 1 cm‑label past. Het PNG‑formaat behoudt lossless kwaliteit, ideaal voor verdere verwerking of afdrukken.

---

## Stap 5: Verander Beeldverhouding naar 30 en Sla Op Nog Een Keer

Wil je een plattere barcode? Pas simpelweg de `AspectRatio`‑eigenschap aan en roep `Save` opnieuw aan. Het is niet nodig om de generator opnieuw te maken.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Waarom dezelfde generator hergebruiken?* Aspose‑objecten zijn lichtgewicht; een eigenschap wijzigen en opnieuw opslaan is sneller dan een nieuw exemplaar construeren, en het garandeert dat dezelfde coderingsinstellingen (bijv. X‑Dimension) consistent blijven.

---

## Volledig Werkend Voorbeeld

Alles bij elkaar, hier is het complete, zelfstandige programma dat je kunt copy‑pasten in een nieuw console‑project.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt een `Barcodes`‑submap aan met:

- `DatabarAspectRatio15.png` – hoger, klassieke uitstraling.
- `DatabarAspectRatio30.png` – platter, beter voor brede etiketten.

Beide afbeeldingen renderen dezelfde GTIN‑data; alleen de visuele proporties verschillen.

---

## Het Voorbeeld Uitbreiden (Randgevallen & Variaties)

### 1. Verschillende Afbeeldingsformaten

Aspose ondersteunt BMP, JPEG, TIFF en SVG naast PNG. Vervang de enum‑waarde:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG is vector‑gebaseerd, wat betekent dat je het kunt schalen zonder scherpte te verliezen – handig voor responsieve web‑apps.

### 2. Kleuren Aanpassen

Je hebt misschien een witte barcode op een donkere achtergrond nodig. Stel `ForeColor` en `BackColor` in:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Ongeldige Beeldverhoudingen Afhandelen

Aspose valideert het bereik (meestal 5‑50). Als je een waarde buiten dit bereik doorgeeft, wordt een `ArgumentException` gegooid. Plaats de save‑aanroep in een try‑catch om een vriendelijke melding te geven:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Batch‑Generatie

Wanneer je een lijst met GTIN‑s hebt, loop er dan over, werk `CodeText` bij en sla elk bestand op met een unieke naam. Het generator‑object kan hergebruikt worden, waardoor het geheugenverbruik laag blijft.

---

## Veelvoorkomende Valkuilen & Pro‑Tips

- **Vergeet nooit `XDimension`** vóór het opslaan; de standaard (0,33 mm) kan vage beelden opleveren op laag‑resolutie displays.
- **Beeldverhouding is hoogte‑tot‑breedte**, niet andersom. Een groter getal maakt de barcode *korter* verticaal.
- **Bestandspaden:** Gebruik `Path.Combine` om platform‑specifieke scheidingstekens te vermijden – vooral als je code draait in Linux‑containers.
- **Licensing:** Aspose.BarCode is commercieel. In trial‑modus verschijnt er een watermerk op de afbeelding. Registreer vroegtijdig een licentie om verrassingen in productie te voorkomen.

---

## Conclusie

Je weet nu hoe je **omnidirectionele barcode afbeelding** maakt met Aspose, de beeldverhouding aanpast en PNG‑bestanden exporteert – alles in minder dan 30 regels C#. Deze tutorial liet de stap‑voor‑stap‑procedure zien, legde uit waarom elke instelling belangrijk is, en besprak uitbreidingen zoals verschillende formaten, kleuren en batch‑verwerking.

Klaar voor de volgende uitdaging? Probeer QR‑codes te genereren, de barcode in een PDF te embedden, of de output te integreren in een ASP.NET Core API. Dezelfde **generate barcode with Aspose**‑principes gelden voor alle barcode‑typen, zodat je vandaag geleerde kennis direct kunt hergebruiken.

Heb je vragen of wil je je eigen tweaks delen? Laat een reactie achter – happy coding!


## Wat Moet Je Hierna Leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}