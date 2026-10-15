---
category: general
date: 2026-10-12
description: Leer hoe je een micro‑PDF417‑barcode maakt en de barcode converteert
  naar PNG met C#. Stapsgewijze gids met volledige code en tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: nl
lastmod: 2026-10-12
og_description: Maak een micro PDF417‑barcode en converteer de barcode naar PNG met
  C#. Volg deze volledige gids om zowel de standaard‑ als de GS1‑versies te genereren.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Maak een micro PDF417-barcode en converteer deze naar PNG – C#-tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hoe maak je een micro PDF417-barcode en converteer je deze naar PNG in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een micro PDF417 barcode te maken en deze te converteren naar PNG in C#

Als je een **micro PDF417 barcode** moet maken in een .NET‑applicatie, laat deze tutorial je precies zien hoe. Je ziet een volledig, uitvoerbaar voorbeeld dat zowel een standaard Micro PDF417 barcode als een GS1‑compatibele versie genereert, en vervolgens **barcode naar PNG converteert** voor downstream gebruik zoals afdrukken of weergave op het web.

Een barcode genereren is meer dan alleen een enkele methode aanroepen—het kiezen van de juiste modulegrootte, kolomaantal en coderingsformaat bepaalt de scanbetrouwbaarheid. Aan het einde van deze gids begrijp je waarom elke instelling belangrijk is en hoe je ze kunt aanpassen voor je eigen projecten.

## Vereisten

| Vereiste | Reden |
|----------|-------|
| .NET 6.0 SDK of later | Biedt de runtime voor de C# console‑applicatie |
| Visual Studio 2022 (of elke C# IDE) | Maakt bewerken en debuggen gemakkelijker |
| **Aspose.BarCode for .NET** NuGet‑pakket | Levert de klassen `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` |
| Schrijfrechten voor de doelmap | Vereist voor `Save`‑aanroepen die PNG‑bestanden maken |

Je kunt het Aspose.BarCode‑pakket toevoegen via de CLI:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Een minimaal console‑project opzetten

Maak een nieuw console‑project aan en verwijs naar de barcode‑bibliotheek. De volgende `Program.cs` bevat alle code die je nodig hebt; er zijn geen externe bestanden vereist.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Waarom elke regel belangrijk is

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – De eerste maakt een eenvoudige Micro PDF417 barcode, terwijl de tweede de GS1‑normen volgt en Application Identifiers (AIs) insluit. Kies op basis van of je downstream‑systeem GS1‑gegevens verwacht.
* **`XDimension.Pixels = 2`** – Regelt de modulebreedte. Kleinere waarden creëren een dichtere afbeelding, maar kunnen onleesbaar worden op scanners met lage resolutie. Twee pixels is een veilige standaard voor de meeste labelprinters.
* **`Pdf417.Columns = 4`** – Met Micro PDF417 kun je het aantal kolommen beperken, waardoor de totale breedte afneemt. Vier kolommen houden de barcode compact zonder de gegevenscapaciteit voor korte payloads te verminderen.
* **`BarCodeImageFormat.Png`** – PNG behoudt verliesvrije kwaliteit, essentieel voor de duidelijkheid van de barcode. Daarom **converteren we de barcode naar PNG** in plaats van JPEG.

## Stap 2: Het programma uitvoeren en de output verifiëren

1. Bouw het project: `dotnet build`.
2. Voer uit: `dotnet run`.

Je zou console‑berichten moeten zien die lijken op:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Open de gegenereerde PNG‑bestanden met een willekeurige afbeeldingsviewer. Beide afbeeldingen tonen een scherpe, hoog‑contrast barcode die klaar is om te scannen.

### Verwacht visueel resultaat

| Barcodetype | Uiterlijk |
|-------------|-----------|
| **Micro PDF417** | Klein rechthoekig patroon met 4 kolommen, leesbaar door de meeste 2‑D barcode‑scanners. |
| **GS1 Micro PDF417** | Zelfde grootte maar codeert GS1 AIs; een scanner die GS1 begrijpt zal de GTIN en serienummer teruggeven. |

Als een scanner de afbeelding niet kan lezen, probeer dan `XDimension.Pixels` te verhogen naar **3** of **4**, of verlaag het kolomaantal voor de standaard Micro PDF417.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Vage barcode na het afdrukken | Printerinstellingen met lage DPI | Exporteer PNG met 300 dpi of hoger, of laat de printerdriver de schaalverdeling afhandelen. |
| Scanner geeft “ongeldige data” terug | Ontbrekend of verkeerd geformatteerd GS1 AI‑formaat | Zorg ervoor dat elke AI tussen haakjes staat en voldoet aan de GS1‑specificatie (bijv. `(01)` voor GTIN‑14). |
| Afbeeldingsbestand niet aangemaakt | Doelmap heeft geen schrijfrechten | Voer het programma uit met verhoogde rechten of kies een map zoals `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode te groot voor label | Standaard kolomaantal te hoog | Verlaag `Pdf417.Columns` (bijv. naar **3**) of vergroot `XDimension` om de totale grootte te verkleinen. |

## Het voorbeeld uitbreiden

* **Verschillende afbeeldingsformaten** – Vervang `BarCodeImageFormat.Png` door `Jpeg` of `Bmp` als je workflow dat vereist. PNG blijft de beste keuze voor verliesvrije kwaliteit.
* **Dynamische gegevens** – Geef gebruikersinvoer of database‑waarden door aan de `BarcodeGenerator`‑constructor om barcodes on‑the‑fly te maken.
* **Batch‑generatie** – Plaats de creatielogica in een lus die rijen uit een CSV‑bestand leest en elke barcode opslaat met een unieke bestandsnaam.

## Conclusie

Je weet nu hoe je een **micro PDF417 barcode** in C# kunt **maken** en **barcode naar PNG kunt converteren** voor zowel standaard als GS1‑compatibele scenario's. De volledige, uitvoerbare code toont de essentiële instellingen—X‑dimensie, kolomaantal en coderings‑type—zodat je de oplossing kunt aanpassen aan elk .NET‑project dat compacte, hoogwaardige 2‑D barcodes nodig heeft.

*Volgende stappen*: verken andere symbologieën die door Aspose.BarCode worden ondersteund (bijv. QR, DataMatrix), experimenteer met verschillende `XDimension`‑waarden voor high‑resolution afdrukken, of integreer de gegenereerde PNG‑bestanden in een web‑API die barcodes on‑demand levert.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een micro pdf417 barcode te maken in C# en op te slaan als PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Barcode PNG maken in C# – volledige gids voor GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Micro PDF417 Barcode genereren in C# – Complete gids](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}