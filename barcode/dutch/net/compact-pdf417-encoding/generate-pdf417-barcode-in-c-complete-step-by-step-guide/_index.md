---
category: general
date: 2026-07-15
description: Genereer PDF417-barcode snel met C#. Leer hoe je een barcode uit tekst
  genereert, de barcodegrootte aanpast en aangepaste barcode-afmetingen instelt in
  enkele minuten.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: nl
lastmod: 2026-07-15
og_description: Genereer PDF417‑barcode in C# direct. Deze gids laat zien hoe je een
  barcode uit tekst genereert, de barcodegrootte aanpast en aangepaste barcode‑afmetingen
  toepast.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Genereer PDF417-barcode in C# – Volledige programmeertutorial
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Genereer PDF417‑barcode in C# – Complete stap‑voor‑stap gids
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 Barcode genereren in C# – Complete Staps‑voor‑Stap Gids

Heb je ooit **een PDF417 barcode moeten genereren** maar wist je niet welke instellingen je moest aanpassen? Je bent niet de enige—veel ontwikkelaars lopen tegen dezelfde muur aan wanneer ze voor het eerst met 2‑D barcodes werken. Het goede nieuws? Met een paar regels C# kun je elke string omzetten in een scanbare PDF417‑afbeelding, de exacte grootte regelen en zelfs een aangepaste kolom‑rij‑indeling definiëren.

In deze tutorial lopen we stap voor stap uit hoe je **een barcode uit tekst genereert**, de barcodegrootte aanpast, en aangepaste barcode‑dimensies instelt — alles met de populaire Aspose.BarCode‑bibliotheek. Aan het einde heb je een kant‑klaar voorbeeld dat je in elk .NET‑project kunt gebruiken.

