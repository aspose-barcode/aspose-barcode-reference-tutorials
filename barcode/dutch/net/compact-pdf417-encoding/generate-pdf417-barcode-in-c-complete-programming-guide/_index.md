---
category: general
date: 2026-07-18
description: Genereer PDF417‑barcode snel. Leer hoe je linked‑mode instelt en hoe
  je een PDF417‑barcode genereert met Aspose.BarCode in een duidelijke stap‑voor‑stap‑tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: nl
lastmod: 2026-07-18
og_description: Genereer direct een PDF417‑barcode. Deze tutorial laat zien hoe je
  de gelinkte modus instelt en hoe je een PDF417‑barcode genereert met Aspose.BarCode,
  compleet met uitvoerbare code.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: PDF417-barcode genereren in C# – Volledige stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: PDF417-barcode genereren in C# – Complete programmeergids
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417‑barcode genereren in C# – Complete programmeergids

Heb je ooit een **PDF417‑barcode moeten genereren** in een .NET‑app, maar wist je niet waar je moest beginnen? Je bent niet de enige. Of je nu een boarding‑pass‑printer, een magazijnscanner bouwt, of gewoon experimenteert met 2‑D‑barcodes, een PDF417‑barcode laten werken is makkelijker dan je denkt.

In deze gids lopen we stap voor stap door hoe je **PDF417‑barcode genereert** met Aspose.BarCode, laten we **zien hoe je linked‑mode instelt**, en behandelen we **hoe je PDF417‑barcode genereert** met aangepaste parameters — alles in één copy‑paste‑klaar voorbeeld.

## Wat je zult leren

- Het minimale NuGet‑pakket dat je nodig hebt.  
- Hoe je de PDF417‑generator initialiseert met je eigen tekst.  
- **Hoe je linked‑mode instelt** zodat de barcode over meerdere rijen kan lopen.  
- Extra tweaks zoals module‑grootte en kolomaantal.  
- Hoe je het resultaat opslaat als PNG, JPEG of een ander ondersteund formaat.  
- Veelvoorkomende valkuilen en snelle probleemoplossingstips.

### Vereisten

- .NET 6.0 of hoger (de code werkt ook op .NET Framework 4.7+).  
- Basiskennis van C#.  
- Visual Studio 2022 (of een andere IDE naar keuze).  
- Een gratis Aspose.BarCode‑trial of een gelicentieerde versie.

> **Pro tip:** Als je op een nieuwe machine werkt, voer `dotnet add package Aspose.BarCode` uit in de terminal binnen je projectmap. Het haalt alles binnen dat je nodig hebt.

---

## Stap 1: Installeer Aspose.BarCode en voeg namespaces toe

Allereerst — laten we de bibliotheek in het project opnemen.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Voeg vervolgens bovenaan je C#‑bestand de benodigde namespaces toe:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Waarom dit belangrijk is:** Zonder de `Aspose.BarCode.Generation`‑namespace heb je geen toegang tot `BarcodeGenerator`, en de `System.Drawing.Imaging`‑namespace levert de `ImageFormat`‑enum voor het opslaan van bestanden.

---

## Stap 2: Initialiseert de PDF417‑barcode‑generator

Nu maken we een generator‑instance en voeren we de tekst in die we willen coderen. Dit is de kern van **hoe je PDF417‑barcode genereert**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Uitleg:** `EncodeTypes.Pdf417` vertelt Aspose dat we met een PDF417‑symbool werken. Het tweede argument, `"Aspose"`, is de data die verschijnt wanneer de barcode wordt gescand.

---

## Stap 3: Definieer de module‑grootte (X‑dimensie)

De module‑grootte bepaalt hoe groot elk klein vierkantje (of “pixel”) van de barcode wordt weergegeven. Lagere waarden geven een compactere barcode; hogere waarden maken hem beter leesbaar op printers met lage resolutie.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Typisch bereik:** 1–4 pixels werkt voor de meeste schermen. Als je op een high‑DPI‑etiketprinter print, verhoog dit dan naar 3 of 4.

---

## Stap 4: Configureer kolommen en schakel linked‑mode in

Hier beantwoorden we **hoe je linked‑mode instelt**. Linked‑mode laat een PDF417‑barcode over meerdere rijen splitsen, wat handig is wanneer je beperkte horizontale ruimte hebt.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Waarom linked‑mode?** Stel je voor dat de barcode in een smal UI‑element moet passen. Met `IsLinked = true` breekt de bibliotheek het symbool automatisch in rijen, terwijl de scanbaarheid behouden blijft.  

