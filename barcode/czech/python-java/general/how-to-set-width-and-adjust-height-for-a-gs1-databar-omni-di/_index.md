---
category: general
date: 2026-09-29
description: Jak nastavit šířku GS1 DataBar Omni‑Directional čárového kódu a jak změnit
  výšku pomocí C#. Postupujte podle průvodce krok za krokem s kompletním kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: cs
lastmod: 2026-09-29
og_description: Jak nastavit šířku čárového kódu GS1 DataBar Omni‑Directional a jak
  změnit výšku v C#. Naučte se přesné volání API a podívejte se na kompletní spustitelný
  příklad.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Jak nastavit šířku čárového kódu GS1 DataBar – průvodce C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Jak nastavit šířku a upravit výšku GS1 DataBar Omni‑Directional čárového kódu
  v C#
url: /cs/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit šířku a upravit výšku pro GS1 DataBar Omni‑Directional čárový kód v C#

Nastavení šířky GS1 DataBar Omni‑Directional čárového kódu je častý úkol, když potřebujete přesné rozměry pro skenovací zařízení. V tomto tutoriálu se také naučíte **jak změnit výšku**, aby čárový kód dokonale zapadl do vašeho rozvržení. Průvodce vás provede celým procesem, od nastavení projektu až po plně spustitelný ukázkový kód.

Probereme:

* Požadovaný NuGet balíček a verzi .NET.
* Proč X‑dimenze (šířka modulu) ovlivňuje čitelnost čárového kódu.
* Přesné volání API pro **nastavení šířky** a **změnu výšky**.
* Řešení okrajových případů, jako je minimální šířka modulu a renderování ve vysokém rozlišení.
* Kompletní příklad ke zkopírování, který vytvoří dva PNG soubory s různou výškou čáry.

## Požadavky

