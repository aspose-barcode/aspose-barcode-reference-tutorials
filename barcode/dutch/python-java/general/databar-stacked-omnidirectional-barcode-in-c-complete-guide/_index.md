---
category: general
date: 2026-07-15
description: Databar stacked omnidirectionele barcode in C#-tutorial. Leer hoe je
  databar genereert, de beeldverhouding instelt en een barcode-generator in C# gebruikt
  voor perfecte resultaten.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: nl
lastmod: 2026-07-15
og_description: Databar stacked omnidirectionele barcode in C# uitgelegd. Volg deze
  stapsgewijze tutorial om een databar te genereren, de beeldverhouding aan te passen
  en de barcodegenerator in C# onder de knie te krijgen.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: databar gestapelde omnidirectionele barcode – C#-gids
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: databar gestapelde omnidirectionele barcode in C# – Complete gids
url: /nl/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar stacked omnidirectional barcode in C# – Complete gids

Heb je je ooit afgevraagd hoe je de beeldverhouding kunt instellen wanneer je **databar stacked omnidirectional barcode** in C# maakt? Je bent niet de enige. Veel ontwikkelaars lopen tegen een muur aan bij het fijn afstemmen van die barcodes voor retail‑ of logistieke etiketten, en de documentatie kan wat schaars aanvoelen.  

In deze tutorial lopen we stap voor stap door **hoe je een databar genereert**, de X‑Dimension configureert, en – vooral – **hoe je de beeldverhouding instelt** zodat de scanner deze foutloos leest. Aan het einde heb je een kant‑klaar code‑voorbeeld dat twee barcode‑afbeeldingen naast elkaar maakt, één met een beeldverhouding van 15 en een andere met 30. Geen mysterie, alleen duidelijke stappen.

## Wat deze gids behandelt

- Een **barcode generator c#** opzetten met de populaire Aspose.BarCode‑bibliotheek.  
- De anatomie van een **databar stacked omnidirectional**‑symbool begrijpen.  
- De **aspect ratio** afstemmen om te voldoen aan de GS1‑specificaties.  
- Het resultaat opslaan als PNG‑bestanden die je in elk .NET‑project kunt gebruiken.  

Prerequisites? Alleen een recente .NET SDK (4.6+ of .NET Core 3.1+) en een NuGet‑referentie naar `Aspose.BarCode`. Als je die hebt, ben je klaar om te starten.

---

## Understanding the databar stacked omnidirectional barcode

De **databar stacked omnidirectional**‑indeling verpakt een 14‑cijferige GTIN en een paar aanvullende cijfers in een compact, twee‑rijig symbool. Het is de favoriete keuze voor kleine artikelen waar ruimte schaars is – denk aan cosmetica, farmaceutica of piepkleine snackverpakkingen.

Waarom is de beeldverhouding belangrijk? De barcode‑specificatie definieert een breedte‑naar‑hoogte‑relatie die de scan‑betrouwbaarheid beïnvloedt. Te samengedrukt en een scanner mist mogelijk een balk; te uitgerekt en de code kan de labelafmetingen overschrijden. De `AspectRatio`‑eigenschap op het `DataBar`‑object laat je die balans fijn afstemmen.

---

## Step 1: Create a **databar stacked omnidirectional** barcode generator

Eerst start je de generator met het juiste encode‑type en de data die je wilt embedden. Hier gebruiken we een voorbeeld‑GTIN‑14‑waarde tussen haakjes, zoals de specificatie vereist.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Pro tip:** De string moet beginnen met “(01)” om de bibliotheek te laten weten dat de volgende 14 cijfers een GTIN zijn. Het weglaten van de haakjes veroorzaakt een `ArgumentException`.

---

## Step 2: Define the basic size of the bars (X‑Dimension)

De X‑Dimension bepaalt hoeveel pixels elke module (de kleinste balk) inneemt. Een veelgebruikt startpunt is 2 pixels per module, wat een goede balans biedt tussen leesbaarheid en bestandsgrootte.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Als je afdrukt op een high‑resolution laserprinter, kun je dit verhogen naar 3 of 4 pixels. Onthoud: een grotere X‑Dimension betekent grotere totale barcode‑afmetingen.

---

## Step 3: **How to set aspect ratio** – first version (15)

Nu volgt het deel dat veel mensen tegenkomt: de `AspectRatio`. Het is een eenvoudige integer, maar beïnvloedt direct de hoogte van de gestapelde rijen ten opzichte van de breedte.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

De resulterende PNG ziet er ongeveer zo uit (placeholder‑afbeelding):

![databar stacked omnidirectional barcode with aspect ratio 15](databar_aspect_ratio_15.png)

