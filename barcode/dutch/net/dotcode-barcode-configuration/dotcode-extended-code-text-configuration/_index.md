---
date: 2026-09-28
description: Leer hoe je een 2D-matrixbarcode maakt met Aspose.BarCode voor .NET –
  een stapsgewijze handleiding voor het genereren van DotCode-barcodes met uitgebreide
  code-tekst.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode Uitgebreide Code-tekst Configuratie
og_description: Leer hoe je een 2D-matrixbarcode maakt met Aspose.BarCode voor .NET.
  Deze handleiding toont stap-voor-stap hoe DotCode-barcodes met uitgebreide code-tekst
  te genereren.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Maak een 2D-matrixbarcode met Aspose.BarCode voor .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Hoe maak je een 2D-matrixbarcode via Aspose.BarCode voor .NET
url: /nl/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een 2d matrix barcode via Aspose.BarCode voor .NET

## Introductie

Op het gebied van barcode‑generatie en -beheer valt Aspose.BarCode voor .NET op als een veelzijdige oplossing die **meer dan 50 invoer‑ en uitvoerformaten** ondersteunt en documenten van meerdere honderden pagina's kan verwerken zonder het volledige bestand in het geheugen te laden. Of je nu barcodes nodig hebt voor producttracking, voorraadbeheer of data‑rijke toepassingen, het maken van een **2d matrix barcode** zoals DotCode met uitgebreide codetext stelt je in staat zowel tekstuele als binaire payloads in een compact vierkant symbool te embedden. Deze tutorial leidt je stap‑voor‑stap door het bouwen van die uitgebreide codetext en het renderen van de uiteindelijke afbeelding.

## Snelle antwoorden
- **Wat betekent “create dotcode extended codetext”?** Het betekent het bouwen van een DotCode barcode die FNC1, ECICodetext, platte tekst en symboolscheidingstekens bevat in één uitgebreide payload.  
- **Welke bibliotheek is vereist?** Aspose.BarCode voor .NET.  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisvoorbeeld.

## Hoe maak je dotcode extended codetext

Laad je project, stel de map in, bouw de uitgebreide codetext en genereer de afbeelding – alles in minder dan een dozijn regels code. Het volgende directe antwoord vat het hele proces samen:

Laad de `BarcodeGenerator` met `EncodeTypes.DotCode`, bouw de uitgebreide codetext met behulp van `DotCodeExtendedCodetextBuilder` (voeg FNC1, ECICodetext, platte tekst en FNC3‑scheidingstekens toe), roep vervolgens `Save` aan om een PNG‑bestand te schrijven. Deze volgorde creëert een volledig conforme 2d matrix barcode in één enkele oproep.

## Wat is dotcode extended codetext?

De **dotcode extended codetext** is een samengestelde string die meerdere gegevenssegmenten combineert — zoals FNC1‑identifiers, ECICodetext, platte tekst en FNC3‑scheidingstekens — tot één payload die DotCode kan decoderen. Het maakt het mogelijk om meertalige tekst, binaire blobs en gestructureerde data te coderen binnen één enkele 2d matrix barcode, waardoor het ideaal is voor supply‑chain, gezondheidszorg en IoT‑scenario's.

## Waarom Aspose.BarCode voor deze taak gebruiken?

Aspose.BarCode verwerkt **tot 500 pagina's per seconde** op typische serverhardware en ondersteunt **meer dan 30 barcode‑symbologieën**, inclusief DotCode. De `GetExtendedCodetext`‑API garandeert de juiste plaatsing van controle‑karakters, elimineert handmatige string‑concatenatiefouten en zorgt voor naleving van ISO/IEC 24724. Bovendien biedt het ingebouwde foutcorrectie en automatische quiet‑zone‑afhandeling, waardoor handmatige afstemming overbodig wordt.

## Vereisten

