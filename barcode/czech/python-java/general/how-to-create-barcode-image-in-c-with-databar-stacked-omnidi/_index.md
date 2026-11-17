---
category: general
date: 2026-11-17
description: Vytvořte obrázek čárového kódu v C# pomocí knihovny Barcode Generator.
  Postupujte podle tohoto návodu a krok za krokem se naučte generovat DataBar stacked
  omnidirectional kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: cs
lastmod: 2026-11-17
og_description: Vytvořte obrázek čárového kódu v C# s stručným příkladem. Naučte se
  generovat DataBar stacked omnidirectional čárové kódy pomocí knihovny Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Vytvořte obrázek čárového kódu v C# – kompletní průvodce kódy DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit obrázek čárového kódu v C# s DataBar stacked omnidirectional
url: /cs/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu v C# s DataBar stacked omnidirectional

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento tutoriál vám ukáže kompletní, připravené řešení. Uvidíte přesně, jak použít **Barcode Generator C#** API k vytvoření stacked omnidirectional DataBar, což je formát pokrytý dotazem *how to generate databar*.

Průvodce vás provede každým potřebným krokem — od instalace knihovny po jemné doladění poměru stran — abyste mohli zkopírovat kód, spustit ho a okamžitě získat PNG soubor. Není nutné vyhledávat externí dokumentaci.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný (ukázka také funguje s .NET Framework 4.7+)
* Vývojové prostředí jako Visual Studio 2022 nebo VS Code
* NuGet balíček **Aspose.BarCode for .NET** (knihovna, která poskytuje `BarcodeGenerator`)

Balíček můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Použijte přepínač `--version` k uzamčení balíčku na nejnovější stabilní verzi, např. `dotnet add package Aspose.BarCode --version 23.9`.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte nový konzolový projekt a odkažte požadované jmenné prostory. Tento krok připraví prostředí pro **barcode generator c#** kód, který následuje.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

Jmenný prostor `Aspose.BarCode.Generation` obsahuje třídu `BarcodeGenerator`, která je jádrem workflow **vytvořit obrázek čárového kódu**.

## Krok 2: Inicializace BarcodeGenerator pro stacked omnidirectional DataBar

Generátor potřebuje dvě informace: typ čárového kódu a data k zakódování. Hodnota výčtu `EncodeTypes.DatabarStackedOmniDirectional` vybírá přesnou variantu DataBar požadovanou v scénářích *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Proč je to důležité:* Výběrem správné hodnoty `EncodeTypes` zajistíte, že výsledný obrázek bude vyhovovat průmyslovým specifikacím pro maloobchodní skenování.

## Krok 3: Definování velikosti modulu (X‑dimenze) v pixelech

Vizuální hustota čárového kódu je řízena X‑dimenzí. Nastavením rozumné pixelové hodnoty garantujete čitelnost obrázku jak na obrazovce, tak při tisku.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Pokud potřebujete větší čárový kód pro tisk s nízkým rozlišením, zvýšte pixelovou hodnotu odpovídajícím způsobem.

## Krok 4: Úprava poměru stran DataBar pro vyšší řádky

Stacked omnidirectional DataBar se skládá ze dvou řad. Úpravou `AspectRatio` můžete řídit výšku každé řady, což je užitečné, když výchozí velikost vypadá stísněně.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Poměr stran `15` je běžná volba pro maloobchodní štítky; můžete experimentovat s hodnotami mezi `10` a `20`, abyste splnili konkrétní požadavky na rozvržení.

## Krok 5: Uložení vygenerovaného čárového kódu jako PNG obrázek

Nakonec zapište obrázek na disk. PNG je bezztrátový formát, což ho činí ideálním pro následné zpracování nebo vložení do PDF.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Spuštěním programu vznikne soubor pojmenovaný **DatabarAspectRatio15.png** ve výstupním adresáři projektu. Otevřením souboru uvidíte čistý, vysokokontrastní čárový kód připravený ke skenování.

### Očekávaný výstup

Uložený obrázek vypadá podobně jako ilustrace níže (skutečný vizuál je vynechán pro stručnost).

*Alt text pro ukázkový obrázek:* **vytvořit obrázek čárového kódu** – PNG soubor zobrazující stacked omnidirectional DataBar s poměrem stran 15.

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Different payload length** | Nahraďte GTIN řetězec libovolným platným DataBar obsahem (např. `(01)01234567890123`). |
| **Higher resolution for large prints** | Zvyšte `XDimension.Pixels` na 4 nebo 5 a volitelně nastavte `Resolution` v `Parameters.Image`. |
| **Other DataBar formats** | Použijte `EncodeTypes.DatabarStacked` pro dvouřádkovou stacked variantu bez omnidirekční schopnosti. |
| **Saving as JPEG** | Změňte `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` a volitelně nastavte `Quality`. |

Tyto varianty odpovídají širší otázce *how to generate databar* tím, že ukazují, že stejný generátor lze přenastavit pro různé rodiny DataBar.

## Kompletní přehled zdrojového kódu

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Zkopírujte kód do `Program.cs`, obnovte NuGet balíčky a spusťte `dotnet run`. Konzole potvrdí umístění obrázku a můžete otevřít PNG a ověřit výsledek **vytvořit obrázek čárového kódu**.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí knihovny Barcode Generator a jak **generovat DataBar** kódy s přesnou kontrolou velikosti a poměru stran. Kompletní příklad demonstruje všechna potřebná nastavení — od inicializace `BarcodeGenerator` po export PNG souboru — takže můžete integrovat tvorbu čárových kódů do libovolné .NET aplikace bez dalšího výzkumu.

### Co dál?

* Prozkoumejte další symbologie čárových kódů s `EncodeTypes` (např. QR, Code128) – přirozené rozšíření workflow **barcode generator c#**.
* Kombinujte vygenerovaný obrázek s PDF nebo Excel reporty pomocí Aspose.PDF nebo Aspose.Cells.
* Upravit barvu, přidat okraje nebo vložit čárový kód do webového API pro generování na požádání.

Neváhejte experimentovat s parametry a nechte kód sloužit jako spolehlivý základ pro všechny vaše budoucí projekty související s čárovými kódy. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}