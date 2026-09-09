---
category: general
date: 2026-07-21
description: Rychle generujte čárový kód v C# pomocí Aspose.BarCode. Naučte se vytvořit
  DataBar čárový kód, přizpůsobit jeho velikost a exportovat obrázek čárového kódu
  během několika kroků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: cs
lastmod: 2026-07-21
og_description: Generujte čárový kód v C# pomocí Aspose.BarCode. Vytvořte DataBar
  čárový kód, přizpůsobte jeho velikost a okamžitě exportujte obrázek.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Generovat čárový kód v C# – Vytvářejte DataBar čárové kódy s vlastní velikostí
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Generovat čárový kód v C# – Vytvořit DataBar čárový kód
url: /cs/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu C# – Vytvoření DataBar čárového kódu

Hledáte **generování čárového kódu C#** bez ztrácení času v nekonečných dokumentacích? Jste na správném místě. V tomto průvodci si ukážeme, jak vytvořit **DataBar čárový kód**, upravit jeho rozměry a nakonec **exportovat obrázek čárového kódu**—vše pomocí několika řádků C#.

Představte si, že potřebujete kompaktní štítek produktu, který se vejde na malý regálový štítek. Symbolika DataBar Expanded Stacked to umožňuje a s Aspose.BarCode můžete přesně řídit, kolik sloupců nebo řádků se použije. Připravení? Pojďme na to.

## Co dosáhnete

- **Vytvořit DataBar čárový kód** (varianta „expanded stacked“) od nuly.  
- **Přizpůsobit velikost čárového kódu** nastavením sloupců nebo řádků přímo.  
- **Měnit rozměry čárového kódu** za běhu bez nutnosti znovu vytvářet generátor.  
- **Exportovat obrázek čárového kódu** do PNG (nebo jakéhokoli formátu, který Aspose podporuje).  

Žádné externí služby, žádná komplikovaná nastavení—jen čistý, spustitelný C# kód.

## Požadavky

- .NET 6.0 nebo novější (kód funguje také na .NET Framework 4.7+).  
- Platná licence Aspose.BarCode pro .NET (nebo můžete spustit v režimu trial).  
- IDE podle vašeho výběru—Visual Studio, Rider nebo VS Code vám postačí.  

Pokud jste ještě nenainstalovali NuGet balíček, spusťte:

```bash
dotnet add package Aspose.BarCode
```

A to je vše—žádné další závislosti.

## Krok 1: Nastavení generátoru čárového kódu (Jak **generovat čárový kód C#**)

Nejprve potřebujeme instanci `BarcodeGenerator`, která bude používat **DataBar Expanded Stacked** symboliku. Tento objekt je motorem, který později vytvoří obrázek.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Proč je to důležité*: Výčtový typ `EncodeTypes.DatabarExpandedStacked` říká Aspose, že chceme verzi se zásobníkem, což je ideální pro úzké prostory. Text, který předáme, se stane kódovanou hodnotou; můžete jej nahradit libovolným číselným řetězcem, který vaše aplikace vyžaduje.

## Krok 2: **Přizpůsobení velikosti čárového kódu** – nastavení sloupců

DataBar čárové kódy umožňují ovlivnit vizuální hustotu zadáním buď počtu **sloupců** *nebo* **řádků**. Začneme sloupci. Počet řádků bude automaticky vypočítán tak, aby byl čárový kód platný.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Tip*: Sloupce ovlivňují šířku čárového kódu. Více sloupců → širší čárový kód, což může zlepšit spolehlivost skenování na tiskárnách s nízkým rozlišením.

## Krok 3: **Export obrázku čárového kódu** s nastavením sloupců

Nyní zapíšeme obrázek na disk. Můžete zvolit PNG, JPEG, BMP nebo dokonce SVG. Zde je PNG pro ostrý, bezztrátový výstup.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Očekávaný výsledek** – Otevřete `DatabarCols4.png` a uvidíte pěkně uspořádaný DataBar se čtyřmi sloupci. Vypadá jako hustý zásobník vertikálních pruhů, ideální pro malý štítek.

## Krok 4: **Změna rozměrů čárového kódu** – nastavení řádků

Někdy potřebujete vyšší čárový kód místo širšího. Přepněte na řízení řádků; Aspose automaticky přepočítá sloupce.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Proč přepnout?* Řádky ovlivňují výšku čárového kódu. Více řádků znamená vyšší symbol, což může být užitečné, když máte vertikální prostor, ale omezenou šířku.

## Krok 5: **Export obrázku čárového kódu** s nastavením řádků

Uložte druhou variantu. Všimněte si, že název souboru odráží změnu; můžete si také ponechat oba obrázky pro porovnání.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Výsledek** – `DatabarRows3.png` nyní zobrazuje vyšší verzi stejného data, stále dokonale čitelnou.

## Kompletní funkční příklad

Spojením všech částí získáte samostatnou konzolovou aplikaci, kterou můžete zkopírovat a spustit okamžitě:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Spusťte program, pak otevřete oba PNG soubory. Právě jste **generovali čárový kód C#**, **přizpůsobili velikost čárového kódu**, **změnili rozměry čárového kódu** a **exportovali obrázek čárového kódu**—vše za méně než minutu.

## Často kladené otázky a okrajové případy

- **Co když potřebuji jiný formát obrázku?**  
  Nahraďte `BarCodeImageFormat.Png` hodnotou `Jpeg`, `Bmp`, `Gif` nebo `Svg`. API provede konverzi automaticky.

- **Mohu změnit najednou jak řádky, tak sloupce?**  
  Technicky můžete nastavit obojí, ale Aspose upřednostní poslední nastavenou vlastnost. Je bezpečnější nastavit *jednu* dimenzi a nechat knihovnu vypočítat druhou, aby byl DataBar platný.

- **Jak nastavit barvu popředí/backgroundu?**  
  Použijte `barcodeGen.Parameters.Barcode.ForegroundColor` a `BackgroundColor`. Příklad:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Existuje limit velikosti pro kódovaná data?**  
  DataBar Expanded Stacked podporuje až 74 číselných znaků (nebo 30 alfanumerických). Překročení této hodnoty vyvolá výjimku.

## Další kroky

Nyní, když ovládáte základy **vytvoření databar čárového kódu**, můžete zvážit:

- Přidání **textových anotací** pod čárový kód (`barcodeGen.Parameters.CaptionAbove.Text`).  
- Vložení PNG přímo do PDF pomocí Aspose.PDF.  
- Hromadné generování čárových kódů pomocí smyčky přes CSV soubor s ID produktů.

Všechny tyto témata staví na stejném objektu `BarcodeGenerator`, takže nebudete muset začínat od nuly.

---

**Závěr**: nyní víte, jak **generovat čárový kód C#**, **přizpůsobit velikost čárového kódu**, **změnit rozměry čárového kódu** a **exportovat obrázek čárového kódu** s Aspose.BarCode. Experimentujte s hodnotami sloupců/řádků, měňte formáty obrázků a integrujte kód do svého skladového nebo POS systému. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}