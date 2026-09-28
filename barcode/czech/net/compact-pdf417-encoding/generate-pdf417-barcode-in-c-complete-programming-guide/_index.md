---
category: general
date: 2026-07-18
description: Rychle generujte čárový kód PDF417. Naučte se, jak nastavit propojený
  režim a jak generovat čárový kód PDF417 pomocí Aspose.BarCode v přehledném krok‑za‑krokem
  tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: cs
lastmod: 2026-07-18
og_description: Okamžitě vygenerujte čárový kód PDF417. Tento tutoriál ukazuje, jak
  nastavit spojený režim a jak vygenerovat čárový kód PDF417 pomocí Aspose.BarCode,
  včetně spustitelného kódu.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Generování čárového kódu PDF417 v C# – Kompletní průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Generování čárového kódu PDF417 v C# – Kompletní programovací průvodce
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu v C# – Kompletní programovací průvodce

Už jste někdy potřebovali **vytvořit PDF417 čárový kód** v .NET aplikaci, ale nebyli jste si jisti, kde začít? Nejste v tom sami. Ať už stavíte tiskárnu palubních lístků, skladový skener, nebo jen experimentujete s 2‑D čárovými kódy, získat PDF417 do provozu je snadnější, než si myslíte.

V tomto průvodci projdeme přesné kroky k **vytvoření PDF417 čárového kódu** pomocí Aspose.BarCode, ukážeme **jak nastavit linked mode**, a pokryjeme **jak vytvořit PDF417 čárový kód** s vlastními parametry — vše v jediném, připraveném ke zkopírování příkladu.

## Co se naučíte

- Nejmenší NuGet balíček, který potřebujete.
- Jak inicializovat PDF417 generátor s vlastním textem.
- **Jak nastavit linked mode**, aby se čárový kód mohl zalamovat přes řádky.
- Další úpravy jako velikost modulu a počet sloupců.
- Jak uložit výsledek jako PNG, JPEG nebo jakýkoli podporovaný formát.
- Běžné úskalí a rychlé tipy na odstraňování problémů.

### Požadavky

- .NET 6.0 nebo novější (kód také funguje na .NET Framework 4.7+).
- Základní znalost C#.
- Visual Studio 2022 (nebo jakékoli IDE dle vašeho výběru).
- Bezplatná zkušební verze Aspose.BarCode nebo licencovaná kopie.

> **Tip:** Pokud pracujete na novém počítači, spusťte `dotnet add package Aspose.BarCode` z terminálu ve složce projektu. Stáhne vše, co potřebujete.

---

## Krok 1: Nainstalujte Aspose.BarCode a přidejte jmenné prostory

Nejprve – přidejme knihovnu do projektu.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Poté, na začátku vašeho C# souboru, zahrňte požadované jmenné prostory:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Proč je to důležité:** Bez jmenného prostoru `Aspose.BarCode.Generation` nebudete mít přístup k `BarcodeGenerator`, a jmenný prostor `System.Drawing.Imaging` poskytuje výčet `ImageFormat` pro ukládání souborů.

---

## Krok 2: Inicializujte PDF417 generátor čárových kódů

Nyní vytvoříme instanci generátoru a předáme mu text, který chceme zakódovat. Toto je jádro **jak vytvořit PDF417 čárový kód**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Vysvětlení:** `EncodeTypes.Pdf417` říká Aspose, že pracujeme se symbologií PDF417. Druhý argument, `"Aspose"`, jsou data, která se zobrazí po načtení čárového kódu.

---

## Krok 3: Definujte velikost modulu (X‑dimenzi)

Velikost modulu určuje, jak velký se zobrazí každý malý čtvereček (nebo „pixel“) čárového kódu. Menší hodnoty vytvářejí kompaktnější kód; větší hodnoty ho učiní čitelnějším na tiskárnách s nízkým rozlišením.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Typický rozsah:** 1–4 pixely fungují pro většinu obrazovek. Pokud tisknete na štítkovou tiskárnu s vysokým DPI, zvyšte to na 3 nebo 4.

---

## Krok 4: Nastavte sloupce a povolte linked mode

