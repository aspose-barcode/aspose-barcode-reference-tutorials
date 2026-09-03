---
category: general
date: 2026-07-18
description: Maak een PDF417‑barcode in C# met de C# PDF417 barcodegenerator. Volg
  een stapsgewijze tutorial om uitgebreide codetekst te bouwen, het uiterlijk in te
  stellen en de afbeelding op te slaan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: nl
lastmod: 2026-07-18
og_description: Maak direct een PDF417‑barcode in C#. Deze gids laat zien hoe je de
  C# PDF417‑barcodegenerator gebruikt, de uitgebreide modus configureert en een PNG
  exporteert.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: PDF417-barcode maken in C# – Volledige handleiding voor de generator
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: PDF417-barcode maken in C# – Gids voor barcodegenerator
url: /nl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-barcode maken in C# – Barcode Generator‑gids

Heb je ooit een **PDF417‑barcode** moeten **maken** in een C#‑applicatie, maar wist je niet waar je moest beginnen? Je bent niet de enige—veel ontwikkelaars lopen tegen dezelfde muur aan wanneer ze voor het eerst twee‑dimensionale barcodes aanpakken. Het goede nieuws? Met de ingebouwde **C# PDF417 barcode generator** kun je in slechts een handvol regels een volledig functionele barcode genereren.

In deze tutorial lopen we het volledige proces door: een uitgebreide codetext bouwen die verschillende tekensets combineert, de generator configureren voor de juiste visuele stijl, en uiteindelijk de barcode opslaan als een PNG‑bestand. Aan het einde heb je een kant‑klaar fragment dat je in elk .NET‑project kunt plaatsen, plus tips voor het omgaan met randgevallen zoals Unicode‑tekens of aangepaste module‑breedtes.

---

## Wat je nodig hebt

Voordat we beginnen, zorg dat je het volgende op je machine hebt staan:

- **.NET 6.0** of hoger (het voorbeeld werkt ook met .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (of een andere compatibele bibliotheek die `BarcodeGenerator`, `EncodeTypes.Pdf417`, enz. exposeert)
- Een code‑editor—Visual Studio, Rider, of zelfs VS Code volstaat
- Een map waarin je kunt schrijven, want de generator slaat de PNG daar op

Dat is alles—geen extra NuGet‑pakketten naast de barcode‑bibliotheek zelf.

---

## Stapsgewijze gids om **PDF417‑barcode te maken**

### 1. Installeer de barcode‑bibliotheek

Open je terminal in de projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode`‑namespace toe, waarin de `BarcodeGenerator`‑klasse zit die we gedurende de tutorial gebruiken.

### 2. Bouw de uitgebreide codetext

PDF417 ondersteunt **extended encoding**, waardoor je verschillende tekensets in één barcode kunt mixen. Hieronder maken we drie segmenten:

- Een Windows‑1251 (Cyrillisch) segment
- Een UTF‑8 segment met Unicode‑tekens (de Japanse kanji voor “dog” en “right”)
- Een gewone tekstsegment

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Waarom dit belangrijk is:**  
Als je alleen platte tekst gebruikt, ben je beperkt tot de standaard ASCII‑subset. Door expliciet ECI‑ (Extended Channel Interpretation) segmenten te declareren, zorg je ervoor dat scanners elk deel correct interpreteren, ongeacht de taal of symbolen.

### 3. Initialiseert de **C# PDF417 barcode generator**

Nu we een geldige codetext‑string hebben, geven we die aan de generator. De `using`‑statement zorgt ervoor dat de onderliggende resources automatisch worden vrijgegeven.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configureer uiterlijk en coderingsmodus

De standaardinstellingen geven je een kleine barcode die moeilijk leesbaar kan zijn. Laten we een paar parameters aanpassen:

- **X‑Dimension** – bepaalt de breedte van elk module (pixelgrootte)
- **EncodeMode** – vertelt de engine om de invoer als extended‑mode te behandelen
- **TwoDDisplayText** – optionele menselijk leesbare tekst onder de barcode

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Pro‑tip:** Als je de barcode op een labelprinter afdrukt, verhoog dan de `XDimension` tot 20 px of meer; de meeste scanners houden van een beetje extra ruimte.

### 5. Sla de barcode‑afbeelding op

Schrijf tenslotte de afbeelding naar schijf. De bibliotheek ondersteunt PNG, JPEG, BMP en diverse vectorformaten—PNG is een veilige standaard omdat het scherpe randen behoudt.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Zorg dat `YOUR_DIRECTORY` bestaat en beschrijfbaar is. Na het uitvoeren van het programma zie je een bestand dat lijkt op de screenshot hieronder.

![PDF417‑barcode gegenereerd met C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "PDF417‑barcode gegenereerd met C# PDF417 barcode generator")

---

## Werken met de **C# PDF417 barcode generator** – dieper ingaan

### Unicode‑ en speciale tekens verwerken

Wanneer je Unicode‑symbolen rechtstreeks in een platte‑tekst barcode stopt, kan de generator terugvallen op een fallback‑encoding, wat leidt tot onleesbare output. Door `AddECICodetext` te gebruiken, vertel je de encoder expliciet welke tekenset moet worden toegepast, waardoor giswerk wordt geëlimineerd. Als je ooit **Arabisch**, **Hebreeuws** of **emoji** moet ondersteunen, kies dan de juiste `ECIEncodings`‑waarde.

### Foutcorrectieniveau aanpassen

PDF417 biedt vier fout‑correctieniveaus (0‑8). Hogere niveaus verhogen de robuustheid maar maken de barcode ook groter. Pas het aan via:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Schalen voor afdruk versus scherm

Voor weergave op scherm kun je de standaard 96 dpi behouden. Voor hoge‑resolutie‑afdrukken (300 dpi of meer) stel je in:

```csharp
generator.Parameters.ImageResolution = 300;
```

Dat zorgt ervoor dat de opgeslagen PNG genoeg detail behoudt voor laserprinters.

### Veelvoorkomende valkuilen

- **Ontbrekende `using`‑directive** – Het vergeten van `using Aspose.BarCode.Encoding;` leidt tot een ongedefinieerde `ECIEncodings`.
- **Map niet gevonden** – De `Save`‑methode maakt geen tussenliggende mappen aan; maak ze vooraf aan of gebruik `Path.Combine` met `Environment.CurrentDirectory`.
- **Verkeerde coderingsmodus** – Als je `EncodeMode` op `Pdf417EncodeMode.Auto` laat staan, kan de bibliotheek je uitgebreide codetext behandelen als platte tekst en de ECI‑markers verwijderen.

---

## Volledig, kant‑klaar voorbeeld

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Wat kun je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe dotcode‑uitgebreide codetext te maken met Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Barcode‑afbeelding maken c# – Codablock F‑rijen & kolommen configureren](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}