---
category: general
date: 2026-09-10
description: Rychle vytvořte obrázek čárového kódu v C# pomocí příkladu generátoru
  čárových kódů v C#, který ukazuje, jak nastavit rozměry a uložit soubory PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: cs
lastmod: 2026-09-10
og_description: Vytvořte čárový kód v C# pomocí stručného příkladu generátoru čárových
  kódů. Naučte se nastavit velikost, výšku a exportovat PNG soubory během několika
  minut.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Vytvořte obrázek čárového kódu v C# – krok za krokem příklad generátoru
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Vytvořte obrázek čárového kódu v C# s příkladem generátoru čárových kódů
url: /cs/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu C# pomocí příkladu generátoru čárových kódů

Pokud potřebujete **vytvořit obrázek čárového kódu C#** pro označování produktů, sledování zásob nebo mobilní skenování, tento průvodce ukazuje kompletní řešení. Uvidíte **příklad generátoru čárových kódů C#**, který nastavuje šířku modulu, výšku čáry a ukládá soubory PNG během několika řádků kódu.

Tutoriál pokrývá vše od instalace požadované knihovny až po spuštění připraveného ke kompilaci konzolového programu. Na konci budete mít dva PNG soubory s čárovými kódy – jeden s výškou čáry 30 pixelů a druhý s výškou čáry 60 pixelů – připravené k použití v jakékoli .NET aplikaci.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Vývojové prostředí jako Visual Studio 2022 nebo VS Code  
* NuGet balíček **Aspose.BarCode** (kód používá `BarcodeGenerator` z této knihovny)  

Balíček můžete přidat následujícím příkazem CLI:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavení konzolového projektu

Vytvořte nový konzolový projekt a odkažte na knihovnu čárových kódů.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Příkaz vytvoří soubor `Program.cs`, do kterého umístíte kód **příkladu generátoru čárových kódů C#**.

## Krok 2: Napsání kompletního programu pro generování čárových kódů

Nahraďte obsah souboru `Program.cs` kompletním, spustitelným příkladem níže. Program ukazuje, jak **vytvořit obrázek čárového kódu C#** s vlastními rozměry a jak výsledek uložit jako soubory PNG.

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
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Proč je každý řádek důležitý

* **EncodeTypes.DatabarOmniDirectional** – vybere symbologii DataBar Omnidirectional, která kóduje číselná data a je široce používána v maloobchodu.  
* **XDimension.Pixels = 2** – nastaví šířku modulu; menší hodnota vede k kompaktnějšímu čárovému kódu.  
* **BarHeight.Pixels** – řídí vizuální výšku čar. Úpravou této hodnoty můžete vytvořit čárové kódy, které odpovídají různým velikostem štítků.  
* **Save method** – zapíše čárový kód do souboru PNG, formátu, který zachovává ostré hrany a funguje s většinou knihoven pro práci s obrázky.

## Krok 3: Sestavení a spuštění programu

Spusťte následující příkaz ze složky projektu:

```bash
dotnet run
```

Po dokončení programu uvidíte dva PNG soubory ve podsložce `output`:

* `DatabarBarHeight30Pixels.png` – výška čáry 30 pixelů  
* `DatabarBarHeight60Pixels.png` – výška čáry 60 pixelů  

Oba obrázky obsahují stejná zakódovaná data, ale liší se vizuální výškou, což ukazuje, jak lze **příklad generátoru čárových kódů C#** přizpůsobit různým požadavkům na štítky.

## Krok 4: Ověření vygenerovaných čárových kódů

Otevřete PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět čistý, vysokokontrastní DataBar čárový kód. Pro potvrzení čitelnosti můžete použít mobilní skenovací aplikaci (např. aplikace založené na ZXingu) nebo desktopovou knihovnu jako **Aspose.BarCode** v režimu dekódování:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Pokud výstup odpovídá `(01)12345678901231`, generování bylo úspěšné.

## Běžné varianty a okrajové případy

| Situace | Úprava | Ukázka kódu |
|-----------|------------|--------------|
| **Různá symbologie** (např. QR, Code128) | Změňte hodnotu `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Vlastní formát obrázku** (JPEG, BMP) | Použijte jiný výčet `BarCodeImageFormat` | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamická data** (vstup od uživatele) | Nahraďte pevně zakódovaný řetězec proměnnou | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Neplatná délka dat** | Zachyťte `ArgumentException` vyhozenou generátorem | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Tip: vždy ověřujte délku vstupu pro vybranou symbologii; Aspose.BarCode vyhodí výjimku, pokud data nesplňují specifikaci.

## Kontrolní seznam řešení problémů

* **Directory not found** – Pomocná metoda `SaveBarcode` automaticky vytvoří složku `output`, ale ujistěte se, že aplikace má oprávnění k zápisu.  
* **Unexpected image size** – Ověřte, že `XDimension.Pixels` a `BarHeight.Pixels` jsou nastaveny před voláním `Save`. Změna těchto hodnot po uložení neovlivní již vytvořené soubory.  
* **Unreadable barcode** – Ujistěte se, že zakódovaný řetězec dodržuje formát GS1 při použití DataBar symbologií. Chybějící závorky nebo nesprávné identifikátory aplikací způsobují selhání dekódování.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu C#** pomocí praktického **příkladu generátoru čárových kódů C#**. Kompletní program nastavuje šířku modulu, upravuje výšku čáry a ukládá soubory PNG s minimálním množstvím kódu. Odtud můžete zkoumat další funkce, jako je přizpůsobení barev, export více stránek do PDF nebo generování v reálném čase v ASP.NET Core webových API.

**Další kroky**

* Experimentujte s dalšími symbologiemi (`EncodeTypes.Code128`, `EncodeTypes.QR`), abyste rozšířili možnosti skenování.  
* Integrujte generátor do webové služby, která na požádání vrací obrázky čárových kódů.  
* Spojte čárový kód s metadaty produktu v PDF faktuře pomocí Aspose.PDF.

Šťastné programování a užijte si flexibilitu, kterou C# poskytuje při tvorbě obrázků čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Příklad generátoru čárových kódů v C# – nastavení sloupců, řádků a export obrázku](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Vytvoření obrázku čárového kódu C# – příklad GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Příklad generátoru čárových kódů – vytvoření DataBar obrázku v C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}