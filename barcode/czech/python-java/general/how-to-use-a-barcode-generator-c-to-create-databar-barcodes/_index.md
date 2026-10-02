---
category: general
date: 2026-09-07
description: Návod na generátor čárových kódů v C#, který ukazuje, jak generovat PNG
  soubory čárových kódů a vytvářet DataBar čárové kódy s nastavitelným počtem řádků
  a sloupců.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: cs
lastmod: 2026-09-07
og_description: 'Návod na generátor čárových kódů v C#: naučte se generovat PNG soubory
  čárových kódů a vytvářet DataBar čárové kódy s vlastními řádky a sloupci během několika
  minut'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: generátor čárových kódů C# – vytvářejte DataBar čárové kódy a PNG obrázky
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Jak použít generátor čárových kódů v C# k vytvoření DataBar čárových kódů
url: /cs/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generátor čárových kódů C# k vytvoření DataBar čárových kódů

Pokud potřebujete **generátor čárových kódů C#** pro tvorbu vysoce kvalitních čárových kódů, tento návod vám ukáže, jak **generovat PNG soubory čárových kódů** a **vytvořit DataBar čárové kódy** s vlastními řádky a sloupci. Ať už budujete systém inventarizace v maloobchodu nebo platformu pro vstupenky, níže uvedené kroky vám umožní vytvořit DataBar Expanded Stacked čárový kód v jednom, samostatném příkladu.

V tomto tutoriálu se naučíte:

* Jak vytvořit instanci `BarcodeGenerator` pro symbologii DataBar Expanded Stacked.  
* Jak upravit nastavení sloupců a řádků tak, aby vyhovovalo specifikacím ISO / GS1.  
* Jak uložit výstup jako PNG obrázek, který lze vložit do webových stránek nebo vytisknout na štítky.  

Nejsou vyžadovány žádné externí služby — stačí knihovna Aspose.BarCode pro .NET (nebo jakákoli kompatibilní knihovna, která používá stejné API). Kód běží na .NET 6+ a funguje ve Visual Studio, Rideru nebo jakémkoli IDE podporujícím C#.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6 SDK nebo novější nainstalovaný.  
* Odkaz na NuGet balíček `Aspose.BarCode` (nebo ekvivalentní knihovnu, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`).  
* Základní znalosti syntaxe C# a struktury projektu.  

Balíček můžete přidat pomocí příkazové řádky:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Inicializace generátoru čárových kódů C# pro DataBar Expanded Stacked

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která cílí na symbologii **DataBar Expanded Stacked**. Tento objekt obsahuje všechna nastavení vykreslování, včetně textu, který se má kódovat.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Proč je to důležité:** Hodnota výčtu `EncodeTypes.DatabarExpandedStacked` říká knihovně, který standard čárového kódu má použít. Použití správného výčtu zajišťuje, že vygenerovaný obrázek splňuje specifikace GS1 DataBar.

## Krok 2: Nastavení počtu sloupců (použijí se výchozí řádky)

DataBar Expanded Stacked lze rozdělit do více sloupců. Úprava počtu sloupců mění vizuální hustotu a může pomoci umístit delší řetězce dat do omezeného prostoru.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** Výchozí počet sloupců je 1. Nastavením na 4 vytvoříte čtyři sloučené sloupce, což je ideální pro delší číselné řetězce při zachování přijatelných rozměrů výšky čárového kódu.

## Krok 3: Generování PNG čárového kódu s aplikovaným nastavením sloupců

Nyní uložte čárový kód jako PNG obrázek. PNG zachovává ostré hrany potřebné pro skenery a dobře funguje jak na webu, tak v tisku.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Soubor `DatabarCols4.png` obsahuje **PNG čárový kód**, který můžete vložit přímo do HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Krok 4: Vytvoření samostatné instance generátoru pro nastavení řádků

Pokud potřebujete řídit počet řádků místo sloupců, vytvořte novou instanci `BarcodeGenerator`. Opětovné použití stejné instance po změně rozměru může vést k neočekávaným artefaktům rozvržení, takže čerstvý objekt je nejbezpečnější přístup.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Krok 5: Nastavení počtu řádků (použijí se výchozí sloupce)

Řádky ovlivňují vertikální uspořádání modulů čárového kódu. Zvýšení počtu řádků může čárový kód prodloužit, což může být vyžadováno pro určité velikosti štítků.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Proč řádky vs. sloupce:** Sloupce rozdělují čárový kód horizontálně, zatímco řádky jej prodlužují vertikálně. Vyberte orientaci, která nejlépe vyhovuje rozvržení vašeho štítku.

## Krok 6: Generování PNG čárového kódu s aplikovaným nastavením řádků

Nakonec uložte čárový kód upravený podle řádků jako PNG soubor.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Nyní máte dva odlišné PNG soubory:

* `DatabarCols4.png` – 4 sloupce, 1 řádek.  
* `DatabarRows3.png` – 1 sloupec, 3 řádky.

Oba obrázky jsou připravené k okamžitému použití v aplikacích, reportech nebo tištěných štítcích.

## Jak generovat PNG soubory čárových kódů v C# s vlastními rozměry

Vzor výše lze znovu použít pro libovolnou variantu DataBar nebo jiné symbologie podporované knihovnou. Zde je kompaktní šablona, kterou můžete zkopírovat a vložit do pomocné třídy:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Metodu zavolejte takto:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Okrajové případy, které je třeba zvážit**

* **Délka dat** – DataBar Expanded Stacked může kódovat až 74 číselných znaků. Překročení tohoto limitu vyvolá výjimku. Ověřte délku vstupu před voláním generátoru.  
* **Neplatné rozměry** – Knihovna omezuje sloupce na 1‑4 a řádky na 1‑3 pro tuto symbologii. Zadání hodnot mimo tato rozmezí bude ignorováno nebo způsobí chybu.  
* **Rozlišení obrázku (DPI)** – Pokud potřebujete vyšší rozlišení pro tisk, nastavte `generator.Parameters.ImageResolution` před uložením.

## Očekávaný výstup

Po otevření souboru `DatabarCols4.png` nebo `DatabarRows3.png` byste měli vidět čistý, vysokokontrastní DataBar čárový kód. Naskenováním obrázku GS1‑kompatibilním skenerem získáte původní text `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Alt text: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#*

## Závěr

Tento tutoriál ukázal, jak lze **generátor čárových kódů C#** použít k **vytvoření DataBar čárových kódů** a **generování PNG souborů čárových kódů** s vlastními nastaveními řádků a sloupců. Dodržením šesti kroků — inicializace generátoru, konfigurace sloupců nebo řádků a uložení jako PNG — získáte obrázky připravené pro výrobu, vhodné pro inventární systémy, vstupenky nebo jakýkoli scénář vyžadující spolehlivé vykreslování čárových kódů.

Dále můžete zkusit:

* Přidat barvu nebo pozadí do PNG (stále kompatibilní s většinou skenerů).  
* Použít jiné symbologie, jako QR, Code 128 nebo PDF417, pomocí stejného API `BarcodeGenerator`.  
* Vložit vygenerované PNG přímo do pohledů ASP.NET Core MVC nebo komponent Blazor.

Neváhejte experimentovat s různými řetězci dat, rozměry a formáty obrázků (např. JPEG, BMP). Stejný vzor platí, což dělá **generátor čárových kódů C#** všestranným nástrojem v arzenálu každého .NET vývojáře. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}