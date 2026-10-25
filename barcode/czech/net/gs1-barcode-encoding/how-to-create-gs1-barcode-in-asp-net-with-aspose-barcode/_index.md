---
category: general
date: 2026-10-24
description: Naučte se, jak vytvořit GS1 čárový kód v ASP.NET pomocí Aspose.BarCode.
  Krok za krokem průvodce generováním čárového kódu ze řetězce a vykreslením PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: cs
lastmod: 2026-10-24
og_description: Jak vytvořit GS1 čárový kód v ASP.NET pomocí Aspose.BarCode. Postupujte
  podle tohoto tutoriálu, abyste vygenerovali čárový kód ze řetězce, nakonfigurovali
  vizuální nastavení a uložili PNG soubory.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Jak vytvořit GS1 čárový kód v ASP.NET – kompletní průvodce Aspose
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
title: Jak vytvořit GS1 čárový kód v ASP.NET pomocí Aspose.BarCode
url: /cs/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit GS1 čárový kód v ASP.NET s Aspose.BarCode

Pokud potřebujete **jak vytvořit GS1 čárový kód** v aplikaci ASP.NET, tento průvodce vám ukáže přesné kroky. Uvidíte, jak vygenerovat čárový kód ze řetězce, nakonfigurovat jeho vizuální vzhled a uložit výsledek jako PNG obrázek.

Vytváření GS1 čárových kódů nevyžaduje vlastní kódování. Použitím Aspose.BarCode získáte spolehlivé, standardy‑vyhovující řešení, které funguje na .NET 6+ i starších frameworkech. Tento tutoriál pokrývá vše od nastavení projektu až po ověření výstupu, takže můžete kód přímo zkopírovat do svého webového projektu.

## Požadavky

* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)
* .NET 6 SDK (nebo .NET Framework 4.7.2 a vyšší)
* Základní znalost ASP.NET Core nebo ASP.NET Framework
* Licence Aspose.BarCode (bezplatná zkušební verze funguje pro testování)

Žádné další knihovny třetích stran nejsou potřeba, protože Aspose.BarCode zpracovává veškeré kódování a vykreslování interně.

## Krok 1: Vytvořte nový ASP.NET projekt

Otevřete Visual Studio a vytvořte **ASP.NET Core Web App** (zvolte šablonu *Empty*). Pro klasický projekt Web Forms funguje stejný kód v souboru code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Spuštěním projektu by se v prohlížeči mělo zobrazit *GS1 barcode generator is ready.*. Tím se potvrdí, že webový host je funkční.

## Krok 2: Nainstalujte Aspose.BarCode přes NuGet

Otevřete **Package Manager Console** a spusťte:

```powershell
Install-Package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode.Generation`, který obsahuje třídu `BarcodeGenerator`, kterou použijete k **vygenerovat čárový kód ze řetězce**. Příkaz NuGet také aktualizuje soubor projektu s požadovanou referencí.

## Krok 3: Vygenerujte jednoduchý čárový kód ze řetězce

Pro ilustraci základního použití vytvořte pomocnou metodu, která vrací pole bajtů PNG. Tuto metodu lze volat z kontroleru, Razor stránky nebo jakéhokoli endpointu.

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

Nyní můžete z libovolného endpointu zavolat `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` a zapsat výsledné bajty do HTTP odpovědi. To demonstruje vzor **barcode generator asp.net** pro libovolné řetězce.

## Krok 4: Jak vytvořit GS1 čárový kód – příklad Micro PDF417

GS1 čárové kódy obsahují identifikátory aplikací (AI), které přenášejí informace o produktu. Aspose.BarCode podporuje GS1‑kompatibilní variantu Micro PDF417, která je ideální pro kompaktní reprezentaci dat.

### 4.1 Připravte GS1 datový řetězec

GS1 data musí být uzavřena v závorkách s kódem AI. Pro identifikátor produktu (01) a číslo šarže (10) řetězec vypadá takto:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Závorky jsou součástí standardu; Aspose.BarCode je automaticky parsuje.

