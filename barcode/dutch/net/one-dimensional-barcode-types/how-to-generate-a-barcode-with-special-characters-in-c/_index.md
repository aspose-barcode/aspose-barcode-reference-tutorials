---
category: general
date: 2026-10-02
description: streepjescode met speciale tekens in C# – leer hoe je een streepjescode
  met speciale tekens genereert met Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: nl
lastmod: 2026-10-02
og_description: barcode met speciale tekens in C# – deze tutorial laat zien hoe je
  een barcode in C# genereert die geaccentueerde en handelsmerksymbolen bevat, compleet
  met code en uitleg.
og_image_alt: barcode with special characters example output
og_title: Genereer een barcode met speciale tekens in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe genereer je een barcode met speciale tekens in C#
url: /nl/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode met speciale tekens te genereren in C#

Als je een barcode met speciale tekens in C# moet genereren, laat deze gids je een complete, kant‑klaar oplossing zien. Of je nu accenten letters zoals **Å** of symbolen zoals **©** codeert, de onderstaande stappen laten je een MacroPdf417‑barcode maken die elk teken precies behoudt zoals je het hebt getypt.

Je leert hoe je barcode c# genereert met de Aspose.BarCode‑bibliotheek, MacroPdf417‑specifieke metadata configureert en het resultaat opslaat als een PNG‑afbeelding. Er zijn geen externe tools nodig—alleen een .NET‑ontwikkelomgeving en het Aspose.BarCode‑NuGet‑pakket.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een IDE die C# ondersteunt)  
* Aspose.BarCode voor .NET toegevoegd aan je project (`dotnet add package Aspose.BarCode`)  

Deze vereisten zorgen ervoor dat de code compileert zonder extra afhankelijkheden.

## Een barcode met speciale tekens genereren in C#

De kern van de oplossing is het maken van een `BarcodeGenerator`‑instantie die het `EncodeTypes.MacroPdf417`‑formaat gebruikt. De generator accepteert elke Unicode‑string, zodat je speciale tekens direct kunt insluiten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Waarom dit werkt

* **Unicode-ondersteuning** – `BarcodeGenerator` accepteert een `string` die elk Unicode‑glyph bevat, zodat tekens zoals **Å**, **ó**, en **©** worden gecodeerd zonder extra stappen.  
* **MacroPdf417** – Dit formaat maakt het mogelijk om metadata op bestandsniveau toe te voegen (file ID, segment ID, checksum, enz.) die veel enterprise‑scanners verwachten.  
* **Pixel‑niveau controle** – Het instellen van `XDimension.Pixels` bepaalt de modulebreedte, wat de leesbaarheid op printers met lage resolutie beïnvloedt.  

## Basisuiterlijk van de barcode instellen

Het aanpassen van `XDimension` en het aantal kolommen beïnvloedt zowel de visuele grootte als de hoeveelheid data die op één rij past. Een waarde van `2` pixels levert een compacte maar scanbare barcode op, terwijl `Columns = 5` het symbool smal genoeg houdt voor de meeste labels.

### Pro‑tip

Als je een high‑density labelprinter target, verhoog dan `XDimension.Pixels` naar `3` of `4` om pixel‑vervorming te voorkomen.

## MacroPdf417‑metadata configureren

MacroPdf417 breidt de standaard PDF417‑specificatie uit met velden die beschrijven hoe een multi‑segment bestand moet worden gereconstrueerd. De eigenschappen die je in het voorbeeld instelt, komen overeen met een typisch gebruiksscenario:

| Eigenschap | Doel |
|------------|------|
| `MacroPdf417FileID` | Unieke identifier voor het gehele bestand |
| `MacroPdf417SegmentID` | Index van het huidige segment (begint bij 1) |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten in het bestand |
| `MacroPdf417FileName` | Logische naam van het bestand (gebruikt door sommige scanners) |
| `MacroPdf417Checksum` | CCITT‑16 checksum voor gegevensintegriteit |
| `MacroPdf417FileSize` | Verwachte grootte in bytes – helpt scanners de volledigheid te valideren |
| `MacroPdf417TimeStamp` | Creatie‑tijdstempel voor audit‑trails |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Optionele routeringsinformatie |
| `MacroPdf417Terminator` | Geeft aan of dit het laatste segment is (`Set`) of een tussenliggend segment (`Unset`) |

### Afhandeling van randgevallen

* **Grote bestands‑ID's** – De `FileID`‑eigenschap accepteert een 32‑bit integer. Als je systeem GUID's gebruikt, hash dan de GUID naar een 32‑bit waarde vóór toewijzing.  
* **Tijdstempel‑precisie** – De eigenschap slaat een `DateTime` op. Als je sub‑seconde precisie nodig hebt, neem die dan op in de bestandsnaam, omdat de standaard geen milliseconden ondersteunt.  

## De barcode‑afbeelding opslaan

De `Save`‑methode schrijft de gerenderde barcode naar het bestandssysteem. Je kunt andere formaten kiezen (`Jpeg`, `Bmp`, `Svg`) door `BarCodeImageFormat.Png` te vervangen. PNG is verliesloos, waardoor het ideaal is voor verdere verwerking of inbedden in PDF's.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

Na het uitvoeren van het programma vind je `ExtPDF417Meta.png` in de output‑map. Het openen van de afbeelding toont een dichte, multi‑row barcode die de tekst **Åspóse.Barcóde©** bevat, samen met de macro‑metadata die je hebt geconfigureerd.

### Verwachte output

* Een PNG‑bestand van ongeveer 300 × 150 pixels (grootte varieert met het aantal kolommen).  
* Wanneer gescand met een PDF417‑compatibele lezer, toont de gedecodeerde tekst exact **Åspóse.Barcóde©** en kan de scanner het oorspronkelijke bestand reconstrueren met behulp van de macro‑velden.

## Hoe barcode c# te genereren – veelvoorkomende valkuilen

Hoewel de code eenvoudig is, komen ontwikkelaars vaak de volgende problemen tegen:

1. **Ontbrekend NuGet‑pakket** – Het vergeten te installeren van `Aspose.BarCode` leidt tot compile‑time fouten. Controleer de pakketreferentie in je `.csproj`.  
2. **Ongeldige tekens voor de gekozen symbologie** – Sommige barcode‑typen (bijv. Code 128) weigeren bepaalde Unicode‑bereiken. MacroPdf417 accepteert de volledige Unicode‑set, waardoor het de veiligste keuze is voor speciale tekens.  
3. **Onjuist bestandspad** – Het gebruiken van een relatief pad zonder de juiste permissies kan een runtime `UnauthorizedAccessException` veroorzaken. Geef een absoluut pad op of zorg ervoor dat de applicatie schrijfrechten heeft op de doelmap.  

Het aanpakken van deze punten zorgt ervoor dat hoe je barcode c# genereert een soepele ervaring blijft.

## Volledig werkend voorbeeld

Kopieer het volledige programma hieronder naar een nieuw console‑project en voer het uit. Er is geen extra configuratie nodig naast het NuGet‑pakket.



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode met speciale tekens – Complete gids voor het genereren van PDF417](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [Hoe een barcode‑afbeelding te genereren met Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [Hoe een PDF417‑barcode‑afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}