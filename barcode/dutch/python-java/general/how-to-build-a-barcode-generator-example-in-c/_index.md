---
category: general
date: 2026-09-19
description: barcodegenerator‑voorbeeld dat laat zien hoe de hoogte aan te passen,
  DataBar Omni‑Directional te maken en de afmetingen van de barcode te wijzigen voor
  C#‑afbeeldingsoutput
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: nl
lastmod: 2026-09-19
og_description: barcodegenerator‑voorbeeld dat uitlegt hoe je de hoogte wijzigt, DataBar
  Omni‑Directional maakt en de barcode‑afmetingen aanpast voor een C# PNG‑afbeelding
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Barcodegenerator‑voorbeeld in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcodegenerator-voorbeeld in C# te bouwen
url: /nl/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator voorbeeld in C# – volledige programmeergids

Als je een **barcode generator voorbeeld** nodig hebt voor een .NET‑project, laat deze gids je precies zien hoe je een DataBar Omni‑Directional barcode maakt, configureert en opslaat met C#. Je leert hoe je de hoogte wijzigt, de afmetingen van de barcode aanpast en een PNG‑afbeelding van hoge kwaliteit genereert – alles in één uitvoerbare console‑applicatie.

De onderstaande stappen behandelen alles, van het installeren van de benodigde SDK tot het afstellen van de X‑dimensie en de balkhoogte. Aan het einde van de tutorial heb je een kant‑klaar barcode‑generator die je kunt integreren in facturering, voorraadbeheer of elke scan‑workflow.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere IDE die .NET ondersteunt)  
* Een actieve licentie voor **Aspose.BarCode for .NET** (de gratis proefversie werkt voor testen)  

Als je een andere bibliotheek verkiest, blijven de concepten voor het aanpassen van afmetingen en het opslaan van de afbeelding hetzelfde; vervang gewoon de API‑aanroepen dienovereenkomstig.

## Stap 1: Het project opzetten en het Aspose.BarCode‑pakket toevoegen

Maak een nieuw console‑project aan en verwijs naar de barcode‑bibliotheek.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Met het commando `dotnet add package` haal je de nieuwste stabiele versie van Aspose.BarCode op, die volledige ondersteuning biedt voor DataBar Omni‑Directional‑symbolen.

## Stap 2: Het volledige barcode generator voorbeeld schrijven

Open **Program.cs** en vervang de inhoud door de volgende code. Dit blok bevat het volledige **barcode generator voorbeeld** – zonder ontbrekende onderdelen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is

* **Create a barcode generator** – De `BarcodeGenerator`‑constructor koppelt het coderings‑type (`EncodeTypes.DatabarOmniDirectional`) aan de gegevens die je wilt embedden. Dit is de kern van de **how to create databar** stap.  
* **Adjust barcode dimensions** – De eigenschap `XDimension.Pixels` bepaalt de breedte van de smalste balk. Het wijzigen van deze waarde beïnvloedt de totale grootte en de scan‑betrouwbaarheid.  
* **How to change height** – De eigenschap `BarHeight.Pixels` regelt de verticale grootte. Een hogere balk verbetert de leesbaarheid voor handscanners, terwijl een lagere balk ruimte bespaart op kleine etiketten.  
* **Optional tweaks** – Het instellen van voor‑/achtergrondkleuren of fout‑correctieniveaus is optioneel, maar laat zien hoe je het **adjust barcode dimensions**‑concept kunt uitbreiden.  
* **Create barcode image C#** – De `Save`‑methode schrijft de barcode naar schijf. Het gebruik van `BarCodeImageFormat.Png` zorgt voor verliesloze compressie, wat ideaal is voor de meeste toepassingen.

## Stap 3: Het voorbeeld bouwen en uitvoeren

Compileer en voer het programma uit:

```bash
dotnet run
```

Je zou de volgende console‑output moeten zien:

```
Barcode saved to DatabarOmniDirectional.png
```

Er verschijnt een bestand genaamd **DatabarOmniDirectional.png** in de projectmap. Het openen van de afbeelding toont een scherpe DataBar Omni‑Directional barcode die klaar is om te scannen.

