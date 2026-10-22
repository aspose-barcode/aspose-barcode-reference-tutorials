---
category: general
date: 2026-10-21
description: Hur man läser PDF417‑streckkod i C# med en streckkodsläsare från en bild.
  Följ detta steg‑för‑steg C#‑exempel på streckkodsläsare för pålitlig avkodning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: sv
lastmod: 2026-10-21
og_description: Hur man läser PDF417‑streckkod i C# med ett komplett streckkodsläsar‑exempel.
  Lär dig att avkoda Macro PDF417‑bilder och komma åt alla utökade fält.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Hur man läser PDF417-streckkod i C# – detaljerad guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hur man läser PDF417‑streckkod i C# – komplett guide för streckkodsläsare
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417-streckkod i C# – komplett streckkodsläsarguide

Om du behöver **läsa PDF417-streckkod** i en .NET‑applikation, visar den här guiden en färdig‑att‑köra‑lösning. Du får se hur du **läser streckkod från bild C#** med ett populärt streckkodsbibliotek och får alla Macro PDF417‑attribut utan extra verktyg.

Handledningen täcker allt som krävs för ett **C# streckkodsläsare‑exempel**: projektuppsättning, kodgenomgång och tips för att hantera kantfall. När du är klar kan du klistra in koden i ett konsolprojekt och börja avkoda PDF417‑bilder omedelbart.

## Vad du behöver

Innan du börjar, bekräfta följande förutsättningar:

