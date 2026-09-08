---
date: 2026-09-08
description: Leer hoe je een code 128 barcode maakt en GS1 barcodes genereert in C#
  met Aspose.BarCode voor .NET. Stapsgewijze handleiding, vereisten en code‑vrije
  aanpassing.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 voorbeeld
og_description: Leer hoe je een code 128 barcode maakt en GS1 barcodes genereert in
  C# met Aspose.BarCode voor .NET. Volg een stapsgewijze handleiding om barcode‑afbeeldingen
  snel te genereren en op te slaan.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Hoe maak je een code 128 barcode met GS1 met behulp van Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Hoe maak je een code 128 barcode met GS1 met behulp van Aspose.BarCode
url: /nl/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een code 128 barcode met GS1 met Aspose.BarCode

In deze tutorial leer je hoe je **een code 128 barcode** maakt die voldoet aan de GS1‑standaard met behulp van de Aspose.BarCode‑bibliotheek voor .NET. Of je nu een barcode nodig hebt voor voorraad, verzending of point‑of‑sale, deze gids leidt je stap voor stap—van het opzetten van de ontwikkelomgeving tot het opslaan van de uiteindelijke afbeelding—zodat je binnen enkele minuten betrouwbare barcodes kunt genereren.

## Snelle antwoorden
- **Wat is de primaire klasse om een barcode te genereren?** `BarcodeGenerator` maakt en configureert de barcode‑afbeelding.  
- **Welke symbologie gebruikt GS1 Code 128?** Het gebruikt het type `EncodeTypes.Code128` met GS1‑specifieke gegevensopmaak.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik het afbeeldingsformaat wijzigen?** Ja—sla op als PNG, JPEG, BMP of TIFF door de bestandsextensie te veranderen.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ en .NET 6+.

## Wat is een code 128 barcode?
`create code 128 barcode` verwijst naar het genereren van een lineaire barcode die alfanumerieke gegevens codeert met de Code 128‑symbologie, die breed wordt toegepast in de logistiek omdat hij de volledige ASCII‑set ondersteunt en GS1 Application Identifiers kan bevatten. De barcode kan product‑identifiers, serienummers en andere aangepaste gegevens opslaan, waardoor hij geschikt is voor een breed scala aan zakelijke scenario’s.

## Waarom Aspose.BarCode gebruiken voor GS1 Code 128?
Aspose.BarCode ondersteunt **meer dan 30 barcode‑symbologieën** en kan afbeeldingen renderen tot **10.000 × 10.000 px** zonder kwaliteitsverlies, waardoor hij geschikt is voor hoge‑resolutie‑label‑afdrukken. De bibliotheek valideert GS1‑gegevensstructuren automatisch, waardoor het risico op foutieve barcodes in productielijnen wordt verminderd. Bovendien biedt hij uitgebreide aanpassingsopties voor grootte, kleur en lay‑out, wat helpt om te voldoen aan strenge industrienormen.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **.NET‑ontwikkelomgeving** – Visual Studio 2022, Rider of een IDE die .NET 6+ ondersteunt.  
2. **Aspose.BarCode voor .NET** – download deze van de **Aspose.BarCode voor .NET downloadpagina** op [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) en voeg het NuGet‑pakket `Aspose.BarCode` toe aan je project.  
3. **Basiskennis van C#** – je moet vertrouwd zijn met het maken van console‑ of Windows‑applicaties.  
4. **Begrip van GS1 Code 128** – optioneel maar nuttig; GS1 gebruikt Application Identifiers (AIs) zoals `(01)` voor GTIN en `(21)` voor serienummers.

## Hoe maak je stap voor stap een code 128 barcode

Laad de bibliotheek, configureer het barcode‑type, stel GS1‑gegevens in, pas afmetingen aan en sla tenslotte de afbeelding op. Het directe antwoord op de vraag “hoe maak je een code 128 barcode?” is: **instantieer `BarcodeGenerator` met `EncodeTypes.Code128` en GS1‑geformatteerde gegevens, pas `XDimension` aan indien nodig, en roep vervolgens `Save` aan met de gewenste bestandsnaam en -formaat**. De volgende secties splitsen elke stap uit.

