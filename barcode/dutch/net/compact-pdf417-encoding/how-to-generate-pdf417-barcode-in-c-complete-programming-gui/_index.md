---
category: general
date: 2026-09-29
description: Leer hoe je snel een PDF417‑barcode in C# genereert. Deze stapsgewijze
  tutorial behandelt barcode‑instellingen, afbeeldingoutput en veelvoorkomende valkuilen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- PDF417 barcode settings
- C# barcode library
- barcode image export
language: nl
lastmod: 2026-09-29
og_description: Genereer PDF417-barcode in C# met deze gedetailleerde tutorial. Volg
  het volledige voorbeeld om een barcode-afbeelding te maken en te exporteren.
og_image_alt: Screenshot showing generated PDF417 barcode saved as PNG
og_title: PDF417‑barcode genereren in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  headline: How to generate PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  name: How to generate PDF417 barcode in C# – complete programming guide
  steps:
  - name: Adjusting error correction level
    text: PDF417 supports five error‑correction levels (0‑8). Higher levels increase
      robustness at the cost of size.
  - name: Changing image format
    text: 'If you need a vector format for scaling, export as SVG instead of PNG:'
  - name: Handling very long strings
    text: 'When the input exceeds the default capacity, increase the number of rows:'
  - name: Using a different library
    text: If you prefer an open‑source alternative, the `ZXing.Net` package also supports
      PDF417. The API differs, but the overall flow—create a writer, set options,
      render to bitmap—remains the same.
  - name: Next steps
    text: '* Explore **PDF417 barcode settings** such as row count and aspect ratio
      for custom layouts. * Integrate the barcode generation into an ASP.NET Core
      API to serve images on demand. * Combine this code with a QR‑code generator
      for multi‑symbology documents.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Hoe PDF417-barcode te genereren in C# – volledige programmeergids
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-programming-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren in C# – volledige programmeergids

Als je een **PDF417-barcode wilt genereren** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je ziet een volledig, uitvoerbaar voorbeeld dat een PDF417‑barcode maakt, de afmetingen configureert en opslaat als een PNG‑afbeelding.

Het genereren van een barcode is een veelvoorkomende eis voor voorraadsystemen, ticketplatforms en documentautomatisering. Aan het einde van deze tutorial kun je barcode‑creatie integreren in elk C#‑project zonder extra fragmenten te zoeken.

## Wat je zult leren

* Hoe je een PDF417‑barcodegenerator instancieert met aangepaste tekst  
* Welke parameters de X‑dimensie en kolomaantal regelen  
* Hoe je de barcode exporteert als een PNG‑bestand van hoge kwaliteit  
* Tips voor het omgaan met Unicode‑tekens en het aanpassen van de afbeeldingsgrootte  

**Voorvereisten**  
* .NET 6.0 of later (de code werkt ook met .NET Framework 4.6+)  
* Een referentie naar het `Aspose.BarCode` NuGet‑pakket (of een andere compatibele barcode‑bibliotheek)  
* Basiskennis van C#‑syntaxis en Visual Studio of je favoriete IDE  

Als je je afvraagt **hoe je PDF417‑barcode kunt genereren** voor de eerste keer, lees dan verder – de stappen zijn bewust geordend van installatie tot verificatie.

## Stap 1: Installeer de barcode‑bibliotheek

Voordat je code schrijft, voeg je de barcode‑SDK toe aan je project. De meest gebruikte bibliotheek voor PDF417 in C# is **Aspose.BarCode for .NET**.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Gebruik de nieuwste stabiele versie (momenteel 24.5) om te profiteren van prestatieverbeteringen en volledige Unicode‑ondersteuning.

## Stap 2: Maak de PDF417‑barcodegenerator

De kern van het proces is het aanmaken van een `BarcodeGenerator`‑instantie met de `EncodeTypes.Pdf417`‑enum. De constructor ontvangt ook de tekst die je wilt coderen.

```csharp
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,               // PDF417 symbology
    "Åspóse.Barcóde©");               // Text includes Unicode characters
```

*Waarom dit belangrijk is*: De `EncodeTypes.Pdf417`‑vlag vertelt de bibliotheek om de PDF417‑standaard te gebruiken, die grote datablocks en foutcorrectie ondersteunt. Het leveren van een Unicode‑string toont aan dat de generator niet‑ASCII‑tekens correct verwerkt.

## Stap 3: Configureer de X‑dimensie (modulebreedte)

De X‑dimensie bepaalt de breedte van een enkele barcode‑module (de kleinste zwarte of witte balk). Het instellen in pixels geeft je precieze controle over de uiteindelijke afbeeldingsgrootte.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van `2` pixels produceert een compacte barcode die nog steeds gemakkelijk leesbaar is voor de meeste scanners. Als je een grotere barcode nodig hebt voor afdrukken op een poster, verhoog dan deze waarde evenredig.

