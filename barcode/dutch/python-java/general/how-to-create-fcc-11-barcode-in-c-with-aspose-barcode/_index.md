---
category: general
date: 2026-08-22
description: Maak een FCC 11‑barcode in C# met Aspose.BarCode. Leer stap‑voor‑stap
  de code, configureer de afmetingen en genereer PNG‑afbeeldingen voor Australia Post.
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
language: nl
lastmod: 2026-08-22
og_description: Maak een FCC 11‑barcode in C# met Aspose.BarCode. Volg deze beknopte
  tutorial om PNG‑barcodes voor Australia Post te genereren, inclusief de FCC 59‑
  en FCC 62‑varianten.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Maak FCC 11‑barcode in C# – volledige Aspose.BarCode‑gids
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
title: Hoe maak je een FCC 11 barcode in C# met Aspose.BarCode
url: /nl/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een FCC 11 barcode te maken in C# met Aspose.BarCode

Als je een **FCC 11 barcode** moet **maken** in een .NET‑applicatie, laat deze gids je de exacte code zien die nodig is. Je ziet hoe je de afmetingen van de barcode configureert, de juiste coderingstabel kiest en het resultaat opslaat als een PNG‑bestand.

Het genereren van Australia Post‑barcodes is een veelvoorkomende eis voor logistiek, mailsystemen en voorraadtracking. Deze tutorial behandelt het FCC 11‑formaat en laat ook zien hoe je FCC 59‑ en FCC 62‑barcodes kunt produceren met verschillende coderingstabellen, zodat je hetzelfde patroon kunt hergebruiken voor andere postdiensten.

## Wat je nodig hebt

Voordat je begint, zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑compatibele IDE)  
* Een geldige licentie voor **Aspose.BarCode for .NET** – de community‑edition werkt voor evaluatie  
* Schrijfrechten op een map waar de PNG‑bestanden worden opgeslagen  

Deze voorwaarden garanderen dat de code compileert en draait zonder extra configuratie.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open een terminal in de projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van de bibliotheek toe aan je projectbestand. Het pakket bevat de `BarcodeGenerator`‑klasse die door de hele tutorial wordt gebruikt.

## Stap 2: Definieer de uitvoermap

Maak een map aan waar de gegenereerde afbeeldingen worden opgeslagen. Het pad kan absoluut of relatief ten opzichte van het uitvoerbare bestand zijn.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` zorgt ervoor dat de map bestaat, waardoor runtime‑fouten worden voorkomen wanneer de `Save`‑methode het bestand schrijft.

## Stap 3: Genereer de FCC 11 barcode

Het FCC 11‑formaat is de standaardcodering voor Australia Post‑postbarcodes. De volgende code maakt een barcode die de numerieke tekenreeks `1101234567` codeert.

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

**Waarom dit werkt:**  
* `EncodeTypes.AustraliaPost` vertelt de bibliotheek om de Australia Post‑coderingregels toe te passen.  
* De data‑reeks `1101234567` volgt de FCC 11‑specificatie: de eerste twee cijfers (`11`) identificeren het formaat, gevolgd door een 7‑cijferige klantreferentie.  
* `XDimension` en `BarHeight` bepalen de grootte van de afgedrukte barcode, wat belangrijk is voor de leesbaarheid door scanners.  

Na het uitvoeren van het programma vind je `PostalAustraliaPostFCC11.png` in de map `Barcodes`. De afbeelding ziet er als volgt uit:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Stap 4: Maak extra Australia Post‑barcodes (optioneel)

Hoewel het primaire doel is om een **FCC 11 barcode** te **maken**, heb je vaak FCC 59‑ of FCC 62‑barcodes nodig voor verschillende postklassen. De code hieronder hergebruikt dezelfde `BarcodeGenerator`‑instantie, waarbij alleen de data‑reeks en de optionele coderingstabel worden aangepast.

### 4.1 FCC 59 met N‑Table‑codering

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

### 4.2 FCC 62 met N‑Table‑codering

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

### 4.3 FCC 62 met C‑Table‑codering

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

### 4.4 FCC 62 met andere codering

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

Alle vier de afbeeldingen worden naast elkaar opgeslagen in dezelfde map, waardoor het eenvoudig is om visuele verschillen te vergelijken.

## Stap 5: Begrijp de coderingstabellen

Australia Post definieert drie coderingstabellen:

* **N‑Table** – interpreteert numerieke klantinformatie. Gebruik deze wanneer de payload alleen cijfers bevat.  
* **C‑Table** – ondersteunt alfanumerieke tekens, nuttig voor referentienummers die letters bevatten.  
* **Other** – een fallback voor aangepaste of uitgebreide dataformaten.

Het kiezen van de juiste tabel zorgt ervoor dat de barcodescanner de informatie exact decodeert zoals bedoeld. Als je de eigenschap `AustralianPostEncodingTable` weglaat, gebruikt de bibliotheek standaard de N‑Table, waardoor niet‑numerieke tekens mogelijk worden afgekapt.

## Tips, randgevallen en veelvoorkomende valkuilen

| Situatie | Aanbevolen aanpak |
|-----------|----------------------|
| Data‑reeks is korter dan vereist | Vul het numerieke gedeelte aan met voorloopnullen om aan de FCC‑specificatie te voldoen. |
| Barcode is onscherp bij afdrukken | Verhoog `XDimension` naar 5 of 6 pixels en controleer de DPI‑instellingen van de printer. |
| Scanner geeft “invalid format” terug | Controleer of de juiste coderingstabel (N‑Table, C‑Table, Other) overeenkomt met de data‑payload. |
| Uitvoeren op Linux zonder GUI | Zorg dat het `System.Drawing.Common`‑pakket is gerefereerd, of gebruik de `Save`‑methode met `BarCodeImageFormat.Png` die geen weergave‑context vereist. |
| Een ander afbeeldingsformaat nodig | Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Tiff` zoals vereist. |

Deze praktische tips komen voort uit real‑world implementaties van post‑barcode‑oplossingen.

## Volledig uitvoerbaar voorbeeld

Hieronder staat een zelfstandig programma dat je kunt kopiëren naar een nieuw console‑project (`dotnet new console`) en uitvoeren zonder aanpassingen.



## Wat je hierna moet leren

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}