---
category: general
date: 2026-08-22
description: Barcode-generator C#-tutorial laat zien hoe je barcode‑PNG‑bestanden
  genereert, DataBar‑barcodes maakt en de barcode‑hoogte aanpast in slechts een paar
  stappen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: nl
lastmod: 2026-08-22
og_description: Barcode generator C#-gids leidt je stap voor stap door het genereren
  van barcode‑PNG’s, het maken van DataBar‑barcodes en het efficiënt aanpassen van
  de barcodehoogte.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: Barcode-generator C# – maak DataBar-barcodes en pas de hoogte aan
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcodegenerator in C# te gebruiken om DataBar omnidirectionele barcodes
  te maken
url: /nl/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode generator C# te gebruiken om DataBar Omni‑directionele barcodes te maken

Als je een **barcode generator C#** nodig hebt die hoogwaardige PNG‑afbeeldingen kan produceren, biedt deze gids alles wat je nodig hebt. Je leert hoe je barcode PNG‑bestanden genereert, een DataBar Omni‑directionele barcode maakt, en de barcode‑hoogte aanpast zonder je IDE te verlaten.

Het programmatisch genereren van barcodes verwijdert de handmatige stap van het gebruik van een grafische editor. Aan het einde van deze tutorial heb je twee PNG‑bestanden—een met een bar‑hoogte van 30 pixel en een met een bar‑hoogte van 60 pixel—klaar voor opname in facturen, labels of voorraadbeheersystemen.

**Vereisten**

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
- Een referentie naar het `Aspose.BarCode` NuGet‑pakket (of een bibliotheek die een vergelijkbare API biedt)
- Basiskennis van C# en Visual Studio of je favoriete IDE

---

## Stap 1: Zet het barcode generator C#‑project op

Een **barcode generator C#**‑instantie maken is het eerste wat je doet. De constructor neemt twee argumenten: het barcode‑type (`EncodeTypes.DatabarOmniDirectional`) en de gegevenspayload. In dit voorbeeld volgt de payload het GS1 Application Identifier‑formaat voor een 14‑cijferige GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Waarom dit belangrijk is:** De `EncodeTypes.DatabarOmniDirectional`‑enum vertelt de bibliotheek om een DataBar te renderen die vanuit elke richting kan worden gelezen, wat ideaal is voor kleine retail‑labels.

---

## Stap 2: Definieer de module‑dimensie (X‑dimensie)

De X‑dimensie bepaalt de breedte van een enkele barcode‑module. Instellen op 2 pixels geeft een scherpe, leesbare afbeelding terwijl de bestandsgrootte laag blijft.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** Als je een compactere barcode nodig hebt voor beperkte ruimte, verlaag de waarde naar 1 pixel, maar test de leesbaarheid met een scanner.

---

## Stap 3: Genereer de eerste PNG met een bar‑hoogte van 30 pixel

Bar‑hoogte bepaalt hoe hoog de staven verschijnen. Een hoogte van 30 pixel is een veelvoorkomende standaard voor standaardlabels.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Het bestand `DatabarBarHeight30Pixels.png` bevat nu een **generate barcode PNG** die direct in webpagina's kan worden gebruikt of op aanvraag kan worden afgedrukt.

---

## Stap 4: Pas de barcode‑hoogte aan naar 60 pixel en sla een tweede PNG op

De bar‑hoogte wijzigen is zo simpel als een nieuwe waarde toewijzen aan dezelfde eigenschap. Dit toont de **adjust barcode height**‑functionaliteit van de generator.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Nu heb je `DatabarBarHeight60Pixels.png`, ideaal voor grotere verpakkingen waarbij de barcode van een afstand moet worden gescand.

**Verwachte output**

- `DatabarBarHeight30Pixels.png` – een compacte DataBar Omni‑directionele barcode, 30 px hoog.
- `DatabarBarHeight60Pixels.png` – dezelfde barcode, verdubbeld in hoogte voor betere zichtbaarheid.

Beide afbeeldingen zijn PNG‑bestanden, behouden verliesvrije kwaliteit en ondersteunen transparantie indien nodig.

---

## Hoe barcode PNG‑bestanden in verschillende formaten te genereren

Hoewel deze tutorial zich richt op PNG, accepteert de `Save`‑methode andere formaten zoals `Jpeg`, `Bmp` en `Svg`. Om **how to generate barcode**‑bestanden in een ander formaat te maken, vervang je eenvoudig `BarCodeImageFormat.Png` door de gewenste enum‑waarde:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Kiezen voor SVG is handig wanneer je een vectorafbeelding nodig hebt die schaalt zonder pixelatie.

---

## Veelvoorkomende valkuilen bij het **create DataBar barcode**‑afbeeldingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Barcode ziet er wazig uit | X‑dimensie te laag voor de doelresolutie | Verhoog `XDimension.Pixels` naar 3 of 4 |
| Scanner kan de code niet lezen | Bar‑hoogte te kort voor de optiek van de scanner | Gebruik minimaal 30 pixel of volg de specificaties van de scanner |
| Dataketen wordt afgewezen | Onjuiste GS1‑opmaak | Zorg ervoor dat de string begint met de juiste Application Identifier, bv. `(01)` voor GTIN‑14 |

---

## Geavanceerde tip: dezelfde generator hergebruiken voor meerdere barcodes

Als je **generate barcode PNG**‑bestanden voor een batch producten moet maken, hergebruik dan dezelfde `BarcodeGenerator`‑instantie en werk alleen de `CodeText`‑eigenschap bij:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Dit patroon minimaliseert de overhead van objectcreatie en houdt je code beknopt.

---

## Conclusie

Je hebt nu een volledige **barcode generator C#**‑workflow die **DataBar barcodes** maakt, **barcode PNG**‑bestanden genereert, en je in staat stelt de **barcode height** aan te passen met één enkele eigenschapswijziging. Het voorbeeld behandelt alles van projectopzet tot het omgaan met randgevallen, zodat je barcode‑creatie in elke .NET‑applicatie kunt integreren met vertrouwen.

**Volgende stappen**

- Verken andere barcode‑symbologieën (`EncodeTypes.QR`, `EncodeTypes.Code128`) om je oplossing uit te breiden.
- Combineer de generator met ASP.NET Core om barcodes on‑the‑fly te serveren via een API‑endpoint.
- Experimenteer met kleuropties (`generator.Parameters.Barcode.ForeColor`) voor brandingdoeleinden.

Veel plezier met coderen, en moge je scans altijd snel zijn!

## Wat moet je hierna leren?

- [Hoe barcode‑hoogte te genereren en aan te passen voor één-dimensionale Databar met Aspose.BarCode voor .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Genereer één-dimensionale Databar 2D‑barcodes met Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}