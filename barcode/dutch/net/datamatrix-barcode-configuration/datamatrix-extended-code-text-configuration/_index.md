---
date: 2026-09-23
description: Leer hoe u Aspose.BarCode gebruikt om een DataMatrix-barcode met uitgebreide
  code text te genereren in .NET, ideaal voor voorraad- en logistieke toepassingen.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix Uitgebreide Code Text Configuratie
og_description: Hoe u Aspose.BarCode gebruikt om een DataMatrix-barcode met uitgebreide
  code text te genereren in .NET. Volg een snelle stapsgewijze handleiding voor voorraad-
  en logistieke oplossingen.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Hoe u Aspose.BarCode gebruikt om DataMatrix code text te maken in .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Hoe u Aspose.BarCode gebruikt om DataMatrix code text te maken in .NET
url: /nl/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe gebruik je Aspose.BarCode om DataMatrix-codetekst te maken in .NET

Het integreren van barcodes in moderne .NET‑applicaties is geen niche‑taak meer – het is een kernvereiste voor voorraadbeheer, logistiek en mobiele scanoplossingen. In deze gids leer je **hoe je Aspose.BarCode** kunt gebruiken om een DataMatrix‑barcode met uitgebreide codetekst te configureren, de afbeelding te genereren en deze programmatisch te verifiëren. Je ziet waarom deze aanpak ideaal is voor het maken van barcodes voor voorraad en hoe het past in .NET Core of .NET 6‑projecten.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.BarCode for .NET  
- **Welk type barcode?** DataMatrix with extended code text  
- **Kan ik .NET Core / .NET 6 gebruiken?** Yes, the API is cross‑platform  
- **Heb ik een licentie nodig voor testen?** A free trial works for development; a license is required for production  
- **Hoe lang duurt de implementatie?** About 10‑15 minutes for a basic example  

## Wat is Aspose.BarCode voor .NET?
Aspose.BarCode voor .NET is een commerciële bibliotheek die ontwikkelaars in staat stelt meer dan 30 barcode‑symbologieën te genereren en te herkennen, waaronder DataMatrix, QR en Code 128, en afbeeldingen te produceren tot 10.000 × 10.000 pixels zonder externe afhankelijkheden. Het ondersteunt .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6/7.

## Waarom DataMatrix‑uitgebreide codetekst gebruiken?
DataMatrix‑uitgebreide codetekst stelt je in staat meerdere coderingsschema’s—UTF‑8, C40, Text, X12—in één symbool te embedden, waardoor tot **3116 codewoorden** (ongeveer 155 KB aan data) in één compact vierkant passen. Deze mogelijkheid is perfect voor meertalige productetikettering, het volgen van medische apparaten en slimme verpakkingen waar je alfanumerieke ID’s moet combineren met binaire payloads.

## Voorvereisten

Controleer voordat je begint of je het volgende hebt:

1. **Aspose.BarCode for .NET** – download het van de officiële site **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Een .NET‑ontwikkelomgeving** – Visual Studio, Rider, of VS Code met de .NET SDK.  
3. **Basis C#‑kennis** – je moet vertrouwd zijn met klassen, namespaces en de `using`‑directive.

## Namespaces importeren

Voeg de benodigde namespaces toe aan de bovenkant van je C#‑bestand zodat de compiler weet waar de barcode‑klassen te vinden zijn.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Deze namespaces geven je toegang tot zowel barcode‑generatie‑ als herkenningsfuncties.

## Hoe configureer je DataMatrix‑uitgebreide codetekst?

Laad de builder, voeg de gewenste segmenten toe, en laat Aspose.BarCode de ECI‑markers automatisch afhandelen. Deze directe‑antwoordparagraaf geeft je de exacte stappen: maak een `DataMatrixExtCodetextBuilder` aan, voeg Unicode-, C40-, platte‑tekst‑ en Text‑modus‑segmenten toe, en haal vervolgens de gecombineerde string op voor de generator.

### Stap 1: Definieer de uitvoermap

Geef op waar de gegenereerde barcode‑afbeelding moet worden opgeslagen. Vervang de placeholder door een geldig pad op je machine.

```csharp
string path = "Your Directory Path";
```

### Stap 2: Bouw de uitgebreide codetekst

`DataMatrixExtCodetextBuilder` is een hulpprogrammaklasse die de uitgebreide codetekst samenstelt volgens de DataMatrix‑specificatie. Het voegt automatisch de vereiste ECI (Extended Channel Interpretation)‑markers in.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Deze mix toont hoe je Unicode‑tekens, C40‑codering, platte tekst en Text‑modus kunt combineren in één DataMatrix‑symbool.

### Stap 3: Genereer de uiteindelijke codetekst‑string

Na het configureren van alle onderdelen haal je de gecombineerde string op die Aspose.BarCode in de barcode zal embedden.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Stap 4: Maak de DataMatrix‑barcode

`BarcodeGenerator` is de kernklasse die barcode‑afbeeldingen produceert. Instantieer deze met `EncodeTypes.DataMatrix` en de uitgebreide codetekst, en stel vervolgens visuele parameters in zoals X‑dimensie, afbeeldingsformaat en optionele mens‑leesbare tekst.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

De bovenstaande code **maakt een barcode met Aspose .NET** met de gewenste uitgebreide codetekst en slaat deze op als een PNG‑bestand.

### Stap 5: Verifieer de barcode door deze terug te lezen

`BarCodeReader` valideert dat het gegenereerde symbool correct kan worden gedecodeerd, wat essentieel is voor geautomatiseerde test‑pipelines en kwaliteitsborging.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Als alles correct is ingesteld, zal de console de exacte uitgebreide codetekst weergeven die je eerder hebt opgebouwd.

## Veelvoorkomende valkuilen en probleemoplossing

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Barcode niet leesbaar | X‑dimensie te laag | Verhoog `XDimension.Pixels` (bijv., 4 → 6) |
| Vervormde tekens | Verkeerde ECI‑codering | Zorg ervoor dat `ECIEncodings.UTF8` overeenkomt met de tekenset |
| Bestand niet opgeslagen | Ongeldig pad | Gebruik een absoluut pad of zorg dat de map bestaat |
| Licentie‑exception | Trial verlopen | Pas een tijdelijke of volledige licentie toe (zie FAQ) |

## Veelgestelde vragen

### Q1: Wat is Aspose.BarCode voor .NET?
A1: Aspose.BarCode voor .NET is een krachtige bibliotheek die ontwikkelaars in staat stelt een breed scala aan barcode‑symbologieën te genereren en te herkennen, waaronder DataMatrix, QR, Code128 en meer.

### Q2: Waar kan ik de documentatie voor Aspose.BarCode voor .NET vinden?
A2: Je kunt de volledige API‑referentie bekijken **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Is er een gratis proefversie beschikbaar voor Aspose.BarCode voor .NET?
A3: Ja, een gratis proefversie kan worden gedownload van **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Hoe verkrijg ik een tijdelijke licentie voor testen?
A4: Tijdelijke licenties worden verstrekt voor evaluatiedoeleinden en kunnen worden aangevraagd via **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Waar kan ik ondersteuning krijgen of vragen stellen over Aspose.BarCode voor .NET?
A5: Het officiële Aspose.BarCode‑forum is de beste plek om hulp te zoeken: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Laatst bijgewerkt:** 2026-09-23  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/net/datamatrix-barcode-configuration/)
- [Genereer een DataMatrix‑barcode in ASCII‑modus met Aspose.BarCode voor .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Genereer Aztec‑barcode met Tekstcodering met Aspose.BarCode voor .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}