## Hoe de hoogte later aanpassen

Als je barcodes met verschillende hoogtes moet genereren, plaats je de hoogte‑toewijzing in een methode:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Roep `SetBarHeight(generator, 45);` aan vóór `Save`. Deze aanpak stelt je in staat om **how to change height** dynamisch aan te passen op basis van gebruikersinvoer of configuratiebestanden.

## Hoe DataBar Omni‑Directional barcodes met verschillende gegevens maken

De DataBar Omni‑Directional‑symbologie ondersteunt GTIN‑14, GTIN‑13 en andere numerieke identifiers. Om een andere waarde te coderen, vervang je simpelweg de string in de constructor:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Zorg ervoor dat de gegevens numeriek en correct geformatteerd zijn; anders gooit de generator een `BarcodeException`.

## Barcode‑afmetingen aanpassen voor verschillende print‑scenario's

Verschillende printers en etiketgroottes vereisen verschillende X‑dimensies en hoogtes. Gebruik de volgende tabel als snelle referentie:

| Scenario                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| Klein etiket (25 mm × 15 mm)  | 1                    | 20                  |
| Middelgroot etiket (50 mm × 30 mm) | 2                    | 30                  |
| Groot etiket (100 mm × 50 mm) | 3                    | 45                  |

Pas deze waarden toe door `generator.Parameters.Barcode.XDimension.Pixels` en `BarHeight.Pixels` overeenkomstig in te stellen.

## Pro‑tip: de gegenereerde barcode valideren

Voordat je een etiket verzendt, kun je de leesbaarheid programmatisch verifiëren:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Dit fragment toont een snelle **adjust barcode dimensions** sanity‑check, zodat de barcode voldoet aan de scan‑vereisten.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Valkuil                              | Waarom het gebeurt                              | Oplossing                                                                 |
|--------------------------------------|-------------------------------------------------|--------------------------------------------------------------------------|
| Niet‑numerieke data voor DataBar     | DataBar verwacht numerieke GTIN‑formaten        | Zorg dat de string overeenkomt met het patroon `(01)XXXXXXXXXXXXX`.      |
| X‑dimension op 0 of negatief zetten  | Bibliotheek gooit `ArgumentOutOfRangeException`| Gebruik minimaal 1 pixel; test eerst op de doel‑printer.                |
| Opslaan in een alleen‑lezen map       | `UnauthorizedAccessException` bij `Save`       | Kies een schrijfbare directory of voer de app uit met juiste rechten. |
| Vergeten `BarCodeReader` te disposen | Geheugenlek in langdurige services              | Plaats de reader in een `using`‑block of roep handmatig `Dispose()` aan. |

Deze problemen vroegtijdig aanpakken bespaart debug‑tijd en verbetert de stabiliteit in productie.

## Volledige broncode‑overzicht

Hieronder vind je het complete, kant‑klaar programma dat het **barcode generator voorbeeld** van begin tot eind implementeert.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Het uitvoeren van dit programma produceert een PNG‑bestand dat er als volgt uitziet (illustratief):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Afbeeldings‑alt‑tekst*: **DataBar Omni‑Directional barcode gegenereerd in C#** (komt overeen met `og_image_alt`).

## Conclusie

Je beschikt nu over een **barcode generator voorbeeld** dat laat zien hoe je de hoogte wijzigt, DataBar Omni‑Directional‑symbolen maakt en **adjust barcode dimensions** optimaliseert voor betrouwbare scans. De volledige C#‑code slaat een PNG‑afbeelding op, valideert deze en kan worden uitgebreid voor bulk‑generatie of integratie in webservices.

Verken vervolgens gerelateerde onderwerpen zoals **QR‑codes maken met Aspose.BarCode**, **batch‑verwerking van meerdere barcode‑waarden**, of **barcodes in PDF‑documenten embedden**. Elk van deze bouwt voort op de dezelfde basisprincipes die in deze gids behandeld zijn.

Happy coding, en moge je barcodes altijd scanbaar blijven!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}