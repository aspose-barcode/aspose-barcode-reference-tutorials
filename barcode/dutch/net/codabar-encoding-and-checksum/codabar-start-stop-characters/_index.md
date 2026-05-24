---
date: 2026-05-24
description: Leer hoe u een Codabar-barcode met start‑ en stop‑tekens maakt met behulp
  van Aspose.BarCode voor .NET. Stapsgewijze tutorial voor barcode‑generatie voor
  ontwikkelaars.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar start/stop‑tekens
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Maak Codabar-barcode met start/stop‑tekens in Aspose.BarCode voor .NET
url: /nl/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Codabar-barcode met start/stop‑tekens in Aspose.BarCode voor .NET

## Introductie

In deze tutorial **maak je Codabar‑barcode**‑afbeeldingen die expliciete start/stop‑tekens bevatten met Aspose.BarCode voor .NET. Of je nu een retail‑inventarisatiesysteem, een laboratorium‑monstertracker of een medische‑recordoplossing bouwt, de numerieke symbologie van Codabar vertrouwt op die grenssymbolen om betrouwbare scanning te garanderen. In de komende paar minuten behandelen we alles van omgeving‑configuratie tot het opslaan van PNG‑bestanden, zodat je meteen Codabar‑barcodes kunt genereren.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.BarCode for .NET  
- **In welk formaat kan ik de barcode opslaan?** PNG (`BarCodeImageFormat.Png`)  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de start/stop‑symbolen wijzigen?** Ja – gebruik `CodabarSymbol.A`, `B`, `C` of `D`.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is Codabar en waarom zijn start/stop‑tekens essentieel?

Codabar is een numerieke barcode‑symbologie die veel wordt gebruikt in bibliotheken, de gezondheidszorg en voorraadbeheer. De start‑ en stop‑tekens (A‑D of streepje) definiëren de grenzen van de barcode, waardoor scanners kunnen detecteren waar de gegevens beginnen en eindigen met een leesnauwkeurigheid van 99,9 %.

## Waarom Aspose.BarCode voor .NET gebruiken?

Aspose.BarCode ondersteunt **meer dan 30 barcode‑symbologieën** en kan afbeeldingen genereren tot **10.000 × 10.000 px** zonder het volledige document in het geheugen te laden. Het draait op Windows, Linux en macOS, en is compatibel met .NET Framework, .NET Core en .NET 5+ — wat je flexibiliteit geeft op alle moderne platforms.

## Vereisten

