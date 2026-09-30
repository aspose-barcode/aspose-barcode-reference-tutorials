---
category: general
date: 2026-08-19
description: Genereer PDF417-barcode in C# snel. Leer hoe je een PDF417-barcode in
  C# kunt genereren met Aspose.BarCode in compacte modus en aangepaste instellingen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: nl
lastmod: 2026-08-19
og_description: Genereer PDF417‑barcode in C# met Aspose.BarCode. Deze tutorial laat
  zien hoe je een PDF417‑barcode in C# genereert in compacte modus, de X‑dimensie
  instelt en opslaat als PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: PDF417‑barcode genereren in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: PDF417-barcode genereren in C# – volledige gids met compacte indeling
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer PDF417 barcode in C# – volledige gids

Als je een **PDF417 barcode wilt genereren** in een .NET‑applicatie, laat deze tutorial je precies zien hoe je dat doet. Je ziet een beknopt, productie‑klaar voorbeeld dat een compacte PDF417 barcode maakt, de X‑dimensie aanpast en het resultaat opslaat als een PNG‑afbeelding.

Het genereren van een PDF417 barcode is gebruikelijk wanneer je grote hoeveelheden data moet coderen—zoals ticketinformatie, verzendmanifesten of identiteitsdocumenten—in een machine‑leesbaar formaat. Het gebruik van Aspose.BarCode maakt het proces eenvoudig, en de code werkt met .NET 6+ of .NET Framework 4.7.2 en later.

In deze gids zal je:

* Het Aspose.BarCode NuGet‑pakket installeren.
* Een zelfstandige C#‑programma schrijven dat **PDF417 barcode genereert** met een klein aantal kolommen en compacte (afgekorte) modus.
* De balkbreedte (X‑dimensie) aanpassen voor scherpere weergave.
* De barcode opslaan als een PNG‑bestand.
* Variaties, randgevallen en best‑practice‑tips verkennen.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* Visual Studio 2022 (of een andere C#‑IDE) met .NET 6 SDK geïnstalleerd.
* Internettoegang om het **Aspose.BarCode** NuGet‑pakket te downloaden.
* Schrijfrechten op een map waar het PNG‑bestand wordt opgeslagen.

Er zijn geen extra bibliotheken nodig; Aspose.BarCode verwerkt de afbeeldingcodering intern.

## Stap 1: Voeg het Aspose.BarCode‑pakket toe

Open je project in Visual Studio, klik met de rechtermuisknop op de solution en selecteer **Manage NuGet Packages**. Zoek naar `Aspose.BarCode` en installeer de nieuwste stabiele versie.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Houd het pakket up‑to‑date. Nieuwe releases bevatten vaak prestatieverbeteringen en ondersteuning voor de nieuwste .NET‑runtimes.

## Stap 2: Maak een minimale console‑applicatie

Maak een nieuw C# console‑project aan als je er nog geen hebt:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Vervang de inhoud van `Program.cs` door het volledige voorbeeld hieronder. Dit programma laat zien **hoe je PDF417 barcode in C# genereert** van begin tot eind.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is

* **`EncodeTypes.Pdf417`** – selecteert de PDF417‑symbool, die tot ongeveer 1,1 KB aan data ondersteunt.
* **`XDimension.Pixels = 2`** – stelt de basisbalkbreedte in. Kleinere waarden maken de barcode dunner; grotere waarden verbeteren de leesbaarheid op apparaten met lage resolutie.
* **`Pdf417.Columns = 3`** – beperkt het aantal kolommen, waardoor de generator meer rijen gebruikt, wat resulteert in een hogere maar smallere barcode.
* **`Pdf417.Truncate = true`** – activeert compacte modus, verwijdert het stop‑patroon en verkleint de afbeelding zonder verlies van gegevensintegriteit.
* **`Save(..., BarCodeImageFormat.Png)`** – schrijft een PNG‑bestand. Je kunt ook `Jpeg`, `Bmp` of `Svg` kiezen, afhankelijk van downstream‑behoeften.

Voer het programma uit:

```bash
dotnet run
```

Je zou de console‑output moeten zien die de bestandslocatie bevestigt, en de map zal `CompactPdf417.png` bevatten. Het openen van de PNG toont een duidelijke, compacte PDF417 barcode die de Unicode‑string codeert.

## Stap 3: Verifieer de barcode (optioneel maar aanbevolen)

Om te zorgen dat de barcode leesbaar is, kun je een standaard PDF417‑scanner‑app op een smartphone of een desktop‑decoder‑bibliotheek gebruiken. De gecodeerde tekst moet exact overeenkomen met de oorspronkelijke `data`‑string, inclusief de speciale tekens.

Als je decoderingproblemen tegenkomt:

* Verhoog de `XDimension` naar 3 of 4 pixels.
* Verminder het aantal kolommen (bijv. `Columns = 2`).
* Schakel `Truncate` uit (`Truncate = false`) om het stop‑patroon toe te voegen.

Deze aanpassingen ruilen grootte in voor leesbaarheid, wat nuttig is voor printers of scanners met lage resolutie.

## Stap 4: Verken veelvoorkomende variaties

### 4️⃣ Genereer een hoge‑dichtheid PDF417 voor afdrukken

Als je een barcode nodig hebt die op een klein label past, verhoog dan het aantal kolommen en verlaag de X‑dimensie:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Verander het uitvoerformaat naar SVG voor vector‑schaling

SVG‑output schaalt zonder kwaliteitsverlies, perfect voor responsieve webpagina's.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Encode binaire data (bijv. een byte‑array)

Als je binaire payloads moet insluiten, converteer ze dan eerst naar een Base64‑string:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

## Veelgestelde vragen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik PDF417 genereren zonder Aspose?** | Ja, andere bibliotheken zoals ZXing.Net of Dynamsoft bestaan, maar Aspose.BarCode biedt rijkere lay-outcontrole (kolommen, afkapping) en betere Unicode‑afhandeling. |
| **Wat is de maximale datalengte?** | PDF417 kan tot 1.108 bytes (≈ 1 KB) binaire data coderen. Als je dit overschrijdt, overweeg dan de data over meerdere barcodes te verdelen. |
| **Is compacte modus conform aan standaarden?** | Afgekorte PDF417 maakt deel uit van de ISO/IEC 15438‑specificatie en wordt breed ondersteund, maar controleer of je doelscanner het expliciet ondersteunt. |
| **Hoe wijzig ik de achtergrondkleur?** | Stel `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` en `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` in vóór het opslaan. |

## Conclusie

Je weet nu **hoe je PDF417 barcode in C# genereert** met Aspose.BarCode, hoe je de X‑dimensie fijnstelt, compacte modus inschakelt en het resultaat exporteert als een PNG‑afbeelding. Het volledige, uitvoerbare voorbeeld kan in elk .NET‑project worden gekopieerd, en de getoonde variaties laten je de barcode aanpassen voor afdrukken, web of binaire payload‑scenario's.

Volgende stappen die je kunt verkennen:

* Integreer de barcode‑generatie in een ASP.NET Core API die de afbeelding op aanvraag retourneert.
* Combineer PDF417 met QR‑codes op hetzelfde label voor dual‑format scanning.
* Gebruik de Aspose.BarCode `Reader`‑klasse om de gegenereerde afbeelding te decoderen en de data programmatisch te verifiëren.

Veel plezier met coderen, en geniet van de flexibiliteit die **PDF417 barcode‑generatie** oplossingen aan je applicaties bieden!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compacte PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een barcode‑afbeelding te genereren met aanvullende ruimte‑aanpassing met Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}