### Stap 1: stel je mappad in
Definieer de map waar de gegenereerde afbeelding wordt opgeslagen. Het configureerbaar houden van het pad maakt de code herbruikbaar in verschillende omgevingen.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Vervang `"Your Directory Path"` door een absoluut of relatief pad waar je applicatie naar kan schrijven, bijvoorbeeld `@"C:\Barcodes"` of `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Stap 2: maak een GS1 Code 128 barcode
Maak de barcode‑generator, specificeer de symbologie en lever GS1‑geformatteerde gegevens. De gegevensreeks moet Application Identifiers bevatten die tussen haakjes staan.

```csharp
string path = "Your Directory Path";
```

Het voorbeeld gebruikt de GTIN `(01)12345678901231`, een serienummer `(21)ASPOSE` en een extra aangepaste AI `(30)9876`. Aspose.BarCode voegt automatisch het vereiste FNC1‑teken toe voor GS1‑conformiteit.

### Stap 3: pas barcode‑parameters aan
Pas visuele parameters aan, zoals `XDimension` (de breedte van de smalle balk) om de dichtheid van de barcode te regelen. Je kunt ook hoogte, kleuren en marges aanpassen.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Het instellen van `XDimension = 2` levert een barcode op die gemakkelijk leesbaar is voor de meeste handscanners, terwijl de afbeeldingsgrootte bescheiden blijft.

### Stap 4: sla de barcode‑afbeelding op
Sla de gegenereerde barcode op schijf op. Je kunt kiezen voor PNG voor verliesvrije kwaliteit, JPEG voor kleinere bestanden, of TIFF voor afdruk‑workflows. De `Save`‑methode schrijft het afbeeldingsbestand in het formaat dat door de bestandsextensie wordt aangegeven.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Vervang `GS1Code128Example.png` door een geldige bestandsnaam en extensie die overeenkomt met het gewenste uitvoerformaat.

### Stap 5: controleer de barcode (optioneel)
Na het opslaan kun je de afbeelding terug in je applicatie laden of een barcodescanner gebruiken om te bevestigen dat de gecodeerde gegevens overeenkomen met de oorspronkelijke string. Deze stap is nuttig tijdens ontwikkeling en geautomatiseerd testen.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Veelvoorkomende problemen en tips voor probleemoplossing
- **FNC1 niet gedetecteerd** – Zorg ervoor dat de gegevensreeks begint met een openingshaakje en geldige GS1‑AIs bevat; de bibliotheek voegt FNC1 alleen automatisch in voor herkende patronen.  
- **Afbeelding niet opgeslagen** – Controleer of de doelmap bestaat en de applicatie schrijfrechten heeft. Gebruik `Directory.CreateDirectory(path)` om deze on‑the‑fly aan te maken.  
- **Barcode te dicht** – Verlaag `XDimension` of vergroot de afbeeldingshoogte om scanners meer ruimte te geven om smalle balken te lezen.  
- **Niet‑ondersteunde tekens** – Code 128 kan alleen de volledige ASCII‑set coderen; vermijd Unicode‑tekens buiten dit bereik.

## Veelgestelde vragen

**Q:** Kan ik barcodes genereren in een web‑API zonder het volledige .NET Framework te installeren?  
**A:** Ja, Aspose.BarCode werkt met .NET Core en .NET 5/6, zodat je een lichte REST‑endpoint kunt aanbieden die barcode‑afbeeldingen on‑demand retourneert.

**Q:** Ondersteunt de bibliotheek batch‑generatie van meerdere barcodes?  
**A:** Absoluut. Loop door een collectie van gegevensreeksen, instantieer een `BarcodeGenerator` voor elk, en roep `Save` aan binnen de lus. De bibliotheek is thread‑safe voor parallelle verwerking.

**Q:** Is er een manier om de barcode direct in een PDF te embedden?  
**A:** Gebruik Aspose.PDF om een PDF‑document te maken, en roep vervolgens `PdfPage.AddImage` aan met de barcode‑afbeeldingsstroom. Dit voorkomt het schrijven van tussenliggende bestanden naar schijf.

**Q:** Hoe kan ik ervoor zorgen dat de barcode voldoet aan de ISO/GS1‑kwaliteitsnormen?  
**A:** Stel `BarcodeGenerator.Options.Barcode.XDimension` in op minimaal 0,33 mm en stel `BarHeight` in volgens de labelgrootte. Aspose.BarCode valideert het AI‑formaat en gooit een uitzondering bij ongeldige gegevens.

**Q:** Welke licentie‑opties zijn beschikbaar voor productiegebruik?  
**A:** Aspose biedt eeuwigdurende, abonnements‑ en cloud‑gebaseerde licentiemodellen. Een proeflicentie werkt voor evaluatie, maar een betaalde licentie verwijdert het proef‑watermerk en ontgrendelt alle functies.

## Aanvullende bronnen

- **[Documentatie]** – Toegang tot de volledige API‑referentie op [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **[Download]** – Haal de nieuwste bibliotheekversie op van [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **[Gratis proefversie]** – Start een 30‑daagse proefversie op [https://releases.aspose.com/](https://releases.aspose.com/).  
- **[Aankoop]** – Koop een commerciële licentie via [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **[Ondersteuning]** – Word lid van het community‑forum op [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) voor hulp bij probleemoplossing.

---

**Laatst bijgewerkt:** 2026-09-08  
**Getest met:** Aspose.BarCode 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/net/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}