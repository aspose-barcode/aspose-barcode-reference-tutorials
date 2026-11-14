---
category: general
date: 2026-11-14
description: Leer hoe je snel een PDF417-barcode in C# maakt. Deze gids laat ook zien
  hoe je PDF417 genereert en hoe je de PDF417-instellingen kunt aanpassen voor precieze
  controle.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: nl
lastmod: 2026-11-14
og_description: Maak een PDF417‑barcode in C# met stapsgewijze instructies. Leer hoe
  je PDF417 genereert en hoe je PDF417‑parameters aanpast voor exacte resultaten.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: PDF417-barcode maken in C# – volledige gids met aangepaste lay-out
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Hoe maak je een PDF417-barcode met aangepaste lay-out in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te maken met aangepaste lay-out in C#

Als je een **pdf417 barcode** moet maken voor een ticketsysteem, voorraadlabel of mobiele‑app scan, laat deze tutorial het volledige proces zien. Je ziet hoe je PDF417 snel kunt genereren en hoe je PDF417‑instellingen zoals kolommen en rijen kunt aanpassen, zodat de barcode past binnen je ontwerpbeperkingen.

Het genereren van een barcode vereist geen complexe grafische bibliotheek—alleen Aspose.BarCode for .NET (of een compatibele API). Aan het einde van deze gids heb je een kant‑klaar PNG‑bestand dat je kunt insluiten in PDF's, webpagina's of direct vanuit je applicatie kunt afdrukken.

## Vereisten

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
- Aspose.BarCode for .NET (NuGet‑pakket `Aspose.BarCode`)
- Basiskennis van C# en Visual Studio (of een IDE)

> **Pro tip:** Als je een CI/CD‑pipeline gebruikt, voeg dan de NuGet‑pakketreferentie toe in je projectbestand zodat builds reproduceerbaar blijven.

## Stap 1: Installeer de barcode‑bibliotheek

Open je projectmap in een terminal en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket bevat de `BarcodeGenerator`‑klasse die door de hele tutorial wordt gebruikt. Er zijn geen extra native afhankelijkheden nodig.

## Stap 2: Maak een basis‑PDF417‑barcode

Het eerste doel is om een **pdf417 barcode** te **maken** met standaardinstellingen. Het volgende programma configureert de generator, codeert een voorbeeldtekst en slaat het resultaat op als een PNG‑afbeelding.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Waarom dit werkt:**  
`EncodeTypes.Pdf417` vertelt de bibliotheek om de PDF417‑symbologie te gebruiken. De constructor maakt automatisch een `Barcode`‑object aan met standaard kolom‑/rij‑waarden die de scanbaarheid voor de meeste toepassingen garanderen.

Voer het programma uit (`dotnet run`). Je vindt `Pdf417Default.png` in de projectmap. Het openen van de afbeelding toont een standaard PDF417‑barcode klaar om te scannen.

