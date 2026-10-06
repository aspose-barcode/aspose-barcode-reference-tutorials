---
category: general
date: 2026-09-10
description: Generera PDF417‑streckkod i C# snabbt. Lär dig hur du genererar PDF417
  och hur du ändrar streckkodens storlek med Aspose.BarCode på bara några rader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: sv
lastmod: 2026-09-10
og_description: Generera PDF417‑streckkod i C# omedelbart. Denna handledning visar
  hur du genererar PDF417 och hur du ändrar streckkodens storlek med Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Generera PDF417-streckkod i C# – komplett programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hur man genererar PDF417‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod i C# – steg‑för‑steg‑guide

Om du behöver **generera PDF417‑streckkod** i en .NET‑applikation visar den här guiden exakt hur du gör det. Du får se ett kortfattat, färdigt‑att‑köra‑exempel som skapar en PDF417‑streckkod, låter dig kontrollera dess storlek och sparar resultatet som en PNG‑bild.

Att generera en PDF417‑streckkod är ett vanligt krav för lagersystem, boardingkort och dokumentspårning. I den här handledningen täcker vi också **hur man ändrar streckkodens storlek** så att koden anpassas till olika utskrifts‑ eller skärmvisningsbehov.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+)
* Visual Studio 2022 eller någon C#‑IDE
* **Aspose.BarCode for .NET**‑paketet via NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Grundläggande kunskap om C#‑konsolapplikationer

## Projektuppsättning

1. Skapa ett nytt konsolprojekt:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Lägg till Aspose.BarCode‑referensen (se förutsättningar).  

3. Öppna `Program.cs` och ersätt dess innehåll med hela exemplet nedan.

## Steg 1: Generera PDF417‑streckkod

Det första steget är att skapa en `BarcodeGenerator`‑instans konfigurerad för **PDF417**‑symbologin. Detta objekt är ingångspunkten för alla streckkodsåtgärder.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Varför detta är viktigt* – Enum‑värdet `EncodeTypes.Pdf417` talar om för Aspose.BarCode att använda PDF417‑standarden, medan det andra argumentet tillhandahåller den data som ska kodas. Generatorn innehåller nu ett komplett streckkodsobjekt som du kan anpassa innan du sparar.

## Steg 2: Hur man ändrar streckkodens storlek (modulstorlek)

PDF417‑streckkoder består av små fyrkantiga moduler. Att justera modulstorleken ändrar bildens totala dimensioner utan att förändra den kodade datan.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Varför detta är viktigt* – En större `XDimension` ger en större streckkod som är lämplig för högupplöst utskrift; ett mindre värde är bättre för skärmvisning. Standardvärdet är vanligtvis 1 px, vilket kan se trångt ut på moderna bildskärmar.

## Steg 3: Konfigurera layout – kolumner och rader

PDF417 låter dig definiera antalet kolumner och rader, vilket påverkar både streckkodens form och dess felkorrigeringskapacitet.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Varför detta är viktigt* – Fler kolumner gör streckkoden bredare, medan fler rader gör den högre. Justera dessa värden för att passa det tillgängliga utrymmet i ditt UI eller på den utskrivna etiketten.

## Steg 4: Spara streckkodens bild

Till sist skrivs streckkoden till en fil. Här använder vi PNG eftersom det bevarar skarpa kanter och stödjer transparens.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

När programmet körs skapas `LayoutPdf417.png` i projektets output‑mapp. Bilden kommer att se ut så här:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="generera PDF417‑streckkodsexempel som visar 4 kolumner och 9 rader"}

*Tips*: Om du behöver ett annat bildformat (JPEG, BMP, TIFF), ersätt `BarCodeImageFormat.Png` med det lämpliga enum‑värdet.

## Hur man genererar PDF417 – alternativa datakällor

Koden ovan använder en hårdkodad sträng `"Layout test"`. I verkliga scenarier hämtar du ofta data från en databas, en fil eller användarinmatning.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Resten av stegen (storlek, layout, sparande) förblir oförändrade. Detta demonstrerar **hur man genererar PDF417** från dynamiska källor utan extra komplexitet.

## Vanliga fallgropar och hur man undviker dem

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| Streckkoden blir suddig | `XDimension` är satt för lågt för utdataupplösningen | Öka `XDimension.Pixels` eller spara som ett vektorformat som SVG (`BarCodeImageFormat.Svg`) |
| Texten får inte plats i den valda layouten | För många tecken för de valda raderna/kolumnerna | Minska antalet rader/kolumner eller dela upp datan i flera streckkoder |
| Bildfilen skapades inte | Utdatamappen finns inte eller skrivbehörigheter saknas | Säkerställ att katalogen finns (`Directory.CreateDirectory`) och att appen körs med rätt behörigheter |

## Verifiera streckkoden

Efter att bilden har genererats kan du verifiera den med någon PDF417‑skannerapp (mobiltelefoner har gratis skannrar) eller den inbyggda Aspose.BarCode‑läsaren:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Om resultatet matchar den ursprungliga texten har processen **generera PDF417‑streckkod** lyckats.

## Fullt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera‑och‑klistra in i `Program.cs`. Det innehåller alla using‑direktiv, felhantering och kommentarer.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

När detta program körs skrivs följande ut:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Du har nu en **fullständig, fristående lösning** för att generera PDF417‑streckkoder och kontrollera deras storlek.

## Slutsats

I den här handledningen lärde du dig hur man **genererar PDF417‑streckkod** i C# med Aspose.BarCode, hur man **ändrar streckkodens storlek** genom att justera X‑dimensionen, och hur man konfigurerar kolumner och rader för layoutkontroll. Du såg också hur man verifierar resultatet programatiskt och hur man anpassar koden för dynamisk data.

Nästa steg kan vara att utforska:

* **Hur man genererar PDF417** med justering av felkorrigeringsnivå (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exportera till **vektorformat** (SVG, EPS) för oändlig skalning
* Bädda in streckkoden i ett PDF‑dokument med **Aspose.PDF**

Experimentera med olika modulstorlekar och layoutalternativ för att passa dina specifika UI‑ eller utskriftskrav. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkod med Aspose – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [justera streckkodens storlek – C#‑guide för att generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Hur man sparar streckkod i C# – Generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}