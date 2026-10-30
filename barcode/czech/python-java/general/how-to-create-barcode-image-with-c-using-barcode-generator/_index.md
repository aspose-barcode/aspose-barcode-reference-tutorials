---
category: general
date: 2026-10-28
description: Vytvořte rychle obrázek čárového kódu v C#. Naučte se používat generátor
  čárových kódů v C#, jak nastavit velikost pixelu a jak změnit poměr stran pro DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: cs
lastmod: 2026-10-28
og_description: Vytvořte obrázek čárového kódu v C# pomocí generátoru čárových kódů.
  Postupujte podle tohoto návodu, abyste nastavili velikost pixelu, změnili poměr
  stran a generovali DataBar čárové kódy.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Vytvořte obrázek čárového kódu v C# – průvodce krok za krokem
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Jak vytvořit obrázek čárového kódu v C# pomocí generátoru čárových kódů
url: /cs/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu v C# pomocí Barcode Generator

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který používá knihovnu Barcode Generator C# k vygenerování DataBar stacked omnidirectional čárového kódu, nastavení velikosti pixelu a změně poměru stran.

Programatické generování čárových kódů odstraňuje potřebu externích nástrojů a umožňuje vložit obrázek přímo do PDF, reportů nebo UI komponent. V následujících krocích také pokrýváme **jak nastavit velikost pixelu** a **jak změnit poměr stran**, dva běžné požadavky, když potřebujete ostrý, správně měřítkový čárový kód.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno  
* IDE kompatibilní s C# (Visual Studio, Rider nebo VS Code)  
* NuGet balíček `BarcodeGenerator` (např. `GroupDocs.Barcode` nebo `Aspose.Barcode`) nainstalovaný ve vašem projektu  

Balíček můžete přidat pomocí následujícího příkazu:

```bash
dotnet add package GroupDocs.Barcode
```

> **Tip:** Ověřte, že verze balíčku odpovídá vašemu cílovému frameworku, aby nedošlo k nekompatibilitám za běhu.

## Vytvoření obrázku čárového kódu pomocí Barcode Generator C#

Prvním krokem je vytvořit instanci generátoru s požadovaným typem čárového kódu a daty. Níže uvedený příklad vytváří **DataBar stacked omnidirectional** čárový kód, který je ideální pro scénáře maloobchodního skenování.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Proč je každý řádek důležitý

* **Instancovat `BarcodeGenerator`** – Konstruktor přijímá symbologii čárového kódu (`EncodeTypes.DatabarStackedOmniDirectional`) a řetězec surových dat. Výběrem správné symbologie zajistíte, že skener kód přečte.  
* **Nastavit `XDimension.Pixels`** – Tato vlastnost řídí šířku nejmenšího pruhu. Hodnota `2` vytváří jemně strukturovaný obrázek, který zůstává čitelný na většině obrazovek. Zvyšte ji, pokud potřebujete větší čárový kód pro tiskárny s nízkým rozlišením.  
* **Konfigurovat `AspectRatio`** – Rodina DataBar podporuje několik poměrů stran, které ovlivňují vztah výšky k šířce. Hodnoty `15` a `30` jsou běžné; `15` dává kratší čárový kód, zatímco `30` vytváří vyšší.  
* **Metoda `Save`** – Uloží vygenerovaný čárový kód do PNG souboru. Můžete nahradit `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp`, pokud váš následný systém vyžaduje jiný formát.

## Jak nastavit velikost pixelu pro různé kontexty vykreslování

Velikost pixelu určuje vizuální hustotu čárového kódu. Pokud bude čárový kód zobrazen na monitoru s vysokým DPI, můžete zvýšit velikost pixelu na `3` nebo `4`. Naopak pro termální tiskárny s nízkým rozlišením menší velikost pixelu (např. `1`) snižuje spotřebu inkoustu.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Hraniční případ:** Nastavení velikosti pixelu příliš nízko (< 1) vyvolá `ArgumentOutOfRangeException`. Vždy před přiřazením hodnotu ověřte.

## Jak změnit poměr stran bez přetvoření generátoru

Změna poměru stran je jednoduchá aktualizace vlastnosti; **nepotřebujete** znovu vytvářet instanci `BarcodeGenerator`. Tím šetříte paměť a zlepšujete výkon, když potřebujete více obrázků s různými tvary.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Pokud potřebujete více než dva poměry, můžete projít pole pomocí smyčky:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Očekávaný výstup

Spuštěním programu se vytvoří dva PNG soubory (nebo více, pokud použijete smyčku). Otevřete je v libovolném prohlížeči obrázků; měli byste vidět čistý DataBar čárový kód:

* **DatabarAspectRatio15.png** – krátký, široký čárový kód vhodný pro úzké štítky.  
* **DatabarAspectRatio30.png** – vyšší čárový kód, který zlepšuje spolehlivost skenování na šikmých skenerech.

Oba obrázky mají stejnou velikost pixelu (2 px na modul), ale liší se pouze výškou, což demonstruje **jak změnit poměr stran** při zachování ostatních parametrů konstantních.

## Časté úskalí a jak se jim vyhnout

| Symptom | Příčina | Oprava |
|---------|----------|--------|
| Čárový kód se jeví rozmazaný | `XDimension.Pixels` nastaven příliš nízko pro výstupní rozlišení | Zvyšte velikost pixelu alespoň na `2` pro zobrazení na obrazovce, `3` pro tisk |
| Skener nemůže kód přečíst | Špatné `EncodeTypes` pro formát dat | Ověřte, že data GTIN‑14 odpovídají zvolené symbologii |
| `ArgumentOutOfRangeException` při poměru stran | Hodnota poměru není podporována knihovnou (platný rozsah: 15‑30) | Používejte pouze hodnoty dokumentované knihovnou, nebo zachyťte výjimku a přejděte na výchozí hodnotu |
| Soubor nebyl nalezen po `Save` | Relativní cesta ukazuje na neexistující adresář | Použijte absolutní cestu nebo se ujistěte, že je nejprve zavoláno `Directory.CreateDirectory` |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Další kroky – rozšíření workflow čárových kódů

Nyní, když můžete **vytvořit obrázek čárového kódu**, můžete chtít:

* **Vložit PNG do PDF** pomocí knihovny jako `PdfSharp` nebo `iTextSharp`.  
* **Generovat jiné symbologie** (QR, Code128, PDF417) změnou enumu `EncodeTypes`.  
* **Použít barevné transformace** přístupem k `barcode.Parameters.Barcode.Image.Color`.  
* **Poskytnout obrázek přes ASP.NET Core endpoint** pro generování za běhu ve webových aplikacích.

Každé z těchto témat staví na stejných základních konceptech pokrytých v tomto tutoriálu, jako je použití **barcode generator c#**, řízení velikosti pixelu a manipulace s poměrem stran.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí Barcode Generator, jak nastavit velikost pixelu, jak změnit poměr stran a jak efektivně generovat DataBar čárové kódy. Kompletní, spustitelný příklad můžete zkopírovat do libovolného .NET projektu, přizpůsobit pro jiné symbologie a rozšířit tak, aby vyhovoval reálným workflow.

Neváhejte experimentovat s různými hodnotami `XDimension`, poměry stran a výstupními formáty. Pokud narazíte na problémy, podívejte se znovu na tabulku „Časté úskalí“ nebo konzultujte oficiální dokumentaci knihovny pro podrobnější konfigurační možnosti. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit obrázek čárového kódu a upravit jeho poměr stran v C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Jak vygenerovat sadu čárových kódů s vlastní velikostí a uložit obrázek v C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Jak použít barcode generator C# k vytvoření DataBar čárových kódů](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}