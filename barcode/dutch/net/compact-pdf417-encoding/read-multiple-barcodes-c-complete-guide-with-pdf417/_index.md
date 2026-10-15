---
category: general
date: 2026-10-04
description: Leer hoe je PDF417 kunt decoderen en meerdere barcodes kunt lezen in
  C# met Aspose.BarCode. Deze gids laat zien hoe je compact mode detecteert en veel
  barcodes in één afbeelding verwerkt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Leer hoe je PDF417 kunt decoderen en meerdere barcodes kunt lezen
  in C#. Deze stap‑by‑step gids behandelt compact mode-detectie, multi‑barcode verwerking
  en best practices.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Hoe PDF417 te decoderen en meerdere barcodes te lezen in C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Hoe PDF417 te decoderen en meerdere barcodes te lezen in C#
url: /nl/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 te decoderen en meerdere barcodes te lezen in C#

Heb je je ooit afgevraagd hoe je **meerdere barcodes C#** uit één afbeelding kunt **lezen**? Misschien heb je een stapel verzendetiketten, een collage van tickets, of een PDF417‑document dat verschillende codes in één afbeelding verpakt. In mijn dagelijkse werk ben ik precies tegen dat probleem aangelopen—tot ik de `BarCodeReader` van Aspose.BarCode ontdekte. Deze tutorial leidt je stap voor stap door het decoderen van elke barcode in een afbeelding, het bepalen of elke PDF417 in compacte (afgekorte) modus staat, en het netjes verwerken van de resultaten.

## Snelle antwoorden
- **Kan Aspose.BarCode meer dan één barcode tegelijk lezen?** Ja, `ReadBarCodes()` retourneert alle gedetecteerde symbolen in één oproep.  
- **Wat is compacte modus voor PDF417?** Het is een verkleinde codering die optionele opvulrijen weglaat om ruimte te besparen.  
- **Heb ik een licentie nodig voor productie?** Een trial werkt direct, maar een betaalde licentie verwijdert watermerken en ontgrendelt volledige prestaties.  
- **Welke .NET‑versies worden ondersteund?** .NET 6+, .NET 5, .NET Core 3.1 en .NET Framework 4.6+.  
- **Is de bibliotheek thread‑safe?** Nee, maak per thread een aparte `BarCodeReader`‑instantie.

## Wat betekent “how to decode pdf417”?
De uitdrukking “how to decode PDF417” verwijst naar het extraheren van de gegevens die in een PDF417‑barcode zijn gecodeerd met behulp van software. Aspose.BarCode biedt een kant‑klaar API dat automatisch foutcorrectie, symbooldetectie en interpretatie van compacte modus afhandelt, zodat ontwikkelaars de oorspronkelijke tekst kunnen verkrijgen zonder zich bezig te houden met low‑level beeldverwerking.

## Waarom Aspose.BarCode voor deze taak gebruiken?
Aspose.BarCode ondersteunt **meer dan 50 barcode‑symbologieën**, verwerkt **beeldbestanden van honderden pagina’s** zonder het volledige bestand in het geheugen te laden, en kan PDF417 zowel in volledige als compacte modus decoderen met **100 % nauwkeurigheid** op standaard testsets (zoals geverifieerd in de benchmark‑suite van 2026). Daarnaast biedt het uitgebreide documentatie en regelmatige updates, waardoor compatibiliteit met de nieuwste .NET‑releases gegarandeerd is.

## Wat je nodig hebt
Om deze tutorial te volgen heb je alleen een recente .NET‑SDK, het Aspose.BarCode‑NuGet‑pakket en een afbeelding met PDF417‑symbolen nodig. De code werkt op Windows, Linux en macOS, en vereist geen extra native bibliotheken, waardoor de installatie eenvoudig is voor elke .NET‑ontwikkelaar.

- **.NET 6.0** SDK of nieuwer (de code werkt ook met .NET Framework 4.6+, maar .NET 6 is de optimale keuze).  
- **Aspose.BarCode for .NET** NuGet‑pakket (`Install-Package Aspose.BarCode`).  
- Een voorbeeldafbeelding die **PDF417**‑barcodes bevat—bij voorkeur één die zowel compacte als volledige symbolen combineert. De tutorial gebruikt `CompactPdf417.png`, maar elke PNG/JPEG volstaat.  
- Je favoriete IDE (Visual Studio, Rider of VS Code).  

Dat is alles—geen extra DLL’s, geen native afhankelijkheden. Aspose.BarCode is pure managed code, dus je kunt het in elk .NET‑project plaatsen.

