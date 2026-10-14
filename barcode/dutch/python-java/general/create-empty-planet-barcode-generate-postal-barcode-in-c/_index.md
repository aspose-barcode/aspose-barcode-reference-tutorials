---
category: general
date: 2026-10-08
description: Maak een lege planet barcode met C# en leer hoe je een postbarcode genereert
  met Aspose.BarCode. Stap‑voor‑stap code en tips inbegrepen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: nl
lastmod: 2026-10-08
og_description: Maak een lege planet barcode met Aspose.BarCode in C# en zie hoe je
  postbarcode‑afbeeldingen kunt genereren voor mailingtoepassingen.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Maak een lege planeetbarcode – C# gids voor postbarcode
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Maak lege planeetbarcode, genereer postbarcode in C#
url: /nl/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak lege planet barcode, genereer postbarcode in C#

Als u een **lege planet barcode** moet maken voor een postverwerkingssysteem, laat deze gids u precies zien hoe u dit doet met Aspose.BarCode voor .NET. U leert ook **hoe u postbarcode** afbeeldingen zoals Planet en RM4SCC kunt genereren, de balkbreedte kunt aanpassen en de optie voor gevulde‑balken kunt regelen.

Het genereren van postbarcodes vereist geen aparte grafische bibliotheek. De Aspose.BarCode SDK biedt één enkele API die codering, afbeeldingsrendering en selectie van afbeeldingsformaten afhandelt. Aan het einde van deze tutorial heeft u drie kant‑klaar PNG‑bestanden:

* `PostalPlanetEmptyBars.png` – een lege‑balken Planet barcode  
* `PostalPlanetFilledBars.png` – de standaard gevulde‑balken Planet barcode  
* `PostalRM4SCCFilledBars.png` – een gevulde‑balken RM4SCC barcode  

U kunt deze bestanden in elke postetiket‑template plaatsen, afdrukken op enveloppen, of doorgeven aan een externe dienst.

## Vereisten

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+).  
* Visual Studio 2022 of een C#‑IDE.  
* Aspose.BarCode for .NET – installeren via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Er zijn geen extra afhankelijkheden vereist.

## Maak lege planet barcode met Aspose.BarCode

De Planet‑symbologie maakt deel uit van de barcode‑familie van de United States Postal Service (USPS). Standaard tekent de SDK **gevulde** balken. Om een **lege planet barcode** te **maken**, schakelt u de `FilledBars`‑vlag uit.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Waarom dit werkt:**  
`EncodeTypes.Planet` vertelt de generator om de Planet‑symbologie te gebruiken. `XDimension.Pixels` regelt de fysieke breedte van elke balk, wat cruciaal is voor postscanners die een specifieke modulegrootte verwachten. Het instellen van `FilledBars` op `false` vertelt de renderer alleen de omtrek van elke balk te tekenen, waardoor het *lege* uiterlijk ontstaat dat door sommige postnormen vereist is.

### Verwachte output

U vindt `PostalPlanetEmptyBars.png` in de doelmap. De afbeelding toont een Planet‑barcode waarbij elke balk een omtrek is in plaats van een solide rechthoek.

![Voorbeeld lege Planet barcode](empty-planet.png){: .align-center alt="Maak lege planet barcode – voorbeeld van een lege‑balken Planet barcode"}

## Hoe postbarcode‑afbeeldingen te genereren (gevulde versie)

De meeste postprocessen gebruiken de standaard gevulde‑balken versie. dezelfde API kan een gevulde Planet‑barcode en een RM4SCC‑barcode genereren met slechts een paar regels code.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Waarom u RM4SCC nodig zou kunnen hebben:**  
RM4SCC is de nieuwere USPS‑barcode die dezelfde gegevens als Planet codeert maar met een hogere dichtheid. Sommige vervoerders vereisen RM4SCC voor bulk‑mailkortingen. De bovenstaande code laat zien hoe u **postbarcode kunt genereren** voor beide standaarden zonder de algehele workflow te wijzigen.

### Verwachte output

* `PostalPlanetFilledBars.png` – een klassieke gevulde‑balken Planet barcode.  
* `PostalRM4SCCFilledBars.png` – een gevulde‑balken RM4SCC barcode, visueel vergelijkbaar maar met strakkere spatiëring.

Beide bestanden kunnen in elke afbeeldingsviewer worden geopend om de balkpatronen te verifiëren.

## Aanpassen van balkbreedte voor verschillende afdrukresoluties

Postscanners geven vaak een minimale modulebreedte op (bijv. 0.013 inches). Als uw printer werkt op 300 dpi, komt een 4‑pixel module overeen met 0.013 inches. Pas de `XDimension.Pixels`‑waarde aan om overeen te komen met uw hardware:

| Gewenste module (inches) | DPI | Pixels nodig (`XDimension`) |
|--------------------------|-----|------------------------------|
| 0.013                    | 300 | 4                            |
| 0.013                    | 600 | 8                            |
| 0.015                    | 300 | 5                            |

**Pro tip:** Test altijd een

## Wat moet u hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om u te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in uw eigen projecten te verkennen.

- [Hoe een planet barcode PNG te maken met C# – stap‑voor‑stap gids](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Genereer postbarcode in C# – volledige gids met Planet barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Hoe postbarcode te genereren in C# met Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}