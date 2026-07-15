---
category: general
date: 2026-07-15
description: Maak een omnidirectionele barcode in C# snel met Aspose.BarCode – leer
  hoe je een barcode in C# genereert met verstelbare balkhoogte en X‑dimensie.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: nl
lastmod: 2026-07-15
og_description: Maak een omnidirectionele barcode in C# met Aspose.BarCode. Leer hoe
  je een barcode in C# genereert door XDimension en BarHeight aan te passen voor perfecte
  resultaten.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Maak omni-directionele barcode in C# – Complete programmeerhandleiding
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Maak een omnidirectionele barcode in C# – Stap‑voor‑stapgids
url: /nl/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# omni-directionele barcode maken in C# – Stapsgewijze handleiding

Heb je je ooit afgevraagd hoe je een barcode in C# kunt genereren die voldoet aan de GS1 DataBar Omni‑Directional symbologie? Je bent niet de enige. In deze tutorial zullen we **omni-directionele barcode** afbeeldingen vanaf nul maken, de X‑dimensie aanpassen en spelen met de balkhoogte — allemaal met behulp van de Aspose.BarCode bibliotheek.

We lopen door een real‑world scenario: je hebt een compacte, hoge‑dichtheid barcode nodig voor een retail‑label, en je wilt totale controle over de visuele grootte. Aan het einde heb je twee PNG‑bestanden — één met een balkhoogte van 30 px en een andere met 60 px — klaar om in elke afdrukworkflow te gebruiken.

## Vereisten

- .NET 6 (of een recente .NET runtime) geïnstalleerd op je machine.  
- Visual Studio 2022 of VS Code — je favoriete IDE volstaat.  
- Een gratis Aspose.BarCode for .NET NuGet‑pakket (`Aspose.BarCode`).

Geen andere afhankelijkheden zijn vereist. Als je nog nooit met NuGet hebt gewerkt, open dan de Package Manager Console en voer uit:

```powershell
Install-Package Aspose.BarCode
```

## omni-directionele barcode – De basis begrijpen

De **GS1 DataBar Omni‑Directional** symbologie is ontworpen om in elke oriëntatie te scannen, waardoor hij perfect is voor schap‑rand etiketten. Wanneer je `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` aanroept, doet de bibliotheek het zware werk: hij codeert de data, past de symbologie‑regels toe en bereidt een raster‑afbeelding voor.

> **Pro tip:** Wrap de ruwe data altijd in het juiste Application Identifier (AI) formaat, bv. `"(01)12345678901231"` voor een GTIN‑14. Dit vertelt de scanner wat de cijfers vertegenwoordigen.

## Stap 1 – De Barcode Generator instellen (how to generate barcode c#)

Eerst maken we het generator‑object aan. Dit is de hoeksteen van **how to generate barcode c#** met Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

De `EncodeTypes.DatabarOmniDirectional` enum‑waarde vertelt de engine welke symbologie te gebruiken. Het tweede argument is de ruwe dataketen, al gewrapt in de GTIN AI.

## Stap 2 – De X‑dimensie aanpassen (barcode XDimension)

De **barcode XDimension** bepaalt de breedte van de kleinste balk. Een waarde van 2 px is een goede balans tussen leesbaarheid en compactheid voor de meeste labelprinters.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Als je een fijner of grover uiterlijk wilt, wijzig dan simpelweg het getal. Onthoud: de X‑dimensie is de fundamentele eenheid; alle andere balkbreedtes zijn veelvouden van deze waarde.

## Stap 3 – Maak de eerste afbeelding met een balkhoogte van 30 px (barcode BarHeight)

Nu stellen we de **barcode BarHeight** in op 30 px en slaan de afbeelding op. Dit levert een bescheiden‑grote barcode die mooi op een standaard label past.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft een PNG‑bestand naar schijf. Je kunt `BarCodeImageFormat.Jpeg` gebruiken als je JPEG‑output verkiest.

## Stap 4 – Verhoog de balkhoogte naar 60 px voor grotere etiketten (barcode BarHeight)

Soms is een grotere barcode vereist — bijvoorbeeld voor een schap‑label dat verder van de scanner staat. Laten we de hoogte verdubbelen.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Merk op dat we **niet** de generator hoeven te recreëren; we passen alleen de parameter aan en hergebruiken hetzelfde object. Dit bespaart geheugen en houdt de code overzichtelijk.

## Stap 5 – Sla de tweede afbeelding op (how to generate barcode c#)

Tot slot slaan we de tweede PNG op. Je hebt nu twee bestanden die alleen verschillen in balkhoogte.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Verwachte output

- `DatabarBarHeight30Pixels.png` – een omni‑directionele barcode van 30 px hoog.  
- `DatabarBarHeight60Pixels.png` – dezelfde data, maar met een barcode van 60 px hoog.

Open de bestanden in een willekeurige afbeeldingsviewer; je ziet scherpe, scanbare balken die voldoen aan de GS1 DataBar Omni‑Directional specificatie.

## Veelgestelde vragen & randgevallen

### Wat als ik een andere X‑dimensie nodig heb?

Wijs simpelweg een nieuwe waarde toe vóór het aanroepen van `Save`. Voor ultra‑hoge‑dichtheid afdrukken kun je tot 1 px gaan, maar test eerst met je scanner — sommige apparaten hebben moeite met balken onder de 2 px.

### Kan ik mens‑leesbare tekst onder de barcode toevoegen?

Ja. Stel `barcodeGenerator.Parameters.Barcode.CodeText` in op een string en pas eventueel `barcodeGenerator.Parameters.Barcode.CodeLocation` aan naar `BarCodeTextLocation.Below`. Handig voor retail‑omgevingen waar de numerieke GTIN zichtbaar moet zijn.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Is PNG het beste formaat voor afdrukken?

PNG is lossless, waardoor de scherpe randen behouden blijven die barcode‑scanners nodig hebben. Als je downstream‑systeem een ander formaat verwacht (TIFF, BMP), wijzig dan simpelweg de `BarCodeImageFormat` enum.

## Volledig werkend voorbeeld (create omni-directional barcode)

Hieronder staat het complete, kant‑klaar programma. Kopieer‑plak het in een nieuw console‑project en druk op **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Voer het programma uit, controleer de output‑map, en je ziet de twee PNG‑bestanden precies zoals beschreven.

## Samenvatting

We hebben laten zien **how to generate barcode C#** code die een **create omni-directional barcode** maakt met Aspose.BarCode. Door de **barcode XDimension** en **barcode BarHeight** aan te passen, krijg je fijne controle over de visuele grootte zonder in te boeten op scan‑betrouwbaarheid.

## Wat is het volgende?

- Experimenteer met andere **GS1 DataBar Omni-Directional** instellingen zoals `Color` of `Margin`.  
- Combineer meerdere barcodes op één canvas met `Graphics` voor complexe label‑ontwerpen.  
- Integreer de generator in een web‑API zodat je e‑commerce platform barcodes on‑demand kan genereren.

Heb je een twist die je wilt delen? Laat een reactie achter, en laten we het gesprek voortzetten. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode te genereren – Code 39 configuratie met Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hoe barcode‑quiet‑zone te maken voor ITF-14 met Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hoe barcode‑quiet‑zone te maken voor Code 16K met Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}