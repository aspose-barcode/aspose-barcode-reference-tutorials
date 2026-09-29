---
category: general
date: 2026-09-29
description: Maak een planet barcode in C# met zowel gevulde als lege balken – stapsgewijze
  handleiding met Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: nl
lastmod: 2026-09-29
og_description: Maak snel een planet barcode in C#. Leer hoe je gevulde staven rendert,
  overschakelt naar lege staven en de X‑dimensie aanpast met Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Maak een planeetbarcode met gevulde en lege staven – C#‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hoe maak je een planeetbarcode met gevulde en lege balken
url: /nl/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een planet barcode met gevulde en lege balken

Als je **planet barcode** afbeeldingen in C# moet maken, laat deze gids je precies zien hoe je zowel versies met gevulde balken als lege balken kunt genereren. Je ziet hoe je de balkbreedte (X‑dimension) instelt, de `FilledBars`‑eigenschap schakelt, en de resultaten opslaat als PNG‑bestanden—alles met de Aspose.Barcode‑bibliotheek.

Het genereren van postcodes is een veelvoorkomende eis voor verzendsystemen, mailing‑list‑applicaties en logistieke dashboards. Aan het einde van deze tutorial heb je twee kant‑klaar PNG‑bestanden die je kunt insluiten in rapporten, e‑mails of afdrukken.

## Vereisten

| Vereiste | Waarom het belangrijk is |
|----------|--------------------------|
| .NET 6.0 or later | Biedt de runtime voor het C#‑voorbeeld. |
| Visual Studio 2022 (or any C# IDE) | Staat je toe de code te compileren en uit te voeren. |
| **Aspose.Barcode for .NET** NuGet package | Levert de `BarcodeGenerator`‑klasse en `EncodeTypes.Planet`. Installeer het met `dotnet add package Aspose.Barcode`. |
| Write permission to a folder on disk | De `Save`‑methode schrijft PNG‑bestanden naar het pad dat je opgeeft. |

## Stap 1: Zet het project op en importeer namespaces

Maak een nieuw console‑project (of voeg de code toe aan een bestaand project) en verwijs naar de Aspose.Barcode‑namespace.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Deze `using`‑directieven geven je toegang tot de `BarcodeGenerator`, `EncodeTypes` en image‑format‑enums die nodig zijn voor de tutorial.

## Stap 2: Maak een Planet barcode met standaard (gevulde) balken

De eerste barcode gebruikt de standaard weergave van de bibliotheek, die de balken vult.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Waarom dit werkt:**  
`EncodeTypes.Planet` vertelt Aspose.Barcode om de **Planet**‑symbologie te gebruiken, een postbarcode die wordt gebruikt door de United States Postal Service. De `XDimension`‑eigenschap bepaalt de breedte van elke balk; deze op 4 pixels instellen levert een barcode die goed afdrukt op standaard labelprinters. Standaard is `FilledBars` `true`, waardoor de balken massief verschijnen.

## Stap 3: Maak een Planet barcode met lege balken

Om dezelfde data te genereren met *lege* balken, hoef je alleen de `FilledBars`‑vlag om te zetten terwijl je de andere instellingen identiek houdt.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Waarom dit belangrijk is:**  
Sommige mailingsystemen vereisen de **empty‑bars**‑stijl om de leesbaarheid te verbeteren wanneer de barcode wordt afgedrukt op donkere achtergronden of bij een contrasterend kleurenschema. Door `FilledBars = false` in te stellen, tekent de generator alleen de omtrek van de balken, waardoor het binnenste transparant blijft.

## Verwachte output

Na het uitvoeren van het programma bevat de map `C:\Barcodes` (of het pad dat je hebt gekozen) twee PNG‑bestanden:

| Bestand | Visuele beschrijving |
|---------|----------------------|
| `PlanetFilledBars.png` | Balken zijn massieve zwarte rechthoeken op een witte achtergrond. |
| `PlanetEmptyBars.png`  | Balken zijn zwarte omtrekken; het binnenste van elke balk is transparant (toont de achtergrond). |

Beide afbeeldingen coderen dezelfde numerieke string `"123456"` en hebben een balkbreedte van 4 pixels, waardoor ze er consistent uitzien behalve qua vulstijl.

## Veelvoorkomende variaties en randgevallen

### De balkbreedte aanpassen

Als je labelprinter een andere balkbreedte verwacht, wijzig dan de `XDimension.Pixels`‑waarde. Voor high‑resolution printers kan een waarde van **2** of **3** pixels wenselijk zijn; voor low‑resolution printers kunnen **5** of **6** pixels de scanbetrouwbaarheid verbeteren.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Een ander beeldformaat gebruiken

Aspose.Barcode ondersteunt PNG, JPEG, BMP, GIF en TIFF. Vervang `BarCodeImageFormat.Png` door een andere enum‑waarde om aan te sluiten bij je downstream‑workflow.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Meerdere barcodes genereren in een lus

Wanneer je een batch Planet‑barcodes nodig hebt (bijv. voor een mailing‑list), wikkel je de generatorlogica in een `foreach`‑lus en wijzig je de dataketen bij elke iteratie.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Ongeldige invoer afhandelen

De Planet‑symbologie accepteert alleen numerieke strings van **5‑8** cijfers. Het leveren van een ongeldige waarde veroorzaakt een `ArgumentException`. Bescherm hiertegen met een eenvoudige validatiemethode.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Pro‑tip: Verifieer de barcode met een scanner‑emulator

Aspose.Barcode bevat een `BarcodeReader`‑klasse die je kunt gebruiken om te bevestigen dat de gegenereerde afbeelding terug decodeert naar de oorspronkelijke data.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Als de output `"123456"` toont voor beide bestanden, is de barcode correct gegenereerd.

## Conclusie

Je weet nu hoe je **planet barcode**‑afbeeldingen in C# kunt maken met zowel gevulde als lege balkstijlen, de **Planet barcode XDimension** kunt regelen, en de resultaten in PNG‑formaat kunt opslaan met de **Aspose.Barcode**‑bibliotheek. Pas de balkbreedte aan, wissel van beeldformaat, of loop over een collectie waarden om te passen in elke post‑code workflow.

Next, you might explore:

* **Human‑readable tekst toevoegen** onder de barcode (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Barcodes insluiten in PDF‑documenten** met Aspose.PDF.
* **Andere post‑symbologieën genereren** zoals **USPS POSTNET** of **Intelligent Mail**.

Voel je vrij om te experimenteren met de parameters en de code te integreren in je verzend‑ of mailsysteem. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}