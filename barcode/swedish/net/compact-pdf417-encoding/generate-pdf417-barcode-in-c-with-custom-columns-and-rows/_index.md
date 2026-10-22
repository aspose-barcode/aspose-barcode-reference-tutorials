---
category: general
date: 2026-10-21
description: Generera pdf417-streckkod snabbt i C#. Lär dig hur du genererar pdf417-streckkod
  med anpassad layout, kolumner, rader och PNG-utdata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: sv
lastmod: 2026-10-21
og_description: Generera pdf417-streckkod i C#. Följ den här handledningen för att
  lära dig hur du genererar pdf417-streckkod med anpassade kolumner, rader och PNG-utdata.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generera pdf417-streckkod i C# – fullständig steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Generera pdf417-streckkod i C# med anpassade kolumner och rader
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera pdf417-streckkod i C# – komplett programmeringsguide

Om du behöver **generera pdf417-streckkod** i en .NET-applikation visar den här guiden hur du gör det med några få rader kod. Du får se ett praktiskt exempel som konfigurerar antalet kolumner och rader och sedan sparar resultatet som en PNG-bild. Samma metod fungerar för vilken text du vill koda, så du kan anpassa den för fakturor, biljetter eller ID-kort.

Att generera en **pdf417-streckkod** känns ofta som en separat uppgift från resten av din kodbas. I slutet av den här tutorialen kommer du att förstå varför layoutparametrar är viktiga, hur du kontrollerar bildkvaliteten och vilka bibliotekskallar som krävs för att **generera pdf417-streckkod** på ett pålitligt sätt.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* En C#‑kompatibel IDE (Visual Studio, VS Code, Rider, etc.)  
* **Aspose.BarCode for .NET** NuGet‑paketet (eller något kompatibelt streckkodsbibliotek)  

Du kan lägga till biblioteket med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

Biblioteket tillhandahåller klassen `BarcodeGenerator` som används genom hela tutorialen.

## Steg 1: Skapa en barcode‑generatorinstans

Den första raden skapar ett objekt som vet hur man **genererar pdf417-streckkod**. Du måste ange kodningstypen (`EncodeTypes.Pdf417`) och den text du vill koda.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Varför detta steg är viktigt* – `BarcodeGenerator` kapslar in alla inställningar för streckkoden. Att instansiera den med rätt `EncodeTypes` talar om för motorn att använda PDF417‑symbologi istället för QR, Code128 eller andra format.

## Steg 2: Konfigurera PDF417‑layouten

PDF417 låter dig styra antalet kolumner och rader, vilket direkt påverkar streckkodens storlek och densitet. Att justera dessa värden är kärnan i **hur man genererar pdf417-streckkod** med en anpassad layout.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Varför du kan vilja ändra dessa värden* – Fler kolumner minskar streckkodens höjd, medan fler rader ökar bredden. Välj värden som passar den avsedda skanningsenheten och det tillgängliga utskriftsområdet.

> **Proffstips:** Om du utelämnar rader beräknar biblioteket automatiskt det optimala antalet baserat på datalängden. Att explicit ange rader är användbart när du behöver en fast bildstorlek för UI‑layouter.

## Steg 3: Välj bildformat och spara filen

Efter att ha konfigurerat layouten kan du rendera streckkoden till en bild. Exemplet nedan sparar streckkoden som en PNG‑fil, men du kan också välja JPEG, BMP eller TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

När koden körs kommer `CustomLayout.png` att innehålla en tydlig **pdf417-streckkod** som matchar de kolumn-/radinställningar du angav.

### Förväntat resultat

Att öppna `CustomLayout.png` visar en rektangulär streckkod med fyra datakolumner och nio rader. Att skanna bilden med någon PDF417‑läsare returnerar den ursprungliga texten **“Sample Text”**.

![Genererad PDF417 streckkod exempel](generated-pdf417.png){: .center-image alt="Genererad pdf417-streckkod sparad som en PNG-fil"}

## Steg 4: Fullt, körbart exempel

Nedan är en fristående konsolapplikation som sätter ihop alla delarna. Kopiera koden till ett nytt `.csproj`‑projekt och kör det – inga extra filer behövs.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

När programmet körs skrivs en bekräftelsesrad ut och PNG‑filen skapas i en `output`‑undermapp. Bilden kan bäddas in i rapporter, skrivas ut på etiketter eller skickas till en mobil enhet för skanning.

## Vanliga variationer och kantfall

| Scenario | Vad du ska ändra | Varför det är viktigt |
|----------|-------------------|-----------------------|
| **Koda en lång sträng** | Öka `Rows` eller låt biblioteket auto‑beräkna genom att utelämna `Rows`‑tilldelningen | PDF417 kan innehålla upp till 1 850 tecken; otillräckligt antal rader ger avklippning |
| **Högre visuell kvalitet** | Sätt `generator.Parameters.ImageResolution` till 600 DPI | Användbart för utskrift på högupplösta skrivare |
| **Annat bildformat** | Byt `BarCodeImageFormat.Png` mot `Jpeg` eller `Tiff` | JPEG minskar filstorlek; TIFF bevarar förlustfri data för arkivering |
| **Lägg till ett tyst område** | `generator.Parameters.Barcode.XDimension = 2;` (eller justera `Margins`) | Tysta områden förbättrar skanningspålitlighet i bullriga miljöer |
| **Dynamisk text från användarinmatning** | Byt den hårdkodade strängen mot `Console.ReadLine()` | Möjliggör generering i körning baserat på användardata |

### Hur man genererar pdf417-streckkod i ett web‑API

Om du behöver exponera streckkodsgenerering via en ASP.NET Core‑endpoint, returnera bilden som en byte‑array:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Detta kodsnutt svarar på **hur man genererar pdf417-streckkod** i farten utan att skriva till disk, vilket är idealiskt för mikrotjänster eller mobila back‑ends.

## Testa den genererade streckkoden

För att verifiera att streckkoden skapades korrekt:

1. Öppna PNG‑filen i någon bildvisare.  
2. Använd en gratis PDF417‑skannerapp (t.ex. ZXing, PDF417 Decoder) för att skanna bilden.  
3. Bekräfta att den avkodade texten matchar den ursprungliga inmatningen.

Om skannern rapporterar fel, dubbelkolla kolumn‑/radvärden och säkerställ att bildens upplösning är tillräckligt hög för din enhet.

## Slutsats

Du vet nu hur man **genererar pdf417-streckkod** i C# med full kontroll över kolumner, rader och utdataformat. Det kompletta exemplet demonstrerar hela arbetsflödet – från att skapa `BarcodeGenerator` till att spara en PNG‑fil – så att du kan integrera streckkodsskapande i vilket .NET‑projekt som helst. Nästa steg, utforska relaterade ämnen såsom **pdf417-streckkodslayout**‑optimering, inbäddning av streckkoder i PDF‑rapporter eller avkodning av streckkoder på mobila enheter. Att justera felkorrigeringsnivåer och experimentera med olika bildupplösningar hjälper dig finjustera lösningen för ditt specifika användningsfall. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man sparar streckkod i C# – Generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Hur man genererar PDF417‑streckkod – komplett programmeringsguide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}