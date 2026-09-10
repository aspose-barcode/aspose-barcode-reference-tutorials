---
category: general
date: 2026-09-10
description: Leer hoe je een barcode uit een afbeelding decodeert met een beknopt
  C#‑barcodelezer‑voorbeeld dat Macro PDF417‑codes leest in slechts een paar regels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: nl
lastmod: 2026-09-10
og_description: Decodeer een barcode uit een afbeelding met een kort C# barcode‑lezer‑voorbeeld.
  Volg de stap‑voor‑stap‑gids om Macro PDF417‑gegevens direct te lezen.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Barcode decoderen van afbeelding met een C# barcodelezer‑voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Decodeer een barcode uit een afbeelding met een C# barcodelezer‑voorbeeld
url: /nl/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode decoderen van afbeelding met een C# barcodelezer‑voorbeeld

Als je een **barcode van afbeelding wilt decoderen**, laat deze gids je precies zien hoe je dat in C# doet. Met een compact **C# barcode lezer voorbeeld** lees je Macro PDF417‑gegevens met slechts een paar regels code.

Je ziet een compleet, uitvoerbaar programma, begrijpt waarom elk onderdeel belangrijk is, en leert tips die veelvoorkomende valkuilen voorkomen. Er is geen externe documentatie nodig—alles wat je nodig hebt staat hier.

## Wat je zult leren

- Installeer het benodigde NuGet‑pakket voor barcode‑decodering.  
- Schrijf een **C# barcode lezer voorbeeld** dat een afbeeldingsbestand opent en elke barcode extraheert.  
- Toegang tot uitgebreide Macro PDF417‑velden zoals de bestand‑ID.  
- Controleer de output en pas de code aan voor andere barcode‑typen.

### Vereisten

- .NET 6.0 SDK of later (de code werkt ook met .NET Core 3.1 en .NET Framework 4.7+).  
- Basiskennis van C# console‑applicaties.  
- Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (bijv. `MacroPdf417.png`).  

## Stap 1: Installeer de barcode‑bibliotheek

Het voorbeeld maakt gebruik van **Aspose.BarCode for .NET**, een veelgebruikte bibliotheek die Macro PDF417‑decodering ondersteunt.

```bash
dotnet add package Aspose.BarCode
```

> **Waarom deze bibliotheek?**  
> Het biedt een enkele `BarCodeReader`‑klasse die veel formaten verwerkt, hoge nauwkeurigheid levert en uitgebreide informatie retourneert voor Macro PDF417‑codes—alles zonder extra configuratie.

## Stap 2: Maak een C# barcode lezer voorbeeld

Maak een nieuw console‑project en vervang de gegenereerde `Program.cs` door de onderstaande code. Het voorbeeld volgt drie duidelijke acties:

1. **Initialiseer** een `BarCodeReader` voor de doelafbeelding.  
2. **Itereer** over elke gedetecteerde barcode.  
3. **Print** de standaard- en uitgebreide Macro PDF417‑gegevens.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Uitleg van elk gedeelte

- **`BarCodeReader` constructor** – Het eerste argument is het pad naar de afbeelding; het tweede vertelt de bibliotheek specifiek naar Macro PDF417‑codes te zoeken. Deze gerichte decodering verbetert de prestaties vergeleken met het scannen van elk mogelijk formaat.  
- **`ReadBarCodes()`** – Retourneert een enumerable van alle barcodes die in de afbeelding zijn gedetecteerd, waardoor je meerdere codes in één bestand kunt verwerken.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 slaat extra metadata op (bestand‑ID, segment‑aantal, enz.). Het voorbeeld controleert op null om een `NullReferenceException` te voorkomen wanneer de afbeelding geen Macro‑barcode bevat.

## Stap 3: Voer het programma uit en controleer de output

Compileer en voer de console‑applicatie uit:

```bash
dotnet run
```

Je zou een output moeten zien die lijkt op:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Als de afbeelding geen Macro PDF417‑barcode bevat, zal het programma nog steeds andere gedetecteerde formaten weergeven, maar het uitgebreide veld wordt weggelaten.

## Pro‑tip: Decodeer andere barcode‑typen zonder veel code te wijzigen

Om een **barcode van afbeelding te decoderen** voor een ander formaat, wijzig je de `DecodeType`‑enumwaarde:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Je kunt ook `DecodeType.AllSupportedTypes` doorgeven zodat de bibliotheek elke barcode detecteert die hij kent.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Symptoom | Oorzaak | Oplossing |
|----------|---------|-----------|
| Geen output whatsoever | Verkeerd afbeeldingspad of niet‑ondersteund bestandsformaat | Controleer het pad, zorg dat het bestand een ondersteunde afbeelding is (PNG, JPEG, BMP) |
| `result.Extended` is null voor Macro PDF417 | De barcode is geen Macro PDF417‑variant | Bevestig dat de bronafbeelding daadwerkelijk een Macro PDF417‑code bevat |
| Exception `System.IO.FileNotFoundException` | Ontbrekend NuGet‑pakket tijdens runtime | Voer `dotnet restore` uit en zorg dat `Aspose.BarCode.dll` naar de output‑map wordt gekopieerd |

## Volledige broncode voor snelle copy‑paste

Hieronder staat het volledige programma, klaar om te kopiëren naar `Program.cs`. Er zijn geen extra bestanden nodig.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Volgende stappen

- **Verken andere uitgebreide velden** zoals `MacroPdf417SegmentID` of `MacroPdf417FileSize` om volledige document‑reconstructieworkflows te bouwen.  
- **Integreer de lezer in een web‑API** zodat clients afbeeldingen kunnen uploaden en direct gedecodeerde data ontvangen.  
- **Benchmark de prestaties** door grote batches afbeeldingen te decoderen; de `BarCodeReader` ondersteunt asynchrone verwerking in nieuwere Aspose‑versies.

---

Door dit **C# barcode lezer voorbeeld** te volgen, heb je nu een betrouwbare manier om **barcode van afbeelding te decoderen** en rijke Macro PDF417‑informatie te extraheren. Experimenteer met verschillende `DecodeType`‑waarden, combineer deze logica met bestands‑watchers, of embed het in mobiele back‑ends—je barcode‑verwerkingsmogelijkheden zijn klaar om te schalen.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 te lezen in C# – Volledig barcode lezer voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Barcode genereren met tekst – Volledige PDF417 Macro gids](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Hoe PDF417 barcode te maken met Aspose – Volledige stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}