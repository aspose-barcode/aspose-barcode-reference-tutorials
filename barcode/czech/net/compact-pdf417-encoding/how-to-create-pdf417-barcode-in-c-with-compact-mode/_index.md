---
category: general
date: 2026-09-10
description: Vytvořte PDF417 čárový kód v C# rychle. Naučte se, jak povolit kompaktní
  režim, nastavit sloupce a vygenerovat PNG pomocí BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: cs
lastmod: 2026-09-10
og_description: Vytvořte čárový kód PDF417 v C# povolením kompaktního režimu, nastavením
  sloupců a uložením jako PNG. Postupujte podle kompletního krok‑za‑krokem návodu.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Vytvoření PDF417 čárového kódu v C# – tutoriál kompaktního režimu
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak vytvořit PDF417 čárový kód v C# s kompaktním režimem
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód v C# s kompaktním režimem

Pokud potřebujete **vytvořit PDF417 čárový kód** v .NET aplikaci, tento návod vám přesně ukáže, jak na to. Ukážeme si, jak **povolit kompaktní režim**, nastavit počet sloupců a uložit výsledek jako PNG obrázek pomocí knihovny BarcodeGenerator pro C#.

Generování čárového kódu je běžná potřeba pro sledování zásob, systémy vstupenek a mobilní skenovací aplikace. Na konci tohoto tutoriálu budete mít samostatný, spustitelný příklad, který vytváří kompaktní PDF417 čárový kód připravený pro produkční použití.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný (kód funguje také s .NET Framework 4.7+)
* Aktuální verzi knihovny **BarcodeGenerator** (např. Aspose.BarCode for .NET)
* IDE nebo editor, jako je Visual Studio 2022 nebo VS Code
* Oprávnění k zápisu do složky, kam bude PNG uloženo

Žádné další NuGet balíčky nejsou potřeba nad rámec samotné knihovny pro čárové kódy.

## Krok 1: Vytvořte generátor PDF417 čárového kódu

Prvním krokem je vytvořit objekt `BarcodeGenerator` s výčtem `EncodeTypes.Pdf417` a textem, který chcete zakódovat. Tento objekt řídí celý proces generování.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Proč je to důležité*: Hodnota `EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417, zatímco druhý argument poskytuje data. Můžete nahradit `"Compact mode"` libovolným alfanumerickým řetězcem, který potřebujete zakódovat.

## Krok 2: Nastavte X rozměr (šířka modulu)

X rozměr určuje šířku každého malého čtverečku (modulu) v čárovém kódu. Menší hodnoty vytvářejí hustší obrázek, což je užitečné, když je místo omezené.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota `2` pixely představuje dobrý kompromis mezi čitelností a kompaktností pro většinu skenerů založených na obrazovce.

## Krok 3: Definujte počet sloupců

PDF417 může uspořádat data v mřížce řádků a sloupců. Úprava počtu sloupců mění poměr stran čárového kódu.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Nastavení **how to set columns** na `3` vytvoří krátký, široký čárový kód, který se dobře vejde na štítek. Můžete experimentovat s hodnotami od `1` do `30` podle množství dat a cílového skeneru.

## Krok 4: Povolit kompaktní režim

Kompaktní režim odstraňuje zbytečné řádky odsazení, čímž zmenšuje čárový kód bez ztráty integrity dat. Toto je klíčový krok pro **kompaktní PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Když je `Truncate` nastaveno na `true`, knihovna automaticky vypočítá minimální počet řádků potřebných k uložení dat, což je důvod, proč finální obrázek vypadá „těsně“.

## Krok 5: Uložte vygenerovaný čárový kód jako PNG obrázek

Nakonec zapíšete čárový kód do souboru. PNG zachovává ostré hrany potřebné pro spolehlivé skenování.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, do které může vaše aplikace zapisovat. Po spuštění najdete soubor `CompactPdf417.png`, který obsahuje čárový kód.

### Kompletní zdrojový kód

Spojením všech kroků získáte jeden připravený program:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Po spuštění tohoto programu se vygeneruje `CompactPdf417.png` ve stejné složce jako spustitelný soubor. Otevřete obrázek v libovolném prohlížeči; měli byste vidět hustý, vysokokontrastní PDF417 čárový kód připravený ke skenování.

## Jak povolit kompaktní režim v jiných scénářích

* **Dávkové generování** – Při vytváření mnoha čárových kódů nastavte `Truncate` jednou na generátoru a znovu jej použijte pro každý nový payload.
* **Různé formáty obrázků** – Stejná metoda `Save` funguje s `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp`, pokud potřebujete jiný typ souboru.
* **Dynamický počet sloupců** – Pokud se délka kódovaného řetězce liší, vypočítejte optimální počet sloupců na základě délky řetězce a rozlišení skeneru.

## Jak nastavit sloupce pro konkrétní případy použití

* **Tisk štítků** – Použijte nízký počet sloupců (např. `2`‑`5`), aby byl čárový kód dostatečně krátký pro úzké štítky.
* **Mobilní skenování** – Vyšší počet sloupců (`10`‑`15`) vytváří vyšší čárové kódy, které jsou pro fotoaparáty telefonů snáze zaostřitelné.
* **Kompenzace chybové korekce** – Více sloupců snižuje počet řádků, což může ovlivnit vestavěnou korekci chyb. Otestujte s vaším cílovým skenerem, abyste našli optimální nastavení.

## Časté problémy a tipy od profesionálů

| Problém | Proč se vyskytuje | Řešení |
|-------|----------------|-----|
| Čárový kód je nečitelný | X rozměr je příliš nízký (např. `1` pixel) | Zvyšte `XDimension.Pixels` alespoň na `2` |
| Obrázek je příliš velký | Sloupce nastaveny příliš vysoko pro krátký payload | Snižte `Pdf417.Columns` nebo povolte `Truncate` |
| PNG soubor je prázdný | Výstupní složka neexistuje nebo nemá oprávnění k zápisu | Ujistěte se, že adresář existuje a proces má práva k zápisu |
| Skener hlásí „data poškozena“ | Truncate vypnutý při použití mnoha sloupců | Povolte `Truncate` nebo snižte počet sloupců |

## Ověření výsledku

Čárový kód můžete ověřit libovolnou PDF417 skenovací aplikací (existuje mnoho bezplatných Android/iOS aplikací). Otevřete `CompactPdf417.png` v aplikaci a potvrďte, že dekódovaný text odpovídá původnímu payloadu („Compact mode“). Pokud se text liší, zkontrolujte nastavení `Truncate` a počet sloupců.

## Další kroky

* **Integrace s ASP.NET Core** – Vraťte PNG přímo z akce kontroleru místo ukládání na disk.
* **Přidání lidsky čitelného textu** – Použijte `barcodeGenerator.Parameters.Barcode.CodeTextParameters` k zobrazení zakódovaného řetězce pod čárovým kódem.
* **Prozkoumejte další symbologie** – Třída `BarcodeGenerator` podporuje QR, Code128, DataMatrix a další. Změňte `EncodeTypes` a vyzkoušejte je.

---

### Závěr

Nyní víte, jak **vytvořit PDF417 čárový kód** v C# při **povolení kompaktního režimu**, jak **nastavit počet sloupců** a jak pomocí **barcode generator C#** API **generovat čárový kód**, který splňuje reálné požadavky na velikost. Použijte tyto kroky v jakémkoli .NET projektu, který potřebuje kompaktní, vysoce husté čárové kódy, a rozšiřte tento vzor na další formáty čárových kódů podle potřeby. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}