### 4.2 Vytvořte generátor GS1 Micro PDF417

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

### 4.3 Zveřejněte generátor přes ASP.NET endpoint

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

Navštívením `https://localhost:5001/gs1barcode` nyní získáte streamovaný vygenerovaný PNG. Obrázek odpovídá specifikaci GS1 a soubor je také uložen na disku pro pozdější použití.

## Krok 5: Vykreslování dalších typů čárových kódů

Stejný přístup **create barcode with aspose** funguje i pro jiné symbologie. Níže je rychlý příklad, který vytváří QR kód z URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Můžete zaměnit `EncodeTypes.QR` za `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` nebo jakýkoli jiný podporovaný typ. Vizuální parametry (`XDimension`, `Resolution`, `Color`) jsou konfigurovatelné pomocí objektu `Parameters`.

## Krok 6: Časté problémy a tipy pro nejlepší postupy

| Problém | Proč se to stane | Jak tomu předejít |
|-------|----------------|-----------------|
| **Nesprávné formátování AI** | Chybějící závorky nebo nesprávná délka AI způsobují chyby při kódování. | Vždy sestavujte GS1 řetězec přesně podle specifikace standardu. Použijte pomocnou metodu pro spojování AI. |
| **Příliš mnoho sloupců** | Micro PDF417 podporuje pouze 1‑4 sloupce; nastavení 5 vyvolá výjimku. | Ověřte hodnotu sloupce před přiřazením: `if (columns < 1 || columns > 4) throw …` |
| **Nízké rozlišení obrázku** | Malé hodnoty `XDimension` mohou způsobit, že čárový kód bude na tiskárnách nečitelný. | Pro tiskové čárové kódy zvyšte `Resolution` (např. `generator.Parameters.Image.Resolution = 300`). |
| **Problémy s cestou k souboru na Linuxu** | Pevně zakódované zpětné lomítka selhávají na ne‑Windows hostitelích. | Použijte `Path.Combine` pro tvorbu cest k souborům; zvládá OS‑specifické oddělovače. |
| **Licence není použita** | Bezplatná zkušební verze přidává vodoznak po 30 dnech. | Aplikujte licenci co nejdříve: `new License().SetLicense("Aspose.BarCode.lic");` |

## Krok 7: Ověřte vygenerovaný čárový kód

Po spuštění endpointu otevřete PNG v libovolném prohlížeči obrázků. Pro potvrzení, že GS1 data jsou zakódována správně, můžete použít bezplatný mobilní skener, který podporuje GS1 Micro PDF417 (mnoho aplikací pro skenování čárových kódů tuto symbologii uvádí). Naskenujte obrázek; aplikace by měla vrátit:

```
(01)12345678901234
(10)ABCD
```

Pokud skener hlásí chybu, zkontrolujte formátování AI a počet sloupců.

## Závěr

Nyní víte **jak vytvořit GS1 čárový kód** v prostředí ASP.NET pomocí Aspose.BarCode. Tutoriál pokryl:

* Nastavení ASP.NET projektu a instalace NuGet balíčku Aspose.BarCode.  
* Použití **generate barcode from string** pro obecné čárové kódy.  
* Implementaci **create barcode with aspose** pro vytvoření GS1‑kompatibilního obrázku Micro PDF417.  
* Ukládání obrázku na disk a streamování přes HTTP endpoint.  

Odtud můžete prozkoumat další GS1 symbologie (např. GS1 DataMatrix) nebo integrovat generátor do většího workflow zpracování objednávek. Experimentujte s různými hodnotami `XDimension`, barvami a úrovněmi korekce chyb, aby odpovídaly vaší značce a prostředí skenování.

Šťastné kódování a ať vaše aplikace mluví univerzálním jazykem čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód code 128 s GS1 pomocí Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak vytvořit ITF-14 čárový kód .NET – komplexní tutoriály Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}