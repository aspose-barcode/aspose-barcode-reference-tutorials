---
category: general
date: 2026-10-24
description: Leer hoe je een GS1‑barcode maakt in ASP.NET met Aspose.BarCode. Stapsgewijze
  handleiding om een barcode te genereren vanuit een string en deze als PNG weer te
  geven.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: nl
lastmod: 2026-10-24
og_description: Hoe maak je een GS1-barcode in ASP.NET met Aspose.BarCode. Volg deze
  tutorial om een barcode te genereren vanuit een string, visuele instellingen te
  configureren en PNG‑bestanden op te slaan.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Hoe maak je een GS1-barcode in ASP.NET – volledige Aspose-gids
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
title: Hoe maak je een GS1-barcode in ASP.NET met Aspose.BarCode
url: /nl/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een GS1 barcode in ASP.NET met Aspose.BarCode

Als je **hoe je een GS1 barcode maakt** in een ASP.NET‑applicatie nodig hebt, laat deze gids je de exacte stappen zien. Je zult zien hoe je een barcode genereert vanuit een string, het uiterlijk configureert en het resultaat opslaat als een PNG‑afbeelding.

Het maken van GS1‑barcodes vereist geen aangepaste coderingslogica. Door Aspose.BarCode te gebruiken krijg je een betrouwbare, aan de normen‑conforme oplossing die werkt op .NET 6+ en eerdere frameworks. Deze tutorial behandelt alles van projectconfiguratie tot het verifiëren van de output, zodat je de code direct kunt kopiëren naar je eigen webproject.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* Visual Studio 2022 (of een IDE die .NET ondersteunt)
* .NET 6 SDK (of .NET Framework 4.7.2 en hoger)
* Basiskennis van ASP.NET Core of ASP.NET Framework
* Een Aspose.BarCode‑licentie (de gratis evaluatie werkt voor testen)

Er zijn geen extra third‑party libraries nodig omdat Aspose.BarCode alle codering en weergave intern afhandelt.

## Stap 1: Maak een nieuw ASP.NET‑project

Open Visual Studio en maak een **ASP.NET Core Web App** (kies *Empty*‑template). Voor een klassiek Web Forms‑project werkt dezelfde code binnen een code‑behind‑bestand.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Het uitvoeren van het project moet *GS1 barcode generator is ready.* in de browser weergeven. Dit bevestigt dat de webhost operationeel is.

## Stap 2: Installeer Aspose.BarCode via NuGet

Open de **Package Manager Console** en voer uit:

```powershell
Install-Package Aspose.BarCode
```

Het pakket voegt de namespace `Aspose.BarCode.Generation` toe, die de `BarcodeGenerator`‑klasse bevat die je zult gebruiken om **barcode from string** te **genereren**. Het NuGet‑commando werkt ook het projectbestand bij met de vereiste referentie.

## Stap 3: Genereer een eenvoudige barcode vanuit een string

Om het basisgebruik te illustreren, maak je een helper‑methode die een PNG‑byte‑array retourneert. Deze methode kan worden aangeroepen vanuit een controller, een Razor‑pagina of elk endpoint.

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

Je kunt nu `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` aanroepen vanaf elk endpoint en de resulterende bytes naar de HTTP‑respons schrijven. Dit demonstreert het **barcode generator asp.net**‑patroon voor willekeurige strings.

## Stap 4: Hoe maak je een GS1 barcode – Micro PDF417‑voorbeeld

GS1‑barcodes bevatten application‑identifiers (AIs) die productinformatie overbrengen. Aspose.BarCode ondersteunt de GS1‑compatibele variant van Micro PDF417, die ideaal is voor compacte datavertegenwoordiging.

### 4.1 Bereid de GS1‑datastream voor

GS1‑data moet worden omgeven door haakjes met de AI‑code. Voor een product‑identifier (01) en een batch‑nummer (10) ziet de string er als volgt uit:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

De haakjes maken deel uit van de standaard; Aspose.BarCode parseert ze automatisch.

### 4.2 Bouw de GS1 Micro PDF417‑generator

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

### 4.3 Maak de generator beschikbaar via een ASP.NET‑endpoint

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

Het bezoeken van `https://localhost:5001/gs1barcode` streamt nu de gegenereerde PNG. De afbeelding voldoet aan de GS1‑specificatie, en het bestand wordt ook op schijf opgeslagen voor later gebruik.

## Stap 5: Renderen van extra barcode‑typen

Dezelfde **create barcode with aspose**‑aanpak werkt voor andere symbologieën. Hieronder een snel voorbeeld dat een QR‑code maakt vanuit een URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Je kunt `EncodeTypes.QR` vervangen door `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` of een ander ondersteund type. De visuele parameters (`XDimension`, `Resolution`, `Color`) zijn configureerbaar via het `Parameters`‑object.

## Stap 6: Veelvoorkomende valkuilen en best‑practice‑tips

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Incorrect AI formatting** | Missing parentheses or wrong AI length causes encoding errors. | Always build the GS1 string exactly as the standard specifies. Use a helper method to concatenate AIs. |
| **Too many columns** | Micro PDF417 supports only 1‑4 columns; setting 5 throws an exception. | Validate the column value before assigning: `if (columns < 1 || columns > 4) throw …` |
| **Low image resolution** | Small `XDimension` values can make the barcode unreadable on printers. | For print‑ready barcodes, increase `Resolution` (e.g., `generator.Parameters.Image.Resolution = 300`). |
| **File path issues on Linux** | Hard‑coded backslashes break on non‑Windows hosts. | Use `Path.Combine` to build file paths; it handles OS‑specific separators. |
| **License not applied** | The free evaluation adds a watermark after 30 days. | Apply your license early: `new License().SetLicense("Aspose.BarCode.lic");` |

## Stap 7: Verifieer de gegenereerde barcode

Nadat je het endpoint hebt uitgevoerd, open je de PNG in een willekeurige afbeeldingsviewer. Om te bevestigen dat de GS1‑data correct is gecodeerd, kun je een gratis mobiele scanner gebruiken die GS1 Micro PDF417 ondersteunt (veel barcode‑scanner‑apps vermelden deze symbologie). Scan de afbeelding; de app zou moeten teruggeven:

```
(01)12345678901234
(10)ABCD
```

Als de scanner een fout meldt, controleer dan de AI‑formattering en het aantal kolommen opnieuw.

## Conclusie

Je weet nu **hoe je een GS1 barcode maakt** in een ASP.NET‑omgeving met Aspose.BarCode. De tutorial behandelde:

* Het opzetten van een ASP.NET‑project en het installeren van het Aspose.BarCode NuGet‑pakket.  
* Het gebruik van **generate barcode from string** voor generieke barcodes.  
* Het implementeren van **create barcode with aspose** om een GS1‑compatibele Micro PDF417‑afbeelding te produceren.  
* Het opslaan van de afbeelding op schijf en het streamen ervan via een HTTP‑endpoint.  

Vanaf hier kun je andere GS1‑symbologieën verkennen (bijv. GS1 DataMatrix) of de generator integreren in een grotere order‑verwerkingsworkflow. Experimenteer met verschillende `XDimension`‑waarden, kleuren en fout‑correctieniveaus om aan je branding en scan‑omgeving te voldoen.

Happy coding, and let your applications speak the universal language of barcodes!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to create code 128 barcode with GS1 using Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}