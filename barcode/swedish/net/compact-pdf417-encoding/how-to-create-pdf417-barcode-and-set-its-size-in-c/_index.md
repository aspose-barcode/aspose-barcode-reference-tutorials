---
category: general
date: 2026-09-22
description: Lär dig hur du skapar PDF417‑streckkod i C#, ställer in streckkodens
  storlek och genererar streckkodsbilder med tydliga steg‑för‑steg‑kodexempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: sv
lastmod: 2026-09-22
og_description: Skapa PDF417-streckkod i C# snabbt. Denna handledning visar hur du
  ställer in streckkodens storlek, aktiverar kompakt läge och genererar PNG‑bilder
  för vilket .NET‑projekt som helst.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Skapa PDF417-streckkod i C# – steg-för-steg guide
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Hur man skapar PDF417‑streckkod och anger dess storlek i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du PDF417-streckkod och ställer in dess storlek i C#

Om du behöver **create PDF417 barcode** i C#, visar den här guiden hur du genererar streckkoden, styr dess dimensioner och sparar resultatet som en bildfil. Oavsett om du bygger ett biljettsystem, en logistiklapp eller ett säkert legitimationsbevis, låter behärskning av PDF417-formatet dig koda stora mängder data i en kompakt visuell form.

I den här handledningen kommer du att lära dig att:

* **Create PDF417 barcode** med Aspose.BarCode (eller någon kompatibel) bibliotek.  
* **Set barcode size** genom att justera X‑dimensionen och antalet kolumner.  
* Generera en **barcode image in C#** för PNG-, JPEG- eller BMP-utdata.  

Exemplet använder den kostnadsfria community-editionen av Aspose.BarCode för .NET, men samma koncept gäller för andra bibliotek som exponerar liknande egenskaper.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat.  
* En C#-IDE (Visual Studio, Visual Studio Code, Rider, etc.).  
* NuGet‑paketet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Ingen ytterligare konfiguration krävs; biblioteket fungerar på Windows, Linux och macOS.

## Steg 1: Skapa en grundläggande PDF417-streckkod och ställ in dess storlek

Det första steget är att instansiera en `BarcodeGenerator` med enum‑värdet `EncodeTypes.Pdf417` och ange den text du vill koda. Justera sedan **X‑dimension** (modulbredd) och antalet **columns** för att kontrollera den totala storleken.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Varför dessa inställningar är viktiga**

* `XDimension.Pixels` bestämmer den smalaste stapelbredden. Mindre värden ger en tätare streckkod, medan större värden ökar läsbarheten på lågupplösta skannrar.  
* `Pdf417.Columns` påverkar streckkodens bildförhållande. Färre kolumner gör streckkoden högre; fler kolumner gör den plattare. Att justera kolumner är det primära sättet att **set barcode size** utan att ändra den kodade datan.

Efter att ha kört koden hittar du `Pdf417Basic.png` i den angivna mappen. Bilden ser liknande ut som skärmbilden nedan:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Steg 2: Skapa en kompakt PDF417-streckkod (truncate‑läge) med samma storlek

Ibland behöver du en kortare streckkod för begränsat utrymme. PDF417 erbjuder ett *truncate* (kompakt) läge som tar bort stoppmönstret och minskar den totala höjden. Egenskapen `Truncate` växlar detta beteende.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Vad förändras med `Truncate = true`?**

* Streckkoden blir ungefär 15‑20 % kortare vertikalt, vilket är användbart för små etiketter eller mobila skärmar.  
* Datan förblir fullt återvinningsbar; de flesta moderna skannrar förstår truncate‑läget automatiskt.

Den resulterande `CompactPdf417.png` visas som en smalare version av den grundläggande streckkoden.

## Steg 3: Skapa en Micro PDF417-streckkod, justera kolumner och spara den

Micro PDF417 är en nyare, högdensitetsvariant avsedd för mycket små utrymmen (t.ex. ID‑kort). Den stöder endast 1‑4 kolumner, och biblioteket exponerar samma `XDimension`‑egenskap för storlekskontroll.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Viktiga punkter för Micro PDF417**

* Enum‑värdet `EncodeTypes.MicroPdf417` väljer automatiskt mikrovarianten.  
* Eftersom symbolen är tätare kan du behöva en skrivare med högre DPI (300 dpi eller mer) för att hålla streckkoden läsbar.  
* Justering av kolumnantalet är den enda tillgängliga storlekskontrollen; biblioteket respekterar fortfarande `XDimension`.

## Hur du ställer in streckkodens storlek för olika utdataformat

Exemplen ovan använder PNG, men samma `Save`‑metod fungerar med JPEG, BMP eller TIFF. Om du behöver en specifik bilddimension (t.ex. 300 × 150 px), kombinera `XDimension` med `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Att öka `ImageResolution` samtidigt som du skalar `XDimension` bevarar den visuella kvaliteten på högupplösta utskrifter.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Streckkoden ser suddig ut på skärmen | Låg DPI kombinerat med liten `XDimension` | Öka `ImageResolution` och/eller `XDimension.Pixels` |
| Skannern kan inte läsa truncate‑läge | Äldre skannerfirmware saknar stöd | Använd fullständigt (icke‑trunkerat) läge för äldre hårdvara |
| Micro PDF417 är oläsbar | Utskrivet med < 300 dpi eller med otillräcklig kontrast | Skriv ut på matt papper med 300 dpi eller högre, säkerställ mörk förgrund |
| Utdatafilen är korrupt | Saknar skrivbehörighet till målmappen | Verifiera att `YOUR_DIRECTORY` finns och är skrivbar |

**Pro‑tips:** Generera alltid streckkoden som PNG när du behöver förlustfri kvalitet för vidare bearbetning (t.ex. inbäddning i PDF‑filer). PNG bevarar exakta pixelvärden, medan JPEG introducerar komprimeringsartefakter som kan påverka streckkodens läsbarhet.

## Fullt, körbart exempel

Nedan är ett komplett konsolprogram som demonstrerar alla tre streckkodstyper i ett enda körning. Kopiera koden till ett nytt .NET‑konsolprojekt och kör det.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Förväntat resultat**

När programmet körs skapas tre PNG‑filer i en `Barcodes`‑mapp:

* `Pdf417Basic.png` – en standard PDF417‑streckkod med tre kolumner.  
* `CompactPdf417.png` – samma data i truncate (kompakt) läge, något kortare.  
* `MicroPdf417.png` – en högdensitets‑Micro PDF417‑variant med fyra kolumner.

Öppna någon bild med en bildvisare; du bör se den distinkta staplade

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man ställer in felnivå i PDF417-streckkod – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Skapa PDF417-streckkodmetadata i C# – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}