| Požadavek | Důvod |
|------------|--------|
| .NET 6.0 SDK nebo novější | Příklad používá moderní funkce C# a běží na Windows, Linuxu nebo macOS. |
| Visual Studio 2022 (nebo jakékoli C# IDE) | Poskytuje IntelliSense pro Aspose.Barcode API. |
| **Aspose.Barcode for .NET** NuGet balíček | Obsahuje `BarcodeGenerator`, `EncodeTypes` a podporu formátů obrázků. Nainstalujte pomocí `dotnet add package Aspose.Barcode`. |
| Zápisové oprávnění do složky, kam budou ukládány PNG soubory | Generátor zapisuje výstupní obrázky na disk. |

## Jak nastavit šířku čárového kódu

Krok **nastavení šířky** se provádí nastavením vlastnosti `XDimension` parametrů čárového kódu. `XDimension` představuje šířku modulu (nejmenší čáru nebo mezeru) v pixelech, bodech nebo milimetrech. Správné nastavení zajišťuje, že čárový kód splňuje specifikace skeneru.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Proč je X‑dimenze důležitá

* **Tolerance skeneru** – Většina skenerů očekává minimální šířku modulu; příliš malá hodnota může způsobit chyby při čtení.
* **Rozlišení tisku** – Při tisku na 300 dpi se 2 px modul převádí na ~0,17 mm, což je v doporučeném rozsahu pro GS1 DataBar.
* **Velikost obrázku** – Větší hodnoty X‑dimenze zvyšují celkovou šířku čárového kódu, což může ovlivnit rozvržení.

### Tipy pro spolehlivé nastavení šířky

* **Nikdy nenastavujte XDimension pod 1 px** – knihovna hodnotu omezí, ale výsledný čárový kód může být nečitelný.
* **Přizpůsobte cílovému DPI** – pokud renderujete do formátu s vysokým rozlišením (např. TIFF při 600 dpi), zvyšte XDimension úměrně.
* **Otestujte skutečným skenerem** – po změně šířky ověřte čárový kód na zařízení, které jej bude číst.

## Jak změnit výšku čárového kódu

Jakmile je šířka definována, můžete vertikální rozměr ovládat pomocí vlastnosti `BarHeight`. Následující kód ukazuje **jak změnit výšku** z 30 px na 60 px a uložit dva samostatné obrázky.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Porozumění výšce čáry

* **Vizální rovnováha** – Vyšší čáry zlepšují čitelnost na pozadích s nízkým kontrastem, ale zvětšují vertikální rozměr obrázku.
* **Regulační limity** – Některé normy (např. pro maloobchodní označování) stanovují maximální výšku čáry; upravte ji podle toho.
* **Poměr stran** – Změna výšky neovlivňuje šířku modulu; můžete tak oba parametry ladit nezávisle.

### Řešení okrajových případů při úpravě výšky

| Situace | Doporučený přístup |
|-----------|----------------------|
| Výška < 10 px | Zvyšte na alespoň 10 px; velmi krátké čáry mohou skenery ignorovat. |
| Velmi vysoké čáry (≥ 100 px) | Ověřte, že výstupní médium (papír, štítek) pojme dodatečný prostor. |
| Potřeba proporcionálního škálování | Vypočítejte `BarHeight = XDimension * požadovanýPoměr` pro zachování vizuální konzistence. |

## Kompletní, spustitelný příklad

Níže je kompletní program, který kombinuje kroky **nastavení šířky** a **změny výšky**. Zkopírujte kód do nového konzolového projektu, obnovte NuGet balíček Aspose.Barcode a spusťte jej. Ve složce `bin/Debug/net6.0` se objeví dva PNG soubory.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Očekávaný výstup**

Po spuštění programu vzniknou dva PNG soubory:

* `DatabarBarHeight30Pixels.png` – čárový kód vysoký 30 px, moduly široké 2 px.
* `DatabarBarHeight60Pixels.png` – stejný čárový kód s dvojnásobnou výškou.

Otevřete kterýkoli obrázek v libovolném prohlížeči; uvidíte čistý GS1 DataBar Omni‑Directional symbol připravený ke skenování.

## Často kladené otázky

| Otázka | Odpověď |
|----------|--------|
| *Mohu místo pixelů použít milimetry?* | Ano. Nastavte `generator.Parameters.Barcode.XDimension.Millimeters` a `BarHeight.Millimeters`. Knihovna převede na pixely zařízení podle DPI obrázku. |
| *Co když potřebuji jiný typ čárového kódu?* | Nahraďte `EncodeTypes.DatabarOmniDirectional` libovolnou hodnotou `EncodeTypes` (např. `EncodeTypes.QR`). Vlastnosti šířky a výšky fungují stejně. |
| *Existuje způsob, jak generovat SVG místo PNG?* | Použijte `BarCodeImageFormat.Svg` v metodě `Save`. Nastavení šířky/výšky zůstává použitelné. |
| *Musím volat `generator.Dispose()`?* | `BarcodeGenerator` implementuje `IDisposable`. V konzolové aplikaci jej můžete zabalit do bloku `using`, ale pro krátké ukázky je volitelné. |

## Závěr

Nyní víte **jak nastavit šířku** GS1 DataBar Omni‑Directional čárového kódu a **jak změnit výšku** pomocí Aspose.Barcode API v C#. Kompletní příklad ukazuje vytvoření generátoru, konfiguraci `XDimension` a `BarHeight` a uložení PNG souborů s různými vertikálními rozměry.  

Odtud můžete:

* Experimentovat s dalšími `EncodeTypes` (např. QR, Code128).
* Renderovat do formátů s vysokým rozlišením, jako je TIFF, pro tisk.
* Integrovat generátor do webového API, které vrací čárové kódy za běhu.

Šťastné programování a ať vaše čárové kódy vždy skenují čistě!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak změnit výšku čárového kódu v C# – Kompletní průvodce](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Příklad generátoru čárových kódů v C# – nastavení šířky a výšky](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Jak použít generátor čárových kódů v C# k vytvoření DataBar Omni‑directional čárových kódů](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}