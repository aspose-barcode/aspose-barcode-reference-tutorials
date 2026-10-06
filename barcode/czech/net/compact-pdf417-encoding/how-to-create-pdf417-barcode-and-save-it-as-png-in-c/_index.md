---
category: general
date: 2026-10-05
description: Naučte se, jak v C# vytvořit čárový kód PDF417 a vygenerovat PNG čárového
  kódu pomocí krok‑za‑krokem kódu a tipů na osvědčené postupy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: cs
lastmod: 2026-10-05
og_description: Vytvořte PDF417 čárový kód v C# a okamžitě vygenerujte PNG čárového
  kódu. Sledujte tento kompletní tutoriál pro řešení připravené na produkci.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Vytvořte PDF417 čárový kód v C# – kompletní návod na generování PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Jak vytvořit čárový kód PDF417 a uložit jej jako PNG v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód a uložit jej jako PNG v C#

Pokud potřebujete **vytvořit PDF417 čárový kód** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Získáte připravený úryvek C#, který generuje vysoce kvalitní **PNG soubor s čárovým kódem**, a pochopíte každé nastavení, které ovlivňuje výstup.

Generování čárových kódů je běžnou požadavkem pro systémy vstupenek, sledování zásob a zabezpečené kódování dokumentů. Na konci tohoto tutoriálu budete schopni odpovědět na otázku “**jak generovat PDF417**” pomocí kompletního, spustitelného příkladu.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Vývojové prostředí jako Visual Studio 2022 nebo VS Code  
* NuGet balíček **Aspose.BarCode for .NET** (nebo jakákoli kompatibilní knihovna podporující PDF417)  

Můžete přidat balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

Níže uvedený kód používá Aspose API, protože poskytuje detailní kontrolu nad parametry PDF417 a podporuje export do PNG přímo z krabice.

## Krok 1: Nastavte projekt a importujte jmenné prostory

Vytvořte nový konzolový projekt a importujte požadované jmenné prostory:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Jmenný prostor `Aspose.BarCode.Generation` obsahuje třídu `BarcodeGenerator`, která je vstupním bodem pro **vytváření PDF417 čárových kódů**.

## Krok 2: Vytvořte PDF417 čárový kód s požadovaným textem

Vytvořte instanci generátoru s výčtem `EncodeTypes.Pdf417` a daty, která chcete zakódovat. Příklad používá řetězec obsahující speciální znaky pro demonstraci zpracování Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

## Krok 3: Nakonfigurujte vizuální parametry

Doladění čárového kódu zlepšuje čitelnost a snižuje velikost obrázku. Nejčastěji upravovaná nastavení jsou **X‑dimenze**, **sloupce** a **kompaktní režim**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** řídí šířku každého modulu; hodnota `2` pixely poskytuje kompaktní, ale čitelný čárový kód.  
* **Columns** určuje, kolik datových sloupců kód používá. Méně sloupců dělá čárový kód užší, ale vyšší.  
* **Truncate** aktivuje „kompaktní“ režim definovaný specifikací PDF417, který odstraňuje zbytečné řádky výplně.

Můžete experimentovat s `Rows` a `ErrorCorrectionLevel`, pokud váš případ vyžaduje vyšší odolnost vůči poškození.

## Krok 4: Uložte čárový kód jako PNG obrázek

Nakonec exportujte čárový kód do souboru PNG. PNG zachovává ostré hrany a podporuje průhlednost, což ho činí ideálním pro webové a tiskové scénáře.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Když otevřete `CompactPdf417.png`, měli byste vidět svislý, vysokohustotní čárový kód, který kóduje řetězec *Åspóse.Barcóde©*. Naskenováním obrázku libovolným PDF417 čtečkou získáte původní text.

![Kompaktní PDF417 čárový kód vytvořený v C#](compact-pdf417.png "Příklad kompaktního PDF417 čárového kódu vytvořeného v C#")

*Alt text výše obsahuje primární klíčové slovo, splňující jak požadavky SEO, tak přístupnosti.*

## Kompletní, spustitelný příklad

Spojením všech částí dohromady zde máte samostatný program, který můžete zkopírovat, vložit a spustit:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Očekávaný výstup

Když otevřete `CompactPdf417.png`, měli byste vidět svislý, vysokohustotní čárový kód, který kóduje řetězec *Åspóse.Barcóde©*. Naskenováním obrázku libovolným PDF417 čtečkou získáte původní text.

## Proč jsou tato nastavení důležitá

* **X‑dimension** ovlivňuje jak fyzickou velikost, tak rychlost skenování. Menší moduly zvyšují datovou hustotu, ale mohou vyžadovat skenery s vyšším rozlišením.  
* **Columns** ovlivňují poměr stran. Pro mobilní účtenky nízký počet sloupců udržuje čárový kód dostatečně úzký, aby se vešel na úzký papír.  
* **Truncate** snižuje počet řádků, šetří inkoust a prostor bez ztráty integrity dat, protože PDF417 již obsahuje kódy pro opravu chyb.

Pochopení těchto parametrů vám umožní přizpůsobit čárový kód omezením vašeho cílového média – ať už jde o tiskárnu štítků, webovou stránku nebo mobilní aplikaci.

## Běžné varianty a okrajové případy

### Generování jiných formátů obrázků

Pokud dáváte přednost JPEG nebo BMP, změňte výčet `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG komprimuje obrázek, ale může zavést artefakty, které ovlivňují skenování při malých rozměrech.

### Úprava opravy chyb

Pro drsné prostředí (např. venkovní značení) zvyšte úroveň opravy chyb:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

### Kódování binárních dat

PDF417 může kódovat binární data. Předávejte `byte[]` místo řetězce:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Knihovna automaticky přepne do binárního režimu.

### Zpracování velmi dlouhých řetězců

Když data překročí výchozí kapacitu, generátor automaticky vytvoří další řádky. Můžete omezit počet řádků, abyste se vyhnuli příliš velkým obrázkům:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Pokud obsah stále nepasuje, zvažte rozdělení na více čárových kódů.

## Profesionální tipy

* **Cache the generator** pokud potřebujete vytvořit mnoho čárových kódů se stejným nastavením. Opětovné použití objektu zabraňuje opakovanému přidělování interních zdrojů.  
* **Set `Resolution`** na `ImageOptions`, pokud potřebujete konkrétní DPI pro tisk:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output** programově pomocí `BarCodeReader`, abyste zajistili, že vygenerovaný PNG lze dekódovat před jeho distribucí uživatelům.

## Závěr

Nyní víte, jak **vytvořit PDF417 čárový kód** v C# a **generovat PNG soubory s čárovým kódem** s plnou kontrolou nad velikostí, sloupci a kompaktním režimem. Kompletní příklad demonstruje standardní přístup, vysvětluje, proč je každé nastavení důležité, a pokrývá varianty jako oprava chyb, alternativní formáty a binární data. Použijte výše uvedené tipy k přizpůsobení řešení vašemu konkrétnímu workflow, ať už vytváříte systém vstupenek, generátor logistických štítků nebo zabezpečený kódovač dokumentů.

---

**Další kroky**

* Prozkoumejte další 2D symbologie (DataMatrix, QR) pomocí stejné třídy `BarcodeGenerator`.  
* Integrovat vytváření čárových kódů do ASP.NET Core API pro poskytování PNG na vyžádání.  
* Kombinovat obrázek čárového kódu s knihovnami pro generování PDF a vložit jej přímo do reportů.

Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit pdf417 čárový kód v C# – krok za krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak vygenerovat micro pdf417 čárový kód v C# – krok za krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak vytvořit PDF417 čárový kód v C# s kompaktním režimem](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}