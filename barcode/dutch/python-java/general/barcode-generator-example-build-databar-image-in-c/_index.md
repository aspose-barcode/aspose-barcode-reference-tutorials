---
category: general
date: 2026-07-18
description: Barcodegenerator‑voorbeeld dat laat zien hoe je afmetingen instelt en
  een DataBar Stacked Omni‑Directional barcode‑afbeelding genereert in C#. Leer barcode‑encodeertypen
  snel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: nl
lastmod: 2026-07-18
og_description: Barcodegenerator‑voorbeeld leidt je stap voor stap door het instellen
  van afmetingen, het kiezen van barcode‑encodeertypen en het maken van barcode‑afbeeldingsprojecten
  in C# met minimale code.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Barcode Generator Voorbeeld – Snelle DataBar-afbeeldingscreatie in C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Barcode Generator Voorbeeld – Maak DataBar-afbeelding in C#
url: /nl/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator-voorbeeld – DataBar-afbeelding maken in C#

Heb je ooit een **barcode generator voorbeeld** nodig gehad dat echt een werkelijke barcode maakt zonder dat je je haar uittrekt? Je bent niet de enige. De meeste ontwikkelaars lopen tegen een muur aan wanneer ze proberen **hoe de afmetingen in te stellen** voor een DataBar Stacked Omni‑Directional barcode, vooral omdat de documentatie begraven ligt onder lagen jargon.

In deze tutorial lopen we stap voor stap door een compleet, kant‑klaar C#‑programma dat laat zien **hoe je databar**‑afbeeldingen genereert, de juiste **barcode encode types** kiest, en uiteindelijk **barcode image c#**‑bestanden maakt die je in elk project kunt gebruiken. Geen poespas—alleen de code die je kunt copy‑pasten, plus de reden achter elke regel.

## Wat je nodig hebt

- **.NET 6** (of een recente .NET‑versie) – de API die we gebruiken richt zich op .NET Standard, dus hij werkt ook op .NET Framework.  
- **Aspose.BarCode for .NET** – de bibliotheek die `BarcodeGenerator` levert. Je kunt hem via NuGet halen met `Install-Package Aspose.BarCode`.  
- Een **C#‑IDE** – Visual Studio, Rider of VS Code volstaat.  
- Een map op schijf waar de PNG‑bestanden worden opgeslagen (de code maakt `DatabarAspectRatio15.png` en `DatabarAspectRatio30.png` aan).

Heb je alles? Geweldig—laten we beginnen.

## Barcode Generator-voorbeeld – Initialiseer de Generator

Allereerst hebben we een instantie van `BarcodeGenerator` nodig die is geconfigureerd voor de **DataBar Stacked Omni‑Directional** symbologie. Dit is het **barcode encode type** waarmee we gaan werken.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Waarom dit belangrijk is:** `EncodeTypes.DatabarStackedOmniDirectional` vertelt Aspose precies welke symbologie moet worden gerenderd. Als je het verkeerde type kiest, zal de scanner de barcode niet herkennen, hoe mooi de afbeelding er ook uitziet.

## Hoe de afmetingen voor de barcode in te stellen

De leesbaarheid van een barcode hangt af van de **X‑dimension** (de breedte van de smalste balk). In de meeste gevallen werkt een waarde van 2 pixels prima, maar je kunt dit aanpassen aan je printer of scherm.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Pro tip:** Als je je ooit afvraagt **hoe je de afmetingen instelt** voor een andere barcode‑familie, geldt dezelfde eigenschapsketen (`Parameters.Barcode.XDimension`)—verander alleen de `Pixels`‑waarde.

## Hoe een DataBar Stacked Omni‑Directional barcode te genereren

Nu de generator klaar is, gaan we spelen met de **aspect ratio**‑eigenschap. Deze bepaalt de hoogte‑tot‑breedte‑verhouding van de DataBar, zodat je een kort, vierkant symbool of een lang, smal symbool kunt maken.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Wat gebeurt er?** `AspectRatio = 15` vertelt de engine om de balken 15 keer hoger te maken dan ze breed zijn. De resulterende PNG wordt opgeslagen naast je uitvoerbare bestand.

## Create Barcode Image C# – De aspect ratio wijzigen

Laten we de flexibiliteit bewijzen door de ratio naar 30 te veranderen en een tweede bestand op te slaan.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Wanneer je het programma uitvoert, krijg je twee PNG‑bestanden:

| Bestand | Aspect Ratio | Geschatte grootte |
|---------|--------------|-------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Open ze in een willekeurige afbeeldingsviewer—je zou schone, scanbare DataBar‑symbolen moeten zien.

## Overzicht van Barcode Encode Types (Optioneel maar Handig)

Als je nieuwsgierig bent naar andere **barcode encode types** die door Aspose worden ondersteund, hier een snelle cheat‑sheet:

| EncodeTypes Enum | Beschrijving |
|------------------|--------------|
| `EncodeTypes.Code128` | Hoge‑dichtheid alfanumeriek |
| `EncodeTypes.QR` | 2‑D matrixcode |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar voor retail |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Onze focus** – compact, omnidirectioneel |

De juiste enum kennen bespaart je veel trial‑and‑error wanneer je van project wisselt.

## Veelvoorkomende valkuilen & hoe ze te vermijden

- **Ontbrekend NuGet‑pakket** – De code compileert niet zonder `Aspose.BarCode`. Voer eerst `dotnet add package Aspose.BarCode` uit.  
- **Verkeerd bestandspad** – Als je een absoluut pad gebruikt, controleer dan de backslashes (`\\`) op Windows. Relatieve paden (zoals hier) houden het draagbaar.  
- **Aspect ratio te extreem** – Ratio’s boven 50 kunnen de barcode te hoog maken voor typische scanners. Houd je aan 15‑30 voor de meeste scenario’s.

## Volledige broncode (Klaar om te copy‑pasten)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Voer het programma uit (`dotnet run` of druk op **F5** in Visual Studio) en je ziet een console‑bericht dat bevestigt dat de bestanden op schijf staan.

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Voorbeeldoutput van barcode generator met DataBar barcode en aspect ratio 15"}

## Afronding

We hebben zojuist een **barcode generator voorbeeld** voltooid dat laat zien **hoe je de afmetingen instelt**, het juiste **barcode encode type** kiest, en uiteindelijk **barcode image c#**‑bestanden maakt die je overal kunt inbedden. De code is klein, de concepten zijn glashelder, en je hebt nu een solide basis om de oplossing uit te breiden—misschien door tekstbijschriften toe te voegen, de afbeelding te roteren, of over te schakelen naar een andere symbologie.

### Wat is de volgende stap?

- Experimenteer met **verschillende X‑dimensions** om te zien hoe de toleranties van scanners veranderen.  
- Probeer andere **EncodeTypes** zoals `Code128` of `QR` om je gereedschapskist uit te breiden.  
- Automatiseer batch‑generatie: loop over een CSV met product‑ID’s en genereer een PNG voor elk.

Als je tegen een probleem aanloopt, laat dan een reactie achter of raadpleeg de Aspose.BarCode‑documentatie—die zit boordevol voorbeelden die aansluiten bij wat we hier behandeld hebben.

Happy coding, en moge je barcodes altijd bij de eerste poging scannen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}