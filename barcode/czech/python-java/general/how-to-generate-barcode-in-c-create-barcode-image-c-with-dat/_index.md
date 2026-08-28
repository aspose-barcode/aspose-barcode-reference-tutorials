---
category: general
date: 2026-08-22
description: Jak generovat čárový kód v C# pomocí Aspose.BarCode. Naučte se krok za
  krokem vytvořit obrázek čárového kódu v C#, vypnout 2‑D komponentu a uložit soubory
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: cs
lastmod: 2026-08-22
og_description: Jak generovat čárový kód v C# pomocí Aspose.BarCode. Tento tutoriál
  vám ukáže, jak vytvořit obrázek čárového kódu v C# pomocí DataBar Expanded, přepnout
  2‑D komponentu a uložit soubory PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Jak vygenerovat čárový kód v C# – kompletní průvodce tvorbou obrázku čárového
  kódu v C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Jak generovat čárový kód v C# – vytvořit obrázek čárového kódu v C# s DataBar
  Expanded
url: /cs/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód v C# – vytvořit obrázek čárového kódu c# s DataBar Expanded

Generování čárového kódu v C# je častý požadavek, když potřebujete vložit strojově čitelná data do svých aplikací. Tento průvodce vám ukáže, jak vytvořit obrázek čárového kódu c# pomocí knihovny Aspose.BarCode, zakázat 2‑D komponentu composite a uložit výsledek jako soubory PNG.

Uvidíte kompletní spustitelný program, vysvětlení každé konfigurační možnosti a tipy pro přizpůsobení výstupu. Není potřeba žádná externí dokumentace – stačí kód níže a vývojové prostředí .NET.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* NuGet balíček Aspose.BarCode pro .NET (`Aspose.BarCode`)  

Můžete přidat balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

Knihovna poskytuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte novou konzolovou aplikaci a importujte požadované jmenné prostory:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Jmenný prostor `Aspose.BarCode.Generation` obsahuje všechny třídy potřebné pro konfiguraci a vykreslování čárových kódů.

## Krok 2: Inicializace generátoru čárového kódu DataBar Expanded

První funkční řádek vytvoří `BarcodeGenerator` pro symbologii **DataBar Expanded** a předá řetězec surových dat. Řetězec dat odpovídá formátu GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Vytvoření generátoru alokuje interní bitmapové plátno, takže můžete před vykreslením upravit velikost a vzhled.

## Krok 3: Definice šířky modulu (X‑dimenze)

X‑dimenze určuje šířku nejmenšího elementu čárového kódu. Nastavením v pixelech získáte přesnou kontrolu nad konečnou velikostí obrázku.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota `2` pixely dobře funguje pro zobrazení na obrazovce; pro vyšší rozlišení tisku ji můžete zvýšit.

## Krok 4: Zakázat 2‑D komponentu composite

DataBar Expanded může volitelně obsahovat 2‑D komponentu, která přenáší další informace. Pro vygenerování čárového kódu **bez** této komponenty nastavte příznak na `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Zakázání komponenty snižuje vizuální složitost a vytváří menší soubor PNG.

## Krok 5: Uložit obrázek čárového kódu bez 2‑D komponenty

Zvolte výstupní adresář a zapište obrázek na disk. Výčet `BarCodeImageFormat.Png` zajišťuje bezztrátový soubor PNG.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Po tomto volání obsahuje `Databar2DComponentDisabled.png` čistý DataBar Expanded čárový kód.

## Krok 6: Povolit 2‑D komponentu composite

Pokud potřebujete extra datovou vrstvu, znovu povolte příznak. Stejnou instanci generátoru lze znovu použít, což zabraňuje vytvoření druhého objektu.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Krok 7: Uložit obrázek čárového kódu s povolenou 2‑D komponentou

Vykreslete druhý obrázek pomocí stejných nastavení, kromě 2‑D příznaku.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Nyní `Databar2DComponentEnabled.png` zobrazuje čárový kód s doplňujícím 2‑D vzorem.

## Kompletní zdrojový kód

Zkopírujte celý úryvek níže do souboru `Program.cs` a spusťte projekt. Program vytvoří oba PNG soubory ve složce, kterou určíte.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Očekávaný výstup

Spuštění programu vypíše:

```
Barcode images generated successfully.
```

a vytvoří dva soubory:

* `Databar2DComponentDisabled.png` – čárový kód bez 2‑D komponenty  
* `Databar2DComponentEnabled.png` – čárový kód s 2‑D komponentou  

Otevřete PNG soubory v libovolném prohlížeči obrázků a ověřte vizuální rozdíl.

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Různá symbologie** | Nahraďte `EncodeTypes.DatabarExpanded` jinou hodnotou, např. `EncodeTypes.Code128`. |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` na 4 nebo 5, nebo nastavte `Resolution` v `barcodeGenerator.Parameters.Image`. |
| **Jiné formáty obrázků** | Použijte `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` nebo `BarCodeImageFormat.Svg`. |
| **Spuštění ve webové aplikaci** | Přímým streamováním bajtů obrázku do HTTP odpovědi místo ukládání na disk. |
| **Správa paměti** | Zabalte generátor do bloku `using`, pokud cílíte na .NET Framework, aby byly uvolněny neřízené prostředky. |

## Profesionální tipy

* **Znovupoužití generátoru** – Změna pouze 2‑D příznaku zabraňuje opětovnému vytvoření objektu, což šetří cykly CPU.  
* **Validace dat** – Data GS1 musí splňovat přesnou délku a pravidla kontrolního součtu; neplatný vstup vyvolá `ArgumentException`.  
* **Dávkové zpracování** – Procházejte kolekci řetězců dat, podle potřeby přepínejte 2‑D příznak a uložte každý obrázek pod jedinečným názvem souboru.  

## Závěr

Nyní víte, jak generovat čárový kód v C# a vytvořit obrázek čárového kódu c# s plnou kontrolou nad 2‑D komponentou composite. Příklad ukazuje inicializaci generátoru, nastavení X‑dimenze, přepínání komponenty a ukládání PNG souborů. Odtud můžete zkoumat další symbologie, vkládat obrázky do PDF nebo integrovat generování čárových kódů do služeb ASP.NET Core.

--- 

*Další kroky*: vyzkoušejte generování QR kódů, experimentujte s různými rozlišeními obrázků nebo vložte vygenerované PNG do PDF pomocí Aspose.PDF. Tyto rozšíření staví na stejném API `BarcodeGenerator` a udržují váš pracovní postup konzistentní.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}