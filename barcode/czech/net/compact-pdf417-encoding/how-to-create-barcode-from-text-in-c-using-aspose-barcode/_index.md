---
category: general
date: 2026-10-28
description: Vytvořte čárový kód z textu v C# pomocí Aspose.BarCode. Naučte se generovat
  obrázek čárového kódu PDF417, nastavit sloupce, upravit X‑rozměr a povolit kompaktní
  režim.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: cs
lastmod: 2026-10-28
og_description: Vytvořte čárový kód z textu v C# pomocí Aspose.BarCode. Tento tutoriál
  ukazuje, jak vygenerovat obrázek čárového kódu PDF417, přizpůsobit velikost, sloupce
  a kompaktní režim.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Vytvořte čárový kód z textu v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Jak vytvořit čárový kód z textu v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód z textu v C# pomocí Aspose.BarCode

Pokud potřebujete **vytvořit čárový kód z textu** v .NET aplikaci, tento průvodce poskytuje připravené řešení k okamžitému spuštění. Ukážeme si, jak **generovat PDF417 čárový kód** obrázky, řídit šířku modulu, počet sloupců a povolit kompaktní režim, aniž byste opustili své IDE.

Tutoriál pokrývá vše potřebné k **generování čárových kódů v C#**, od instalace knihovny až po uložení finálního PNG souboru. Na konci budete schopni vložit vysoce hustý PDF417 čárový kód do reportů, vstupenek nebo inventárních štítků.

## Předpoklady

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakýkoli editor podporující .NET)  
* Přístup k internetu pro stažení NuGet balíčku Aspose.BarCode pro .NET  

Tyto položky jsou dostačující pro zkompilování a spuštění příkladu na Windows, Linuxu nebo macOS.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Knihovna, která umožňuje generování čárových kódů, je **Aspose.BarCode pro .NET**. Nainstalujte ji pomocí .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode`, který obsahuje třídu `BarcodeGenerator` používanou v celém tomto tutoriálu.

## Krok 2: Vytvoření konzolového projektu a přidání kódu

Vytvořte nový konzolový projekt a nahraďte vygenerovaný soubor `Program.cs` následujícím kódem. Program ukazuje, jak **vytvořit čárový kód z textu** a uložit jej jako **obrázek PDF417 čárového kódu**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Proč je každý řádek důležitý

* **`EncodeTypes.Pdf417`** vybírá symbologii PDF417, která je ideální pro kódování velkého množství dat ve dvourozměrném formátu.  
* **`XDimension.Pixels = 2`** snižuje šířku modulu, čímž činí čárový kód hustším a vhodnějším pro omezený prostor.  
* **`Pdf417.Columns = 3`** řídí počet vertikálních datových sloupců; nižší počet vede k vyššímu, ale užšímu čárovému kódu.  
* **`Pdf417.Truncate = true`** aktivuje kompaktní režim, ořezávající nevyužité sloupce na pravé straně. Toto je klíčové nastavení, které převádí běžný PDF417 na **kompaktní PDF417 obrázek čárového kódu**.  

## Krok 3: Sestavení a spuštění projektu

Spusťte následující příkazy v adresáři projektu:

```bash
dotnet build
dotnet run
```

Po dokončení programu uvidíte zprávu v konzoli potvrzující umístění souboru. Otevřete `CompactPdf417.png` v libovolném prohlížeči obrázků a ověřte výsledek.

**Očekávaný výstup** – vysokokontrastní PNG zobrazující kompaktní PDF417 čárový kód, který kóduje řetězec `Åspóse.Barcóde©`. Naskenováním obrázku standardním čtečkou čárových kódů získáte původní text, což potvrzuje úspěšné **generování pdf417 čárového kódu**.

## Krok 4: Přizpůsobení čárového kódu pro různé scénáře

Ačkoliv příklad používá pevný počet sloupců a X‑dimenzi, můžete generátor přizpůsobit dalším požadavkům:

| Scénář | Úprava |
|----------|------------|
| Větší objem dat | Zvyšte `Pdf417.Columns` nebo nastavte `Pdf417.Rows` ručně |
| Vyšší spolehlivost skenování | Zvyšte `XDimension.Pixels` na 3 nebo 4 |
| Jiný formát obrázku | Nahraďte `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp` |
| Průhledné pozadí | Nastavte `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Tyto možnosti vám umožní **generovat čárové kódy v C#** řešení, která vyhovují mobilním aplikacím, desktopovým reportům nebo webovým službám.

## Krok 5: Řešení okrajových případů a osvědčené postupy

* **Podpora Unicode** – Generátor automaticky kóduje Unicode znaky, ale ujistěte se, že váš zdrojový řetězec je kódován v UTF‑8, pokud jej čtete ze souboru.  
* **Velký text** – PDF417 může kódovat až 1 850 alfanumerických znaků. Pokud tento limit překročíte, knihovna vyhodí výjimku; rozdělte data do více čárových kódů nebo přejděte na symbologii s vyšší kapacitou.  
* **Zpracování chyb** – Zabalte kód generování do bloku `try/catch`, abyste zachytili `BarCodeException` a poskytli uživatelsky přívětivou chybovou zprávu.  
* **Výkon** – Generování mnoha čárových kódů ve smyčce těží z opětovného použití jedné instance `BarcodeGenerator` a aktualizace pouze `CodeText` mezi iteracemi.  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Kompletní výpis zdrojového kódu

Níže je kompletní, samostatný program, který můžete zkopírovat do `Program.cs`. Žádné další soubory nejsou potřeba.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Spuštěním tohoto programu vytvoříte **obrázek pdf417 čárového kódu**, který je zobrazen na ilustraci níže.

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="příklad vytvoření čárového kódu z textu zobrazující kompaktní PDF417 čárový kód"}

*Popis obrázku: PNG soubor zobrazuje kompaktní PDF417 čárový kód, který kóduje řetězec “Åspóse.Barcóde©”.*  

## Závěr

Nyní víte, jak **vytvořit čárový kód z textu** v C# a vytvořit **obrázek PDF417 čárového kódu** s vlastními rozměry a kompaktním režimem. Příklad ukazuje základní kroky k **generování čárových kódů v C#**, práci s Unicode daty a úpravu vizuálních parametrů pro různé nasazovací scénáře.

Cílem dalšího kroku je prozkoumat související témata, jako je **generování QR kódu v C#**, **přidání čárového kódu do PDF dokumentů** nebo **vložení čárových kódů do ASP.NET Core API**. Každé z nich staví na stejných základech `BarcodeGenerator`, které jsou zde popsány.

Šťastné programování a užijte si integraci čárových kódů do vašich .NET řešení!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Generovat PDF417 čárový kód v C# – Vytvořit PDF417 čárový kód C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Jak generovat PDF417 čárový kód pomocí Aspose.BarCode v C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Jak vytvořit PDF417 čárový kód obrázek v C# – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}