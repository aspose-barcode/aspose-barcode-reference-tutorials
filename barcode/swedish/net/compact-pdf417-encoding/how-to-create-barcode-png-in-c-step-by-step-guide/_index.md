---
category: general
date: 2026-10-15
description: Skapa en streckkod PNG i C# med ett kompakt PDF417‑exempel – lär dig
  hur du ställer in kolumner, justerar dimensioner och genererar bilden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: sv
lastmod: 2026-10-15
og_description: Skapa streckkod PNG i C# med ett kompakt PDF417‑exempel. Denna guide
  visar hur du ställer in kolumner, justerar dimensioner och sparar bilden.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Skapa streckkod PNG i C# – komplett programmeringshandledning
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Hur man skapar en streckkod‑PNG i C# – steg‑för‑steg guide
url: /sv/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod PNG i C# – steg‑för‑steg guide

Om du behöver **create barcode PNG**-filer från C#-kod, visar den här handledningen en komplett lösning på bara några rader. Du kommer att se hur du ställer in kolumner, justerar modulstorleken och sparar en kompakt PDF417-streckkod som en PNG-bild – allt med ett enda, lättläst exempel.

Att generera streckkoder programatiskt tar bort det manuella steget att använda en grafikredigerare, och låter dig bädda in streckkoder direkt i fakturor, biljetter eller lageretiketter. I avsnitten som följer kommer vi att täcka allt du behöver veta för att **how to create barcode**-bilder, varför varje konfiguration är viktig, och hur du anpassar koden för olika användningsfall.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
* En referens till ett streckkodsbibliotek som stöder PDF417, till exempel **Aspose.BarCode for .NET** eller **IronBarcode**. Exemplet använder Aspose.BarCode, som du kan installera via NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Grundläggande kunskap om C#-syntax och Visual Studio (eller någon IDE du föredrar).

> **Pro tip:** Om du föredrar ett gratis alternativ, stöder det öppna källkods‑biblioteket **ZXing.Net** också PDF417, men egenskapsnamnen skiljer sig något. Koncepten som visas här förblir desamma.

## Hur man skapar streckkod PNG i C# (primärt steg)

Kärnan i lösningen är ett `BarcodeGenerator`-objekt konfigurerat för PDF417‑kodning. Följande avsnitt bryter ner varje kodrad, förklarar **how to set columns**, och visar varför inställningarna påverkar den slutliga PNG‑storleken.

### Steg 1: Initiera streckkodsgeneratorn med önskad text

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Varför detta är viktigt*: `EncodeTypes.Pdf417`‑enumet talar om för biblioteket att producera en tvådimensionell staplad streckkod. Konstruktorn accepterar också den data du vill koda, så du behöver inte ett separat `SetData`‑anrop.

### Steg 2: Ställ in modul (X)-dimensionen i pixlar

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X-dimensionen** styr den visuella densiteten i streckkoden. Ett mindre värde ger en tätare bild, vilket är användbart när du behöver en kompakt PNG för mobila skärmar eller begränsat utskriftsutrymme.

### Steg 3: Definiera antalet kolumner för PDF417‑streckkoden

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Denna rad demonstrerar **how to set columns**. PDF417 kan automatiskt välja det optimala antalet kolumner, men att explicit ange det ger dig en förutsägbar bredd, särskilt när du bäddar in PNG‑filen i en layout med fast storlek.

### Steg 4: Aktivera kompakt layout genom att trunkera streckkoden

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

När `Truncate` är true tar biblioteket bort efterföljande rader som inte innehåller data, vilket minskar bildens totala höjd utan att förlora information.

### Steg 5: Spara streckkodsbilden som PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save`‑metoden skriver streckkoden till disk i det format du anger. PNG är förlustfri, vilket gör den idealisk för skanningsapplikationer som kräver exakt kantdetektering.

### Fullt, körbart exempel

När allt sätts ihop, här är ett fristående program som du kan kopiera, klistra in och köra:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Förväntad output** – Efter att ha kört programmet hittar du `CompactPdf417.png` i körningsmappen. Bilden innehåller en PDF417‑streckkod med tre kolumner som är tillräckligt kompakt för att passa på en standard 2 × 2 cm‑etikett samtidigt som den förblir fullt läsbar.