*Image alt text (for SEO):* **databar stacked omnidirectional barcode with aspect ratio 15**.

---

## Step 4: **How to set aspect ratio** – second version (30)

Soms is een hogere ratio vereist, vooral wanneer de labelhoogte ruim is of de scanner een hoger symbool verwacht. Laten we overschakelen naar 30 en een tweede bestand opslaan.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

En de output:

![databar stacked omnidirectional barcode with aspect ratio 30](databar_aspect_ratio_30.png)

*Image alt text:* **databar stacked omnidirectional barcode with aspect ratio 30**.

Je zult merken dat de balken hoger zijn, maar de breedte blijft gelijk omdat we de X‑Dimension constant hielden.

---

## Step 5: Verify the output – quick sanity check

Open de twee PNG‑bestanden in een willekeurige afbeeldingsviewer. Beide moeten een nette, twee‑rijige barcode tonen met dezelfde numerieke data. Als je een handscanner bij de hand hebt, probeer dan elk bestand te scannen. De scanner moet de ruwe GTIN‑string `(01)12345678901231` teruggeven.  

Als een scan mislukt, controleer dan:

1. De **X‑Dimension** is niet te laag (onder 1 pixel is onmogelijk).  
2. De **AspectRatio** komt overeen met wat je scan‑hardware verwacht.  
3. Het **output‑pad** schrijfbaar is – soms verbergt een `UnauthorizedAccessException` zich achter een stille fout.

---

## Common pitfalls when you **create databar barcode**

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Lege afbeelding opgeslagen | `EncodeTypes`‑mismatch (bijv. `DatabarExpanded` gebruiken in plaats van `DatabarStackedOmniDirectional`) | Controleer `EncodeTypes.DatabarStackedOmniDirectional` |
| Barcode te breed | X‑Dimension te hoog ingesteld | Verlaag `XDimension.Pixels` |
| Scanner meldt “invalid format” | Aspect ratio niet ondersteund door het scanner‑model | Pas `AspectRatio` aan naar 15 of 30 volgens de apparaat‑specificaties |
| Exception bij `Save` | Doelmap ontbreekt of geen schrijfrechten | Maak de map aan of voer uit met verhoogde rechten |

---

## Advanced: Dynamically choosing the aspect ratio

In real‑world apps moet je mogelijk een aspect ratio kiezen op basis van de labelgrootte. Hier is een kleine hulpfunctie die 15 kiest voor smalle labels en 30 voor hoge labels.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Nu past je **barcode generator c#**‑code zich dynamisch aan – geen noodzaak om twee aparte saves hard‑coded te hebben.

---

## Recap – what we achieved

- **Created** een **databar stacked omnidirectional** barcode‑generator in C#.  
- **Set** de X‑Dimension op 2 pixels per module voor scherpe weergave.  
- **Demonstrated** **how to set aspect ratio** zowel op 15 als 30, en elk bestand als PNG opgeslagen.  
- **Explored** veelvoorkomende fouten en een kleine dynamische‑ratio‑helper aangeboden.

Dit alles past in één enkel, zelf‑voorzienend bestand dat je in elk .NET‑project kunt plaatsen. Geen externe scripts, geen mysterieuze configuratie‑bestanden.

---

## What’s next? Expand your barcode toolbox

Nu je de basis van **create databar barcode** onder de knie hebt, kun je overwegen om te verkennen:

- **Adding human‑readable text** onder het symbool (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Embedding the barcode** direct in een PDF met `Aspose.Pdf` voor factuurgeneratie.  
- **Batch processing** van een lijst GTINs met een `foreach`‑loop en elk bestand een naam geven op basis van de productcode.  

Elk van deze onderwerpen bouwt voort op dezelfde kernconcepten die je net geleerd hebt, en ze maken je **barcode generator c#**‑projecten nog krachtiger.

---

### Final Thoughts

Een **databar stacked omnidirectional** barcode genereren in C# is geen magie; het is slechts een handvol eigenschaps‑aanpassingen op een solide bibliotheek. Door de X‑Dimension en de **aspect ratio** te regelen, krijg je volledige controle over de vorm en scan‑betrouwbaarheid van de barcode.  

Laat de code draaien, pas de getallen aan, en zie de scanner dansen. Als je een probleem tegenkomt, raadpleeg dan de tabel “Common pitfalls” – de meeste issues lossen zich snel op met een kleine eigenschap‑aanpassing.  

Happy coding, and may your labels always scan on the first try!

## What Should You Learn Next?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Pas de aspectratio van databar stacked omnidirectional aan in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [Aanpassen van de hoogte van één-dimensionale Databar barcode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode‑afbeelding genereren – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}