Zde odpovídáme na **jak nastavit linked mode**. Linked mode umožňuje PDF417 čárovému kódu rozdělit se do více řádků, což je užitečné, když máte omezený horizontální prostor.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Proč linked mode?** Představte si, že potřebujete, aby čárový kód zapadl do úzkého UI prvku. S `IsLinked = true` knihovna automaticky rozbije symbol do řádků a zachová čitelnost.

> **Hraniční případ:** Pokud nastavíte `Columns` příliš nízko a zároveň povolíte linked mode, Aspose může dramaticky zvýšit počet řádků, což může přetečit malý plátno obrázku. Sledujte konečné rozměry obrázku.

---

## Krok 5: Uložte obrázek čárového kódu

Nakonec zapište čárový kód do souboru. Můžete zvolit PNG, JPEG, BMP nebo dokonce PDF. PNG je bezztrátový, což je ideální pro další zpracování.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Výsledek:** Uvidíte ostrý PDF417 čárový kód se třemi sloupci, velikostí modulu 2 pixely a propojenými řádky, pokud data přesáhnou šířku jednoho řádku.

---

## Kompletní funkční příklad

Níže je kompletní, připravený ke spuštění program. Zkopírujte jej do nového konzolového projektu (`dotnet new console`) a stiskněte **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Očekávaný výstup

Spuštění programu vytiskne potvrzovací řádek a složka nyní obsahuje `Pdf417Linked.png`. Otevření PNG zobrazí PDF417 čárový kód se třemi sloupci, který může zabírat dva řádky (díky linked mode). Načtení pomocí aplikace na smartphonu odhalí text **„Aspose“**.

---

## Časté otázky a řešení problémů

### 1. *Co když čárový kód vypadá rozmazaně?*  
Obvykle jde o problém s DPI. Zvyšte `XDimension.Pixels` nebo uložte obrázek ve vyšším rozlišení pomocí `generator.Save(..., BarCodeImageFormat.Png, 300)`, kde `300` je DPI.

### 2. *Mohu kódovat delší řetězce?*  
Ano — PDF417 může pojmout až ~1 850 znaků. Pokud překročíte kapacitu zvoleného počtu sloupců, knihovna automaticky přidá řádky. Upravit `Columns` nebo povolit `IsLinked` pro udržení kompaktnosti čárového kódu.

### 3. *Potřebuji licenci pro produkci?*  
Aspose.BarCode funguje v evaluačním režimu, ale vygenerovaný čárový kód bude mít malý vodoznak. Zakoupením licence jej odstraníte a odemknete pokročilé funkce, jako je ladění úrovně opravy chyb.

### 4. *Jak vytvořit PDF417 čárový kód v jiných formátech?*  
Jednoduše změňte druhý argument `Save`. Pro JPEG použijte `BarCodeImageFormat.Jpeg`; pro PDF použijte `BarCodeImageFormat.Pdf`.

---

## Rozšíření příkladu

Nyní, když víte **jak vytvořit PDF417 čárový kód** a **jak nastavit linked mode**, můžete chtít prozkoumat:

- **Error correction level** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **Přidání okraje** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **Vlastní barvy** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **Vložení čárového kódu do PDF reportu** – kombinujte Aspose.PDF s Aspose.BarCode.

Každé z těchto vyladění následuje stejný vzor: najděte odpovídající vlastnost pod `generator.Parameters.Barcode.Pdf417` (nebo obecný objekt `Barcode`) a nastavte hodnotu.

---

## Závěr

Probrali jsme vše, co potřebujete k **vytvoření PDF417 čárového kódu** v C#, od instalace Aspose.BarCode po konfiguraci linked mode a uložení obrázku. Dodržením výše uvedených kroků budete mít generátor čárových kódů připravený pro produkci, který můžete vložit do libovolného .NET řešení.

Pamatujte, klíčové body jsou:

1. Inicializujte pomocí `EncodeTypes.Pdf417`.
2. Upravit `XDimension` pro vizuální jasnost.
3. Nastavte `Columns` a povolte `IsLinked` pro řízení rozvržení (**jak nastavit linked mode**).
4. Uložte v požadovaném formátu.

Neváhejte experimentovat s dalšími parametry a nebojte se sdílet své výsledky nebo klást otázky v komentářích. Šťastné programování a ať vaše čárové kódy vždy načtou na první pokus!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}