- **Aspose.BarCode for .NET** – download van de [Aspose.BarCode voor .NET documentatie](https://reference.aspose.com/barcode/net/).  
- Een .NET‑ontwikkelomgeving (Visual Studio 2022 of later aanbevolen).  
- Optioneel: een tijdelijk licentiebestand voor evaluatie.

## Namespaces importeren

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Deze namespaces maken de `BarcodeGenerator`‑klasse en de `DotCodeExtendedCodetextBuilder`‑helper beschikbaar die nodig zijn voor het voorbeeld.

```csharp
using Aspose.BarCode.Generation;
```

Nu we de vereisten hebben behandeld, laten we het proces van het genereren van DotCode Extended Code Text opsplitsen in een stapsgewijze gids.

## Stap 1: definieer het mappad

Geef op waar de gegenereerde PNG moet worden opgeslagen. Gebruik een absoluut of relatief pad waar je applicatie naar kan schrijven.

```csharp
string path = "Your Directory Path";
```

Vervang `"Your Directory Path"` door het daadwerkelijke pad op jouw systeem.

## Stap 2: maak dotcode extended codetext

De `DotCodeExtendedCodetextBuilder`‑klasse stelt de verschillende segmenten samen tot één uitgebreide codetext‑string.

Om de DotCode Extended Code Text te maken, volg je deze sub‑stappen:

### 2.1 voeg fnc1 format identifier toe

De FNC1‑formaat‑identifier markeert het begin van een nieuw gegevensveld. Het is vereist voor GS1‑conforme DotCode‑symbolen.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 voeg ecicodetext toe

De ECICodetext codeert speciale tekens en internationale tekst. In dit voorbeeld coderen we `"犬Right狗"` met UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 voeg platte codetext toe

Je kunt ook platte tekst toevoegen aan de DotCode Extended Code Text. Hier voegen we `"Plain text"` toe.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 voeg fnc3 symboolscheidingsteken toe

Het FNC3‑symboolscheidingsteken scheidt verschillende secties van de code, waardoor de leesbaarheid voor scanners verbetert.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 voeg fnc3 lezerinitialisatie toe

Deze stap voegt de FNC3‑Reader‑initialisatie‑informatie toe, die de scanner vertelt hoe de volgende gegevens geïnterpreteerd moeten worden.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 genereer codetext

Genereer nu de DotCode Extended Codetext door de `GetExtendedCodetext`‑methode aan te roepen op het `textBuilder`‑object.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Stap 3: genereer dotcode afbeelding

Render de barcode‑afbeelding vanuit de uitgebreide codetext.

#### 3.1 initialiseert barcode‑generator

De `BarcodeGenerator`‑klasse is het kernobject van Aspose.BarCode voor het maken van elke barcode. Je instantiateert het met de gewenste symbologie (`EncodeTypes.DotCode`) en de uitgebreide codetext die je zojuist hebt opgebouwd.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Roep tenslotte `Save` aan om het PNG‑bestand naar schijf te schrijven. De afbeelding is klaar om te worden ingebed in rapporten, mobiele apps of afgedrukte etiketten.

## Veelvoorkomende problemen en oplossingen

- **Onjuiste codering** – Zorg ervoor dat je `ECIEncodings.UTF8` gebruikt bij het toevoegen van meertalige tekst; anders kunnen tekens er vervormd uitzien.  
- **Bestands‑toegangs fouten** – Controleer of de applicatie schrijfrechten heeft op de doelmap.  
- **Quiet zone ontbreekt** – Stel `gen.Parameters.Barcode.Margin` in als scanners extra witruimte rond het symbool nodig hebben.

## Veelgestelde vragen

**V: Kan ik de gegenereerde barcode gebruiken in een mobiele app?**  
A: Ja. De PNG‑afbeelding die door de generator wordt geproduceerd kan worden ingebed in iOS, Android of elke cross‑platform mobiele applicatie.

**V: Wat als ik binaire data moet coderen in plaats van tekst?**  
A: Gebruik de `AddECICodetext`‑methode met de juiste `ECIEncodings` (bijv. `ECIEncodings.Base64`) om binaire payloads in te sluiten.

**V: Hoe wijzig ik de barcode‑grootte zonder de leesbaarheid te beïnvloeden?**  
A: Pas de `XDimension.Pixels`‑eigenschap aan; hogere waarden vergroten de module‑grootte, terwijl lagere waarden de barcode compacter maken.

**V: Is er een manier om een quiet zone rond de barcode toe te voegen?**  
A: Ja. Stel `gen.Parameters.Barcode.Margin` in om de gewenste quiet zone in pixels te definiëren.

**V: Ondersteunt de bibliotheek .NET 8?**  
A: De nieuwste Aspose.BarCode‑releases zijn compatibel met .NET 8; verwijs gewoon naar de juiste NuGet‑pakketversie.

Als je verdere begeleiding nodig hebt of vragen hebt, aarzel dan niet om de [Aspose.BarCode voor .NET documentatie](https://reference.aspose.com/barcode/net/) te bezoeken of deel te nemen aan de community op het [Aspose.BarCode supportforum](https://forum.aspose.com/c/barcode/13).

**Laatst bijgewerkt:** 2026-09-28  
**Getest met:** Aspose.BarCode 24.12 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak DotCode Barcode .NET (Auto-modus) met Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Hoe DataMatrix Barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/net/datamatrix-barcode-configuration/)
- [Hoe een Aztec barcode te maken met Aspose.BarCode voor .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}