> **Randgeval:** Als je `Columns` te laag zet én linked‑mode inschakelt, kan Aspose het aantal rijen sterk laten toenemen, waardoor een klein afbeeldingscanvas kan overlopen. Houd de uiteindelijke afbeeldingsafmetingen in de gaten.

---

## Stap 5: Sla de barcode‑afbeelding op

Tot slot schrijven we de barcode naar een bestand. Je kunt kiezen voor PNG, JPEG, BMP of zelfs PDF. PNG is lossless, waardoor het ideaal is voor verdere verwerking.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Resultaat:** Je krijgt een scherpe PDF417‑barcode met drie kolommen, een module‑grootte van 2 pixels, en linked‑rijen als de data breder is dan één rij.

---

## Volledig werkend voorbeeld

Hieronder staat het complete, kant‑en‑klaar programma. Kopieer‑plak het in een nieuw console‑project (`dotnet new console`) en druk op **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Verwachte output

Het uitvoeren van het programma geeft een bevestigingsregel weer, en de map bevat nu `Pdf417Linked.png`. Het openen van de PNG toont een drie‑koloms PDF417‑barcode die mogelijk over twee rijen loopt (dankzij linked‑mode). Scannen met een smartphone‑app onthult de tekst **“Aspose”**.

---

## Veelgestelde vragen & probleemoplossing

### 1. *Wat als de barcode er onscherp uitziet?*  
Meestal een DPI‑probleem. Verhoog `XDimension.Pixels` of sla de afbeelding op met een hogere resolutie via `generator.Save(..., BarCodeImageFormat.Png, 300)` waarbij `300` de DPI is.

### 2. *Kan ik langere strings coderen?*  
Ja — PDF417 kan tot ~1.850 tekens bevatten. Als je de capaciteit van het gekozen kolomaantal overschrijdt, voegt de bibliotheek automatisch rijen toe. Pas `Columns` aan of schakel `IsLinked` in om de barcode compact te houden.

### 3. *Heb ik een licentie nodig voor productie?*  
Aspose.BarCode werkt in evaluatiemodus, maar de gegenereerde barcode krijgt een klein watermerk. Koop een licentie om dit te verwijderen en geavanceerde functies zoals het aanpassen van het foutcorrectieniveau te ontgrendelen.

### 4. *Hoe genereer ik PDF417‑barcode in andere formaten?*  
Verander simpelweg het tweede argument van `Save`. Voor JPEG gebruik je `BarCodeImageFormat.Jpeg`; voor PDF `BarCodeImageFormat.Pdf`.

---

## Het voorbeeld uitbreiden

Nu je weet **hoe je PDF417‑barcode genereert** en **hoe je linked‑mode instelt**, kun je experimenteren met:

- **Error‑correction level** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`  
- **Een rand toevoegen** – `generator.Parameters.Barcode.BorderWidth = 1;`  
- **Aangepaste kleuren** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`  
- **De barcode in een PDF‑rapport embedden** – combineer Aspose.PDF met Aspose.BarCode.

Elk van deze tweaks volgt hetzelfde patroon: zoek de juiste eigenschap onder `generator.Parameters.Barcode.Pdf417` (of het generieke `Barcode`‑object) en stel een waarde in.

---

## Conclusie

We hebben alles behandeld wat je nodig hebt om **PDF417‑barcode te genereren** in C#, van het installeren van Aspose.BarCode tot het configureren van linked‑mode en het opslaan van de afbeelding. Door de bovenstaande stappen te volgen, heb je een productie‑klare barcode‑generator die in elke .NET‑oplossing kan worden geïntegreerd.

Onthoud de belangrijkste punten:

1. Initialiseert met `EncodeTypes.Pdf417`.  
2. Pas `XDimension` aan voor visuele helderheid.  
3. Stel `Columns` in en schakel `IsLinked` in om de layout te regelen (**hoe je linked‑mode instelt**).  
4. Sla op in het gewenste formaat.

Voel je vrij om met de extra parameters te experimenteren, en aarzel niet om je resultaten te delen of vragen te stellen in de reacties. Veel programmeerplezier, en moge je barcodes altijd bij de eerste poging scannen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)  
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}