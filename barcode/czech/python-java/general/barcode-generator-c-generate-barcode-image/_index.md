---
category: general
date: 2026-08-03
description: Návod na generátor čárových kódů v C# ukazuje, jak vygenerovat obrázek
  čárového kódu pomocí Aspose.BarCode, nastavit sloupce a řádky a uložit PNG soubory
  pro DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: cs
lastmod: 2026-08-03
og_description: Návod na generátor čárových kódů v C# vysvětluje, jak vytvořit obrázek
  čárového kódu pomocí Aspose.BarCode, nakonfigurovat sloupce a řádky DataBar Expanded
  Stacked a uložit soubory PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generátor čárových kódů v C# – krok za krokem průvodce generováním obrázku
  čárového kódu
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generátor čárových kódů C# – vytvořit obrázek čárového kódu
url: /cs/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generátor čárových kódů C# – generování obrázku čárového kódu

Pokud potřebujete generátor čárových kódů C#, který dokáže vytvořit obrázek čárového kódu pro DataBar Expanded Stacked, tento průvodce vás provede celým procesem. Naučíte se, jak nastavit sloupce a řádky, uložit výsledek jako PNG a přizpůsobit kód pro další symbologie.

Programové generování obrázků čárových kódů odstraňuje ruční kroky a zajišťuje konzistenci napříč fakturami, štítky pro dopravu a skladovými systémy. Tento tutoriál pokrývá vše, co potřebujete, od nastavení projektu až po kompletní zdrojový kód, takže můžete příklad spustit okamžitě.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný  
* IDE, například Visual Studio 2022 (funguje jakýkoli editor podporující C#)  
* Licenci pro **Aspose.BarCode for .NET** – zdarma k vyzkoušení stačí pro testování  
* Základní znalost syntaxe C#  

Pokud některá z těchto položek chybí, nainstalujte .NET SDK z dotnet.microsoft.com a získejte NuGet balíček Aspose.BarCode pomocí:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvořte projekt generátoru čárových kódů C#

Vytvořte novou konzolovou aplikaci a přidejte potřebné `using` direktivy:

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
            // The implementation starts in the next sections
        }
    }
}
```

Třída `BarcodeGenerator` je jádrem API generátoru čárových kódů C#. Přijímá typ symbologie a text, který má být zakódován.

## Krok 2: Vygenerujte DataBar Expanded Stacked čárový kód a nastavte sloupce

První příklad vytváří čárový kód se čtyřmi sloupci. Úprava vlastnosti `Columns` mění vizuální hustotu symbologie DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Proč je to důležité:** Počet sloupců ovlivňuje množství dat, která lze uložit do kompaktního prostoru. Nastavení na 4 vytvoří širší čárový kód, který zůstává čitelný většinou skenerů.

## Krok 3: Vygenerujte čárový kód s vlastním počtem řádků

Druhý příklad ukazuje, jak ovládat vertikální rozložení nastavením vlastnosti `Rows`. Konfigurace se třemi řádky je užitečná, když potřebujete vyšší čárový kód při omezeném horizontálním prostoru.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Proč je to důležité:** Úprava řádků vám umožní umístit čárový kód do úzkého sloupce při zachování čitelnosti. Generátor čárových kódů C# automaticky přepočítá velikost modulu tak, aby splňoval specifikaci.

## Krok 4: Kompletní, spustitelný příklad

Níže je samostatný program, který kombinuje předchozí kroky. Zkopírujte kód do souboru `Program.cs`, nahraďte `YOUR_DIRECTORY` existující cestou ke složce a spusťte aplikaci.

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
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Očekávaný výstup

Po spuštění programu se v cílovém adresáři objeví dva PNG soubory:

* **DatabarCols4.png** – DataBar Expanded Stacked čárový kód se čtyřmi sloupci  
* **DatabarRows3.png** – stejná data zakódovaná ve třech řádcích  

Otevřete obrázky libovolným prohlížečem; zobrazí ostré, skenovatelné čárové kódy připravené k tisku nebo vložení do PDF.

## Jak vygenerovat obrázek čárového kódu s vlastními rozměry

Pokud potřebujete konkrétní velikost obrázku, upravte vlastnosti `ImageHeight` a `ImageWidth` před voláním `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Změna rozměrů neovlivní zakódovaná data; pouze škáluje vizuální reprezentaci. Tato technika je užitečná při integraci čárových kódů do UI komponent s pevnými rozloženími.

## Časté problémy a tipy pro profesionály

* **Oddělovače cest:** Používejte doslovné řetězce (`@"C:\Path\file.png"`) nebo `Path.Combine`, abyste se vyhnuli problémům s únikovými znaky ve Windows.  
* **Vynucení licence:** Bez platné licence obsahují vygenerované obrázky vodoznak. Licenci aplikujte co nejdříve v aplikaci:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Limity kódování:** DataBar Expanded Stacked podporuje až 74 číselných znaků. Překročení tohoto limitu vyvolá výjimku. Ověřte délku vstupu před vytvořením generátoru.  
* **Výkon:** Opakované použití jedné instance `BarcodeGenerator` pro více ukládání snižuje alokaci paměti. Měňte vlastnosti `Rows` nebo `Columns` mezi ukládáními jen pokud se zakódovaný text nemění.

## Další kroky

Nyní, když umíte generovat obrázky čárových kódů pomocí generátoru čárových kódů C#, můžete zkusit:

* **Různé symbologie** – vyzkoušejte `EncodeTypes.QR`, `EncodeTypes.Code128` nebo `EncodeTypes.Pdf417`.  
* **Přizpůsobení barev** – nastavte `Parameters.Barcode.ForeColor` a `BackColor` podle firemní identity.  
* **Vkládání do PDF** – spojte vygenerované PNG s Aspose.PDF a vytvořte tisknutelné dokumenty.  

Tyto rozšíření vám umožní postavit plnohodnotné řešení čárových kódů pro skladové, logistické nebo maloobchodní aplikace.

---


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}