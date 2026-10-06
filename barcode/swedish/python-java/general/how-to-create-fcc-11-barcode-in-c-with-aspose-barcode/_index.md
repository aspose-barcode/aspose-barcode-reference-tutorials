---
category: general
date: 2026-08-22
description: Skapa FCC 11‑streckkod i C# med Aspose.BarCode. Lär dig steg‑för‑steg‑kod,
  konfigurera dimensioner och generera PNG‑bilder för Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: sv
lastmod: 2026-08-22
og_description: Skapa FCC 11‑streckkod i C# med Aspose.BarCode. Följ den här korta
  handledningen för att generera PNG‑streckkoder för Australia Post, inklusive varianterna
  FCC 59 och FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Skapa FCC 11-streckkod i C# – komplett guide för Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Hur du skapar FCC 11‑streckkod i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du FCC 11‑streckkod i C# med Aspose.BarCode

Om du behöver **skapa FCC 11‑streckkod** i en .NET‑applikation visar den här guiden exakt vilken kod som krävs. Du får se hur du konfigurerar streckkodens dimensioner, väljer rätt kodningstabell och sparar resultatet som en PNG‑fil.

Att generera Australia Post‑streckkoder är ett vanligt krav för logistik, posthanteringssystem och lagerstyrning. Denna handledning täcker FCC 11‑formatet och visar även hur du producerar FCC 59‑ och FCC 62‑streckkoder med olika kodningstabeller, så att du kan återanvända samma mönster för andra posttjänster.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon annan C#‑kompatibel IDE)  
* En giltig licens för **Aspose.BarCode for .NET** – community‑editionen fungerar för utvärdering  
* Skrivrättigheter till en mapp där PNG‑filerna ska sparas  

Dessa förutsättningar garanterar att koden kompileras och körs utan ytterligare konfiguration.

## Steg 1: Installera Aspose.BarCode‑paketet via NuGet

Öppna en terminal i projektmappen och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av biblioteket i din projektfil. Paketet innehåller klassen `BarcodeGenerator` som används genom hela handledningen.

## Steg 2: Definiera utdatamappen

Skapa en mapp där de genererade bilderna ska lagras. Sökvägen kan vara absolut eller relativ till den körbara filen.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` säkerställer att mappen finns, vilket förhindrar körfel när `Save`‑metoden skriver filen.

## Steg 3: Generera FCC 11‑streckkoden

FCC 11‑formatet är standardkodningen för Australia Posts poststreckkoder. Följande kod skapar en streckkod som kodar den numeriska strängen `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Varför detta fungerar:**  
* `EncodeTypes.AustraliaPost` talar om för biblioteket att använda Australia Post‑kodningsreglerna.  
* Datatsträngen `1101234567` följer FCC 11‑specifikationen: de två första siffrorna (`11`) identifierar formatet, följt av en 7‑siffrig kundreferens.  
* `XDimension` och `BarHeight` styr storleken på den utskrivna streckkoden, vilket är viktigt för skannerns läsbarhet.  

När programmet har körts hittar du `PostalAustraliaPostFCC11.png` i mappen `Barcodes`. Bilden ser ut så här:

![exempel på att skapa fcc 11 streckkod](https://example.com/fcc11.png "FCC 11 streckkod genererad av Aspose.BarCode")

## Steg 4: Skapa ytterligare Australia Post‑streckkoder (valfritt)

Medan huvudmålet är att **skapa FCC 11‑streckkod**, behöver du ofta FCC 59‑ eller FCC 62‑streckkoder för olika postklasser. Koden nedan återanvänder samma `BarcodeGenerator`‑instans och ändrar bara datatsträngen samt den valfria kodningstabellen.

### 4.1 FCC 59 med N‑Table‑kodning

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 med N‑Table‑kodning

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 med C‑Table‑kodning

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 med annan kodning

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Alla fyra bilder sparas sida‑vid‑sida i samma mapp, vilket gör det enkelt att jämföra visuella skillnader.

## Steg 5: Förstå kodningstabellerna

Australia Post definierar tre kodningstabeller:

* **N‑Table** – tolkar numerisk kundinformation. Använd den när payloaden endast innehåller siffror.  
* **C‑Table** – stöder alfanumeriska tecken, användbart för referensnummer som innehåller bokstäver.  
* **Other** – en reserv för anpassade eller utökade dataformat.

Att välja rätt tabell säkerställer att streckkodsläsaren avkodar informationen exakt som avsett. Om du utelämnar egenskapen `AustralianPostEncodingTable` använder biblioteket som standard N‑Table, vilket kan trunkera icke‑numeriska tecken.

## Tips, kantfall och vanliga fallgropar

| Situation | Rekommenderad åtgärd |
|-----------|----------------------|
| Datatsträngens längd är kortare än vad som krävs | Fyll på den numeriska delen med inledande nollor för att uppfylla FCC‑specifikationen. |
| Streckkoden blir suddig vid utskrift | Öka `XDimension` till 5 eller 6 pixlar och kontrollera skrivarens DPI‑inställningar. |
| Skannern returnerar “invalid format” | Verifiera att rätt kodningstabell (N‑Table, C‑Table, Other) matchar data‑payloaden. |
| Kör på Linux utan GUI | Säkerställ att paketet `System.Drawing.Common` refereras, eller använd `Save`‑metoden med `BarCodeImageFormat.Png` som inte kräver en display‑kontext. |
| Behöver ett annat bildformat | Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Tiff` efter behov. |

Dessa praktiska tips kommer från verkliga implementationer av post‑streckkodslösningar.

## Komplett körbart exempel

Nedan finns ett fristående program som du kan kopiera in i ett nytt konsolprojekt (`dotnet new console`) och köra utan ändringar.



## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod java – Australia Post Barcode med Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Skapa endimensionell Databar GS1‑kodning med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Hur man skapar tyst zon‑inställningar .NET för Code 16K med Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}