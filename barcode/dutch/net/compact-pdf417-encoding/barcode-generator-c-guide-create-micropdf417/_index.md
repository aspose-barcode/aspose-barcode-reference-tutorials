---
category: general
date: 2026-09-29
description: Barcode‑generator C#‑handleiding laat zien hoe je een MicroPdf417‑barcode
  genereert, de afmetingen wijzigt, kolommen instelt en de barcodegrootte aanpast
  in slechts een paar regels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: nl
lastmod: 2026-09-29
og_description: Barcodegenerator C#-handleiding laat zien hoe je een MicroPdf417‑barcode
  genereert, afmetingen wijzigt, kolommen instelt en de barcodegrootte aanpast in
  slechts een paar regels.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Barcodegenerator C#‑gids – maak en pas MicroPdf417 aan
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Barcodegenerator C#‑handleiding: maak MicroPdf417'
url: /nl/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# gids: maak MicroPdf417

Als je een **barcode generator C#** nodig hebt voor je .NET‑project, leidt deze tutorial je stap voor stap door het maken van een MicroPdf417‑barcode vanaf nul. Je leert **hoe je een barcode genereert**, afmetingen aan te passen, kolommen in te stellen en **de barcode‑grootte** moeiteloos te **customizen**.

MicroPdf417 is een compacte 2‑D‑symbologie die goed werkt voor het labelen van kleine onderdelen, tickets of voorraadlabels. Aan het einde van deze gids heb je een volledige, uitvoerbare console‑applicatie die een PNG‑afbeelding van de barcode genereert, en begrijp je hoe elke parameter de uiteindelijke grootte beïnvloedt.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+)
* Een C#‑compatibele IDE (Visual Studio, VS Code, Rider, etc.)
* Het **GroupDocs.Barcode** NuGet‑pakket – installeer het met  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Er zijn geen extra externe tools nodig; de bibliotheek verzorgt codering, rendering en het opslaan van bestanden.

## Barcode generator C#: initialiseren van de generator

De eerste stap is het maken van een instantie van `BarcodeGenerator` en het opgeven van de symbologie (`EncodeTypes.MicroPdf417`) samen met de data die je wilt coderen.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Waarom dit belangrijk is:**  
`BarcodeGenerator` is het toegangspunt voor alle barcode‑bewerkingen. De constructor bindt de gekozen **EncodeTypes** (MicroPdf417) aan de ruwe data‑string. De bibliotheek handelt Unicode‑tekens zoals “Å” en “©” automatisch af, zodat je geen extra codering hoeft toe te passen.

## Hoe de afmetingen van de barcode te wijzigen

De leesbaarheid van een barcode hangt sterk af van de module‑breedte (de X‑dimensie). Een hogere pixelwaarde maakt de staven breder en de afbeelding makkelijker te scannen, vooral op schermen met lage resolutie.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Uitleg:**  
`XDimension.Pixels` bepaalt de breedte van één barcode‑module. Standaard is dit 1 pixel, wat dun kan lijken op high‑DPI‑monitoren. Verhoog je dit naar 2 pixels, dan verdubbelt de totale breedte zonder de gecodeerde data te beïnvloeden.

**Tip:** Als je de barcode op 300 dpi wilt afdrukken, levert een waarde van 3 of 4 pixels vaak de beste balans tussen grootte en scan‑betrouwbaarheid.

## Hoe kolommen in te stellen voor grootte‑controle

MicroPdf417 laat je het aantal kolommen opgeven (maximaal 4). Minder kolommen geven een hogere barcode; meer kolommen maken de barcode breder maar korter. Het aanpassen van deze waarde is de primaire manier om **de barcode‑grootte** te **customizen**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Waarom dit werkt:**  
De eigenschap `Pdf417.Columns` wordt gedeeld door alle PDF417‑gebaseerde symbologieën, inclusief MicroPdf417. Door deze op het maximum (4) te zetten, wordt de data over de breedst mogelijke lay‑out verdeeld, waardoor de totale hoogte afneemt. Als je een compactere hoogte wilt, verlaag je het aantal kolommen naar 2 of 3.

**Randgeval:** Wanneer de data‑string lang is, kan de bibliotheek automatisch extra rijen toevoegen om de inhoud te huisvesten, ongeacht het aantal kolommen. Houd de payload onder de 50 tekens voor voorspelbare afmetingen.

## Barcode‑grootte aanpassen voor verschillende uitvoerformaten

Naast X‑dimensie en kolommen kun je de uiteindelijke afbeeldingsgrootte beïnvloeden door een geschikt afbeeldingformaat en DPI te kiezen. PNG is lossless, perfect voor weergave op het web, terwijl BMP of TIFF geschikter kan zijn voor hoogwaardige afdrukken.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Als je een hogere DPI nodig hebt, kun je deze expliciet instellen:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Resultaat:** Het opgeslagen PNG‑bestand bevat een scherpe MicroPdf417‑barcode die de door jou geconfigureerde afmetingen respecteert. Open het bestand in een willekeurige afbeeldingsviewer om de visuele grootte te verifiëren.

### Verwachte output

Het uitvoeren van het programma genereert een bestand met de naam **MicroPdf417.png** (of **MicroPdf417_300dpi.png** als je DPI hebt ingesteld). De barcode ziet er ongeveer zo uit als de illustratie hieronder:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt‑tekst:* *Barcode generator C# output die een MicroPdf417 PNG toont*

Het scannen van de afbeelding met een standaard 2‑D‑barcodelezer levert de oorspronkelijke string `Åspóse.Barcóde©` op.

## Volledige broncode voor snelle copy‑paste

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Kopieer de code naar een nieuw console‑project, herstel de NuGet‑pakketten en voer `dotnet run` uit. De console bevestigt de locatie van het beeldbestand, en je ziet de gegenereerde barcode in je projectmap.

## Veelgestelde vragen en probleemoplossing

| Vraag | Antwoord |
|----------|--------|
| **Wat als de barcode er onscherp uitziet?** | Verhoog `XDimension.Pixels` of de DPI (`Parameters.Image.DpiX/Y`). Beide vergroten de modules en verbeteren de visuele kwaliteit. |
| **Kan ik een ander afbeeldingformaat gebruiken?** | Ja. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Tiff`. PNG blijft de veiligste keuze voor lossless kwaliteit. |
| **Mijn data bevat emoji’s—worden die gecodeerd?** | MicroPdf417 ondersteunt UTF‑8, dus de meeste emoji’s worden correct gecodeerd. Als je fouten tegenkomt, controleer dan of de string correct genormaliseerd is (`System.Text.Encoding.UTF8`). |
| **Hoe genereer ik andere symbologieën?** | Verander `EncodeTypes.MicroPdf417` naar een andere waarde uit `EncodeTypes` ( |

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode‑afbeelding te genereren in C# – MicroPdf417 gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Hoe PDF417‑barcode te genereren in C# met aangepaste afmetingen](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}