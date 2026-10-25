---
category: general
date: 2026-10-24
description: Lär dig hur du skapar GS1‑streckkod i ASP.NET med Aspose.BarCode. Steg‑för‑steg‑guide
  för att generera streckkod från en sträng och rendera PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: sv
lastmod: 2026-10-24
og_description: Hur man skapar GS1-streckkod i ASP.NET med Aspose.BarCode. Följ den
  här handledningen för att generera streckkod från en sträng, konfigurera visuella
  inställningar och spara PNG-filer.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Hur man skapar GS1-streckkod i ASP.NET – komplett Aspose-guide
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Hur man skapar GS1-streckkod i ASP.NET med Aspose.BarCode
url: /sv/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar GS1‑streckkod i ASP.NET med Aspose.BarCode

Om du behöver **hur man skapar GS1‑streckkod** i en ASP.NET‑applikation, visar den här guiden de exakta stegen. Du kommer att se hur du genererar en streckkod från en sträng, konfigurerar det visuella utseendet och sparar resultatet som en PNG‑bild.

Att skapa GS1‑streckkoder kräver ingen anpassad kodningslogik. Genom att använda Aspose.BarCode får du en pålitlig, standard‑kompatibel lösning som fungerar på .NET 6+ och tidigare ramverk. Denna handledning täcker allt från projektuppsättning till verifiering av resultatet, så att du kan kopiera koden direkt in i ditt eget webbprojekt.

## Förutsättningar

* Visual Studio 2022 (eller någon IDE som stöder .NET)
* .NET 6 SDK (eller .NET Framework 4.7.2 och högre)
* Grundläggande kunskap om ASP.NET Core eller ASP.NET Framework
* En Aspose.BarCode‑licens (den kostnadsfria utvärderingen fungerar för testning)

Inga ytterligare tredjepartsbibliotek krävs eftersom Aspose.BarCode hanterar all kodning och rendering internt.

## Steg 1: Skapa ett nytt ASP.NET‑projekt

Öppna Visual Studio och skapa en **ASP.NET Core Web App** (välj *Empty*-mall). För ett klassiskt Web Forms‑projekt fungerar samma kod i en code‑behind‑fil.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

När projektet körs bör *GS1 barcode generator is ready.* visas i webbläsaren. Detta bekräftar att webbhosten är i drift.

## Steg 2: Installera Aspose.BarCode via NuGet

Öppna **Package Manager Console** och kör:

```powershell
Install-Package Aspose.BarCode
```

Paketet lägger till namnutrymmet `Aspose.BarCode.Generation`, som innehåller klassen `BarcodeGenerator` som du kommer att använda för att **generera streckkod från sträng**. NuGet‑kommandot uppdaterar också projektfilen med den nödvändiga referensen.

## Steg 3: Generera en enkel streckkod från en sträng

För att illustrera grundläggande användning, skapa en hjälpfunktion som returnerar en PNG‑byte‑array. Denna metod kan anropas från en controller, en Razor‑sida eller någon endpoint.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Du kan nu anropa `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` från någon endpoint och skriva de resulterande bytena till HTTP‑svaret. Detta demonstrerar **barcode generator asp.net**‑mönstret för godtyckliga strängar.

## Steg 4: Hur man skapar GS1‑streckkod – Micro PDF417‑exempel

GS1‑streckkoder inbäddar applikationsidentifierare (AIs) som förmedlar produktinformation. Aspose.BarCode stöder den GS1‑kompatibla varianten av Micro PDF417, vilket är idealiskt för kompakt datarapresentation.

### 4.1 Förbered GS1‑datatsträngen

GS1‑data måste omslutas av parenteser med AI‑koden. För en produktidentifierare (01) och ett partinummer (10) ser strängen ut så här:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Parenteserna är en del av standarden; Aspose.BarCode tolkar dem automatiskt.

### 4.2 Bygg GS1 Micro PDF417‑generatorn

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Exponera generatorn via en ASP.NET‑endpoint

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Att besöka `https://localhost:5001/gs1barcode` strömmar nu den genererade PNG‑filen. Bilden följer GS1‑specifikationen, och filen sparas också på disk för senare användning.

## Steg 5: Rendera ytterligare streckkodstyper

Samma **create barcode with aspose**‑metod fungerar för andra symboler. Nedan är ett snabbt exempel som skapar en QR‑kod från en URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Du kan byta `EncodeTypes.QR` mot `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` eller någon annan stödjande typ. De visuella parametrarna (`XDimension`, `Resolution`, `Color`) kan konfigureras via `Parameters`‑objektet.

## Steg 6: Vanliga fallgropar och bästa praxis‑tips

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Felaktig AI‑formatering** | Saknade parenteser eller fel AI‑längd orsakar kodningsfel. | Bygg alltid GS1‑strängen exakt enligt standarden. Använd en hjälpfunktion för att sammanfoga AIs. |
| **För många kolumner** | Micro PDF417 stöder endast 1‑4 kolumner; att sätta 5 ger ett undantag. | Validera kolumnvärdet innan du tilldelar: `if (columns < 1 || columns > 4) throw …` |
| **Låg bildupplösning** | Små `XDimension`‑värden kan göra streckkoden oläslig på skrivare. | För utskriftsklara streckkoder, öka `Resolution` (t.ex. `generator.Parameters.Image.Resolution = 300`). |
| **Filvägsproblem på Linux** | Hårdkodade bakåtsnedstreck fungerar inte på icke‑Windows‑värdar. | Använd `Path.Combine` för att bygga filvägar; det hanterar OS‑specifika separatorer. |
| **Licens ej tillämpad** | Den kostnadsfria utvärderingen lägger till ett vattenmärke efter 30 dagar. | Applicera din licens tidigt: `new License().SetLicense("Aspose.BarCode.lic");` |

## Steg 7: Verifiera den genererade streckkoden

Efter att du har kört endpointen, öppna PNG‑filen i någon bildvisare. För att bekräfta att GS1‑data är korrekt kodad kan du använda en gratis mobilskanner som stöder GS1 Micro PDF417 (många streckkodsskanner‑appar listar denna symbol). Skanna bilden; appen bör returnera:

```
(01)12345678901234
(10)ABCD
```

Om skannern rapporterar ett fel, dubbelkolla AI‑formateringen och antalet kolumner.

## Slutsats

Du vet nu **how to create GS1 barcode** i en ASP.NET‑miljö med Aspose.BarCode. Handledningen täckte:

* Att sätta upp ett ASP.NET‑projekt och installera Aspose.BarCode‑NuGet‑paketet.  
* Använda **generate barcode from string** för generiska streckkoder.  
* Implementera **create barcode with aspose** för att producera en GS1‑kompatibel Micro PDF417‑bild.  
* Spara bilden på disk och strömma den via en HTTP‑endpoint.  

Härifrån kan du utforska andra GS1‑symboler (t.ex. GS1 DataMatrix) eller integrera generatorn i ett större order‑hanteringsflöde. Experimentera med olika `XDimension`‑värden, färger och felkorrigeringsnivåer för att matcha ditt varumärke och skannermiljö.

Lycka till med kodningen, och låt dina applikationer tala det universella språket för streckkoder!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar code 128‑streckkod med GS1 med Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Hur man skapar Barcode Quiet Zone för ITF-14 med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hur man skapar ITF-14‑streckkod .NET – Omfattande Aspose.BarCode‑handledningar](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}