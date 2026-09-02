---
category: general
date: 2026-07-18
description: Genereer een barcode met tekst met Aspose.BarCode voor .NET. Leer hoe
  je PDF417‑barcodes genereert, macro‑opties instelt en PNG‑afbeeldingen exporteert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: nl
lastmod: 2026-07-18
og_description: Genereer barcode met tekst in C# snel. Deze stapsgewijze tutorial
  laat zien hoe je PDF417-barcodes genereert, macro‑instellingen configureert en opslaat
  als PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Barcode genereren met tekst – Master PDF417 Macro Creatie
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Barcode genereren met tekst – Volledige PDF417 Macro‑gids
url: /nl/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode genereren met tekst – Volledige PDF417 Macro‑gids

Heb je je ooit afgevraagd **hoe je PDF417** barcodes kunt genereren die ook aangepaste tekst bevatten? In deze tutorial zie je precies hoe je **barcode met tekst genereert** met Aspose.BarCode for .NET, en we lopen alle instellingen door die je nodig hebt voor een Macro PDF417 symbool. Geen poespas, alleen een compleet, uitvoerbaar voorbeeld dat je vandaag nog in je project kunt plaatsen.

Wij behandelen:

* Het vereiste NuGet‑pakket en using‑directieven.  
* Hoe je een barcode‑generator maakt die Unicode‑tekens bevat.  
* Het instellen van de module‑grootte, kolom‑aantal en macro‑specifieke ID’s.  
* Het opslaan van het resultaat als PNG‑bestand en het verifiëren van de output.  

Aan het einde heb je een kant‑klaar PNG‑beeld van een Macro PDF417 barcode die je kunt insluiten in facturen, tickets of elk document dat een machine‑leesbaar segment nodig heeft.

---

## Voorvereisten

Before we dive in, make sure you have:

| Vereiste | Reden |
|----------|-------|
| **.NET 6.0** of later | Aspose.BarCode ondersteunt .NET Standard 2.0+, dus .NET 6 geeft je de nieuwste runtime. |
| **Visual Studio 2022** (of elke C# IDE) | Voor eenvoudig bewerken en debuggen. |
| **Aspose.BarCode for .NET** NuGet‑pakket | De bibliotheek die daadwerkelijk de barcode maakt. Installeer het met `dotnet add package Aspose.BarCode`. |
| **Schrijfrechten** voor de doelmap | De `Save`‑methode moet het PNG‑bestand schrijven. |

Als een van deze je onbekend voorkomt, pauzeer dan en zorg dat je ze regelt—anders zal de code duidelijke uitzonderingen werpen.

---

## Stap 1 – Installeer en importeer de bibliotheek

Eerst voeg je het NuGet‑pakket toe aan je project:

```bash
dotnet add package Aspose.BarCode
```

Vervolgens breng je de benodigde namespaces in scope:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Pro tip:** Als je Visual Studio gebruikt, klik met de rechtermuisknop op het project → *Manage NuGet Packages* → zoek naar *Aspose.BarCode* en installeer de nieuwste stabiele versie.

---

## Stap 2 – Maak de barcode‑generator met je aangepaste tekst

De *primaire* taak is om **barcode met tekst te genereren** die speciale tekens bevat zoals “Å” en “©”. De constructor neemt het encode‑type en de ruwe data‑string:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Waarom dit belangrijk is: `EncodeTypes.MacroPdf417` vertelt Aspose dat we de macro‑versie willen, waardoor we een groot bericht over meerdere symbolen kunnen verdelen. De tekststring kan elke UTF‑8‑reeks zijn; Aspose verwerkt de conversie intern.

---

## Stap 3 – Pas de basisuiterlijk aan (module‑grootte)

De “module” van een barcode is het kleinste zwart‑of‑wit vierkant. Het instellen van de pixelgrootte bepaalt de totale afmetingen van de afbeelding zonder de datadichtheid te wijzigen:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Als je een grotere afbeelding nodig hebt voor afdrukken, verhoog deze waarde naar 4 of 6. Houd er rekening mee dat grotere modules de uiteindelijke PNG‑grootte vergroten.

---

## Stap 4 – Configureer Macro PDF417‑specifieke opties

Macro PDF417 voegt twee identifiers toe die een scanner in staat stellen meerdere symbolen aan elkaar te plakken. Je stelt meestal het volgende in:

| Eigenschap | Wat het doet |
|------------|--------------|
| `Columns` | Aantal datakolommen per symbool (beïnvloedt de breedte). |
| `MacroPdf417FileID` | Unieke ID voor het volledige macro‑bestand (moet ≤ 2³¹‑1 zijn). |
| `MacroPdf417SegmentID` | Index van het huidige segment (0‑254). |

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Opmerking voor randgevallen:** `MacroPdf417FileID` moet voor elk segment in hetzelfde logische bestand gelijk zijn. Als je meerdere segmenten genereert, gebruik dan dezelfde ID, anders krijg je niet‑gerelateerde symbolen die niet gecombineerd kunnen worden.

---

## Stap 5 – Sla de barcode op als PNG‑afbeelding

Nu alles geconfigureerd is, schrijf je de afbeelding naar schijf:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

De `Save`‑methode maakt automatisch de PNG, waarbij DPI en kleurdiepte voor je worden afgehandeld. Na uitvoering, open het bestand om iets als dit te zien:

![Voorbeeld van barcode met tekst genereren](/images/barcode-example.png){.center alt="Voorbeeld van barcode met tekst genereren"}

Als je geen barcode ziet, controleer dan dubbel of de map bestaat en of je applicatie schrijfrechten heeft.

---

## Volledig, kant‑klaar voorbeeld

Kopieer de volledige code‑fragment hieronder naar een nieuwe console‑app (`dotnet new console`) en voer deze uit. Het zal de PNG genereren in de map `C:\Barcodes` (maak de map eerst aan).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Verwachte output** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

En de PNG zal een compact Macro PDF417 symbool weergeven dat de tekst “Åspóse.Barcóde©” bevat.

---

## Veelgestelde vragen & valkuilen

| Vraag | Antwoord |
|-------|----------|
| *Kan ik een ander afbeeldingformaat gebruiken?* | Zeker—vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif`. PNG is verliesloos, daarom gebruiken we het standaard. |
| *Wat als ik meer dan één segment nodig heb?* | Maak een nieuwe `BarcodeGenerator` voor elk segment, houd `MacroPdf417FileID` identiek en verhoog `MacroPdf417SegmentID` (0‑254). |
| *Mijn tekst bevat emoji’s—werken die?* | Aspose.BarCode ondersteunt UTF‑8, dus de meeste emoji’s werken. Zorg er wel voor dat de doel‑scanner ze kan decoderen; veel industriële scanners verwerken alleen alfanumerieke data. |
| *De barcode is te breed voor mijn label.* | Verminder `Columns` of vergroot de module‑grootte. Minder kolommen geven een smallere symbool, maar kunnen een printer met hogere DPI vereisen. |
| *Heb ik een licentie nodig?* | Een gratis evaluatielicentie werkt voor testen, maar voegt een klein watermerk toe. Voor productie koop je een licentie om het watermerk te verwijderen en alle functies te ontgrendelen. |

---

## Volgende stappen

Nu je weet **hoe je PDF417** barcodes met aangepaste tekst kunt genereren, wil je misschien:

* **Decoderen** van de barcode in een mobiele app met Aspose.BarCode’s `BarCodeReader`.  
* **Combineren** van meerdere macro‑segmenten tot één PDF‑document voor batch‑afdrukken.  
* **Andere symbologieën verkennen** (QR, DataMatrix) met vergelijkbare parameterpatronen.  
* **Foutcorrectieniveau aanpassen** via `Pdf417.ErrorCorrectionLevel` voor ruigere omgevingen.  

Elk van deze onderwerpen bouwt voort op dezelfde kernconcepten die je net geleerd hebt, dus de overgang zal soepel verlopen.

---

## Conclusie

We hebben een volledige end‑to‑end‑oplossing doorlopen die je in staat stelt **barcode met tekst te genereren** en, specifiek, **hoe je PDF417** macro‑symbolen maakt met Aspose.BarCode for .NET. Door de X‑dimensie, kolomaantal en macro‑ID’s in te stellen, krijg je volledige controle over grootte, lay‑out en multi‑segment handling. De resulterende PNG kan worden afgedrukt, ingebed in PDF’s, of naar een scanner gestuurd zonder verdere conversie.

Probeer het, pas de parameters aan, en laat de barcode werken voor jouw bedrijfs­case. Als je tegen een probleem aanloopt, zijn de Aspose‑documentatie en community‑forums uitstekende vervolg‑bronnen. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 barcodes te genereren – Compacte PDF417 codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe DataMatrix barcode te genereren met Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Hoe barcode te genereren – Eén-dimensionale barcode types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}