---
category: general
date: 2026-10-08
description: Leer hoe je een barcode‑afbeelding maakt in C# en ontdek hoe je de aspectverhouding
  kunt aanpassen voor DataBar‑gestapelde omnidirectionele barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: nl
lastmod: 2026-10-08
og_description: Maak een barcode‑afbeelding in C# en leer hoe je de aspectverhouding
  kunt aanpassen voor gestapelde omni‑directionele DataBar‑barcodes met een volledig
  codevoorbeeld.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Barcode‑afbeelding maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcode‑afbeelding te maken en de beeldverhouding aan te passen in
  C#
url: /nl/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding te maken en de beeldverhouding aan te passen in C#

Als je programmatically **barcode‑afbeelding wilt maken**, laat deze gids je een complete, kant‑klaar oplossing zien. Je ziet precies **hoe je de beeldverhouding kunt aanpassen** voor een DataBar stacked omni‑directional barcode, een vereiste die vaak voorkomt in retail‑ en logistieke toepassingen.

In deze tutorial leer je hoe je:
* Een Aspose.BarCode `BarcodeGenerator` initialiseert voor de DataBar stacked omni‑directional symbologie.  
* De X‑dimension (modulebreedte) in pixels instelt om de balkdikte te regelen.  
* Twee verschillende beeldverhoudingen toepast en elk resultaat opslaat als een PNG‑bestand.  
* De output verifieert en begrijpt waarom de beeldverhouding belangrijk is.

Er zijn geen externe tools nodig—alleen de Aspose.BarCode for .NET‑bibliotheek en een .NET 6 (of later) ontwikkelomgeving.

## Hoe een barcode‑afbeelding te maken met Aspose.BarCode

De eerste stap is om de generator te instantieren met de gewenste symbologie en gegevensreeks. De `EncodeTypes.DatabarStackedOmniDirectional`‑enum vertelt Aspose.BarCode om een DataBar stacked omni‑directional barcode te produceren, die veel wordt gebruikt voor GS1‑128‑toepassingen.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Waarom dit belangrijk is:** Het `BarcodeGenerator`‑object is het toegangspunt voor alle barcode‑creatietaken. Door de symbologie en de ruwe data vooraf te specificeren, garandeer je dat de gegenereerde afbeelding voldoet aan de GS1‑standaard.

## Instellen van de X‑dimension (modulebreedte)

De X‑dimension definieert de breedte van de smalste balk (de module). Een grotere X‑dimension resulteert in een dikkere barcode, wat nuttig kan zijn voor low‑resolution printers.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom dit belangrijk is:** Het aanpassen van de X‑dimension maakt deel uit van het visuele afstemmingsproces. Het beïnvloedt de gecodeerde data niet, maar het heeft invloed op de scanbetrouwbaarheid op verschillende apparaten.

## Hoe de beeldverhouding aan te passen – eerste versie (15)

De beeldverhouding bepaalt de hoogte‑tot‑breedte verhouding van de DataBar‑barcode. De eigenschap `DataBar.AspectRatio` accepteert gehele getallen; grotere getallen produceren hogere balken.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Waarom dit belangrijk is:** Een beeldverhouding van 15 is een veelvoorkomende standaard voor retail‑scanners. De resulterende PNG (`DatabarAspectRatio15.png`) zal een hogere uitstraling hebben, wat de scansucces kan verbeteren op handheld‑apparaten.

## Hoe de beeldverhouding aan te passen – tweede versie (30)

Je hebt mogelijk een hogere barcode nodig voor specifieke labelformaten. Het wijzigen van de beeldverhouding is zo simpel als een nieuwe gehele waarde toewijzen voordat je opnieuw `Save` aanroept.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit belangrijk is:** Door **hoe de beeldverhouding aan te passen** te demonstreren, kun je meerdere barcode‑afbeeldingen genereren vanuit dezelfde gegevensbron zonder de generator opnieuw te maken. Dit vermindert het geheugenverbruik en versnelt batchverwerking.

