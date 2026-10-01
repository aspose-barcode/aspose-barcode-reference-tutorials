---
category: general
date: 2026-08-06
description: Rychle vytvořte databar stacked čárový kód v C#. Naučte se nastavit rozměr
  X, upravit poměr stran a exportovat PNG soubory pomocí generátoru DataBar Stacked
  Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: cs
lastmod: 2026-08-06
og_description: Vytvořte databar naskládaný čárový kód v C# s Aspose.BarCode. Tento
  tutoriál ukazuje, jak nastavit rozměr X, změnit poměr stran a uložit PNG obrázky.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Vytvořte vrstvený databar čárový kód v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Vytvořte databar stacked čárový kód v C# – průvodce krok po kroku
url: /cs/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření databar stacked čárového kódu v C# – krok za krokem

Pokud potřebujete **vytvořit databar stacked čárový kód** v C#, tento průvodce vám ukáže přesně, jak na to pomocí knihovny Aspose.BarCode. Naučíte se nastavit X‑rozměr, změnit poměr stran čárového kódu a uložit výsledek jako PNG soubory – vše během několika stručných kroků.

Generování DataBar Stacked čárového kódu je běžné, když musíte kódovat data GS1‑128 pro maloobchodní skenování nebo logistické sledování. V následujících sekcích pokryjeme vše od nastavení projektu až po ověření výstupu, takže můžete řešení integrovat do libovolné .NET aplikace bez ztráty detailů.

## Předpoklady

Než začnete, ujistěte se, že máte:

* **.NET 6.0** (nebo novější) nainstalovaný – kód cílí na moderní SDK.
* **Licencovanou** kopii **Aspose.BarCode for .NET**. Bezplatná zkušební verze funguje pro testování, ale přidává vodoznak.
* IDE jako **Visual Studio 2022** nebo **VS Code** s rozšířením C#.
* Základní znalost syntaxe **C#** a konceptu GS1 Application Identifiers.

> **Tip:** Pokud používáte správce balíčků NuGet, příkaz `dotnet add package Aspose.BarCode` automaticky vyřeší všechny závislosti.

## Krok 1: Vytvořte nový konzolový projekt

Otevřete terminál nebo Package Manager Console a spusťte:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Příkaz `dotnet new console` vytvoří minimální soubor **Program.cs**. Přidání balíčku **Aspose.BarCode** zpřístupní třídu `BarcodeGenerator`.

## Krok 2: Inicializujte generátor DataBar Stacked Omnidirectional

Otevřete **Program.cs** a nahraďte výchozí obsah následujícím kódem. První řádek vytvoří **BarcodeGenerator** nakonfigurovaný pro symbologii **DataBar Stacked Omnidirectional** a předá payload GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Proč je to důležité:** Hodnota výčtu `EncodeTypes.DatabarStackedOmniDirectional` říká knihovně, aby vytvořila **databar stacked čárový kód**, což je vrstvená varianta omnidirekcionální rodiny DataBar. Tato symbologie může pojmout až 14 číselných znaků, což ji činí ideální pro kódy GTIN‑14.

## Krok 3: Nastavte X‑rozměr (šířku modulu)

X‑rozměr určuje šířku nejmenšího pruhu (modulu). Příliš malá hodnota může vést k špatnému vykreslení na nízkém rozlišení tiskáren, zatímco příliš velká může přesáhnout prostor na štítku.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** Vlastnost `Pixels` je pohodlná pro testování na obrazovce. Pro scénáře zaměřené na tisk použijte místo toho `generator.Parameters.Barcode.XDimension.Millimeters`.

## Krok 4: Upravit poměr stran a uložit první obrázek

**Poměr stran** ovlivňuje vztah výšky k šířce vrstveného čárového kódu. Typ DataBar Stacked Omnidirectional podporuje poměry od 10 do 30. Vygenerujeme dva obrázky, abychom ukázali vizuální dopad.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Volání `generator.Save` zapíše soubor **PNG** do aktuálního pracovního adresáře. Výčet `BarCodeImageFormat.Png` zajišťuje bezztrátovou kompresi, což je ideální pro další zpracování nebo vložení do PDF.

## Krok 5: Změňte poměr stran na 30 a uložte druhý obrázek

Nyní zvýšíme výšku vrstvených pruhů změnou poměru stran na **30**. Tím se čárový kód prodlouží, aniž by se změnil X‑rozměr.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Po spuštění programu vzniknou dva PNG soubory:

* **DatabarAspectRatio15.png** – kompaktní čárový kód vhodný pro malé štítky.
* **DatabarAspectRatio30.png** – vyšší čárový kód, který zlepšuje spolehlivost skenování na nízkokontrastních površích.

Obrázky můžete otevřít v libovolném prohlížeči a ověřit, že pruhy jsou správně vrstvené a že zakódovaná data odpovídají původnímu řetězci GS1.

## Krok 6: Ověřte zakódovanou hodnotu (volitelné)

Pokud potřebujete potvrdit, že čárový kód skutečně představuje vstupní řetězec, můžete jej dekódovat stejnou knihovnou:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Dekodér by měl vypsat `(01)12345678901231`, což dokazuje, že proces **vytvoření databar stacked čárového kódu** zachoval data.

## Časté problémy a jak se jim vyhnout

| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| Čárový kód je rozmazaný | X‑rozměr nastaven příliš nízko pro rozlišení výstupu | Zvyšte `XDimension.Pixels` nebo použijte `Millimeters` pro tisk |
| Skener hlásí „symbol not found“ | Poměr stran mimo podporovaný rozsah 10‑30 | Udržujte poměr mezi 10 a 30; 15 a 30 jsou bezpečné výchozí hodnoty |
| PNG obsahuje vodoznak | Používáte bezplatnou evaluační licenci Aspose.BarCode | Zakupte plnou licenci nebo použijte trial pouze pro testování |
| Dekódování selže u druhého obrázku | Dekodér byl nastaven na špatnou symbologii | Použijte `DecodeType.DatabarStackedOmniDirectional` při čtení vrstvených čárových kódů |

## Další kroky

Nyní, když umíte **vytvořit databar stacked čárový kód**, můžete:

* **Vložit PNG do PDF faktur** pomocí PDF knihovny jako **Aspose.PDF**.
* **Generovat čárové kódy za běhu ve webovém API** – vracet PNG bajty přímo z ASP.NET Core kontroleru.
* **Experimentovat s dalšími variantami DataBar** (např. `DatabarExpanded`, `DatabarLimited`) změnou výčtu `EncodeTypes`.
* **Upravit barvy** nastavením `generator.Parameters.Barcode.ForeColor` a `BackColor` pro design podle značky.

Každé z těchto témat staví na stejných základních konceptech: inicializace `BarcodeGenerator`, konfigurace vizuálních parametrů a uložení výsledku pomocí `BarCodeImageFormat`.

---

### Závěr

Tento tutoriál ukázal, jak **vytvořit databar stacked čárový kód** v C# pomocí Aspose.BarCode. Naučili jste se nastavit **X‑rozměr**, upravit **poměr stran čárového kódu** a exportovat výsledek jako **PNG** soubory s `BarcodeGenerator`. S volitelným krokem dekódování můžete také ověřit, že zakódovaná data GS1 jsou přesná. Použijte tyto vzory ve svých aplikacích pro inventář, dopravu nebo pokladny a prozkoumejte široké možnosti přizpůsobení, které knihovna nabízí. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Nastavení výšky jednorozměrného Databar čárového kódu](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generování obrázku čárového kódu – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}