![Create barcode PNG example](placeholder.png){alt="Skapa streckkod PNG med C#"}

## Hur man ställer in kolumner för olika datastorlekar (sekundärt nyckelord)

Antalet kolumner påverkar både bredden och läsbarheten av streckkoden:

| Kolumner | Ungefärlig bredd (px) | Typiskt användningsområde |
|--------|-------------------|------------------|
| 1‑2    | Smal, hög      | Små taggar, RFID‑liknande utskrifter |
| 3‑5    | Balanserad          | Allmänna etiketter |
| 6‑9    | Bred, kort       | Stora affischer eller förpackningar |

Om din datasträng växer kan biblioteket automatiskt öka radantalet för att hålla streckkoden inom kolumngränsen. Att tvinga ett kolumnantal som är för lågt kan dock göra streckkoden onödigt hög, vilket kanske inte får plats på en kvittoskrivare. Justera kolumnantalet baserat på de fysiska begränsningarna för ditt utskriftsmedium.

## Hur man skapar streckkodsbilder i andra format (sekundärt nyckelord)

Även om PNG är det vanligaste formatet för webben och mobila enheter, kan du behöva **how to create barcode**-bilder i JPEG, BMP eller SVG för specialiserade arbetsflöden:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Valet av rätt format beror på downstream‑konsumenten:

* **PNG** – förlustfri, idealisk för skannrar.
* **JPEG** – mindre filstorlek, acceptabel när små komprimeringsartefakter är tolererbara.
* **SVG** – perfekt för högupplöst utskrift eller UI‑skalning.

## C# streckkodsexempel: hantera fel och kantfall

Ett robust **c# barcode example** bör förutse körningsproblem:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Varför omsluta med `try/catch`?* Ogiltiga tecken i texten, ej stödda dimensioner eller skrivbehörighetsproblem kommer att kasta undantag. Att hantera dem på ett smidigt sätt förhindrar att din applikation kraschar under batch‑bearbetning.

## Utöka exemplet: lägga till en logotyp eller bakgrund

Många verkliga scenarier kräver en logotyp‑överlappning eller en färgad bakgrund. Aspose.BarCode‑API:n låter dig kombinera streckkoden med en bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Denna teknik behåller **create barcode PNG**‑arbetsflödet intakt samtidigt som den berikar den visuella varumärkesprofilen för den slutliga bilden.

## Sammanfattning

I den här guiden demonstrerade vi hur man **create barcode PNG**-filer i C# med en kompakt PDF417‑konfiguration. Du lärde dig:

* Den exakta koden som behövs för att initiera en `BarcodeGenerator`.
* **How to set columns** och varför kolumnantalet är viktigt för storlek och läsbarhet.
* Hur man justerar X‑dimensionen och aktiverar trunkering för en tätare PNG.
* Sätt att spara bilden i PNG, JPEG eller SVG.
* Mönster för felhantering för ett produktionsklart **c# barcode example**.
* Valfria utökningar såsom logotyp‑överlappning och bakgrundsanpassning.

Du har nu ett färdigt kodsnutt som du kan integrera i fakturageneratorer, biljettsystem eller lagerhanteringsverktyg. Experimentera med olika kolumnvärden, modulstorlekar eller streckkodstyper (t.ex. QR, Code128) för att se hur bilden förändras.

## Nästa steg

* Utforska andra kodningstyper (`EncodeTypes.QR`, `EncodeTypes.Code128`) för att täcka fler användningsfall.
* Kombinera streckkodsgenerering med PDF‑skaparbibliotek (t.ex. **iTextSharp**) för att bädda in PNG‑filen direkt i dokument.
* Undersök dynamisk storlek: beräkna det optimala kolumnantalet baserat på längden av inmatningssträngen och mål‑etikettens dimensioner.

Lycka till med kodningen, och njut av enkelheten att programatiskt generera skarpa streckkod PNG‑filer i C#!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar PDF417‑streckkod och sparar den som PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Hur man skapar PDF417‑streckkod och ställer in dess storlek i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Hur man skapar PDF417‑streckkod i C# med kompakt läge](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}