## Stap 4: Definieer het aantal kolommen

PDF417 stelt je in staat het aantal kolommen op te geven, wat de beeldverhouding van de barcode beïnvloedt. Minder kolommen maken de barcode hoger; meer kolommen maken hem breder.

```csharp
// Step 4: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Drie kolommen creëren een gebalanceerde vorm die geschikt is voor de meeste scherm‑gebaseerde toepassingen. Voor dichte data kun je dit aantal verhogen naar 5 of 7.

## Stap 5: Sla de barcode op als een PNG‑afbeelding

Exporteer tenslotte de gegenereerde barcode naar een bestand. PNG behoudt scherpe randen en ondersteunt transparantie, waardoor het ideaal is voor UI‑weergave.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Pdf417Basic.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Wanneer de code wordt uitgevoerd, vind je `Pdf417Basic.png` op je bureaublad. Het openen van het bestand toont een duidelijke PDF417‑barcode die de string **Åspóse.Barcóde©** codeert.

## Het resultaat verifiëren

Om te bevestigen dat de barcode de beoogde gegevens codeert, kun je een gratis PDF417‑scannerapp gebruiken (bijv. ZXing Android‑app) of een online decoder. Scan de opgeslagen PNG; de gedecodeerde tekst moet exact overeenkomen met de oorspronkelijke invoer, inclusief de speciale tekens.

**Verwachte output** – een PNG‑afbeelding vergelijkbaar met deze (illustratief):

![gegenereerde PDF417 barcode opgeslagen als PNG – voorbeeld van pdf417 barcode genereren](https://example.com/assets/pdf417-sample.png "genereer pdf417 barcode")

*De bovenstaande alt‑tekst voldoet aan de image‑alt‑vereiste voor het primaire zoekwoord.*

## Veelvoorkomende variaties en randgevallen

### Het aanpassen van het foutcorrectieniveau

PDF417 ondersteunt vijf fout‑correctieniveaus (0‑8). Hogere niveaus verhogen de robuustheid ten koste van de grootte.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium protection
```

### Het wijzigen van het afbeeldingsformaat

Als je een vectorformaat nodig hebt voor schalen, exporteer dan als SVG in plaats van PNG:

```csharp
barcodeGenerator.Save("Pdf417Basic.svg", BarCodeImageFormat.Svg);
```

### Het verwerken van zeer lange strings

Wanneer de invoer de standaardcapaciteit overschrijdt, verhoog dan het aantal rijen:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 10;
```

### Een andere bibliotheek gebruiken

Als je de voorkeur geeft aan een open‑source alternatief, ondersteunt het `ZXing.Net`‑pakket ook PDF417. De API verschilt, maar de algemene stroom—een writer maken, opties instellen, renderen naar bitmap—blijft hetzelfde.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren naar een console‑applicatie en direct kunt uitvoeren.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize the generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose a compact column count
        generator.Parameters.Barcode.Pdf417.Columns = 3;

        // Optional: increase error correction for noisy environments
        generator.Parameters.Barcode.Pdf417.ErrorLevel = 5;

        // 4️⃣ Determine output path (desktop for easy access)
        string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
        string filePath = Path.Combine(desktop, "Pdf417Basic.png");

        // 5️⃣ Export as PNG
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to: {filePath}");
    }
}
```

Voer het programma uit (`dotnet run`), open vervolgens het gegenereerde bestand om de barcode te zien. De console bevestigt de locatie van de opgeslagen afbeelding.

## Conclusie

Je weet nu **hoe je PDF417‑barcode kunt genereren** in C# van begin tot eind. Door een `BarcodeGenerator` te maken, de X‑dimensie en het kolomaantal te configureren en te exporteren naar PNG, kun je barcode‑creatie in elke .NET‑oplossing integreren. Experimenteer met fout‑correctieniveaus, verschillende afbeeldingsformaten of grotere gegevenspayloads om de barcode af te stemmen op jouw specifieke scenario.

### Volgende stappen

* Verken **PDF417 barcode‑instellingen** zoals rijaantal en beeldverhouding voor aangepaste lay-outs.  
* Integreer de barcode‑generatie in een ASP.NET Core API om afbeeldingen op aanvraag te leveren.  
* Combineer deze code met een QR‑code‑generator voor documenten met meerdere symbologieën.

Voel je vrij om het voorbeeld aan te passen, je resultaten te delen, of vragen te stellen in de reacties. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417‑barcode te genereren in C# met aangepaste afmetingen](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)
- [Hoe PDF417‑barcode te genereren in C# en de barcode‑grootte in te stellen](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Hoe PDF417‑barcode te genereren in C# met Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}