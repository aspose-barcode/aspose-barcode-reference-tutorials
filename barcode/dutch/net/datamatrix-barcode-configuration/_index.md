---
date: 2026-06-09
description: Leer hoe u een datamatrix-barcode genereert met Aspose.BarCode voor .NET,
  pas de beeldverhoudingen, ECC-modusinstellingen en datamatrix c40-codering aan voor
  efficiënte barcodecreatie.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix Barcode Configuratie
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Genereer DataMatrix-barcode – Pro-gids met Aspose.BarCode
url: /nl/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer DataMatrix Barcode – Pro Gids met Aspose.BarCode

Welkom bij onze uitgebreide tutorialreeks over **generate datamatrix barcode** met Aspose.BarCode voor .NET. Of je nu een ervaren ontwikkelaar bent die de barcode-uitvoer fijn afstemt of een nieuwkomer die de basis wil begrijpen, deze gids leidt je door elke stap — van basisconfiguratie tot geavanceerde coderingsmethoden — zodat je betrouwbare, scan‑klare barcodes kunt leveren in elke .NET‑applicatie.

## Snelle Antwoorden
- **Wat is het primaire doel?** Om DataMatrix barcodes programmatisch te maken en aan te passen.  
- **Welke bibliotheek wordt gebruikt?** Aspose.BarCode voor .NET.  
- **Heb ik een licentie nodig?** Een gratis proefversie is beschikbaar; een commerciële licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan ik de beeldverhouding aanpassen?** Ja – zie de “How to customize DataMatrix aspect ratio” sectie.

## Wat is generate datamatrix barcode?
Een DataMatrix barcode is een tweedimensionale matrix van zwarte en witte cellen die tot 2 300 alfanumerieke tekens kan opslaan. Met Aspose.BarCode kun je **generate datamatrix barcode** afbeeldingen, PDF's of SVG's rechtstreeks vanuit je .NET‑code genereren, waarbij je de grootte, fout‑correctieniveau en coderingsmodus regelt om aan elke industriestandaard te voldoen.

## Waarom Aspose.BarCode gebruiken voor DataMatrix?
Aspose.BarCode rendert DataMatrix‑symbolen tot **600 dpi** zonder pixelatie, waardoor scherpe scans op hoge‑resolutieprinters gegarandeerd zijn. Het ondersteunt **alle 50+ ECC‑ en macro‑modi** — inclusief ECC 000‑140, ECC 200 en Macro 05/06 — zodat je het optimale fout‑correctieniveau voor de grootte van je gegevens kunt kiezen. De API biedt **ASCII, C40, Text, X12 en Bytes** coderingsopties, waarmee je gegevens efficiënt kunt verpakken. Integratie vereist slechts één NuGet‑pakket en geen externe native bibliotheken.

## Hoe DataMatrix‑beeldverhouding aanpassen
De `AspectRatio`‑eigenschap van `BarCodeGenerator` bepaalt de breedte‑naar‑hoogte verhouding van het gegenereerde DataMatrix‑symbool. `BarCodeGenerator` is de hoofdklasse in Aspose.BarCode die wordt gebruikt om barcode‑afbeeldingen te maken.

