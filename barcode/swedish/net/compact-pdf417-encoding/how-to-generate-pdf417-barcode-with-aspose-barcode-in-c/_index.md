---
category: general
date: 2026-10-24
description: Lär dig hur du genererar PDF417‑streckkod med Aspose.BarCode i C# med
  kompakta inställningar och kontroll av streckkodens X‑dimension.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: sv
lastmod: 2026-10-24
og_description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Följ den här kompletta
  guiden för att skapa kompakta PDF417‑bilder, kontrollera XDimension och ange kolumner.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Generera PDF417‑streckkod med Aspose.BarCode – C# steg för steg
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Hur man genererar PDF417-streckkod med Aspose.BarCode i C#
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417 streckkod med Aspose.BarCode i C#

Om du behöver **generera PDF417 streckkod** i en .NET-applikation, visar den här guiden en komplett, färdig‑att‑köra lösning. Du kommer att se hur Aspose.BarCode gör processen enkel samtidigt som du får fin‑granulär kontroll över **compact PDF417**, **barcode XDimension**, och **PDF417 columns**.

Att skapa en streckkod är ett vanligt krav för lagersystem, biljettplattformar och dokumentarbetsflöden. I slutet av den här tutorialen har du ett självständigt C#-program som producerar en skarp PNG-bild av en PDF417 streckkod, redo att bäddas in i någon UI eller skrivas ut på en etikett.

## Vad du behöver

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.6+)
- Visual Studio 2022 eller någon C#-redigerare du föredrar
- En giltig Aspose.BarCode för .NET-licens (gratis provversion fungerar för utveckling)
- Grundläggande kunskap om C#-syntax

> **Pro tip:** Om du utvärderar Aspose.BarCode, ladda ner provversionen från den officiella webbplatsen och lägg till NuGet‑paketet `Aspose.BarCode` i ditt projekt. Provversionen lägger till ett litet vattenstämpel på den genererade bilden, som försvinner när du applicerar en licens.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Öppna en terminal i din lösningsmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot hämtar den senaste stabila versionen (från och med oktober 2026, version 23.12). Att lägga till paketet återställer `Aspose.BarCode.Generation`‑namnrymden som du kommer att använda för att **generera PDF417 streckkod**‑bilder.

## Steg 2: Skapa ett grundläggande C#-konsolprojekt

Om du ännu inte har ett projekt, skapa ett:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Öppna `Program.cs`. Skelettet innehåller redan en `Main`‑metod där vi kommer att placera koden för streckkodsgenerering.

## Steg 3: Initiera streckkodsgeneratorn

Först, importera den nödvändiga namnrymden:

```csharp
using Aspose.BarCode.Generation;
```

Sedan, inuti `Main`, skapa en instans av `BarcodeGenerator` med PDF417‑symbologi och den data du vill koda:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Strängen innehåller Unicode‑tecken för att demonstrera att Aspose.BarCode korrekt hanterar icke‑ASCII‑inmatning. Om du bara behöver ASCII, ersätt texten med en vanlig sträng.

## Steg 4: Justera streckkodens XDimension (modulstorlek)

**barcode XDimension** bestämmer bredden på den minsta stapeln (modulen). Att sätta den i pixlar ger dig pixel‑perfekt kontroll över den slutliga bildstorleken:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på `2` pixlar ger en kompakt bild utan att kompromissa med skanningspålitlighet. Öka värdet för större streckkoder eller minska det för mycket täta layouter.

## Steg 5: Konfigurera compact PDF417‑alternativ

Två PDF417‑specifika inställningar påverkar den visuella fotavtrycket kraftigt:

| Inställning | Betydelse | Typiskt värde för kompakt utdata |
|-------------|-----------|-----------------------------------|
| `Columns` | Antal datakolumner | `3` |
| `Truncate` (compact mode) | Utelämnar den högra tysta zonen och minskar antalet rader | `true` |

Applicera dem på följande sätt:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Genom att använda **PDF417 columns** satt till `3` tillsammans med `Truncate = true` skapas en *compact PDF417* streckkod som passar bra på en standardetikett samtidigt som den fortfarande är läsbar av de flesta skannrar.

## Steg 6: Spara streckkodsbilden

Slutligen, skriv streckkoden till disk. Exemplet sparar en PNG, men Aspose.BarCode stödjer även BMP, JPEG, GIF, TIFF och SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png`‑konstanten instruerar biblioteket att producera en förlustfri PNG, vilket är idealiskt för vidare bearbetning eller utskrift.

## Fullständig, körbar källkod

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

När programmet körs skapas `CompactPdf417.png` i projektets rotmapp. Öppna filen med någon bildvisare; du kommer att se en kompakt PDF417 streckkod som kodar strängen *Åspóse.Barcóde©*.

![Skärmdump av genererad PDF417 streckkod med Aspose.BarCode](placeholder-image.png "Genererad PDF417 streckkod")

*Bildens alt‑text: Skärmdump av genererad PDF417 streckkod med Aspose.BarCode* – denna alt‑text innehåller huvudnyckelordet för tillgänglighet och SEO.

## Verifiera resultatet

1. Öppna PNG‑filen. Streckkoden bör bestå av tre vertikala datakolumner med en kompakt layout (ingen extra tyst zon på högra sidan).
2. Skanna bilden med en smartphone‑streckkodsläsare som stödjer PDF417. Den avkodade texten måste matcha den ursprungliga inmatningssträngen.
3. Om skannern misslyckas, försök öka `XDimension.Pixels` till `3` eller `4`. Större moduler förbättrar läsbarheten på lågupplösta enheter.

## Vanliga variationer och kantfall

### 1. Ändra bildformatet

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG är vektorbaserat, vilket håller streckkoden skarp på alla zoomnivåer—användbart för webbsidor.

### 2. Koda stora mängder data

PDF417 kan lagra upp till ~1,1 KB text. När payloaden överstiger kapaciteten för tre kolumner lägger biblioteket automatiskt till rader. För att hålla streckkoden kompakt kan du:

- Minska datalängden (t.ex. använd en identifierare istället för ett helt meddelande)
- Öka antalet **PDF417 columns** (t.ex. `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Använda en licens för att ta bort provversionens vattenstämpel

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Placera licensfilen bredvid den körbara filen. Efter licensiering innehåller den genererade bilden ingen vattenstämpel.

### 4. Hantera undantag

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Typiska fel inkluderar otillräckliga skrivbehörigheter eller ett bildformat som inte stöds.

## Varför inställningarna är viktiga

- **barcode XDimension** – Styr den visuella vikten på varje stapel. För liten gör streckkoden oläslig; för stor slösar utrymme.
- **PDF417 columns** – Färre kolumner ger en smalare streckkod men ökar antalet rader


## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417 streckkod med Aspose – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generera PDF417 streckkod med kompakta inställningar i C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Hur man sparar streckkod och genererar PDF417 med Aspose i C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}