| Förutsättning | Orsak |
|--------------|--------|
| .NET 6.0 SDK eller senare | Tillhandahåller runtime för C#‑konsolappen |
| Visual Studio 2022 (eller någon C#‑IDE) | Gör det enkelt att skapa projekt och felsöka |
| Aspose.BarCode for .NET (NuGet‑paket) | Tillhandahåller `BarCodeReader`‑ och `DecodeType`‑klasserna |
| En Macro PDF417‑bildfil (t.ex. `MacroPdf417.png`) | Används som indata för avkodning |

Du kan installera biblioteket med dotnet‑CLI:

```bash
dotnet add package Aspose.BarCode
```

## Hur man läser PDF417‑streckkod från en bild i C#

Kärnan i **läsa streckkod från bild C#**‑arbetsflödet består av tre steg:

1. Initiera `BarCodeReader` för den specifika `DecodeType`.
2. Iterera genom den returnerade `BarCodeResult`‑samlingen.
3. Åtkomst till både grundläggande och utökade PDF417‑fält.

Nedan är den kompletta, körbara koden. Spara den som `Program.cs` i ett konsolprojekt.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Förklaring av varje steg

* **Steg 1 – Initiera läsaren**  
  `BarCodeReader`‑konstruktorn får bildfilens sökväg och en `DecodeType`. `DecodeType.MacroPdf417` talar om för biblioteket att leta efter Macro PDF417‑symboler, som innehåller extra metadata utöver vanliga PDF417‑streckkoder.

* **Steg 2 – ReadBarCodes()**  
  Denna metod returnerar ett `IEnumerable<BarCodeResult>` som kan innehålla flera streckkoder om bilden har mer än en. `foreach`‑loopen garanterar att varje upptäckt symbol bearbetas.

* **Steg 3 – Grundläggande information**  
  `CodeTypeName` identifierar streckkodformatet (t.ex. “MacroPDF417”). `CodeText` innehåller den råa datasträngen som kodats i symbolen.

* **Steg 4 – Utökade fält**  
  Macro PDF417 lägger till en uppsättning utökade egenskaper under `barcodeResult.Extended.Pdf417`. Dessa fält exponerar fil‑nivå‑data såsom `FileID`, `SegmentID` och `FileName`. Genom att åtkomma dem direkt kan du återuppbygga flerdelade dokument eller verifiera integritet.

#### Förväntad konsolutskrift

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

De exakta värdena speglar innehållet som kodats i din `MacroPdf417.png`. Om bilden innehåller ett enda segment blir `SegmentsCount` 1 och `SegmentID` 0.

## Ställ in C#‑streckkodsläsarmiljön

Ett pålitligt **C# streckkodsläsare‑exempel** beror på en ren projektkonfiguration:

1. **Skapa ett nytt konsolprojekt**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Lägg till Aspose.BarCode‑paketet** (som visat tidigare).  
3. **Kopiera bildfilen** till projektmappen eller referera den med en absolut sökväg.  
4. **Bygg och kör**  
   ```bash
   dotnet run
   ```

Om bygget misslyckas med ett saknat referensfel, kontrollera att `using Aspose.BarCode;`‑satserna matchar den installerade paketversionen. Bibliotekets API är stabilt över .NET 6 och .NET 8, så du kan uppgradera runtime utan kodändringar.

## Avkoda Macro PDF417‑streckkoden

När du anropar `ReadBarCodes()` utför biblioteket följande internt:

* **Bildförbehandling** – konverterar bitmapen till en binär matris, korrigerar rotation och brus.  
* **Mönsterdetektion** – söker efter PDF417‑start/stop‑mönster och extraherar modulbredden.  
* **Felkorrigering** – använder Reed‑Solomon‑koder för att återställa skadade kodord.  
* **Macro‑extraktion** – parsar det utökade PDF417‑segmenthuvudet och fyller i `Extended.Pdf417`‑objektet.

Att förstå denna pipeline hjälper dig att avgöra när du bör justera avkodningsalternativ. Till exempel, om dina bilder har låg kontrast, kan du aktivera `BarCodeReader`‑egenskapen `ReadQuality` (tillgänglig i senare versioner) för att förbättra detekteringsgraden.

## Tolka de utökade PDF417‑fälten

De utökade fälten mappar direkt till Macro PDF417‑specifikationen:

| Fält | Betydelse |
|-------|-----------|
| `MacroPdf417FileID` | Unik identifierare för hela filen över alla segment |
| `MacroPdf417SegmentID` | Noll‑baserat index för det aktuella segmentet |
| `MacroPdf417SegmentsCount` | Totalt antal segment som utgör filen |
| `MacroPdf417FileName` | Ursprungligt filnamn som lagrats under kodning |
| `MacroPdf417Checksum` | 16‑bit checksum för integritetsverifiering |
| `MacroPdf417FileSize` | Storlek på originalfilen i byte |
| `MacroPdf417TimeStamp` | UTC‑tidsstämpel när streckkoden genererades |
| `MacroPdf417Addressee` | Avsedd mottagare av dokumentet |
| `MacroPdf417Sender` | Avsändare av dokumentet |
| `MacroPdf417Terminator` | Literalsträngen “END” som markerar sista segmentet |

Du kan använda dessa värden för att rekonstruera ett flerdelat PDF, verifiera att inget segment saknas, eller logga revisionsinformation för efterlevnad.

## Vanliga fallgropar och felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-------|
| Ingen utskrift visas | Fel bildsökväg eller format som inte stöds | Använd en absolut sökväg och säkerställ att filen är PNG/JPEG som stöds av Aspose.BarCode |
| `CodeType` visar “PDF417” istället för “MacroPDF417” | Bilden innehåller en vanlig PDF417‑symbol, inte en macro‑variant | Verifiera att källstreckkoden är kodad med Macro PDF417‑tillägg |
| Vissa fält är tomma | Streckkoden genererades utan dessa macro‑fält | Koda streckkoden med full macro‑payload, eller hantera null‑värden i koden |
| Avkodaren kastar `ArgumentException` | Fel `DecodeType` angiven | Ändra `DecodeType.MacroPdf417` till `DecodeType.Pdf417` om du bara behöver standard‑PDF417‑data |

**Proffstips:** Omge fältåtkomsten med null‑kontroller om du förväntar dig icke‑macro‑streckkoder. `Extended.Pdf417`‑objektet returnerar standardvärden (t.ex. `0` för numeriska fält) när data saknas.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Sammanfattning av komplett fungerande exempel

När allt sätts ihop består det slutgiltiga programmet av `using`‑direktiven, `Main`‑metoden och den fyrastegs‑loopen som visades tidigare. Inga extra konfigurationsfiler behövs. Kompilera och kör projektet för att se konsolutskriften med alla Macro PDF417‑egenskaper.

## Slutsats

Du vet nu **hur man läser PDF417‑streckkod** i C# med ett koncist **C# streckkodsläsare‑exempel**. Guiden har lett dig genom miljöuppsättning, kodimplementation och tolkning av varje utökat Macro PDF417‑fält. Med denna grund kan du integrera streckkodsskanning i lagerhanteringssystem, dokumenthanteringsarbetsflöden eller mobila back‑ends.

### Nästa


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringssätt i dina egna projekt.

- [Hur man läser PDF417 i C# – komplett streckkodsläsarguide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Hur man avkodar PDF417 i C# med ett streckkodsläsare‑exempel](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Hur man skapar PDF417‑streckkodbild i C# med Macro PDF417‑alternativ](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}