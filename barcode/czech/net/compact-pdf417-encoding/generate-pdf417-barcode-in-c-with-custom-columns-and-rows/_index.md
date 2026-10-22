---
category: general
date: 2026-10-21
description: Rychle generujte čárový kód PDF417 v C#. Naučte se, jak generovat čárový
  kód PDF417 s vlastním rozložením, sloupci, řádky a výstupem PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: cs
lastmod: 2026-10-21
og_description: Vytvořte čárový kód pdf417 v C#. Sledujte tento tutoriál, abyste se
  naučili, jak generovat čárový kód pdf417 s vlastními sloupci, řádky a výstupem PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Vytvoření čárového kódu pdf417 v C# – kompletní průvodce krok za krokem
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
title: Vytvořit PDF417 čárový kód v C# s vlastními sloupci a řádky
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření pdf417 čárového kódu v C# – kompletní programovací průvodce

Pokud potřebujete **vytvořit pdf417 čárový kód** v .NET aplikaci, tento průvodce vám ukáže, jak na to pomocí několika řádků kódu. Uvidíte praktický příklad, který nastavuje počet sloupců a řádků a poté výsledek uloží jako PNG obrázek. Stejný přístup funguje pro jakýkoli text, který chcete zakódovat, takže jej můžete přizpůsobit fakturám, vstupenkám nebo ID kartám.

Vytváření **pdf417 čárového kódu** se často zdá jako samostatný úkol oddělený od zbytku vašeho kódu. Na konci tohoto tutoriálu pochopíte, proč jsou důležité parametry rozvržení, jak řídit kvalitu obrázku a které volání knihovny jsou potřeba k **spolehlivému vytvoření pdf417 čárového kódu**.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější nainstalováno  
* IDE kompatibilní s C# (Visual Studio, VS Code, Rider, atd.)  
* NuGet balíček **Aspose.BarCode for .NET** (nebo jakákoli kompatibilní knihovna čárových kódů)  

Knihovnu můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

Knihovna poskytuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu.

## Krok 1: Vytvořte instanci generátoru čárového kódu

První řádek vytvoří objekt, který umí **vytvořit pdf417 čárový kód**. Musíte specifikovat typ kódování (`EncodeTypes.Pdf417`) a text, který chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Proč je tento krok důležitý* – `BarcodeGenerator` zapouzdřuje všechna nastavení čárového kódu. Instancování s správným `EncodeTypes` říká enginu, aby použil symbologii PDF417 místo QR, Code128 nebo jiných formátů.

## Krok 2: Nastavte rozvržení PDF417

PDF417 vám umožňuje řídit počet sloupců a řádků, což přímo ovlivňuje velikost a hustotu čárového kódu. Úprava těchto hodnot je jádrem **jak vytvořit pdf417 čárový kód** s vlastním rozvržením.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Proč byste mohli měnit tyto hodnoty* – Více sloupců snižuje výšku čárového kódu, zatímco více řádků zvyšuje šířku. Zvolte hodnoty, které odpovídají cílovému skenovacímu zařízení a dostupné tiskové ploše.

> **Tip:** Pokud vynecháte řádky, knihovna automaticky vypočítá optimální počet na základě délky dat. Explicitní nastavení řádků je užitečné, když potřebujete pevnou velikost obrázku pro UI rozvržení.

## Krok 3: Vyberte formát obrázku a uložte soubor

Po nastavení rozvržení můžete čárový kód vykreslit do obrázku. Níže uvedený příklad ukládá čárový kód jako PNG soubor, ale můžete také zvolit JPEG, BMP nebo TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Když se kód spustí, `CustomLayout.png` bude obsahovat čistý **pdf417 čárový kód**, který odpovídá nastaveným sloupcům/řádkům.

### Očekávaný výstup

Otevření `CustomLayout.png` ukazuje obdélníkový čárový kód se čtyřmi datovými sloupci a devíti řádky. Skenování obrázku libovolným PDF417 čtečkou vrátí původní text **„Sample Text“**.

![Příklad vygenerovaného PDF417 čárového kódu](generated-pdf417.png){: .center-image alt="Vygenerovaný pdf417 čárový kód uložený jako PNG soubor"}

## Krok 4: Kompletní spustitelný příklad

Níže je samostatná konzolová aplikace, která spojuje všechny části dohromady. Zkopírujte kód do nového projektu `.csproj` a spusťte jej – nejsou potřeba žádné další soubory.

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

Spuštění programu vypíše potvrzovací řádek a vytvoří PNG soubor ve složce `output`. Obrázek lze vložit do zpráv, vytisknout na štítky nebo odeslat mobilnímu zařízení ke skenování.

## Běžné varianty a okrajové případy

| Scénář | Co změnit | Proč je to důležité |
|----------|----------------|----------------|
| **Zakódovat dlouhý řetězec** | Zvyšte `Rows` nebo nechte knihovnu automaticky vypočítat vynecháním přiřazení `Rows` | PDF417 může obsahovat až 1 850 znaků; nedostatečný počet řádků způsobí oříznutí |
| **Vyšší vizuální kvalita** | Nastavte `generator.Parameters.ImageResolution` na 600 DPI | Užitečné pro tisk na vysoce rozlišených tiskárnách |
| **Jiný formát obrázku** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg` nebo `Tiff` | JPEG snižuje velikost souboru; TIFF zachovává bezztrátová data pro archivaci |
| **Přidat tichou zónu** | `generator.Parameters.Barcode.XDimension = 2;` (nebo upravte `Margins`) | Tiché zóny zlepšují spolehlivost skeneru v hlučném prostředí |
| **Dynamický text od uživatele** | Nahraďte pevně zadaný řetězec za `Console.ReadLine()` | Umožňuje generování za běhu na základě uživatelských dat |

### Jak generovat pdf417 čárový kód ve webovém API

Pokud potřebujete vystavit generování čárových kódů přes ASP.NET Core endpoint, vraťte obrázek jako pole bajtů:

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

Tento úryvek odpovídá na otázku **jak generovat pdf417 čárový kód** za běhu bez zápisu na disk, což je ideální pro mikroservisy nebo mobilní backendy.

## Testování vygenerovaného čárového kódu

Pro ověření, že byl čárový kód vytvořen správně:

1. Otevřete PNG soubor v libovolném prohlížeči obrázků.  
2. Použijte bezplatnou aplikaci pro skenování PDF417 (např. ZXing, PDF417 Decoder) k načtení obrázku.  
3. Ověřte, že dekódovaný text odpovídá původnímu vstupu.

Pokud skener hlásí chyby, zkontrolujte hodnoty sloupců/řádků a ujistěte se, že rozlišení obrázku je dostatečně vysoké pro vaše zařízení.

## Závěr

Nyní víte, jak **vytvořit pdf417 čárový kód** v C# s plnou kontrolou nad sloupci, řádky a výstupním formátem. Kompletní příklad demonstruje celý workflow – od vytvoření `BarcodeGenerator` až po uložení PNG souboru – takže můžete integraci čárových kódů použít v jakémkoli .NET projektu.

Dále prozkoumejte související témata, jako je optimalizace **rozvržení pdf417 čárového kódu**, vkládání čárových kódů do PDF zpráv nebo dekódování čárových kódů na mobilních zařízeních. Úprava úrovní korekce chyb a experimentování s různými rozlišeními obrázků vám pomohou doladit řešení pro váš konkrétní případ použití. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich vlastních projektech.

- [Jak generovat PDF417 čárový kód v C# – krok za krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak uložit čárový kód v C# – generovat PDF417 čárové kódy](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Jak generovat PDF417 čárový kód – kompletní programovací průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}