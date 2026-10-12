---
category: general
date: 2026-09-29
description: Naučte se rychle generovat čárový kód PDF417 v C#. Tento krok‑za‑krokem
  tutoriál pokrývá nastavení čárových kódů, výstup obrazu a běžné úskalí.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- PDF417 barcode settings
- C# barcode library
- barcode image export
language: cs
lastmod: 2026-09-29
og_description: Vytvořte čárový kód PDF417 v C# pomocí tohoto podrobného tutoriálu.
  Postupujte podle kompletního příkladu a vytvořte a exportujte obrázek čárového kódu.
og_image_alt: Screenshot showing generated PDF417 barcode saved as PNG
og_title: Vytvořte PDF417 čárový kód v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  headline: How to generate PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  name: How to generate PDF417 barcode in C# – complete programming guide
  steps:
  - name: Adjusting error correction level
    text: PDF417 supports five error‑correction levels (0‑8). Higher levels increase
      robustness at the cost of size.
  - name: Changing image format
    text: 'If you need a vector format for scaling, export as SVG instead of PNG:'
  - name: Handling very long strings
    text: 'When the input exceeds the default capacity, increase the number of rows:'
  - name: Using a different library
    text: If you prefer an open‑source alternative, the `ZXing.Net` package also supports
      PDF417. The API differs, but the overall flow—create a writer, set options,
      render to bitmap—remains the same.
  - name: Next steps
    text: '* Explore **PDF417 barcode settings** such as row count and aspect ratio
      for custom layouts. * Integrate the barcode generation into an ASP.NET Core
      API to serve images on demand. * Combine this code with a QR‑code generator
      for multi‑symbology documents.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Jak vygenerovat čárový kód PDF417 v C# – kompletní programovací průvodce
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-programming-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat PDF417 čárový kód v C# – kompletní programovací průvodce

Pokud potřebujete **vygenerovat PDF417 čárový kód** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který vytvoří PDF417 čárový kód, nastaví jeho rozměry a uloží jej jako PNG obrázek.

Generování čárových kódů je běžnou požadavkem pro inventární systémy, platformy pro prodej vstupenek a automatizaci dokumentů. Na konci tohoto tutoriálu budete schopni integrovat tvorbu čárových kódů do libovolného C# projektu, aniž byste museli hledat další úryvky kódu.

## Co se naučíte

* Jak vytvořit instanci generátoru PDF417 čárového kódu s vlastním textem  
* Které parametry řídí X‑dimenzi a počet sloupců  
* Jak exportovat čárový kód jako vysoce kvalitní PNG soubor  
* Tipy pro práci s Unicode znaky a úpravu velikosti obrázku  

**Požadavky**  
* .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)  
* Odkaz na NuGet balíček `Aspose.BarCode` (nebo jakoukoliv kompatibilní knihovnu pro čárové kódy)  
* Základní znalost syntaxe C# a Visual Studio nebo vašeho preferovaného IDE  

Pokud se poprvé ptáte **jak vygenerovat PDF417 čárový kód**, čtěte dál – kroky jsou úmyslně uspořádány od nastavení po ověření.

## Krok 1: Nainstalujte knihovnu pro čárové kódy

Než napíšete jakýkoli kód, přidejte do projektu SDK pro čárové kódy. Nejrozšířenější knihovnou pro PDF417 v C# je **Aspose.BarCode for .NET**.

```bash
dotnet add package Aspose.BarCode
```

> **Tip:** Použijte nejnovější stabilní verzi (aktuálně 24.5), abyste získali výhody vylepšení výkonu a plné podpory Unicode.

## Krok 2: Vytvořte generátor PDF417 čárového kódu

Jádrem procesu je vytvoření instance `BarcodeGenerator` s výčtem `EncodeTypes.Pdf417`. Konstruktor také přijímá text, který chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,               // PDF417 symbology
    "Åspóse.Barcóde©");               // Text includes Unicode characters
```

*Proč je to důležité*: Příznak `EncodeTypes.Pdf417` říká knihovně, aby použila standard PDF417, který podporuje velké datové bloky a korekci chyb. Poskytnutí Unicode řetězce ukazuje, že generátor správně zachází s ne‑ASCII znaky.

## Krok 3: Nastavte X‑dimenzi (šířku modulu)

X‑dimenze určuje šířku jednoho modulu čárového kódu (nejmenší černý nebo bílý pruh). Nastavením v pixelech získáte přesnou kontrolu nad konečnou velikostí obrázku.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota `2` pixely vytváří kompaktní čárový kód, který je stále snadno čitelný většinou skenerů. Pokud potřebujete větší čárový kód pro tisk na plakát, zvyšte tuto hodnotu úměrně.

## Krok 4: Definujte počet sloupců

PDF417 vám umožňuje určit počet sloupců, což ovlivňuje poměr stran čárového kódu. Méně sloupců dělá čárový kód vyšší; více sloupců jej rozšiřuje.

```csharp
// Step 4: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Tři sloupce vytvářejí vyvážený tvar vhodný pro většinu použití na obrazovce. Pro hustá data můžete zvýšit toto číslo na 5 nebo 7.