![Voorbeeld van PDF417 barcode genereren](https://example.com/og-image.png "Voorbeeld van PDF417 barcode genereren")

## Wat je gaat bouwen

- Een PDF417 barcode die de string `Åspóse.Barcóde©` codeert.
- Nauwkeurige controle over de X‑dimensie (pixelbreedte van elke module).
- Een aangepaste indeling van 4 kolommen en 9 rijen.
- Een PNG‑bestand dat op schijf wordt opgeslagen.

Geen externe services, geen toverstaf‑trucs—gewoon platte C#‑code die je direct kunt compileren.

## Vereisten

- .NET 6.0 of hoger (de code werkt ook op .NET Framework 4.8).
- Visual Studio 2022 of een IDE die C# ondersteunt.
- Aspose.BarCode voor .NET (gratis proefversie of gelicentieerde versie). Installeer via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Dat is alles—zodra het pakket is toegevoegd, ben je klaar om te gaan.

## Stap 1 – PDF417 Barcode genereren met tekstgegevens

Het eerste wat we nodig hebben is een instantie van `BarcodeGenerator` die weet dat we met PDF417‑symbologie werken en de exacte tekst die we willen coderen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Waarom dit belangrijk is:**  
> `EncodeTypes.Pdf417` vertelt de bibliotheek om het PDF417 2‑D‑formaat te gebruiken, terwijl het tweede argument de **barcode uit tekst genereren** payload is. Alles wat je hier opgeeft, wordt de data die in de barcode‑matrix wordt opgeslagen.

## Stap 2 – Barcodegrootte aanpassen (X‑dimensie)

Als je ooit een barcode hebt afgedrukt die te klein op een bon stond, ken je de frustratie dat de scanner hem mist. De eigenschap `XDimension` bepaalt de breedte van één module (het kleinste zwarte of witte vierkant) in pixels.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Pro tip:**  
> Een waarde van 2 px werkt goed voor de meeste scherm‑weergaves. Voor hoge‑resolutie‑afdrukken kun je dit verhogen naar 3 of 4 px. Houd er rekening mee dat grotere X‑dimensies de totale afbeeldingsgrootte vergroten.

## Stap 3 – Aangepaste barcode‑dimensies instellen (Kolommen & Rijen)

PDF417 laat je bepalen hoeveel kolommen en rijen de barcode moet innemen. Hier komen de **aangepaste barcode‑dimensies** om de hoek kijken. Het aanpassen van deze waarden kan je helpen de barcode in een krappe UI‑ruimte te passen of te voldoen aan een specifiek labelformaat.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Wat gebeurt er onder de motorkap?**  
> De bibliotheek verdeelt de gecodeerde data opnieuw over het opgegeven raster. Minder kolommen betekent hogere barcodes; meer rijen maken ze korter. Speel met de getallen totdat de visuele balans goed voelt voor jouw toepassing.

## Stap 4 – Barcode‑afbeelding opslaan

Nu we alles hebben geconfigureerd, vragen we de generator simpelweg om een PNG‑bestand te schrijven. PNG is verliesloos, dus de scherpte van de modules blijft behouden.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Wanneer je het programma uitvoert, zou je een bestand moeten zien op `C:\Barcodes\CustomLayout.png` dat lijkt op de screenshot hierboven. Het scannen ervan met een PDF417‑compatibele lezer geeft de oorspronkelijke string `Åspóse.Barcóde©` terug.

## Volledig Werkend Voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren‑en‑plakken in een console‑applicatie. Het bevat alle using‑directives en foutafhandeling die je in productiecodel verwacht.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Verwachte Output

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…en maakt een PNG die in elke afbeeldingsviewer kan worden geopend. Als je het scant met een mobiele app (bijv. “Barcode Scanner” op iOS/Android), moet de gedecodeerde tekst exact **Åspóse.Barcóde©** zijn.

## Veelgestelde Vragen & Randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik een ander afbeeldingsformaat gebruiken?** | Ja—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, of `Svg` worden allemaal ondersteund. Verander gewoon het tweede argument van `Save`. |
| **Wat als mijn tekst Unicode‑tekens bevat?** | Aspose.BarCode ondersteunt volledig UTF‑8, dus het voorbeeld met `Å` en `©` werkt direct. |
| **Hoe wijzig ik het fout‑corrigatieniveau?** | Gebruik `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (niveaus 0‑8). Hogere niveaus verhogen de redundantie maar ook de grootte. |
| **Ik heb een transparante achtergrond nodig—kan ik dat doen?** | Stel `generator.Parameters.Barcode.Image.TransparentBackground = true;` in vóór het opslaan. |
| **Is er een manier om de barcode direct in een PDF in te sluiten?** | Absoluut. Vervang de `Save`‑aanroep door `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` en je krijgt een één‑pagina PDF met de barcode. |

## Conclusie

Je weet nu hoe je **een PDF417 barcode kunt genereren** in C# vanuit elke string, **de barcodegrootte kunt aanpassen**, en **aangepaste barcode‑dimensies** kunt toepassen om aan je lay-outbehoeften te voldoen. De vier‑stappen‑stroom—initialiseren, grootte, lay-out, opslaan—dekt de kernworkflow voor de meeste 2‑D barcode‑scenario's.

Wat is het volgende? Probeer `EncodeTypes.Pdf417` te vervangen door `EncodeTypes.QR` of `EncodeTypes.Code128` om te zien hoe de API zich aanpast. Experimenteer met verschillende `XDimension`‑waarden, speel met de kolom/rij‑matrix, of voeg de afbeelding in een PDF‑rapport in. De mogelijkheden zijn praktisch eindeloos, en nu heb je een solide basis om op voort te bouwen.

Heb je meer vragen, of een slimme truc ontdekt tijdens het werken met PDF417? Laat een reactie achter—laten we het gesprek gaande houden. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een Aztec barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hoe een barcode te genereren – Eén‑dimensionale barcode‑typen](/barcode/english/net/one-dimensional-barcode-types/)
- [DataMatrix barcode genereren – Pro‑gids met Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}