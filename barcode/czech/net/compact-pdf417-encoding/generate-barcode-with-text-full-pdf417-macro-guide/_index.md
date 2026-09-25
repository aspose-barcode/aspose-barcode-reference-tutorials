---
category: general
date: 2026-07-18
description: Generujte čárový kód s textem pomocí Aspose.BarCode pro .NET. Naučte
  se, jak generovat čárové kódy PDF417, nastavit možnosti makra a exportovat PNG obrázky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: cs
lastmod: 2026-07-18
og_description: Rychle generujte čárový kód s textem v C#. Tento krok‑za‑krokem návod
  ukazuje, jak generovat čárové kódy PDF417, konfigurovat nastavení maker a uložit
  jako PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Generovat čárový kód s textem – Vytvoření makra Master PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Generovat čárový kód s textem – Kompletní průvodce PDF417 Macro
url: /cs/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu s textem – Kompletní průvodce Macro PDF417

Už jste se někdy zamýšleli **jak generovat PDF417** čárové kódy, které také obsahují vlastní text? V tomto tutoriálu uvidíte přesně, jak **generovat čárový kód s textem** pomocí Aspose.BarCode pro .NET a projdeme všechna nastavení, která potřebujete pro symbol Macro PDF417. Žádné zbytečnosti, jen kompletní, spustitelný příklad, který můžete dnes vložit do svého projektu.

Budeme pokrývat:

* Požadovaný NuGet balíček a using direktivy.  
* Jak vytvořit generátor čárového kódu, který zahrnuje Unicode znaky.  
* Nastavení velikosti modulu, počtu sloupců a macro‑specifických ID.  
* Uložení výsledku jako PNG soubor a ověření výstupu.  

Na konci budete mít připravený PNG obrázek Macro PDF417 čárového kódu, který můžete vložit do faktur, vstupenek nebo jakéhokoli dokumentu, který potřebuje strojově čitelný segment.

---

## Požadavky

Než se ponoříme dál, ujistěte se, že máte:

| Požadavek | Důvod |
|-------------|--------|
| **.NET 6.0** nebo novější | Aspose.BarCode podporuje .NET Standard 2.0+, takže .NET 6 poskytuje nejnovější runtime. |
| **Visual Studio 2022** (nebo jakékoli C# IDE) | Pro snadné úpravy a ladění. |
| **Aspose.BarCode for .NET** NuGet balíček | Knihovna, která skutečně vytváří čárový kód. Nainstalujte ji pomocí `dotnet add package Aspose.BarCode`. |
| **Oprávnění zápisu** do výstupní složky | Metoda `Save` potřebuje zapsat PNG soubor. |

Pokud některý z těchto bodů není vám známý, pozastavte se a vyřešte ho – jinak kód vyhodí zjevné výjimky.

---

## Krok 1 – Instalace a import knihovny

Nejprve přidejte NuGet balíček do svého projektu:

```bash
dotnet add package Aspose.BarCode
```

Poté přiveďte potřebné jmenné prostory do rozsahu:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Tip:** Pokud používáte Visual Studio, klikněte pravým tlačítkem na projekt → *Manage NuGet Packages* → vyhledejte *Aspose.BarCode* a nainstalujte nejnovější stabilní verzi.

---

## Krok 2 – Vytvoření generátoru čárového kódu s vlastním textem

Primárním úkolem je **generovat čárový kód s textem**, který obsahuje speciální znaky jako “Å” a “©”. Konstruktor přijímá typ enkódování a řetězec s daty:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Proč je to důležité: `EncodeTypes.MacroPdf417` říká Aspose, že chceme makro verzi, která umožňuje rozdělit velkou zprávu na více symbolů. Textový řetězec může být libovolná UTF‑8 sekvence; Aspose provádí konverzi interně.

---

## Krok 3 – Úprava základního vzhledu (velikost modulu)

„Modul“ čárového kódu je nejmenší černobílý čtvereček. Nastavením jeho velikosti v pixelech ovlivníte celkové rozměry obrázku, aniž byste měnili hustotu dat:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Pokud potřebujete větší obrázek pro tisk, zvýšte tuto hodnotu na 4 nebo 6. Pamatujte, že větší moduly zvětší konečnou velikost PNG souboru.

---

## Krok 4 – Konfigurace specifických možností Macro PDF417

Macro PDF417 přidává dva identifikátory, které umožňují skeneru spojit více symbolů. Obvykle nastavíte:

| Vlastnost | Co dělá |
|----------|--------------|
| `Columns` | Počet datových sloupců na symbol (ovlivňuje šířku). |
| `MacroPdf417FileID` | Jedinečné ID pro celý macro soubor (musí být ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (0‑254). |

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Poznámka k okrajovým případům:** `MacroPdf417FileID` musí být stejné pro každý segment ve stejném logickém souboru. Pokud generujete více segmentů, použijte stejné ID, jinak získáte nesouvisející symboly, které nelze spojit.

---

## Krok 5 – Uložení čárového kódu jako PNG obrázek

Nyní, když je vše nastaveno, zapište obrázek na disk:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Metoda `Save` automaticky vytvoří PNG, přičemž se postará o DPI a barevnou hloubku. Po spuštění otevřete soubor a uvidíte něco podobného:

![Příklad generování čárového kódu s textem](/images/barcode-example.png){.center alt="Příklad generování čárového kódu s textem"}

Pokud nevidíte čárový kód, zkontrolujte, zda složka existuje a zda má vaše aplikace oprávnění k zápisu.

---

## Kompletní, připravený k spuštění příklad

Zkopírujte celý úryvek níže do nové konzolové aplikace (`dotnet new console`) a spusťte ho. Vygeneruje PNG v adresáři `C:\Barcodes` (nejprve složku vytvořte).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Očekávaný výstup** (konzole):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

A PNG zobrazí kompaktní Macro PDF417 symbol obsahující text “Åspóse.Barcóde©”.

---

## Časté otázky a úskalí

| Otázka | Odpověď |
|----------|--------|
| *Mohu použít jiný formát obrázku?* | Samozřejmě – nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. PNG je bezztrátový, proto je výchozí. |
| *Co když potřebuji více než jeden segment?* | Vytvořte nový `BarcodeGenerator` pro každý segment, zachovejte stejné `MacroPdf417FileID` a zvyšte `MacroPdf417SegmentID` (0‑254). |
| *Můj text obsahuje emoji – budou fungovat?* | Aspose.BarCode podporuje UTF‑8, takže většina emoji je v pořádku. Jen se ujistěte, že cílový skener je dokáže dekódovat; mnoho průmyslových skenerů zvládá jen alfanumerická data. |
| *Čárový kód je na mé štítku příliš široký.* | Snižte `Columns` nebo zvětšete velikost modulu. Méně sloupců vytvoří užší symbol, ale může vyžadovat tiskárnu s vyšším DPI. |
| *Potřebuji licenci?* | Bezplatná evaluační licence funguje pro testování, ale přidává malou vodoznak. Pro produkci zakupte licenci, která vodoznak odstraní a odemkne všechny funkce. |

---

## Další kroky

Nyní, když víte **jak generovat PDF417** čárové kódy s vlastním textem, můžete chtít:

* **Dekódovat** čárový kód v mobilní aplikaci pomocí `BarCodeReader` z Aspose.BarCode.  
* **Spojit** více macro segmentů do jednoho PDF dokumentu pro hromadný tisk.  
* **Prozkoumat další symbologie** (QR, DataMatrix) s podobnými vzory parametrů.  
* **Upravit úroveň opravy chyb** pomocí `Pdf417.ErrorCorrectionLevel` pro náročnější prostředí.  

---

## Závěr

Prošli jsme kompletním, end‑to‑end řešením, které vám umožní **generovat čárový kód s textem** a konkrétně **jak generovat PDF417** macro symboly pomocí Aspose.BarCode pro .NET. Nastavením X‑dimenze, počtu sloupců a macro ID získáte plnou kontrolu nad velikostí, rozvržením a zpracováním více segmentů. Výsledné PNG můžete vytisknout, vložit do PDF nebo odeslat skeneru bez další konverze.

Vyzkoušejte to, pohrávejte si s parametry a nechte čárový kód pracovat pro váš obchodní případ. Pokud narazíte na problém, dokumentace Aspose a komunitní fóra jsou vynikajícími zdroji pro další kroky. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Jak generovat PDF417 čárové kódy – Kompaktní PDF417 kódování](/barcode/english/net/compact-pdf417-encoding/)
- [Jak generovat DataMatrix čárový kód pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Jak generovat čárový kód – Jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}