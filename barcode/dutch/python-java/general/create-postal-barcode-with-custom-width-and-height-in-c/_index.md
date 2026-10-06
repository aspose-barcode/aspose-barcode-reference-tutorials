---
category: general
date: 2026-09-16
description: Maak een postbarcode in C# en leer hoe je de breedte instelt en de hoogte
  van de barcode aanpast voor een perfecte scan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: nl
lastmod: 2026-09-16
og_description: Maak een postbarcode in C# met deze stapsgewijze handleiding, waarin
  wordt getoond hoe je de breedte instelt en de barcodehoogte wijzigt voor betrouwbare
  postscan.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Maak een postbarcode met aangepaste breedte en hoogte in C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Maak een postbarcode met aangepaste breedte en hoogte in C#
url: /nl/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak postbarcode met aangepaste breedte en hoogte in C#

Als je **postbarcode** afbeeldingen in C# moet maken, laat deze gids je zien hoe je Planet- en RM4SCC-barcodes genereert met exacte afmetingen. Aan het einde van de eerste twee zinnen weet je welke API‑aanroepen je moet gebruiken om de **breedte in te stellen** en de **barcode‑hoogte te wijzigen**, zodat je scanbare barcodes kunt produceren die voldoen aan de specificaties van de postdienst.

Je leert:
* Hoe je een barcode‑generator instantieert voor Planet‑ en RM4SCC‑formaten.  
* De exacte eigenschap om **breedte in te stellen** (X‑dimensie) in pixels.  
* Hoe je de **barcode‑hoogte wijzigt** voor een specifiek barcode‑type.  
* Waar de gegenereerde PNG‑bestanden worden opgeslagen en hoe ze eruitzien.

De enige voorwaarde is een verwijzing naar de `Aspose.BarCode` (of vergelijkbare) bibliotheek die de `BarcodeGenerator`‑klasse levert. Er zijn geen extra NuGet‑pakketten nodig naast de barcode‑SDK zelf.

---

## Maak postbarcode met aangepaste afmetingen

Voeg eerst de benodigde `using`‑directieven toe en maak een eenvoudig console‑programma. Het volledige, uitvoerbare voorbeeld wordt gepresenteerd na de stap‑voor‑stap‑uitleg.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Waarom dit werkt:**  
* `EncodeTypes.Planet` en `EncodeTypes.RM4SCC` geven de generator aan welke poststandaard gevolgd moet worden.  
* `XDimension.Pixels` bepaalt de **breedte** van elke barcode‑module (het kleinste zwart/wit‑element).  
* `BarHeight.Pixels` stelt je in staat de **barcode‑hoogte te wijzigen** voor formaten die de hoogte niet automatisch berekenen, zoals RM4SCC.

Het uitvoeren van het programma maakt twee PNG‑bestanden aan in de werkmap van het uitvoerbare bestand:
* `PostalPlanetBarWidth4.png` – een Planet‑barcode met een module‑breedte van 4 px.  
* `PostalRM4SCCHeight100.png` – een RM4SCC‑barcode met een breedte van 4 px en een vaste hoogte van 100 px.

---

## Hoe breedte in te stellen voor een postbarcode

De **breedte‑instellen** stap is hetzelfde voor elk ondersteund postformaat:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` is een geheel getal dat de pixelgrootte van een enkele module aangeeft.  
* Een typische waarde voor postbarcodes is **4 px**, maar je kunt deze verhogen voor afdrukken met hogere resolutie.

**Pro tip:** Bij het afdrukken op een DPI‑gecontroleerde printer, vermenigvuldig je de pixelbreedte met de DPI‑factor van de printer om de fysieke afmetingen te behouden.

---

## Hoogte van barcode wijzigen voor RM4SCC postbarcode

Alleen een deel van de post‑symbologieën (bijv. RM4SCC) vereist een expliciete hoogte. Gebruik de **hoogte‑wijzigen** eigenschap:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` is de totale hoogte van de barcode‑afbeelding, niet de hoogte van een enkele module.  
* Het instellen van `BarHeight` op **100 px** levert een hoge, gemakkelijk leesbare barcode op die voldoet aan veel richtlijnen van postdiensten.

**Edge case:** Als je een hoogte instelt die te klein is, kan de barcode onleesbaar worden voor scanners. Test altijd met een fysieke afdruk voordat je grootschalig inzet.

---

## Volledige broncode voor snel kopiëren‑en‑plakken

Hieronder staat het volledige programma dat je kunt kopiëren naar een nieuw console‑project. Er is geen andere code nodig.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Verwachte output** (console):

```
Both postal barcodes have been saved.
```

En twee PNG‑bestanden verschijnen in de uitvoermap, elk met een duidelijke postbarcode die klaar is voor afdrukken of insluiten.

---

## Veelgestelde vragen en probleemoplossing

| Vraag | Antwoord |
|----------|--------|
| *Wat als ik een andere X‑dimensie voor elke barcode nodig heb?* | Maak aparte `BarcodeGenerator`‑instanties aan en ken een aparte `XDimension.Pixels`‑waarde toe voordat je `Save` aanroept. |
| *Waarom negeert de Planet‑barcode `BarHeight`?* | Het Planet‑formaat berekent automatisch de hoogte op basis van de X‑dimensie, dus het instellen van `BarHeight` heeft geen effect. |
| *Kan ik SVG in plaats van PNG exporteren?* | Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Svg`. |
| *Wat als de afbeelding onscherp is bij het afdrukken?* | Verhoog de X‑dimensie (bijv. naar 6 px) en genereer de afbeelding met een hogere DPI via de `Resolution`‑instellingen van de generator. |

---

## Conclusie

Je weet nu hoe je **postbarcode** afbeeldingen in C# kunt maken en nauwkeurig **breedte kunt instellen** en **barcode‑hoogte kunt wijzigen** met behulp van de `BarcodeGenerator`‑API. Het voorbeeld behandelt zowel automatisch geschaalde (Planet) als handmatig geschaalde (RM4SCC) formaten, waardoor je een stevige basis krijgt voor elk post‑automatiseringsproject.

Vervolgens kun je verkennen:
* Het toevoegen van mens‑leesbare tekst onder de barcode (`CodeTextParameters`).  
* Exporteren naar andere formaten zoals SVG of PDF voor vector‑gebaseerd afdrukken.  
* De generator integreren in een web‑API om barcodes op aanvraag te leveren.

Voel je vrij om te experimenteren met verschillende afmetingen, coderingen en uitvoerformaten om aan jouw specifieke verzendworkflow te voldoen. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Postbarcode afbeelding maken in C# – Volledige stap‑voor‑stap‑gids](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Postbarcode maken in C# – Volledig generator‑voorbeeld](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Barcode‑generator voorbeeld in C# – breedte en hoogte instellen](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}