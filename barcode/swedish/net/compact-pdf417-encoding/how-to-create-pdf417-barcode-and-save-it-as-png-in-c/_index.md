---
category: general
date: 2026-10-05
description: Lär dig hur du skapar PDF417‑streckkod i C# och genererar streckkod‑PNG
  med steg‑för‑steg‑kod och bästa‑praxis‑tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: sv
lastmod: 2026-10-05
og_description: Skapa PDF417‑streckkod i C# och generera streckkod‑PNG omedelbart.
  Följ den här kompletta handledningen för en produktionsklar lösning.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Skapa PDF417-streckkod i C# – fullständig guide för att generera PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Hur man skapar PDF417-streckkod och sparar den som PNG i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417-streckkod och sparar den som PNG i C#

Om du behöver **skapa PDF417-streckkod** i en .NET-applikation visar den här guiden exakt hur du gör det. Du får ett färdigt C#‑kodexempel som genererar en högkvalitativ **barcode PNG**‑fil, och du kommer att förstå varje inställning som påverkar resultatet.

Att generera streckkoder är ett vanligt krav för biljettsystem, lagerhantering och säker dokumentkodning. I slutet av den här handledningen kan du svara på frågan “**how to generate PDF417**” med ett komplett, körbart exempel.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* En utvecklingsmiljö såsom Visual Studio 2022 eller VS Code  
* **Aspose.BarCode for .NET** NuGet‑paketet (eller något kompatibelt bibliotek som stödjer PDF417)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

Koden nedan använder Aspose‑API:t eftersom det ger detaljerad kontroll över PDF417‑parametrar och stödjer PNG‑export direkt ur lådan.

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt och importera de nödvändiga namnrymderna:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation`‑namnrymden innehåller `BarcodeGenerator`‑klassen, som är ingångspunkten för **skapa PDF417-streckkod** bilder.

## Steg 2: Skapa PDF417-streckkod med önskad text

Instansiera generatorn med `EncodeTypes.Pdf417`‑enumen och den data du vill koda. Exemplet använder en sträng som innehåller specialtecken för att demonstrera Unicode‑hantering:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Generatorn innehåller nu ett streckkodobjekt som du kan konfigurera innan rendering.

## Steg 3: Konfigurera visuella parametrar

Finjustering av streckkoden förbättrar läsbarheten och minskar bildstorleken. De mest ofta justerade inställningarna är **X‑dimension**, **columns** och **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** styr bredden på varje modul; ett värde på `2` pixlar ger en kompakt men läsbar streckkod.  
* **Columns** bestämmer hur många datakolumner koden använder. Färre kolumner gör streckkoden smalare men högre.  
* **Truncate** aktiverar “compact”-läget som definieras i PDF417‑specifikationen, vilket tar bort onödiga utfyllnadsrader.

Du kan experimentera med `Rows` och `ErrorCorrectionLevel` om ditt användningsfall kräver högre motståndskraft mot skador.

## Steg 4: Spara streckkoden som en PNG‑bild

Slutligen exporterar du streckkoden till en PNG‑fil. PNG bevarar skarpa kanter och stödjer transparens, vilket gör den idealisk för webb‑ och utskrifts­scenarier.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

När programmet körs skapas `CompactPdf417.png` i den angivna katalogen. Bilden ser ut så här:

![Kompakt PDF417-streckkod skapad med C#](compact-pdf417.png "Exempel på en kompakt PDF417-streckkod skapad med C#")

*Alt‑texten ovan innehåller huvudnyckelordet, vilket uppfyller både SEO‑ och tillgänglighetskrav.*

## Fullt, körbart exempel

När alla delar sätts ihop, här är ett fristående program som du kan kopiera, klistra in och köra:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Förväntat resultat

När du öppnar `CompactPdf417.png` bör du se en vertikal, högdensitets‑streckkod som kodar strängen *Åspóse.Barcóde©*. Att skanna bilden med någon PDF417‑läsare returnerar den ursprungliga texten.

## Varför dessa inställningar är viktiga

* **X‑dimension** påverkar både fysisk storlek och skanningshastighet. Småare moduler ökar datadensiteten men kan kräva högupplösta skannrar.  
* **Columns** påverkar bildförhållandet. För mobila kvitton håller ett lågt kolumnantal streckkoden tillräckligt smal för att passa på smalt papper.  
* **Truncate** minskar antalet rader, sparar bläck och utrymme utan att offra dataintegritet, eftersom PDF417 redan innehåller felkorrigeringskodord.

Att förstå dessa parametrar låter dig anpassa streckkoden till begränsningarna i ditt målmedium—oavsett om det är en etikettprinter, en webbsida eller en mobilapp.

## Vanliga variationer och kantfall

### Generera andra bildformat

Om du föredrar JPEG eller BMP, ändra `BarCodeImageFormat`‑enum:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG komprimerar bilden men kan introducera artefakter som påverkar skanning vid små storlekar.

### Justera felkorrigering

För tuffa miljöer (t.ex. utomhusskyltning) öka felkorrigeringsnivån:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Högre nivåer lägger till mer redundans, vilket gör streckkoden större men mer robust.

### Koda binär data

PDF417 kan koda binära nyttolaster. Skicka en `byte[]` istället för en sträng:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Biblioteket växlar automatiskt till binärt läge.

### Hantera mycket långa strängar

När datan överskrider standardkapaciteten skapar generatorn automatiskt extra rader. Du kan begränsa radantalet för att undvika för stora bilder:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Om innehållet fortfarande inte får plats, överväg att dela upp det i flera streckkoder.

## Pro‑tips

* **Cache generatorn** om du behöver skapa många streckkoder med samma inställningar. Återanvändning av objektet undviker upprepade allokeringar av interna resurser.  
* **Ställ in `Resolution`** på `ImageOptions` om du behöver ett specifikt DPI‑värde för utskrift:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validera outputen** programatiskt med `BarCodeReader` för att säkerställa att den genererade PNG‑filen kan avkodas innan den levereras till användare.

## Slutsats

Du vet nu hur du **skapar PDF417-streckkod** i C# och **genererar barcode PNG**‑filer med full kontroll över storlek, kolumner och kompakt läge. Det kompletta exemplet demonstrerar den standardiserade metoden, förklarar varför varje inställning är viktig och täcker variationer såsom felkorrigering, alternativa format och binär data. Använd tipsen ovan för att anpassa lösningen till ditt specifika arbetsflöde, oavsett om du bygger ett biljettsystem, en logistiketikettsgenerator eller en säker dokumentkodare.

---

**Nästa steg**

* Utforska andra 2D‑symbologier (DataMatrix, QR) med samma `BarcodeGenerator`‑klass.  
* Integrera streckkodsskapandet i ett ASP.NET Core‑API för att leverera PNG‑filer på begäran.  
* Kombinera streckkodsbilden med PDF‑genereringsbibliotek för att bädda in den direkt i rapporter.

Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar pdf417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man genererar micro pdf417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man skapar PDF417-streckkod i C# med kompakt läge](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}