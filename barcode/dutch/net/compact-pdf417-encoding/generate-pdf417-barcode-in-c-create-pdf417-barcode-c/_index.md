---
category: general
date: 2026-07-24
description: Genereer PDF417‑barcode in C# met Aspose.BarCode. Leer hoe je in enkele
  minuten een PDF417‑barcode in C# met compacte modus maakt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: nl
lastmod: 2026-07-24
og_description: Genereer PDF417-barcode in C# snel met Aspose.BarCode. Deze tutorial
  laat zien hoe je een PDF417-barcode in C# maakt in compacte modus, inclusief installatie,
  code en verificatie.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: PDF417-barcode genereren in C# – Snelle gids
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Genereer PDF417‑barcode in C# – Maak PDF417‑barcode in C#
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-barcode genereren in C# – Complete programmeerhandleiding

Heb je je ooit afgevraagd hoe je **PDF417 barcode genereren** kunt in een C#‑applicatie zonder eindeloze forumthreads te doorzoeken? Je bent niet de enige. Of je nu een ticketsysteem, een beveiligde ID‑kaart bouwt, of gewoon een snelle manier nodig hebt om gegevens in een afdrukbaar formaat in te sluiten, het beheersen van het PDF417‑formaat kan je uren aan trial‑and‑error besparen.

In deze gids lopen we een **volledig, kant‑klaar voorbeeld** door dat je precies laat zien hoe je **PDF417 barcode C# maakt** met de populaire Aspose.BarCode‑bibliotheek. We behandelen alles, van het installeren van het NuGet‑pakket tot het aanpassen van de compacte modus, zodat je de code kunt kopiëren‑plakken en direct resultaten ziet.

## Wat je zult leren

- Hoe je de Aspose.BarCode‑bibliotheek instelt in een .NET‑project.  
- De exacte C#‑statements die nodig zijn om **PDF417 barcode te genereren** met aangepaste tekst, modulegrootte en kolomaantal.  
- Waarom het schakelen van de *Compact* (Truncate)‑optie belangrijk is voor dichte data.  
- Manieren om de barcode op te slaan als PNG en de output te verifiëren.  

Ervaring met barcodes is niet vereist; alleen een basisbegrip van C# en Visual Studio (of een IDE naar keuze). Aan het einde heb je een herbruikbare methode die je in elk project kunt plaatsen dat een PDF417‑afbeelding nodig heeft.

## Vereisten

| Vereiste | Waarom het belangrijk is |
|----------|--------------------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode ondersteunt beide; nieuwere runtimes bieden betere prestaties. |
| Visual Studio 2022 (or VS Code with C# extensions) | Biedt IntelliSense en eenvoudige debugging. |
| Internet connection (for the first NuGet restore) | De bibliotheek wordt opgehaald van NuGet.org. |
| Basic C# knowledge | Nodig om klassenstructuren en methode‑aanroepen te begrijpen. |

Als je deze al hebt, prima—laten we erin duiken.

## Installeer het Aspose.BarCode NuGet‑pakket

Open je projectmap in een terminal en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Of, binnen Visual Studio, klik met de rechtermuisknop op **Dependencies → Manage NuGet Packages**, zoek naar *Aspose.BarCode* en klik op **Install**. Deze enkele regel brengt alle typen die we gaan gebruiken binnen, inclusief `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat`.

> **Pro tip:** Na de installatie, maak de oplossing schoon en bouw opnieuw om te zorgen dat de assembly correct wordt gerefereerd.

## PDF417-barcode genereren – Setup en afhankelijkheden

Allereerst hebben we een `using`‑blok nodig dat de relevante namespaces in scope haalt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Deze namespaces geven ons toegang tot de generator‑klasse en de enumeratie van barcode‑typen. Niets bijzonders—slechts drie regels, en we zijn klaar om de barcode te maken.

## PDF417-barcode maken in C# – Stapsgewijze implementatie

Hieronder staat een **zelfstandige console‑applicatie** die een compacte PDF417‑barcode maakt van de string `"Åspóse.Barcóde©"` en opslaat als `CompactPdf417.png`. Voel je vrij de tekst te vervangen door wat je nodig hebt; de generator verwerkt Unicode‑tekens direct.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Waarom elke stap belangrijk is

1. **Gegevensdefinitie** – PDF417 kan tot ~1850 tekens opslaan, maar we houden het kort voor de demo. Unicode‑ondersteuning betekent dat die accenten geen problemen veroorzaken.  
2. **Generatorconstructie** – De enum‑waarde `EncodeTypes.Pdf417` vertelt Aspose welke symbologie te gebruiken; vervangen door `EncodeTypes.QR` zou een QR‑code opleveren.  
3. **X‑dimensie** – Dit bepaalt de breedte van elke module (de kleine vierkantjes waaruit de barcode bestaat). Een waarde van `2` pixels levert een scherp beeld op dat nog leesbaar is bij afdrukken op 300 dpi.  
4. **PDF417‑opties** – `Columns` beïnvloedt de beeldverhouding van de barcode; minder kolommen maken de afbeelding hoger, wat handig kan zijn voor bonnen. `Truncate` (ook wel *Compact‑modus* genoemd) verwijdert de start/stop‑patroon‑padding, waardoor de bestandsgrootte afneemt zonder de gegevensintegriteit te schaden.  
5. **Uitvoerpad** – Het gebruik van `Environment.CurrentDirectory` zorgt ervoor dat de afbeelding naast het uitvoerbare bestand wordt geplaatst, waardoor hij tijdens ontwikkeling gemakkelijk te vinden is.  
6. **Opslaan** – `BarCodeImageFormat.Png` levert verliesvrije kwaliteit, perfect voor verdere verwerking of inbedden in PDF‑bestanden.  

Voer het programma uit (`dotnet run` of druk op **F5** in Visual Studio). Na een paar seconden zie je een console‑bericht dat de bestandslocatie bevestigt, en de PNG verschijnt in je projectmap.

![Genereer PDF417 barcode voorbeeld](generated-pdf417.png)

*Afbeelding alt‑tekst: generate pdf417 barcode example – PNG‑afbeelding van een compacte PDF417‑barcode gemaakt met C#.*

## Compacte modus configureren – c# barcode‑generator pdf417‑opties

Als je een grotere barcode nodig hebt (misschien voor scannen op afstand), pas dan de eigenschappen `Columns` en `Rows` aan. Hier is een kort fragment dat alternatieve configuraties laat zien:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Veelgestelde vraag:** *Zal het uitschakelen van Truncate bestaande scanners breken?*  
> Meestal niet. De meeste moderne scanners begrijpen zowel volledige als compacte PDF417. Als je echter op legacy‑hardware mikt, laat `Truncate` dan op `false` staan.

## Opslaan en verifiëren – hoe PDF417‑barcode‑output te genereren

Na het opslaan kun je de PNG openen met elke beeldviewer. Om dubbel te controleren dat de barcode de beoogde gegevens codeert, gebruik je Aspose’s `BarCodeReader`:



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Barcode toevoegen aan PDF met Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}