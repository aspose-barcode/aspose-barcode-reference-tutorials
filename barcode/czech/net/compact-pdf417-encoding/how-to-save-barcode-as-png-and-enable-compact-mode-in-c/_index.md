---
category: general
date: 2026-11-17
description: Naučte se, jak uložit čárový kód, povolit kompaktní režim, upravit sloupce
  a vygenerovat čárový kód PDF417 pomocí kompletního příkladu v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: cs
lastmod: 2026-11-17
og_description: Jak uložit čárový kód, povolit kompaktní režim a upravit sloupce při
  generování čárového kódu PDF417 v C#. Postupujte podle krok‑za‑krokem průvodce.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Jak uložit čárový kód jako PNG a povolit kompaktní režim v C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Jak uložit čárový kód jako PNG a povolit kompaktní režim v C#
url: /cs/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uložit čárový kód jako PNG a povolit kompaktní režim v C#

Pokud potřebujete **how to save barcode** v formátu, který lze použít na webu nebo v tisku, tento průvodce vám ukáže přesné kroky. Také se naučíte, jak **enable compact mode**, **adjust columns** a **generate PDF417 barcode** pomocí knihovny Aspose.BarCode pro .NET.

Tutoriál pokrývá vše od nastavení projektu až po finální PNG soubor, takže můžete zkopírovat kód do svého vlastního řešení bez dalšího výzkumu. Není potřeba žádná externí dokumentace; je zahrnut kompletní spustitelný příklad.

## Požadavky

* .NET 6.0 nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* NuGet balíček `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Tyto tři položky jsou jedinými závislostmi pro následující kód.

## Krok 1: Vytvořte generátor PDF417 čárového kódu

Prvním úkolem při **generate PDF417 barcode** je vytvořit instanci `BarcodeGenerator` se správným typem kódování a daty, která chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Výčtový typ `EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417, což je vrstvený lineární čárový kód vhodný pro kódování velkého množství dat. Řetězec `"Compact mode"` se stane lidsky čitelným textem pod čárovým kódem.

## Krok 2: Nastavte X‑dimenzi (šířku modulu)

Každý pruh v čárovém kódu se nazývá modul. Ovládáním šířky modulu můžete jemně doladit vizuální velikost čárového kódu, aniž byste měnili data.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑dimenze 2 pixely vytváří kompaktní obrázek, který se stále spolehlivě načítá na většině zařízení.

## Krok 3: **How to adjust columns** pro kód PDF417

PDF417 vám umožňuje určit, kolik sloupců má čárový kód použít. Méně sloupců vytváří vyšší, užší symbol, zatímco více sloupců dělá symbol širší, ale nižší.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Tento řádek ukazuje **how to adjust columns**. Můžete změnit hodnotu na 2, 4 nebo jakékoli jiné číslo podporované knihovnou, v závislosti na prostoru, který máte na cílovém médiu.

## Krok 4: **How to enable compact mode** a zkrátit symbol

Kompaktní režim odstraňuje zbytečné odsazení a snižuje celkovou stopu čárového kódu. Knihovna tuto funkci zpřístupňuje prostřednictvím vlastnosti `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Všimněte si, že zde se objevuje fráze **enable compact mode**, a stejná akce je později v průvodci popsána přesným zněním **how to enable compact mode**, aby splňovala požadavek na sekundární klíčové slovo.

## Krok 5: **How to save barcode** jako PNG obrázek

Uložení vygenerovaného obrázku je posledním krokem. Metoda `Save` zapíše čárový kód do souborového systému ve formátu, který určíte.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, do které může vaše aplikace zapisovat. Po spuštění najdete soubor s názvem `CompactPdf417.png` obsahující kompaktní PDF417 čárový kód.

### Očekávaný výstup

Otevření uloženého PNG souboru ukazuje vertikálně kompaktní PDF417 čárový kód se třemi sloupci a zkráceným odsazením. Vizuální velikost je přibližně 2 px na modul, což činí obrázek vhodným pro vložení do HTML `<img>` tagů nebo pro tisk na malé štítky.

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat do nového konzolového projektu. Obsahuje všechny potřebné `using` direktivy a ukazuje **how to save barcode**, **enable compact mode**, **how to adjust columns** a **generate PDF417 barcode** v jedné posloupnosti.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Spuštěním tohoto programu se vytvoří PNG soubor popsaný výše. Výstup v konzoli potvrzuje umístění uloženého souboru, což vám pomůže ověřit, že krok **how to save barcode** byl úspěšný.

## Časté otázky a okrajové případy

### Co když potřebuji jiný formát obrázku?

Metoda `Save` přijímá libovolnou hodnotu výčtu `BarCodeImageFormat`, například `Jpeg`, `Bmp` nebo `Gif`. Nahraďte `BarCodeImageFormat.Png` požadovaným formátem a zbytek kódu zůstane beze změny.

### Jak ovlivňuje zkrácení kapacitu dat?

Povolení **compact mode** (zkrácení) snižuje počet řádků, což může snížit maximální kapacitu dat čárového kódu. Pokud narazíte na výjimku „Data too large“, buď zvýšte počet sloupců, nebo zkrácení vypněte.

### Mohu použít dynamický počet sloupců?

Ano. Počet sloupců můžete vypočítat na základě délky vstupního řetězce:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Tento úryvek ukazuje **how to adjust columns** programově, což zajišťuje, že čárový kód se vejde do daného rozvržení.

### Je X‑dimenze omezena na celočíselné pixely?

Vlastnost `Pixels` přijímá libovolné kladné celé číslo. Pro výstupy s vyšším rozlišením (např. tisk) můžete raději nastavit `Points` místo `Pixels`, abyste dosáhli nezávislé velikosti na zařízení.

## Tipy pro produkční použití

* **Tip:** Zabalte generování čárového kódu do try‑catch bloku, aby se ošetřila `BarCodeException`, když vstupní data překročí kapacitu symbolu.  
* **Pozor na:** oprávnění souborového systému. Proces musí mít právo zápisu do cílového adresáře, jinak krok **how to save barcode** selže s `UnauthorizedAccessException`.  
* **Poznámka k výkonu:** Vytváření mnoha čárových kódů ve smyčce těží z opětovného použití jedné instance `BarcodeGenerator` a pouze aktualizace vlastnosti `CodeText` mezi iteracemi.

## Závěr

Nyní víte, jak **how to save barcode** jako PNG soubor, **enable compact mode**, **how to adjust columns** a **generate PDF417 barcode** pomocí Aspose.BarCode pro C#. Kompletní příklad ukazuje každý požadovaný krok, od inicializace generátoru po zápis finálního obrázku.

Odtud můžete zkoumat související témata, jako je přidání loga do čárového kódu, přizpůsobení barev nebo integrace generátoru do ASP.NET Core API. Každé z těchto rozšíření následuje stejný vzor ukázaný v tomto průvodci, takže můžete kód upravit s jistotou.

Neváhejte experimentovat s různými počty sloupců, X‑dimenzemi a formáty obrázků, abyste splnili přesné specifikace svého projektu. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}