![Voorbeeld van PDF417 barcode](https://example.com/images/pdf417-default.png){:alt="Voorbeeld van PDF417 barcode met standaard lay-out"}

## Stap 3: PDF417 genereren met aangepaste afmetingen

Soms vereist een label met vaste afmeting of een UI‑component een specifiek barcode‑voetafdruk. Dan is **hoe je pdf417 genereert** met aangepaste kolommen en rijen essentieel.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Waarom je dit zou willen:**  
- **Beperkte breedte:** Het verminderen van kolommen en verhogen van rijen creëert een bredere maar kortere barcode, perfect voor smalle labels.  
- **Beperkte hoogte:** Het verhogen van kolommen en verlagen van rijen levert een hogere, smallere barcode op, handig wanneer je verticale ruimte hebt.

Zowel `Columns` als `Rows` accepteren alleen waarden binnen de gedocumenteerde bereiken (2‑30 voor kolommen, 1‑90 voor rijen). Het opgeven van een waarde buiten het bereik veroorzaakt een `ArgumentOutOfRangeException`, dus valideer altijd gebruikersinvoer als je deze instellingen in een UI beschikbaar maakt.

## Stap 4: PDF417 verder aanpassen

Naast kolommen en rijen biedt de PDF417‑symbologie veel optionele parameters:

| Eigenschap | Doel | Typische waarden |
|------------|------|------------------|
| `ErrorLevel` | Regelt de foutcorrectiecapaciteit | 0‑8 (hoger = robuuster) |
| `MacroPdf417` | Schakelt macro PDF417 in voor multi‑segment data | `true`/`false` |
| `CompactPdf417` | Genereert een compactere barcode ten koste van verminderde foutcorrectie | `true`/`false` |
| `SecurityLevel` | Voegt een beveiligingscontrolesom toe | 0‑2 |

Hier is een snel voorbeeld dat ook het foutniveau instelt op het maximum (8) voor een lawaaierige omgeving:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Waarom het belangrijk is:**  
Hogere foutcorrectie stelt scanners in staat om gegevens te herstellen zelfs als een deel van de barcode beschadigd is. Het vergroot echter ook de barcode‑grootte, dus weeg de instelling af tegen je lay‑outbeperkingen.

## Stap 5: Verifieer dat de barcode werkt

Na het genereren van de PNG, test je deze met een barcode‑scanner‑app (de meeste smartphones hebben gratis PDF417‑lezers). Als de scanner de oorspronkelijke tekst (`Custom layout text`) teruggeeft, is de barcode geldig.

Als je scanning‑problemen ondervindt:

1. **Controleer afmetingen:** Zorg dat kolommen/rijen binnen het toegestane bereik blijven.  
2. **Pas foutniveau aan:** Verhoog `ErrorLevel` voor beschadigde media.  
3. **Beoordeel beeldkwaliteit:** Sla op met een hogere DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) als je van plan bent te printen.

## Volledige broncode voor een herbruikbare helper

Hieronder staat een compacte, herbruikbare klasse die je in elk .NET‑project kunt plaatsen. Het omvat **hoe je pdf417 genereert** en **hoe je pdf417 aanpast** in één enkele methode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Je kunt deze helper aanroepen als:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

De methode abstraheert de repetitieve boiler‑plate, zodat je je kunt concentreren op de bedrijfslogica.

## Veelvoorkomende valkuilen en hoe ze te vermijden

- **Waarden buiten bereik:** Valideer altijd `columns` en `rows` voordat je ze toewijst.  
- **Onjuist afbeeldingsformaat:** Sommige oudere scanners accepteren alleen BMP of JPEG. Gebruik `BarCodeImageFormat.Bmp` indien nodig.  
- **Lage DPI voor afdrukken:** De standaard DPI is 96. Voor afdrukken van hoge kwaliteit stel je expliciet een hogere DPI in (bijv. 300) bij het aanroepen van `Save`.  
- **Ontbrekende lettertype‑ondersteuning:** PDF417 codeert binaire data, dus je hoeft meestal geen lettertype op te geven. Als je echter tekst over de afbeelding legt, zorg dan dat het lettertype op de doelmachine geïnstalleerd is.

## Conclusie

Je weet nu hoe je een **pdf417 barcode** van begin tot eind kunt **maken**, hoe je **pdf417 genereert** met aangepaste kolom‑/rij‑instellingen, en hoe je **pdf417 aanpast** voor foutcorrectie en compactheid. Door het herbruikbare helper‑patroon te volgen kun je barcodes on‑demand genereren, ze aanpassen aan elke lay‑outbeperking, en betrouwbare scanning in productieomgevingen garanderen.

**Volgende stappen**

- Verken andere symbologieën zoals QR of Code128 met dezelfde `BarcodeGenerator`‑klasse.  
- Combineer de PNG‑output met een PDF‑generatie‑bibliotheek (bijv. iText7) om barcodes in facturen in te sluiten.  
- Experimenteer met `MacroPdf417` voor multi‑segment datatransmissie, een functie die nuttig is in logistiek‑ en transporttoepassingen.

Veel programmeerplezier, en moge je barcodes altijd bij de eerste poging scannen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 barcode te genereren in C# – stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hoe barcode te genereren en PDF417 barcode aan te passen in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Hoe PDF417 barcode te maken en PNG te exporteren in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}