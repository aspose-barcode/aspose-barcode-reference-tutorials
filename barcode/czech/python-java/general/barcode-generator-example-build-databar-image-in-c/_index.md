---
category: general
date: 2026-07-18
description: Příklad generátoru čárových kódů, který ukazuje, jak nastavit rozměry
  a vygenerovat obrázek čárového kódu DataBar Stacked Omni‑Directional v C#. Rychle
  se naučte typy kódování čárových kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: cs
lastmod: 2026-07-18
og_description: Příklad generátoru čárových kódů vás provede nastavením rozměrů, výběrem
  typů kódování čárových kódů a vytvořením projektů C# pro obrázek čárového kódu s
  minimálním kódem.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Příklad generátoru čárových kódů – rychlé vytvoření DataBar obrázku v C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Příklad generátoru čárových kódů – Vytvořte DataBar obrázek v C#
url: /cs/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad generátoru čárových kódů – Vytvoření DataBar obrázku v C#

Už jste někdy potřebovali **barcode generator example**, který skutečně vygeneruje reálný čárový kód, aniž by vám to roztrhávalo vlasy? Nejste sami. Většina vývojářů narazí na problém, když se snaží zjistit **how to set dimensions** pro DataBar Stacked Omni‑Directional čárový kód, zejména když je dokumentace ukryta pod vrstvou žargonu.

V tomto tutoriálu projdeme kompletní, připravený C# program, který ukazuje **how to generate databar** obrázky, vybírá správné **barcode encode types** a nakonec **create barcode image c#** soubory, které můžete vložit do libovolného projektu. Žádné zbytečnosti – jen kód, který můžete zkopírovat‑vložit, a vysvětlení za každým řádkem.

## Co budete potřebovat

- **.NET 6** (nebo jakákoli novější verze .NET) – API, které používáme, cílí na .NET Standard, takže funguje i na .NET Framework.  
- **Aspose.BarCode for .NET** – knihovna, která poskytuje `BarcodeGenerator`. Získáte ji z NuGet pomocí `Install-Package Aspose.BarCode`.  
- **C# IDE** – Visual Studio, Rider nebo VS Code budou stačit.  
- Složku na disku, kam se uloží PNG soubory (kód vytvoří `DatabarAspectRatio15.png` a `DatabarAspectRatio30.png`).

Máte vše připravené? Skvěle – pojďme na to.

## Barcode Generator Example – Inicializace generátoru

Nejprve potřebujeme instanci `BarcodeGenerator` nakonfigurovanou pro **DataBar Stacked Omni‑Directional** symbologii. Toto je **barcode encode type**, se kterým budeme pracovat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Proč je to důležité:** `EncodeTypes.DatabarStackedOmniDirectional` říká Aspose přesně, kterou symbologii má vykreslit. Pokud vyberete špatný typ, skener čárový kód nerozpozná, ať už je obrázek jakkoli pěkný.

## Jak nastavit rozměry čárového kódu

Čitelnost čárového kódu závisí na jeho **X‑dimension** (šířka nejúzkého pruhu). Ve většině případů hodnota 2 pixely funguje dobře, ale můžete ji upravit podle vašeho tiskárny nebo obrazovky.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** Pokud se někdy zamyslíte **how to set dimensions** pro jinou rodinu čárových kódů, použije se stejný řetězec vlastností (`Parameters.Barcode.XDimension`) – stačí změnit hodnotu `Pixels`.

## Jak vygenerovat DataBar Stacked Omni‑Directional čárový kód

Nyní, když je generátor připraven, pohráváme si s vlastností **aspect ratio**. Ta řídí poměr výšky k šířce DataBaru a umožňuje vám vytvořit krátký, čtvercový symbol nebo vysoký, úzký.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Co se děje?** `AspectRatio = 15` říká enginu, aby udělal pruhy 15‑krát vyšší než široké. Výsledný PNG se uloží vedle spustitelného souboru.

## Create Barcode Image C# – Změna poměru stran

Pojďme dokázat flexibilitu tím, že poměr změníme na 30 a uložíme druhý soubor.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Po spuštění programu získáte dva PNG soubory:

| Soubor | Poměr stran | Přibližná velikost |
|--------|-------------|--------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Otevřete je v libovolném prohlížeči obrázků – měli byste vidět čisté, skenovatelné DataBar symboly.

## Přehled Barcode Encode Types (Volitelné, ale užitečné)

Pokud vás zajímají další **barcode encode types**, které Aspose podporuje, tady je rychlý cheat‑sheet:

| Enum EncodeTypes | Popis |
|------------------|-------|
| `EncodeTypes.Code128` | **Vysoká hustota alfanumerických znaků** |
| `EncodeTypes.QR` | 2‑D maticový kód |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar pro maloobchod |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Náš fokus** – kompaktní, všesměrový |

Znalost správného enumu vám ušetří spoustu pokusů a omylů při přechodu mezi projekty.

## Časté úskalí a jak se jim vyhnout

- **Chybějící NuGet balíček** – Kód se neskompiluje bez `Aspose.BarCode`. Nejprve spusťte `dotnet add package Aspose.BarCode`.  
- **Špatná cesta k souboru** – Pokud používáte absolutní cestu, zkontrolujte zpětná lomítka (`\\`) ve Windows. Relativní cesty (jak jsou ukázány) udržují projekt přenosný.  
- **Příliš extrémní poměr stran** – Poměry nad 50 mohou udělat čárový kód příliš vysoký pro běžné skenery. Držte se 15‑30 pro většinu případů.

## Kompletní zdrojový kód (připravený ke kopírování)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Spusťte program (`dotnet run` nebo stiskněte **F5** ve Visual Studiu) a v konzoli uvidíte zprávu potvrzující, že soubory jsou na disku.

![Příklad výstupu generátoru čárových kódů zobrazující DataBar čárový kód s poměrem stran 15](placeholder/path/to/image.png){: .align-center alt="Příklad výstupu generátoru čárových kódů zobrazující DataBar čárový kód s poměrem stran 15"}

## Závěr

Právě jsme dokončili **barcode generator example**, který demonstruje **how to set dimensions**, vybírá správné **barcode encode types** a nakonec **create barcode image c#** soubory, které můžete vložit kamkoli. Kód je malý, koncepty jsou naprosto jasné a nyní máte pevný základ pro rozšíření řešení – třeba přidání textových popisků, otáčení obrázku nebo přechod na jinou symbologii.

### Co dál?

- Experimentujte s **různými X‑dimension** a sledujte, jak se mění tolerance skeneru.  
- Vyzkoušejte jiné **EncodeTypes** jako `Code128` nebo `QR` a rozšiřte si nástrojovou sadu.  
- Automatizujte hromadné generování: projděte CSV soubor s ID produktů a vytvořte PNG pro každý z nich.

Pokud narazíte na problém, zanechte komentář níže nebo si projděte dokumentaci Aspose.BarCode – je plná příkladů, které doplňují to, co jsme zde probírali.

Šťastné kódování a ať vaše čárové kódy vždy skenují na první pokus!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}