**Direct antwoord:** Stel `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (of een waarde tussen 0,5 en 2,0) in vóór het aanroepen van `GenerateBarCodeImage()`. De bibliotheek herberekent automatisch de module‑grootte om de scanbetrouwbaarheid te behouden terwijl de gevraagde verhouding wordt gerespecteerd.

### Stapsgewijs
1. **Instantiëren** `BarCodeGenerator` met `EncodeTypes.DataMatrix`.  
2. **Aanpassen** `AspectRatio` naar de gewenste waarde.  
3. **Genereren** van de afbeelding en verifiëren met een scanner of de ingebouwde lezer van Aspose.

## Hoe DataMatrix ECC 000‑140 barcodes te genereren
ECC 000‑140 is ideaal voor korte gegevensreeksen waarbij een compact symbool nodig is, en biedt tot 140 fout‑correctiecodewoorden. `DataMatrixEccMode.Ecc000140` selecteert het ECC 000‑140 fout‑correctieschema voor DataMatrix.

**Direct antwoord:** Gebruik `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` vóór het renderen. Dit schakelt de encoder naar het ECC 000‑140 algoritme, waardoor de kleinste mogelijke matrix voor de gegeven gegevens wordt geproduceerd, terwijl toch robuuste foutcorrectie wordt geboden.

### Praktische tip
Bij het coderen van numerieke gegevens onder de 20 tekens levert ECC 000‑140 vaak een 10 × 10 matrix op, wat waardevolle labelruimte bespaart.

## Hoe DataMatrix ECC 200 barcodes te genereren
ECC 200 is de meest gebruikte DataMatrix‑modus, die tot 2 335 alfanumerieke tekens ondersteunt en superieure foutcorrectie biedt. `DataMatrixEccMode.Ecc200` selecteert het ECC 200 fout‑correctieschema voor DataMatrix.

**Direct antwoord:** Stel `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` in en lever je payload via `CodeText`. De bibliotheek selecteert vervolgens automatisch de optimale matrixgrootte.

### Wanneer ECC 200 te verkiezen
Gebruik ECC 200 voor langere strings, gemengde gegevens, of wanneer je de hoogste weerstand tegen schade nodig hebt — tot **30 %** van het symbool kan worden hersteld.

## Hoe DataMatrix‑codering in ASCII te beheersen
ASCII‑modus codeert tekens met één byte per teken, waardoor het de meest ruimte‑efficiënte is voor platte tekst. `DataMatrixEncodeMode.Ascii` instrueert de generator om ASCII‑codering te gebruiken voor het DataMatrix‑symbool.

**Direct antwoord:** Wijs `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` toe en stel `CodeText` in op je ASCII‑string. De engine verpakt de gegevens zonder extra overhead, waardoor de kleinste mogelijke matrix voor pure ASCII‑inhoud wordt geproduceerd.

### Voorbeeldscenario
Een magazijn‑SKU bestaande uit hoofdletters en cijfers (bijv. “AB1234”) past perfect in ASCII‑modus, wat vaak resulteert in een 12 × 12 matrix.

## Hoe DataMatrix‑modus (Auto) te genereren
Auto‑modus laat Aspose.BarCode de invoer analyseren en automatisch de meest efficiënte codering kiezen (ASCII, C40, Text, X12 of Bytes). `DataMatrixEncodeMode.Auto` schakelt deze automatische selectiefunctie in.

**Direct antwoord:** Stel `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto` in. De bibliotheek evalueert de payload, selecteert de optimale modus, en rendert de barcode in één stap.

### Voordelen
Auto‑modus vermindert de ontwikkelingsinspanning en garandeert het kleinste mogelijke symbool voor gemengde gegevens, waardoor de scansnelheid verbetert.

## Hoe DataMatrix‑coderingsmodus (Bytes) te gebruiken
Bytes‑modus is ontworpen voor binaire gegevens, zoals versleutelde payloads of gecomprimeerde bestanden. `DataMatrixEncodeMode.Bytes` instrueert de generator om elke byte als ruwe data te behandelen.

**Direct antwoord:** Gebruik `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` en lever een Base64‑gecodeerde string als `CodeText`. De encoder behandelt elke byte als ruwe data, waardoor de exacte binaire representatie behouden blijft.

### Gebruikssituatie
Een 128‑bit GUID of een klein versleuteld token direct in een DataMatrix‑symbool embedden.

## Hoe DataMatrix‑coderingsmodus (C40) te beheersen
C40‑modus comprimeert hoofdletter‑alfanumerieke gegevens, waardoor tot **40 %** grootte‑reductie ten opzichte van ASCII wordt bereikt. `DataMatrixEncodeMode.C40` activeert dit compressie‑algoritme.

**Direct antwoord:** Stel `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` in en lever een hoofdletter‑string (bijv. “HELLO WORLD”). De engine verpakt drie tekens in twee codewoorden, waardoor de uiteindelijke matrix wordt verkleind.

### Pro‑tip
C40 werkt het beste wanneer de payload voornamelijk bestaat uit hoofdletters, cijfers en spaties. Voor gemengde case, overweeg Auto‑modus.

## Hoe DataMatrix‑code‑tekst te configureren
De `CodeText`‑eigenschap definieert de exacte gegevens die in de barcode worden opgeslagen. Het kan platte tekst, numerieke strings of zelfs XML‑payloads bevatten. `CodeText` is de primaire string‑eigenschap van `BarCodeGenerator` die de barcode‑payload bevat.

**Direct antwoord:** Wijs `generator.Parameters.Barcode.CodeText = "YourDataHere"` toe vóór het renderen. De eigenschap accepteert elke UTF‑8‑string tot de maximale lengte die wordt ondersteund door de gekozen ECC‑modus.

### Geavanceerde tip
Combineer `CodeText` met `ExtendedDataMatrix` om extra metadata in te sluiten zonder de zichtbare matrixgrootte te vergroten.

## Hoe DataMatrix‑macro‑configuratie te beheersen
Macro‑modi (Macro 05 en Macro 06) stellen je in staat een secundair DataMatrix‑symbool in het primaire te embedden, nuttig voor koppeling aan externe gegevensbronnen. `DataMatrixMacroMode.Macro05` en `DataMatrixMacroMode.Macro06` schakelen deze macro‑functies in.

**Direct antwoord:** Schakel macro‑modus in met `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (of `Macro06`) en stel de `MacroPdf417`‑eigenschappen in voor de secundaire payload. De generator maakt een samengesteld symbool dat scanners kunnen interpreteren als twee gekoppelde codes.

