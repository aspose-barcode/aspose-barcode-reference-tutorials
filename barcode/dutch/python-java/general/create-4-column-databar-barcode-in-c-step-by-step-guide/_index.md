---
category: general
date: 2026-08-09
description: Maak snel een 4‑koloms databar‑barcode in C# met Aspose.BarCode. Leer
  hoe je kolommen, rijen configureert en PNG‑afbeeldingen opslaat in deze beknopte
  gids.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: nl
lastmod: 2026-08-09
og_description: Maak een 4‑koloms databar‑streepcode in C# met Aspose.BarCode, pas
  vervolgens rijen aan en exporteer PNG‑afbeeldingen voor uw app.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Maak een 4‑koloms databar barcode in C# – snelle tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Maak een 4‑koloms databar‑barcode in C# – stapsgewijze handleiding
url: /nl/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak 4‑kolom databar barcode in C# – stap‑voor‑stap gids

Als je een **4‑kolom databar barcode** in C# moet maken, laat deze tutorial je precies zien hoe. We lopen door het genereren van een DataBar Expanded Stacked barcode, het configureren van vier kolommen, en het opslaan van het resultaat als een PNG‑afbeelding.

In deze gids leer je hoe je:

* Initialiseer de `BarcodeGenerator` voor een **DataBar Expanded Stacked** symbool.  
* Stel het aantal kolommen in op 4 (de primaire vereiste).  
* Pas het aantal rijen aan wanneer je een gestapelde lay-out met drie rijen nodig hebt.  
* Exporteer de barcode als een PNG met het juiste **barcode image format**.

Je hebt alleen de Aspose.BarCode for .NET bibliotheek nodig (versie 23.10 of later) en een .NET 6+ ontwikkelomgeving zoals Visual Studio 2022. Er zijn geen extra afhankelijkheden vereist.

---

## Hoe maak je een 4‑kolom databar barcode

De eerste stap is het maken van een `BarcodeGenerator`‑instantie die zich richt op de **DataBar Expanded Stacked** symbologie. Deze klasse omvat alle renderopties, waardoor het eenvoudig is om te schakelen tussen kolom‑gebaseerde en rij‑gebaseerde lay-outs.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit werkt:**  
`EncodeTypes.DatabarExpandedStacked` vertelt Aspose.BarCode om de gestapelde versie van de DataBar‑familie te produceren. De eigenschap `DataBar.Columns` bepaalt hoeveel verticale modules de barcode inneemt. Het instellen op 4 voldoet aan de vereiste om een **4‑kolom databar barcode** te **maken**. Ten slotte schrijft `Save` de visuele weergave naar schijf met het **barcode image format** `Png`.

### Configureer DataBar Expanded Stacked kolommen

Als je een ander aantal kolommen nodig hebt, wijzig dan eenvoudig het gehele getal dat aan `Columns` is toegewezen. De eigenschap accepteert waarden van 1 tot 4 voor de expanded stacked variant.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Pro tip:* Test de gegenereerde barcode altijd met een scanner die de DataBar‑familie ondersteunt, omdat alleen de visuele weergave geen leesbaarheid garandeert.

### Sla de barcode‑afbeelding op

De `BarCodeImageFormat`‑enumeratie biedt verschillende opties (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG is verliesvrij en werkt goed voor de meeste web‑ en desktopscenario's.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Als je een ander formaat nodig hebt, vervang dan `Png` door de gewenste enum‑waarde. Het opgeslagen bestand kan direct in HTML, PDF's of op etiketten worden ingevoegd.

## Maak een barcode met aangepaste rijen

Soms is een gestapelde lay-out vereist met een specifiek aantal rijen in plaats van kolommen. Dezelfde `BarcodeGenerator`‑klasse biedt een `Rows`‑eigenschap voor dit doel.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom rijen belangrijk zijn:**  
Wanneer de gestapelde barcode hoger is dan breed, bepaalt de `Rows`‑eigenschap in hoeveel horizontale segmenten het symbool wordt verdeeld. Het instellen van `Rows = 3` creëert een drie‑rij gestapelde barcode, wat nuttig is voor smalle etiketbreedtes.

### Stel barcode‑rijen dynamisch in

Je kunt het aantal rijen tijdens runtime berekenen op basis van invoergegevens:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Deze flexibiliteit stelt je in staat om **barcode‑rijen in te stellen** zonder de applicatie opnieuw te compileren.

## Volledig end‑to‑end voorbeeld

Hieronder staat een enkel programma dat zowel een 4‑kolom barcode als een 3‑rij barcode genereert, en laat zien hoe de twee configuraties naast elkaar bestaan.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Verwachte output:**  
Twee PNG‑bestanden verschijnen in de werkmap van de applicatie:

* `DatabarCols4.png` – een DataBar Expanded Stacked barcode met vier verticale kolommen.  
* `DatabarRows3.png` – dezelfde symbologie gerangschikt in drie horizontale rijen.

Beide afbeeldingen kunnen worden geopend in elke afbeeldingsviewer of ingebed in een UI‑controle.

---

## Veelgestelde vragen en randgevallen

| Vraag | Antwoord |
|----------|--------|
| *Kan ik een andere barcode‑symbologie gebruiken?* | Ja. Vervang `EncodeTypes.DatabarExpandedStacked` door een andere `EncodeTypes`‑waarde (bijv. `EncodeTypes.QR`), maar de `Columns`‑ en `Rows`‑eigenschappen zijn specifiek voor DataBar‑families. |
| *Wat gebeurt er als de gegevensreeks de maximale lengte overschrijdt?* | De DataBar Expanded Stacked symbologie ondersteunt tot 61 numerieke tekens. Het overschrijden van deze limiet veroorzaakt een `ArgumentException`. Valideer de invoer voordat je deze aan de generator toewijst. |
| *Moet ik de `BarcodeGenerator` vrijgeven?* | `BarcodeGenerator` implementeert `IDisposable`. In een langdurige service, wikkel het in een `using`‑blok of roep `Dispose()` handmatig aan om native resources vrij te geven. |
| *Kan ik SVG genereren in plaats van PNG?* | Absoluut. Gebruik `BarCodeImageFormat.Svg` in de `Save`‑methode. |
| *Is de bibliotheek compatibel met .NET Core?* | Aspose.BarCode for .NET ondersteunt .NET Core 3.1, .NET 5, .NET 6 en later. Er zijn geen code‑wijzigingen nodig. |

## Conclusie

Je weet nu hoe je een **4‑kolom databar barcode** in C# kunt **maken** met Aspose.BarCode, hoe je de lay-out met rijen kunt aanpassen, en hoe je het resultaat kunt exporteren in een handig **barcode image format**. Het volledige voorbeeld toont zowel kolom‑gebaseerde als rij‑gebaseerde configuraties, waardoor je een solide basis hebt voor elke label‑print‑ of mobiele‑scan‑situatie.

**Volgende stappen**

* Experimenteer met verschillende gegevenspayloads en controleer de scanner‑compatibiliteit.  
* Verken extra stylingopties zoals voor‑/achtergrondkleuren (`generator.Parameters.Barcode.Color`).  
* Combineer de barcode met andere grafische elementen via de `Graphics`‑API voor aangepaste label‑ontwerpen.

Voel je vrij om de code aan te passen voor ASP.NET Core, Windows Forms of Xamarin‑projecten—Aspose.BarCode werkt op alle .NET‑platformen. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak DotCode barcode‑afbeelding – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Maak barcode‑afbeelding c# – Configureer Codablock F rijen & kolommen](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Hoe maak je dotcode uitgebreide codetext met Aspose.BarCode voor .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}