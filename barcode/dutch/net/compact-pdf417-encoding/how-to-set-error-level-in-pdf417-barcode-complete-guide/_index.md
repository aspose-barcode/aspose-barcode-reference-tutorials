---
category: general
date: 2026-07-18
description: Hoe stel je het foutenniveau in bij een PDF417-barcode met Aspose.BarCode.
  Leer hoe je een PDF417-barcode genereert met aangepaste tekst en de foutcorrectie
  in enkele minuten aanpast.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: nl
lastmod: 2026-07-18
og_description: hoe je snel het foutenniveau in een PDF417-barcode instelt. Deze tutorial
  leidt je door het genereren van een PDF417-barcode met aangepaste tekst en verschillende
  foutcorrectieniveaus.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Hoe het foutniveau in PDF417‑barcode in te stellen – Stapsgewijze gids
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Hoe het foutcorrectieniveau in PDF417-barcode instellen – Complete gids
url: /nl/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de foutniveau in PDF417-barcode in te stellen – Complete gids

Heb je je ooit afgevraagd **hoe je fouten moet instellen** bij het genereren van een PDF417-barcode? Je bent niet de enige—de meeste ontwikkelaars lopen tegen dit probleem aan wanneer ze een robuustere barcode nodig hebben voor scannen in ruwe omgevingen. Het goede nieuws? Het aanpassen van het foutcorrectieniveau is een fluitje van een cent met Aspose.BarCode, en je leert ook **hoe je PDF417 kunt genereren** met je eigen aangepaste tekst terwijl je toch bezig bent.

In deze tutorial lopen we elke stap door, van het maken van een barcode‑generator met speciale tekens tot het opslaan van twee PNG‑bestanden die verschillende fout‑correctieniveaus laten zien. Aan het einde ben je vertrouwd met **het genereren van PDF417‑barcode**, het aanpassen van de X‑dimensie, het aantal kolommen en, vooral, **het instellen van fout**‑niveaus die bij jouw scenario passen.

## Vereisten

- .NET 6.0 of later (de code werkt ook met .NET Framework)
- Aspose.BarCode voor .NET geïnstalleerd (`Install-Package Aspose.BarCode` via NuGet)
- Een map op schijf waar de afbeeldingen kunnen worden weggeschreven (vervang `YOUR_DIRECTORY/` in het voorbeeld)
- Basiskennis van C# — als je eerder een `Console.WriteLine` hebt geschreven, ben je klaar om te beginnen

> **Pro tip:** Als je gericht bent op mobiel scannen, kies dan een hoger foutniveau (Level 5) om vuil, krassen of weinig licht te weerstaan.

## Stap 1: Maak een Barcode‑generator met aangepaste tekst

Het eerste wat je nodig hebt is een `BarcodeGenerator`‑instantie die weet dat hij een **PDF417‑barcode** moet produceren en die de exacte tekst bevat die je wilt coderen. Let op het gebruik van accenten en een copyright‑symbool — dit bewijst dat de generator Unicode direct aankan.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Waarom dit belangrijk is:* De `EncodeTypes.Pdf417`‑vlag vertelt Aspose dat je met een 2‑D gestapelde barcode werkt, terwijl het string‑argument de gegevenspayload wordt. Als je deze stap overslaat, krijg je in plaats daarvan een standaard Code128‑barcode in plaats van de hoge‑capaciteit PDF417 die je nodig hebt.

## Stap 2: Fijn afstellen van visuele parameters

Een PDF417‑barcode is niet alleen data; het is ook een visueel patroon. Het aanpassen van de **X‑dimensie** (de breedte van de kleinste balk) en het aantal **kolommen** geeft je controle over de fysieke grootte en leesbaarheid van de barcode.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Waarom dit belangrijk is:* Een kleinere X‑dimensie levert een compacter beeld op, maar kan onleesbaar worden voor scanners met lage resolutie. Drie kolommen geven een evenwichtige beeldverhouding voor de meeste labelgroottes.

## Stap 3: Stel foutcorrectieniveau in op 2 en sla op

