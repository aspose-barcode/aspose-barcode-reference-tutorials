---
category: general
date: 2026-11-20
description: Maak snel een postbarcode‑afbeelding in C#. Leer hoe je planet‑barcode
  en RM4SCC‑barcode kunt genereren met aanpasbare balkstijlen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: nl
lastmod: 2026-11-20
og_description: Maak een postbarcode‑afbeelding in C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je een planet‑barcode genereert, balkstijlen aanpast en RM4SCC‑afbeeldingen
  maakt.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Maak een postbarcode‑afbeelding in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Maak een postbarcode-afbeelding en genereer een planeetbarcode
url: /nl/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een postbarcode‑afbeelding en genereer een planet‑barcode

Maak een postbarcode‑afbeelding in C# met behulp van de Aspose.BarCode‑bibliotheek. Als je een planet‑barcode of RM4SCC‑barcodes moet genereren voor mailingtoepassingen, biedt deze tutorial een complete, kant‑en‑klare oplossing.

Het genereren van barcodes voor postdiensten vereist vaak precieze afmetingen en de mogelijkheid om te schakelen tussen gevulde en lege balkstijlen. Deze gids leidt je stap voor stap door het instellen van de outputmap, het maken van zowel gevulde als lege Planet‑barcodes, en het produceren van een RM4SCC‑barcode met dezelfde visuele instellingen. Aan het einde heb je vier PNG‑bestanden die je direct in je mailing‑workflow kunt gebruiken.

## Vereisten

* .NET 6.0 of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE naar keuze)  
* Het **Aspose.BarCode** NuGet‑pakket (`Install-Package Aspose.BarCode`)  

Er is geen extra configuratie nodig; de code gebruikt alleen het standaardlettertype en de PNG‑encoder.

## Maak postbarcode‑afbeelding – overzicht

De kern van het proces is de `BarcodeGenerator`‑klasse. Deze accepteert een `EncodeTypes`‑waarde die de barcode‑symbologie bepaalt (bijvoorbeeld `EncodeTypes.Planet` voor een Planet‑barcode). Nadat je de generator hebt geconfigureerd, roep je `Save` aan om het afbeeldingsbestand weg te schrijven.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt‑tekst: Voorbeeld van een postbarcode‑afbeelding met gevulde en lege balken.*

## Stap 1: Stel de outputmap in

Definieer eerst een map waar de PNG‑bestanden worden opgeslagen. Een absoluut of relatief pad werkt op dezelfde manier; zorg er alleen voor dat de map bestaat of laat de code deze aanmaken.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Het programmatic aanmaken van de map voorkomt `DirectoryNotFoundException` wanneer de tutorial op een nieuwe machine wordt uitgevoerd.

## Stap 2: Genereer planet‑barcode met gevulde balken

Een gevulde‑balk Planet‑barcode is de standaard visuele stijl. De volgende code maakt de barcode, stelt de X‑dimensie in op 4 pixels (een gangbare grootte voor posttoepassingen) en slaat de afbeelding op.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Waarom dit werkt:**  
* `EncodeTypes.Planet` vertelt de generator om de Planet‑symbologie te gebruiken, wat vereist is voor veel postdiensten.  
* `XDimension.Pixels` bepaalt de breedte van elke balk; 4 px levert een duidelijke, scanbare afbeelding op zonder een te groot bestand.  
* De `Save`‑methode selecteert automatisch de PNG‑encoder op basis van de `BarCodeImageFormat`‑enum.

## Stap 3: Genereer planet‑barcode met lege balken

Sommige postspecificaties geven de voorkeur aan lege (witte) balken op een donkere achtergrond. Dit kun je bereiken door `FilledBars` op `false` te zetten.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** Wanneer `FilledBars` `false` is, schildert de generator de balken in de achtergrondkleur (standaard wit) en de ruimtes in de voorgrondkleur (zwart). Als je een ander kleurenschema nodig hebt, pas je `Parameters.Barcode.ForeColor` en `BackColor` aan.

## Stap 4: Genereer RM4SCC‑barcode met gevulde balken

RM4SCC is een andere postsymbologie die in het Verenigd Koninkrijk wordt gebruikt. De creatiestappen zijn gelijk aan het Planet‑voorbeeld; alleen de `EncodeTypes`‑waarde verandert.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Wat je kunt verwachten:** De resulterende PNG toont een compacte RM4SCC‑barcode die voldoet aan de Britse postrichtlijnen. De afbeeldingsgrootte zal vergelijkbaar zijn met die van de Planet‑barcodes omdat de X‑dimensie identiek is.

## Stap 5: Verifieer de gegenereerde afbeeldingen

Na het uitvoeren van het programma, open je de vier bestanden in de map `Barcodes`. Je zou moeten zien:

* `PostalPlanetFilledBars.png` – donkere balken op een lichte achtergrond  
* `PostalPlanetEmptyBars.png` – lichte balken op een donkere achtergrond (invers)  
* `PostalRM4SCCFilledBars.png` – standaard RM4SCC‑patroon  

Als een afbeelding vervormd lijkt, controleer dan het volgende:

* **X‑dimension** – te klein (< 2 px) kan vervaging veroorzaken; te groot (> 10 px) kan de label‑grootte‑limieten overschrijden.  
* **Data string** – de waarde `"123456"` moet voldoen aan de lengtvereisten van de gekozen symbologie (Planet verwacht 6 cijfers, RM4SCC verwacht eveneens 6 cijfers).  
* **Map‑rechten** – zorg ervoor dat de applicatie schrijfrechten heeft voor de outputdirectory.

## Veelvoorkomende variaties en randgevallen

| Scenario | Aanpassing |
|----------|------------|
| **Andere barcode‑gegevens** | Vervang `"123456"` door een geldige numerieke tekenreeks. Voor Planet moet de lengte exact 6 cijfers zijn; RM4SCC vereist ook 6 cijfers. |
| **Aangepaste kleuren** | Stel `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` en `BackColor = System.Drawing.Color.LightYellow;` in. |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` naar 6 of 8 voor grotere afdrukken. |
| **Andere afbeeldingsformaten** | Gebruik `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp` in de `Save`‑aanroep. |
| **Batchgeneratie** | Loop over een collectie tekenreeksen en roep dezelfde generatorlogica aan binnen de lus, waarbij je het `outputFolder`‑pad hergebruikt. |

## Volledig, uitvoerbaar voorbeeld

Kopieer de onderstaande code naar een nieuw C#‑console‑project. Het compileert met .NET 6.0 en produceert automatisch alle vier de barcode‑afbeeldingen.



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een postbarcode‑afbeelding met aangepaste hoogtes in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Hoe maak je een RM4SCC‑barcode en genereer je een planet‑barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Maak een postbarcode‑afbeelding in C# – stap‑voor‑stap‑gids](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}