1. **Omgevingsconfiguratie** – Zorg voor een functionele .NET‑ontwikkelomgeving. Als je begeleiding nodig hebt, raadpleeg de [documentatie](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode for .NET Library** – Download en installeer de bibliotheek vanaf de officiële [bron](https://releases.aspose.com/barcode/net/).  
3. **Basis .NET‑kennis** – Vertrouwdheid met C# en een IDE zoals Visual Studio, Rider of VS Code.  
4. **IDE** – Visual Studio, Rider of Visual Studio Code zijn allemaal geschikt.

Nu we de vereisten hebben behandeld, duiken we in de daadwerkelijke code.

## Hoe genereer ik een Codabar-barcode met start/stop‑tekens?

Laad de `BarcodeGenerator`, stel het coderings‑type in op **Codabar**, en geef een gegevensreeks door die de vereiste start/stop‑symbolen al bevat (bijvoorbeeld “-12345-”). Configureer vervolgens de X‑Dimension, kies eventueel een ander start/stop‑symbool, en sla ten slotte de afbeelding op als PNG. Deze end‑to‑end‑stroom maakt een kant‑klaar barcode in slechts een paar regels C#.

### Namespaces importeren

De `BarcodeGenerator` en gerelateerde types bevinden zich in de `Aspose.BarCode.Generation` namespace.

```csharp
using Aspose.BarCode.Generation;
```

### Stap 1: Initialiseer de Barcode‑generator

`BarcodeGenerator` is de kernklasse die barcode‑afbeeldingen maakt. Het neemt het symbooltype en de gegevensreeks als constructor‑argumenten.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro tip:** Het streepje (`-`) is een van de geldige start/stop‑symbolen voor Codabar. Je kunt ook `A`, `B`, `C` of `D` gebruiken, afhankelijk van de eisen van je toepassing.

### Stap 2: Stel de X‑Dimension in (breedte van barcode‑element)

`XDimension` bepaalt de breedte van de smalste balk. Grotere waarden verbeteren de leesbaarheid op laag‑resolutieprinters, terwijl kleinere waarden ruimte besparen op hoge‑dichtheid labels.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Waarom het belangrijk is:** Het aanpassen van `XDimension` helpt je te voldoen aan scanner‑specificaties die vaak een minimale balkbreedte van 0,25 mm vereisen.

### Stap 3: Definieer start‑ en stop‑tekens

Codabar ondersteunt vier start/stop‑symbolen (A, B, C, D). Hieronder vind je voorbeelden voor elke optie. Kies degene die overeenkomt met de specificatie van het systeem waarmee je integreert.

#### Instellen Start A en Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Instellen Start B en Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Instellen Start C en Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Instellen Start D en Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Je kunt de configuratie herhalen voor elk symbool dat je moet genereren; het voorbeeld hieronder slaat vier afzonderlijke afbeeldingen op — een voor elk start/stop‑paar.

### Stap 4: Sla de gegenereerde barcode‑afbeeldingen op (PNG)

`Save` schrijft de barcode naar een bestand. Met `BarCodeImageFormat.Png` krijg je verliesvrije PNG‑afbeeldingen die ideaal zijn voor web‑ en printtoepassingen.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Elke file bevat nu een **Codabar‑barcode‑voorbeeld** met de bijbehorende start/stop‑symbolen.

## Veelvoorkomende problemen & probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Barcode ziet er vervormd uit | X‑Dimension te laag voor de gekozen printerresolutie | Verhoog `XDimension.Pixels` (bijv. naar 3 of 4) |
| Scanner kan start/stop niet lezen | Verkeerd start/stop‑symbool voor het doelsysteem | Controleer het vereiste symbool (A‑D) en stel het correct in |
| PNG‑bestand is leeg of corrupt | Ongeldig uitvoerpad of onvoldoende schrijfrechten | Zorg ervoor dat `path` naar een bestaande map wijst en dat je app schrijfrechten heeft |

## Veelgestelde vragen

**Q1: Wat is Codabar, en waarom zijn start‑ en stop‑tekens belangrijk?**  
A: Codabar is een numerieke barcode‑symbologie die wordt gebruikt in voorraadbeheer, bibliotheken en de gezondheidszorg. Start‑/stop‑tekens definiëren de grenzen van de barcode, zodat scanners weten waar de gegevens beginnen en eindigen.

**Q2: Kan ik het uiterlijk van Codabar‑barcodes aanpassen met Aspose.BarCode voor .NET?**  
A: Ja. Naast X‑Dimension kun je kleuren wijzigen, marges toevoegen en exporteren naar PDF of SVG met dezelfde API.

**Q3: Zijn er beperkingen voor Codabar‑barcodes wat betreft gegevenscodering?**  
A: Codabar ondersteunt voornamelijk numerieke gegevens (0‑9) plus een beperkt aantal speciale tekens. Het is niet geschikt voor volledige alfanumerieke strings.

**Q4: Is Aspose.BarCode voor .NET geschikt voor commercieel gebruik, en hoe kan ik een licentie verkrijgen?**  
A: Ja, het is productie‑klaar. Koop een licentie op de [Aspose's purchase page](https://purchase.aspose.com/buy).

**Q5: Waar kan ik hulp zoeken of discussiëren over problemen met Aspose.BarCode voor .NET?**  
A: Word lid van de community op het [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13) voor assistentie van zowel Aspose‑engineers als mededevelopers.

---

**Laatst bijgewerkt:** 2026-05-24  
**Getest met:** Aspose.BarCode 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Codabar start‑stop‑tekens en controlegetal](/barcode/net/codabar-encoding-and-checksum/)
- [Hoe een controlegetal toe te voegen aan Codabar‑barcodes met Aspose.BarCode voor .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Uitgebreide tutorials en voorbeelden van Aspose.BarCode voor .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}