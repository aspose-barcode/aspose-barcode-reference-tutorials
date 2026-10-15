---
category: general
date: 2026-10-15
description: Rychle vytvořte PNG čárový kód pomocí C#. Naučte se, jak generovat čárový
  kód, měnit řádky, konfigurovat nastavení čárového kódu a generovat PDF417 čárový
  kód v jednom tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: cs
lastmod: 2026-10-15
og_description: Rychle vytvořte PNG čárový kód v C#. Tento tutoriál ukazuje, jak generovat
  čárový kód, měnit řádky, konfigurovat čárový kód a generovat PDF417 čárový kód s
  čistým kódem.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Vytvořte PNG čárový kód PDF417 v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Vytvořte PNG čárový kód s PDF417 v C# – kompletní průvodce
url: /cs/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PNG čárového kódu s PDF417 v C# – kompletní průvodce

Pokud potřebujete **vytvořit PNG čárového kódu** z C# kódu, tento průvodce vám přesně ukáže, jak na to. Provedeme vás generováním PDF417 čárového kódu, změnou řádků a konfigurací všech klíčových parametrů před uložením výsledku jako PNG obrázku.

Naučíte se, jak programově **generovat čárové kódy**, upravit rozvržení tak, aby odpovídalo vašemu designu, a pochopit možnosti konfigurace vzhledu čárového kódu. Nejsou potřeba žádné externí nástroje – stačí knihovna Aspose.BarCode (nebo jakýkoli kompatibilní .NET balíček pro čárové kódy) a několik řádků kódu.

## Co budete potřebovat

- .NET 6.0 nebo novější (ukázka používá .NET 6, ale funguje jakákoli recentní verze .NET)
- Odkaz na NuGet balíček `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Základní znalost C# a Visual Studio (nebo vašeho preferovaného IDE)

> **Tip:** Pokud dáváte přednost bezplatné alternativě, stejná API rozhraní jsou k dispozici v open‑source knihovně `ZXing.Net`; nicméně níže uvedené úryvky kódu cílí na Aspose.BarCode, protože poskytuje přímé ovládání rozvržení PDF417.

## Krok 1: Nastavení projektu a přidání knihovny pro čárové kódy

Create a new console app and add the NuGet package:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Then open `Program.cs` and add the required `using` directives:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

These namespaces expose the `BarcodeGenerator` class and the `EncodeTypes` enumeration you’ll use to **generate PDF417 barcode** images.

## Krok 2: Vytvoření PNG čárového kódu – základní generátor

The first actionable line creates a `BarcodeGenerator` instance configured for PDF417 encoding. This is the core of **how to generate barcode** images.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Proč je to důležité:** Příznak `EncodeTypes.Pdf417` říká knihovně, kterou symboliku použít. Druhý argument (`"Layout test"`) je surový text, který bude zakódován do čárového kódu.

## Krok 3: Jak nakonfigurovat čárový kód – nastavení velikosti modulu

A module (or X dimension) defines the smallest printable element of the barcode. Adjusting it changes the overall image size without affecting data density.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nastavení `Pixels = 2` poskytuje kompaktní, vysoké rozlišení **vytvořeného PNG čárového kódu**, který dobře funguje pro webové náhledy a tisk.

## Krok 4: Jak změnit řádky – přizpůsobení rozvržení PDF417

PDF417 allows you to explicitly control the number of columns and rows. This is the step that answers **how to change rows** in a barcode.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Hraniční případ:** Pokud požádáte o více řádků, než data vyžadují, knihovna automaticky přidá vyplňovací řádky. Naopak, požadování příliš málo řádků může způsobit výjimku, protože data se nevejdou.

## Krok 5: Uložení vygenerovaného čárového kódu jako PNG soubor

Finally, write the image to disk. This completes the **create barcode PNG** workflow.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

Po spuštění programu uvidíte soubor s názvem `Pdf417_4x9.png` ve složce projektu. Obrázek obsahuje PDF417 čárový kód s přesně 4 sloupci a 9 řádky, vykreslený s 2‑pixelovými moduly.

### Kompletní spustitelný příklad

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Expected output** (console):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Otevřete PNG soubor a uvidíte čistý PDF417 čárový kód připravený ke skenování.

## Jak generovat čárový kód s jinými daty

If you need to **generate barcode** for another string, simply replace the second argument of the `BarcodeGenerator` constructor:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Stejné kroky konfigurace (velikost modulu, řádky, sloupce) platí, což vám umožní znovu použít kód pro více datových nákladů.

## Jak dynamicky měnit řádky podle délky obsahu

Sometimes the number of rows must adapt to the length of the encoded text. You can calculate a safe row count before creating the generator:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Tento úryvek zajišťuje, že nikdy nepožádáte o méně než tři řádky (minimum knihovny), a zároveň se přizpůsobí delším datům.

## Jak nakonfigurovat čárový kód pro různé formáty obrázků

Although the tutorial focuses on PNG, you can switch to JPEG, BMP, or TIFF by changing the `BarCodeImageFormat` enum:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG zůstává nejlepším výběrem pro bezztrátovou kvalitu, zejména když bude čárový kód tištěn.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Čárový kód je rozmazaný | X rozměr je příliš velký nebo dochází k měřítkování obrázku po uložení | Udržujte `XDimension.Pixels` ≤ 3 pro zobrazení na obrazovce, nebo použijte vektorový formát (PDF) pro zvětšení |
| Skener nedokáže čárový kód přečíst | Příliš málo řádků pro délku dat | Zvyšte `Pdf417.Rows` nebo nechte knihovnu automaticky nastavit velikost vynecháním explicitního nastavení řádků |
| `ArgumentOutOfRangeException` při uložení | Výstupní adresář neexistuje | Ujistěte se, že `outputPath` ukazuje na platnou složku, nebo ji vytvořte pomocí `Directory.CreateDirectory` |

## Shrnutí

Tento tutoriál ukázal, jak **vytvořit PNG čárových kódů** v C# pomocí symbologie PDF417. Naučili jste se:

- **Jak generovat čárový kód** pomocí třídy `BarcodeGenerator`
- **Jak změnit řádky** a sloupce pro kontrolu rozvržení
- **Jak nakonfigurovat čárový kód** nastavení jako velikost modulu a formát obrázku
- Jak **generovat PDF417 čárový kód** a uložit jej jako PNG obrázek

Máte nyní znovupoužitelný blok kódu, který můžete přizpůsobit pro různé datové náklady, formáty obrázků nebo požadavky na rozvržení.

## Další kroky

- Experimentujte s `Pdf417.ErrorCorrectionLevel` pro zlepšení spolehlivosti skenování při nízké kvalitě tisku.  
- Spojte více čárových kódů do jednoho PDF pomocí Aspose.PDF pro hromadnou tvorbu štítků.  
- Prozkoumejte další symbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) změnou hodnoty výčtu – to odpovídá sekundárnímu klíčovému slovu **generate pdf417 barcode**, zatímco ukazuje širší možnosti.

Šťastné kódování a užívejte si tvorbu ostrých PNG čárových kódů pro každou aplikaci!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create barcode PNG with a custom aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}