### Verwachte output

Na het uitvoeren van het programma vind je twee PNG‑bestanden in de uitvoermap:

| Bestandsnaam                  | Beeldverhouding | Visuele beschrijving |
|-------------------------------|-----------------|----------------------|
| `DatabarAspectRatio15.png`    | 15              | Standaard hoogte, geschikt voor de meeste point‑of‑sale scanners. |
| `DatabarAspectRatio30.png`    | 30              | Hogere balken, nuttig voor grote labels of low‑resolution printers. |

Beide afbeeldingen bevatten dezelfde gecodeerde GTIN `(01)12345678901231`, maar de visuele verhoudingen verschillen volgens de ingestelde beeldverhouding.

## Veelgestelde vragen en edge‑case handling

### Wat als ik een andere X‑dimension nodig heb?

Je kunt `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` wijzigen naar elk geheel getal groter dan nul. Voor zeer hoge resolutie output (bijv. 300 dpi) levert een waarde van 3‑4 pixels vaak duidelijkere resultaten op.

### Hoe kies ik de juiste beeldverhouding?

De optimale verhouding hangt af van de scanomgeving:
* **Low‑profile labels** – gebruik een kleinere verhouding (bijv. 10‑15) om de barcode compact te houden.
* **Large shipping containers** – een hogere verhouding (bijv. 25‑35) verbetert de leesbaarheid op afstand.
* **Regulatory requirements** – sommige standaarden verplichten een minimale hoogte; raadpleeg de GS1‑specificatie voor exacte cijfers.

### Kan ik andere barcode‑formaten genereren met dezelfde code?

Ja. Vervang `EncodeTypes.DatabarStackedOmniDirectional` door een andere `EncodeTypes`‑waarde (bijv. `EncodeTypes.Code128`). De rest van de code—X‑dimension, beeldverhouding (indien van toepassing) en opslaan—blijft hetzelfde.

### Wat als ik de afbeelding in een ander formaat moet maken?

`BarCodeImageFormat` ondersteunt PNG, JPEG, BMP, GIF en TIFF. Verander gewoon het tweede argument van `Save`, bijvoorbeeld:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Pro‑tip: generator hergebruiken voor batchverwerking

Wanneer je tientallen barcodes moet maken met dezelfde visuele instellingen, instantiateer je de generator één keer, werk je alleen de `CodeText`‑eigenschap bij, en roep je `Save` herhaaldelijk aan. Dit voorkomt de overhead van het telkens opnieuw toewijzen van interne buffers.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Conclusie

Je weet nu hoe je **barcode‑afbeelding kunt maken** in C# met Aspose.BarCode en precies **hoe je de beeldverhouding kunt aanpassen** voor DataBar stacked omni‑directional symbolen. Door de X‑dimension en beeldverhouding te regelen, kun je barcodes produceren die aan elke scan‑ of lay‑out‑vereiste voldoen, terwijl de implementatie eenvoudig en onderhoudbaar blijft.

### Volgende stappen

* Verken andere symbologieën zoals **Code128** of **QR Code** door de `EncodeTypes`‑waarde te wisselen.  
* Combineer de barcode‑generatie met PDF‑creatie (bijv. met Aspose.PDF) om barcodes direct in facturen in te sluiten.  
* Experimenteer met dynamische beeldverhouding‑selectie op basis van labelgrootte—dit breidt het **hoe de beeldverhouding aan te passen**‑patroon uit tot een volledig uitgeruste label‑ontwerpengine.

Voel je vrij om het voorbeeld aan te passen, je resultaten te delen, of vervolgvragen te stellen in de reacties. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een databar stacked barcode te maken in C# met Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Hoe een barcode‑afbeelding te maken met Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Hoe de barcode‑grootte aan te passen – Codablock F beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}