### Praktijkvoorbeeld
Een URL embedden in het macro‑gedeelte terwijl productidentifiers in de primaire matrix blijven, waardoor naadloze web‑naar‑barcode‑integratie mogelijk wordt.

*Gebruik Aspose.BarCode voor .NET Tutorials Lijst*

## DataMatrix Barcode Configuratie Tutorials
### [DataMatrix-beeldverhouding aanpassen](./datamatrix-aspect-ratio-customization/)
Leer hoe je DataMatrix barcode-beeldverhoudingen kunt aanpassen met Aspose.BarCode voor .NET. Stapsgewijze gids voor barcode‑generatie.
### [DataMatrix ECC 000-140 barcodes genereren](./datamatrix-ecc-000-140-configuration/)
Maak DataMatrix ECC 000-140 barcodes eenvoudig met Aspose.BarCode voor .NET. Verhoog de efficiëntie in voorraadbeheer en meer.
### [DataMatrix ECC 200 barcodes genereren](./datamatrix-ecc-200-configuration/)
Leer hoe je DataMatrix ECC 200 barcodes genereert in .NET met Aspose.BarCode. Stroomlijn processen met efficiënte barcode‑creatie.
### [DataMatrix-codering in ASCII beheersen](./datamatrix-encoding-mode-ascii/)
Leer DataMatrix barcodes te maken in ASCII‑modus met Aspose.BarCode voor .NET. Stapsgewijze gids voor ontwikkelaars.
### [DataMatrix-modus (Auto) genereren](./datamatrix-encoding-mode-auto/)
Leer hoe je DataMatrix-modus (Auto) genereert met Aspose.BarCode voor .NET. Deze stapsgewijze gids behandelt alles van vereisten tot het lezen van barcodes.
### [DataMatrix-coderingsmodus (Bytes)](./datamatrix-encoding-mode-bytes/)
Leer hoe je gegevens codeert in DataMatrix-formaat met Bytes‑modus met Aspose.BarCode voor .NET. Volg onze stapsgewijze gids voor barcode‑generatie en herkenning.
### [DataMatrix-coderingsmodus (C40) beheersen](./datamatrix-encoding-mode-c40/)
Leer DataMatrix-coderingsmodus (C40) met Aspose.BarCode voor .NET. Maak aangepaste barcodes efficiënt. Verken de stapsgewijze gids.
### [DataMatrix-code-tekst configureren](./datamatrix-extended-code-text-configuration/)
Leer DataMatrix uitgebreide code‑tekst configureren met Aspose.BarCode voor .NET. Genereer, herken en integreer barcodes in je .NET‑applicaties.
### [DataMatrix Macro-configuratie beheersen](./datamatrix-macro-configuration/)
Leer hoe je DataMatrix Macro‑barcodes configureert met Aspose.BarCode voor .NET. Genereer, pas aan en herken DataMatrix‑barcodes in je .NET‑applicaties.

## Veelgestelde Vragen

**V: Hoe bepaal ik welke ECC-modus ik moet gebruiken?**  
A: Kies ECC 000‑140 voor kleine datasets met beperkte foutcorrectie, of ECC 200 voor grotere gegevens en hogere betrouwbaarheid. Macro‑modus voegt een extra gegevenslaag toe voor koppeling.

**V: Kan ik aangepaste tekst embedden in een DataMatrix barcode?**  
A: Ja, stel de `CodeText`‑eigenschap in op je aangepaste string, en selecteer vervolgens de juiste coderingsmodus (ASCII, C40, enz.) om de grootte te beheersen.

**V: Is er een manier om automatisch de beste coderingsmodus te selecteren?**  
A: Stel `EncodeMode` in op `Auto`; Aspose.BarCode evalueert de payload en kiest automatisch de meest ruimte‑efficiënte modus.

**V: Wat zijn de prestatie‑overwegingen voor grote barcode‑batches?**  
A: Hergebruik een enkele `BarCodeGenerator`‑instantie, schakel multi‑threading in, en genereer PNG‑afbeeldingen voor verliesloze kwaliteit of JPEG voor een kleinere bestandsgrootte. Het verwerken van 10 000 symbolen duurt doorgaans minder dan 30 seconden op een standaard 8‑core server.

**V: Ondersteunt Aspose.BarCode .NET Core en .NET 5/6?**  
A: Absoluut – de bibliotheek is volledig compatibel met .NET Framework, .NET Core en de nieuwste .NET‑releases, en biedt dezelfde functionaliteit op alle platforms.

**Laatst bijgewerkt:** 2026-06-09  
**Getest met:** Aspose.BarCode 24.12 for .NET  
**Auteur:** Aspose

## Gerelateerde Tutorials

- [Hoe DataMatrix Barcodes (ECC 200) te genereren met Aspose.BarCode voor .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix-codering in ASCII beheersen met Aspose.BarCode voor .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Barcode PNG maken – DataMatrix-beeldverhouding – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}