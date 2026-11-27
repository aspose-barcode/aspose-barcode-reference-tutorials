---
category: general
date: 2026-11-27
description: Barcodeafbeelding maken in C# en opslaan als PNG‑formaat met Aspose.BarCode
  – stapsgewijze handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: nl
lastmod: 2026-11-27
og_description: Maak een barcode‑afbeelding in C# en sla de afbeelding op in PNG‑formaat
  met Aspose.BarCode. Volg deze tutorial om stap voor stap een Macro PDF417‑barcode
  te genereren.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Barcode-afbeelding maken en opslaan in PNG-formaat in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Barcode-afbeelding maken en opslaan in PNG-formaat in C#
url: /nl/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑afbeelding maken en opslaan in PNG‑formaat in C#

Als je een **barcode‑afbeelding** moet maken in een .NET‑applicatie, laat deze gids zien hoe je een Macro PDF417‑barcode genereert en de **afbeelding opslaat in PNG‑formaat** met Aspose.BarCode. Je krijgt een volledig, uitvoerbaar voorbeeld en een uitleg van elke instelling zodat je de code kunt aanpassen aan je eigen eisen.

Een barcode genereren is meer dan één methode aanroepen; je moet de module‑grootte, macro‑parameters en het uitvoerformaat configureren. Aan het einde van deze tutorial begrijp je waarom elke eigenschap belangrijk is, hoe je veelvoorkomende randgevallen afhandelt, en hoe je kunt verifiëren dat het PNG‑bestand correct is geschreven.

## Wat je nodig hebt

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.6+)
- Aspose.BarCode for .NET (beschikbaar via NuGet: `Install-Package Aspose.BarCode`)
- Een IDE zoals Visual Studio 2022 of Visual Studio Code
- Schrijfrechten voor een map waar het PNG‑bestand wordt opgeslagen

## Stap 1: Initialiseer de barcode‑generator

De eerste stap is het maken van een `BarcodeGenerator`‑instance waarbij je de `EncodeTypes.MacroPdf417`‑symbologie en de tekst die je wilt coderen opgeeft.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Waarom dit belangrijk is:**  
`EncodeTypes.MacroPdf417` vertelt de bibliotheek om de PDF417‑macro‑variant te gebruiken, die bestandsegmentatie en extra metadata ondersteunt. De constructor ontvangt ook de mens‑leesbare tekst die in de barcode wordt gecodeerd.

## Stap 2: Definieer de module‑grootte (X‑dimensie)

De X‑dimensie bepaalt de breedte van één barcode‑module (het kleinste zwart/witte element). Een waarde van `2` pixels werkt goed voor PNG‑afbeeldingen op het scherm.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktische tip:**  
Als je van plan bent de barcode af te drukken, verhoog dan de pixelwaarde (bijv. `4` of `5`) om onscherpe uitvoer op printers met lage resolutie te voorkomen.

## Stap 3: Configureer PDF417‑macro‑parameters

Macro PDF417 voegt verschillende optionele velden toe die helpen bij het identificeren van het bronbestand, de segmentvolgorde en integriteitscontroles. Hieronder staat een volledige set van typische parameters; je kunt er elke weglaten die je niet nodig hebt.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Waarom deze velden nuttig zijn:**  

| Parameter | Doel |
|-----------|------|
| `Columns` | Bepaalt de breedte van de barcode; minder kolommen geven een hogere barcode. |
| `MacroPdf417FileID` | Unieke identifier die alle segmenten met elkaar verbindt. |
| `MacroPdf417SegmentID` | Positie van dit segment binnen het volledige bestand. |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten; vereist voor reconstructie. |
| `MacroPdf417FileName` | Mens‑leesbare naam die kan worden weergegeven door scan‑apps. |
| `MacroPdf417Checksum` | Helpt ontvangers de gegevensintegriteit te verifiëren (CCITT‑16). |
| `MacroPdf417FileSize` | Optionele grootte‑hint voor het originele bestand. |
| `MacroPdf417TimeStamp` | Tijdstempel van de creatie van het originele bestand. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadata voor routing of eigendom. |
| `MacroPdf417Terminator` | Geeft aan of dit het laatste segment is (`Set`) of een tussenliggend segment (`Unset`). |

**Randgeval:**  
Als je een barcode met één segment genereert, stel je `MacroPdf417SegmentsCount` in op `1` en `MacroPdf417Terminator` op `Unset`. De bibliotheek zal automatisch segment‑gerelateerde velden weglaten die niet van toepassing zijn.

## Stap 4: Sla de gegenereerde barcode op als PNG‑afbeelding

Roep tenslotte `Save` aan met een bestandspad en de enum‑waarde `BarCodeImageFormat.Png`. De methode schrijft de afbeelding naar schijf in verliesvrij PNG‑formaat.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Waarom PNG?**  
PNG behoudt exacte pixelwaarden, wat essentieel is voor barcodescanners die afhankelijk zijn van scherp contrast. JPEG‑compressie kan artefacten introduceren die het barcode‑patroon verstoren.

### Verifiëren van de output

Na het uitvoeren van het programma zou je een bestand met de naam `ExtPDF417Meta.png` in de uitvoermap moeten zien. Het openen met een willekeurige afbeeldingsviewer toont een dichte, rechthoekige barcode. Je kunt de juistheid verifiëren door de afbeelding te scannen met een mobiele barcodescanner die PDF417‑macro ondersteunt; de app toont doorgaans de ingebedde metadata (bestand‑ID, segment‑nummer, enz.).

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Barcode ziet er onscherp uit | X‑dimensie te laag voor de gekozen DPI | Verhoog `XDimension.Pixels` of render op een hogere DPI (`generator.Parameters.ImageResolution`). |
| Scanner meldt “checksum‑fout” | Onjuiste `MacroPdf417Checksum`‑waarde | Laat Aspose de checksum automatisch berekenen door de eigenschap weg te laten, of zorg dat de waarde overeenkomt met het CCITT‑16‑algoritme. |
| PNG‑bestand is leeg of niet aangemaakt | Ongeldig uitvoerpad of ontbrekende schrijfrechten | Gebruik `Path.Combine` met een bekende schrijfbare map (bijv. `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Macro‑velden worden genegeerd | `EncodeTypes` ingesteld op reguliere `Pdf417` in plaats van `MacroPdf417` | Controleer of `EncodeTypes.MacroPdf417` wordt gebruikt in de constructor. |

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren naar een console‑applicatie. Het compileert met .NET 6.0 en produceert het hierboven beschreven PNG‑bestand.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Verwachte uitvoer (console):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Het openen van `ExtPDF417Meta.png` toont een duidelijke Macro PDF417‑barcode die klaar is om te scannen.

## Volgende stappen

- **Verander het afbeeldingsformaat** – vervang `BarCodeImageFormat.Png` door `Jpeg` of `Bmp` als je een ander bestandstype nodig hebt. Houd er rekening mee dat JPEG compressie‑artefacten introduceert, wat de scan‑betrouwbaarheid kan beïnvloeden.
- **Pas de resolutie aan** – gebruik

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een barcode‑afbeelding met Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Hoe maak je een PDF417‑barcode‑afbeelding in C# met Macro PDF417‑opties](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Hoe lees je barcodes van een afbeelding met C# en Aspose.BarCode – stap‑voor‑stap‑gids](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}