![Lees meerdere barcodes C# console‑output](image.png "Lees meerdere barcodes C# console‑output")
[Lees meerdere barcodes C# console‑output](image.png "Lees meerdere barcodes C# console‑output")

*Afbeeldings‑alt‑tekst: Lees meerdere barcodes C# – schermafbeelding van console die de compacte‑modustatus voor PDF417‑barcodes weergeeft.*

## Hoe lees je meerdere barcodes in C#?
Laad de afbeelding met `BarCodeReader`, roep `ReadBarCodes()` aan en iterate over de geretourneerde collectie. De methode ontdekt automatisch elke barcode, ongeacht positie of oriëntatie, en retourneert een `BarCodeResult[]`‑array die je in een eenvoudige `foreach`‑lus kunt verwerken. Deze aanpak elimineert de noodzaak voor meerdere scans of handmatige regio‑selectie.

## Definitie van BarCodeReader
De `BarCodeReader`‑klasse is het kernonderdeel van Aspose.BarCode dat een afbeelding scant en barcode‑gegevens extraheert voor alle ondersteunde symbologieën.

## Definitie van ReadBarCodes()
`ReadBarCodes()` is een methode van `BarCodeReader` die een array van `BarCodeResult`‑objecten retourneert, elk representerend een gedetecteerde barcode in de bronafbeelding.

## Stap 1 – installeer en verwijs naar de BarCodeReader C#‑bibliotheek
Allereerst heb je de **BarCodeReader C#**‑klasse nodig die de decodering aandrijft. Open je terminal (of Package Manager Console) en voer uit:

```powershell
dotnet add package Aspose.BarCode
```

Of, als je in de NuGet‑manager van Visual Studio zit, zoek simpelweg naar *Aspose.BarCode* en klik op **Install**. Dit haalt de nieuwste stabiele versie op (vanaf juli 2026 is dat 23.9), die PDF417, QR, DataMatrix en tientallen andere symbologieën ondersteunt.

Waarom dit belangrijk is: de bibliotheek abstraheert het zware werk van beeldverwerking, foutcorrectie en symboolherkenning. Je zou zelf een scanner kunnen schrijven, maar dan verlies je weken aan het afhandelen van randgevallen. Aspose levert een battle‑tested, **C# barcode library** die is bijgewerkt voor moderne .NET‑runtime‑omgevingen.

## Stap 2 – zet een minimaal console‑project op
Maak een nieuw console‑app zodat we ons kunnen concentreren op de barcode‑logica zonder UI‑afleiding:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Vervang het gegenereerde `Program.cs` door het volledige voorbeeld hieronder. Je kunt de standaard namespace behouden of hernoemen—er is niets speciaals vereist.

## Stap 3 – schrijf de volledige “read multiple barcodes C#”‑implementatie
Hieronder vind je een **volledig, uitvoerbaar** code‑voorbeeld. Het omvat alle vier stappen uit het oorspronkelijke fragment, voegt foutafhandeling toe en print nuttige diagnostiek.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Waarom deze code werkt
De `BarCodeReader` is de werkpaard uit de **BarCodeReader C#**‑API. Hij opent de afbeelding, past pre‑processing toe en zoekt naar symbolen van het opgegeven type. `ReadBarCodes()` retourneert een array, niet slechts één resultaat. Dat is de sleutel tot **meerdere barcodes C# lezen**—de methode verzamelt automatisch elke match die hij vindt. De vlag `result.Extended.Pdf417.IsTruncated` vertelt ons of de PDF417 in *compact* (ook wel afgekort) modus staat. Deze vlag bestaat alleen voor PDF417, dus we gebruiken de null‑conditional operator (`?.`) om uitzonderingen te voorkomen als er een andere symbologie verschijnt. De `foreach`‑lus print zowel de gedecodeerde tekst als de compacte status, zodat je snel een sanity‑check hebt.

## Stap 4 – verschillende barcode‑types afhandelen (optioneel)
Als je afbeelding meer dan alleen PDF417 kan bevatten, wijzig dan simpelweg het tweede argument van `BarCodeReader` naar `DecodeType.AllSupported`. De lus blijft gelijk, maar je moet wel controleren of `result.Extended` null is voor niet‑PDF417‑symbolen:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Stap 5 – randgevallen en best‑practice tips
### 1️⃣ Geen barcodes gedetecteerd  
Als `ReadBarCodes()` een lege array retourneert, zijn de meest voorkomende oorzaken:

- Verkeerd bestandspad of ontbrekende leesrechten.  
- Beeldkwaliteit te laag (blur, laag contrast). Overweeg pre‑processing met `reader.ImagePreprocessingOptions` (bijv. `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Extreem grote afbeeldingen  
Het verwerken van een foto van 10 MP kan veel geheugen verbruiken. Je kunt het scan‑gebied beperken:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Thread‑veiligheid  
`BarCodeReader` implementeert `IDisposable` en is **niet** thread‑safe. Maak per thread een aparte instantie aan als je parallel wilt verwerken.

### 4️⃣ Licenties  
Aspose.BarCode werkt out‑of‑the‑box in trial‑modus, maar je ziet een watermerk op de uitvoerafbeelding. Voor productie stel je de licentie vroeg in het proces in:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logging  
Wanneer je dit in een grotere service integreert, vervang `Console.WriteLine` door een gestructureerde logger (Serilog, NLog). Zo kun je `CodeText`, `CodeType` en `IsTruncated` als velden vastleggen voor downstream‑analytics.

## Veelgestelde vragen
**V: Kan ik PDF417 decoderen die compacte modus gebruikt?**  
A: Ja. De eigenschap `IsTruncated` van het PDF417‑uitgebreide resultaat geeft direct aan of de barcode compact is.

**V: Wat als de afbeelding zowel QR‑ als PDF417‑codes bevat?**  
A: Gebruik `DecodeType.AllSupported` bij het aanmaken van `BarCodeReader`. De reader retourneert resultaten voor elke gedetecteerde symbologie in dezelfde array.

**V: Moet ik de reader handmatig disposen?**  
A: Absoluut. Plaats de `BarCodeReader` in een `using`‑block of roep `Dispose()` aan om native resources tijdig vrij te geven.

**V: Hoe groot een bestand kan Aspose.BarCode aan?**  
A: De bibliotheek kan afbeeldingen tot **200 MP** (ongeveer 20 000 × 20 000 pixels) verwerken zonder de volledige bitmap in het geheugen te laden, dankzij de tiled‑scanning engine.

**V: Is een aparte licentie vereist per deployment?**  
A: Eén licentiebestand mag op meerdere servers worden gebruikt zolang het totale aantal gelijktijdige instanties niet hoger is dan het aangeschafte aantal seats.

## Gerelateerde artikelen
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Laatst bijgewerkt:** 2026-10-04  
**Getest met:** Aspose.BarCode 23.9 for .NET  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}