Foutcorrectie is de kern van **hoe je fouten moet instellen** voor PDF417. De `Pdf417ErrorLevel`‑enum loopt van `Level0` (geen extra data) tot `Level5` (maximale redundantie). Hier beginnen we met **Level 2**, wat een bescheiden hoeveelheid fout‑resistentie toevoegt zonder het beeld te veel op te blazen.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Na het uitvoeren van dit fragment vind je `Pdf417ErrorLevel2.png` in je map. Open het bestand; je zou een nette, drie‑koloms barcode moeten zien die nog steeds een behoorlijke hoeveelheid redundantie bevat.

## Stap 4: Verhoog foutcorrectie naar Level 5 en sla opnieuw op

Soms moet de barcode meer agressieve schade overleven — denk aan een magazijnvloer waar etiketten worden geschraapt. Overschakelen naar **Level 5** maximaliseert de foutcorrectie ten koste van een iets groter beeld.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Nu heb je twee PNG‑bestanden naast elkaar: één met gematigde foutcorrectie, een andere met de maximale. Vergelijk ze; de Level 5‑versie heeft meer donkere modules, precies wat het algoritme toevoegt om de data te beschermen.

![hoe de foutniveau in PDF417 barcode in te stellen voorbeeld](image.png)

*Afbeeldingsbeschrijving (alt‑tekst): hoe de foutniveau in PDF417 barcode in te stellen voorbeeld – toont twee PNG‑bestanden met verschillende fout‑correctieniveaus.*

## Verwachte output

| Bestandsnaam                     | Foutniveau | Ongeveer afmetingen (px) |
|----------------------------------|------------|--------------------------|
| `Pdf417ErrorLevel2.png`          | Level 2    | 150 × 80                 |
| `Pdf417ErrorLevel5.png`          | Level 5    | 180 × 95                 |

Beide afbeeldingen coderen de string **“Åspóse.Barcóde©”** en kunnen worden gescand met elke standaard PDF417‑lezer (bijv. ZXing, Scandit). De Level 5‑afbeelding verdraagt tot ~30 % schade, terwijl Level 2 rond ~15 % aankan.

## Veelgestelde vragen & randgevallen

### Wat als mijn tekst regeleinden bevat?
PDF417 codeert automatisch line‑feed (`\n`) tekens. Voeg ze gewoon toe aan de string:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Kan ik een ander afbeeldingsformaat gebruiken?
Zeker. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Svg` afhankelijk van je downstream‑workflow.

### Heeft het wijzigen van de X‑dimensie invloed op foutcorrectie?
Indirect wel. Een grotere X‑dimensie levert grotere modules op, wat de scanbetrouwbaarheid kan verbeteren, maar **verandert niet** het logische fout‑correctieniveau. Pas beide parameters onafhankelijk van elkaar aan voor de beste resultaten.

### Hoe PDF417‑barcode genereren in een web‑API?
Verpak dezelfde code in een ASP.NET Core‑controller en stream de PNG terug als een `FileResult`. De kernlogica blijft ongewijzigd, wat betekent dat **hoe je PDF417 kunt genereren** consistent blijft tussen desktop‑ en webomgevingen.

## Samenvatting

We hebben behandeld **hoe je fouten moet instellen** voor een PDF417‑barcode, laten zien **hoe je PDF417 kunt genereren** met aangepaste Unicode‑tekst, en demonstreren hoe je visuele instellingen zoals X‑dimensie en kolomaantal kunt aanpassen. Door `Pdf417ErrorLevel.Level2` te vervangen door `Level5` kun je de afweging tussen afbeeldingsgrootte en veerkracht regelen.

## Volgende stappen

- Experimenteer met **barcode met aangepaste tekst** die URL’s of product‑ID’s bevat.
- Probeer verschillende kolomaantallen (`generator.Parameters.Barcode.Pdf417.Columns = 5`) om te zien hoe de vorm verandert.
- Combineer PDF417 met andere barcode‑typen in hetzelfde document voor multimodale scanoplossingen.
- Duik in de [officiële documentatie van Aspose](https://docs.aspose.com/barcode/net/) voor geavanceerde functies zoals macro‑PDF417 of compacte modus.

Voel je vrij om een reactie achter te laten als je ergens vastloopt, of deel je eigen gescande resultaten. Veel plezier met het maken van barcodes!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compacte PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een Aztec‑barcode met foutcorrectie te maken in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Hoe DataMatrix‑barcodes (ECC 200) te genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}