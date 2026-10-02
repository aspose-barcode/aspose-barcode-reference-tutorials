---
category: general
date: 2026-08-12
description: Vytvořte obrázek čárového kódu v C# pomocí BarCodeGenerator. Naučte se
  generovat DataBar, ovládat velikost obrázku čárového kódu a efektivně vytvářet více
  čárových kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: cs
lastmod: 2026-08-12
og_description: Vytvořte obrázek čárového kódu v C# pomocí BarCodeGeneratoru. Tento
  tutoriál ukazuje krok za krokem, jak generovat kódy DataBar, upravit velikost obrázku
  čárového kódu a vytvořit více čárových kódů.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Vytvořte obrázek čárového kódu v C# – kompletní průvodce BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Vytvořte obrázek čárového kódu v C# pomocí BarCodeGenerator
url: /cs/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu v C# pomocí BarCodeGenerator

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento průvodce vám přesně ukáže, jak to provést pomocí třídy `BarCodeGenerator`. Ať už budujete maloobchodní POS systém nebo nástroj pro sledování zásob, naučíte se generovat symboly DataBar, řídit velikost obrázku čárového kódu a vytvořit několik čárových kódů v jednom běhu.

Také zjistíte, jak vám API **barcode generator c#** umožňuje upravovat rozměry, přepínat výstupní formáty a řešit okrajové případy, jako jsou neplatné datové řetězce. Na konci tutoriálu budete sebejistě **vytvářet více čárových kódů** bez psaní opakujícího se kódu.

## Požadavky

- .NET 6.0 nebo novější nainstalováno  
- Vývojové prostředí (Visual Studio, Rider nebo VS Code)  
- Aspose.BarCode pro .NET NuGet balíček (nebo jakákoli kompatibilní knihovna, která poskytuje `BarCodeGenerator`)  

Balíček můžete přidat pomocí:

```bash
dotnet add package Aspose.BarCode
```

## Co tento tutoriál pokrývá

1. Nastavení instance **barcode generator c#** pro kódování DataBar Omni‑directional.  
2. Úprava **barcode image size** změnou X‑dimension a výšky čáry.  
3. Použití smyčky k **vytvoření více čárových kódů** s různými výškami.  
4. Uložení obrázků jako PNG soubory a ověření výstupu.  

Všechny úryvky kódu jsou kompletní a připravené ke zkopírování a vložení do nového konzolového projektu.

![Create barcode image example](barcode-example.png){alt="Příklad vytvoření obrázku čárového kódu"}

## Krok 1: Inicializace generátoru – základy vytváření obrázku čárového kódu

Prvním krokem je vytvořit instanci `BarCodeGenerator` s požadovanou symbologií. Pro symbol DataBar Omni‑directional použijete `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Proč je to důležité:** Vytvoření instance generátoru definuje pravidla kódování a datový payload. Pokud vynecháte správnou hodnotu `EncodeTypes`, knihovna vytvoří nepodporovaný čárový kód nebo vyhodí výjimku.

## Krok 2: Nastavení X‑dimension a výšky čáry – kontrola velikosti obrázku čárového kódu

Vizální velikost čárového kódu je určována dvěma parametry:

| Parameter | Co řídí | Typický rozsah |
|-----------|---------|----------------|
| `x_dimension.pixels` | Šířka nejmenšího modulu (tzv. „tečka“) | 1 – 4 px |
| `bar_height.pixels`  | Výška vertikálních čar | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Tip:** Menší X‑dimension poskytuje vyšší rozlišení obrázku, ale může být obtížnější načíst na tiskárnách nízké kvality. Hodnotu upravte podle cílového skenovacího zařízení.

## Krok 3: Uložení prvního čárového kódu – vytvoření obrázku čárového kódu pro výšku 30 px

Nyní můžete vygenerovat obrázek a zapsat jej na disk. Metoda `Save` přijímá cestu k souboru a výčtový typ formátu obrázku.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Očekávaný výsledek:** Soubor PNG s názvem `Databar30.png` se objeví v `C:\Barcodes`. Otevřením souboru se zobrazí symbol DataBar Omni‑directional s čistým, vysokokontrastním vzorem.

## Krok 4: Změna výšky a generování dalších obrázků – vytvoření více čárových kódů

Pro **vytvoření více čárových kódů** s různými rozměry stačí upravit vlastnost `BarHeight` a znovu zavolat `Save`. Tím se vyhnete opětovnému vytvoření instance generátoru, což šetří paměť a čas CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Proč to funguje:** Objekt `BarCodeGenerator` uchovává celý konfigurační stav. Změna jedné vlastnosti aktualizuje renderovací engine pro další volání `Save`, což vám umožní efektivně **vytvářet více čárových kódů**.

## Krok 5: Pokročilé – jak generovat DataBar s vlastním daty

Výše uvedený příklad používá statický GS1 payload. V reálných scénářích často potřebujete vložit proměnné identifikátory produktů. Knihovna přijímá jakýkoli řetězec, který odpovídá specifikaci DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Klíčový bod:** Nastavení `generator.CodeText` aktualizuje kódovaná data bez nutnosti znovu vytvářet objekt. Toto je doporučený vzor **how to generate databar** při práci s velkými datovými sadami.

## Krok 6: Ověření a řešení problémů – zajištění správné velikosti obrázku čárového kódu

Po vygenerování obrázků můžete programově ověřit, že rozměry odpovídají vašim očekáváním. Třída `Image` z `System.Drawing` může soubor načíst a vrátit jeho velikost.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Pokud výška neodpovídá nastavené hodnotě, zkontrolujte:

- **X‑dimension**: Velmi malá hodnota může způsobit, že renderér zaokrouhlí výšku.  
- **Formát obrázku**: Některé formáty (např. JPEG) používají kompresi, která může při ukládání změnit rozměry v pixelech. PNG zachovává přesné rozměry.

## Krok 7: Nejlepší postupy pro velikost obrázku čárového kódu a výkon

| Recommendation | Reason |
|----------------|--------|
| Udržujte `x_dimension.pixels` mezi 2 – 3 px pro většinu skenerů. | Vyvažuje čitelnost a velikost souboru. |
| Používejte PNG pro bezztrátový výstup, pokud bude obrázek tištěn. | Zaručuje přesné rozměry a ostré hrany. |
| Znovu použijte jednu instanci `BarCodeGenerator` při generování mnoha čárových kódů. | Snižuje režii alokace objektů. |
| Ověřte vstupní řetězec podle standardu GS1 před přiřazením do `CodeText`. | Zabraňuje výjimkám za běhu a neplatným skenům. |
| Ukládejte vygenerované obrázky do vyhrazené složky s jasnou konvencí pojmenování (např. `Databar_{GTIN}.png`). | Zjednodušuje následné zpracování a auditní stopy. |

## Kompletní funkční příklad

Níže je kompletní program, který zahrnuje všechny kroky od inicializace po ověření. Zkopírujte kód do nového konzolového projektu a spusťte jej.



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Generovat obrázek čárového kódu – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Vytvořit obrázek DotCode čárového kódu – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}