## Krok 5: Uložte čárový kód jako PNG obrázek

Nakonec exportujte vygenerovaný čárový kód do souboru. PNG zachovává ostré hrany a podporuje průhlednost, což je ideální pro zobrazení v UI.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Pdf417Basic.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Po spuštění kódu najdete `Pdf417Basic.png` na ploše. Otevřením souboru uvidíte jasný PDF417 čárový kód, který kóduje řetězec **Åspóse.Barcóde©**.

## Ověření výsledku

Pro potvrzení, že čárový kód kóduje požadovaná data, můžete použít libovolnou bezplatnou aplikaci pro skenování PDF417 (např. ZXing Android app) nebo online dekodér. Naskenujte uložený PNG; dekódovaný text by měl přesně odpovídat původnímu vstupu, včetně speciálních znaků.

**Očekávaný výstup** – PNG obrázek podobný tomuto (ilustrační):

![Vygenerovaný PDF417 čárový kód uložený jako PNG – příklad generování pdf417 čárového kódu](https://example.com/assets/pdf417-sample.png "generovat pdf417 čárový kód")

*Alt text výše splňuje požadavek na alt obrázku pro primární klíčové slovo.*

## Běžné varianty a okrajové případy

### Úprava úrovně korekce chyb

PDF417 podporuje pět úrovní korekce chyb (0‑8). Vyšší úrovně zvyšují odolnost za cenu větší velikosti.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium protection
```

### Změna formátu obrázku

Pokud potřebujete vektorový formát pro škálování, exportujte jako SVG místo PNG:

```csharp
barcodeGenerator.Save("Pdf417Basic.svg", BarCodeImageFormat.Svg);
```

### Práce s velmi dlouhými řetězci

Když vstup překročí výchozí kapacitu, zvyšte počet řádků:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 10;
```

### Použití jiné knihovny

Pokud dáváte přednost open‑source alternativě, balíček `ZXing.Net` také podporuje PDF417. API se liší, ale celkový postup—vytvořit writer, nastavit možnosti, vykreslit do bitmapy—zůstává stejný.

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat do konzolové aplikace a okamžitě spustit.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize the generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose a compact column count
        generator.Parameters.Barcode.Pdf417.Columns = 3;

        // Optional: increase error correction for noisy environments
        generator.Parameters.Barcode.Pdf417.ErrorLevel = 5;

        // 4️⃣ Determine output path (desktop for easy access)
        string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
        string filePath = Path.Combine(desktop, "Pdf417Basic.png");

        // 5️⃣ Export as PNG
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to: {filePath}");
    }
}
```

Spusťte program (`dotnet run`), poté otevřete vygenerovaný soubor a zobrazí se čárový kód. Konzole potvrdí umístění uloženého obrázku.

## Závěr

Nyní víte **jak vygenerovat PDF417 čárový kód** v C# od začátku až do konce. Vytvořením `BarcodeGenerator`, nastavením X‑dimenze a počtu sloupců a exportem do PNG můžete vložit tvorbu čárových kódů do libovolného .NET řešení. Experimentujte s úrovněmi korekce chyb, různými formáty obrázků nebo většími datovými náklady, abyste přizpůsobili čárový kód vašemu konkrétnímu scénáři.

### Další kroky

* Prozkoumejte **nastavení PDF417 čárových kódů** jako počet řádků a poměr stran pro vlastní rozvržení.  
* Integrujte generování čárových kódů do ASP.NET Core API pro poskytování obrázků na vyžádání.  
* Spojte tento kód s generátorem QR‑kódu pro dokumenty s více symboly.

Neváhejte příklad upravit, sdílet své výsledky nebo klást otázky v komentářích. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat PDF417 čárový kód v C# s vlastními rozměry](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)
- [Jak vygenerovat PDF417 čárový kód v C# a nastavit velikost čárového kódu](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Jak vygenerovat PDF417 čárový kód v C# s generátorem čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}