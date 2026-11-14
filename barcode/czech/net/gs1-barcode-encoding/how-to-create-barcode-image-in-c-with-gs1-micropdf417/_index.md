---
category: general
date: 2026-11-14
description: Naučte se, jak vytvořit obrázek čárového kódu v C# pomocí Aspose.BarCode.
  Tento krok‑za‑krokem průvodce pokrývá nastavení generátoru čárových kódů v C#, formátování
  GS1 a export do PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: cs
lastmod: 2026-11-14
og_description: Rychle vytvořte obrázek čárového kódu v C#. Postupujte podle tohoto
  návodu, abyste se naučili generovat čárový kód, použít generátor čárových kódů v
  C# a exportovat PNG ve formátu GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Vytvořte obrázek čárového kódu v C# – kompletní průvodce pro GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit obrázek čárového kódu v C# pomocí GS1 MicroPDF417
url: /cs/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu v C# s GS1 MicroPDF417

Pokud potřebujete **vytvořit obrázek čárového kódu** v C#, tento průvodce vám ukáže kompletní, připravené řešení. Uvidíte **jak generovat data čárového kódu**, která odpovídají standardu GS1, jak nakonfigurovat generátor a exportovat vysoce kvalitní PNG soubor.

Tutoriál pokrývá vše od instalace požadované knihovny až po řešení běžných problémů s formátem dat. Na konci budete schopni vytvořit **obrázek čárového kódu z dat** pomocí několika řádků kódu a pochopíte, proč má každé nastavení význam.

## Požadavky

* .NET 6.0 nebo novější nainstalovaný (kód také funguje s .NET Framework 4.7+).
* IDE, například Visual Studio 2022 nebo Visual Studio Code.
* NuGet balíček **Aspose.BarCode for .NET**. Nainstalujte jej pomocí:

```bash
dotnet add package Aspose.BarCode
```

* Základní znalost syntaxe C# a formátu GS1 Application Identifier (AI).

> **Tip:** Udržujte verzi knihovny aktuální; poslední vydání přidává podporu pro novější symbologie čárových kódů a zlepšení výkonu.

## Vytvoření obrázku čárového kódu pomocí BarcodeGenerator

Tato sekce obsahuje hlavní implementaci. Kód vytvoří instanci **barcode generator c#**, nastaví X‑dimenzi pro čitelnost a uloží výsledek jako PNG soubor.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Proč je každý řádek důležitý

* **EncodeTypes.MicroPdf417** říká knihovně, aby použila symbologii GS1 MicroPDF417, která je kompaktní a ideální pro mobilní skenování.
* **Data řetězec** musí začínat GS1 AI `(01)` pro Global Trade Item Number (GTIN) následovaným `(21)` pro sériové číslo. Pokud je formát nesprávný, generátor vyhodí výjimku.
* **XDimension.Pixels** řídí šířku nejmenšího pruhu. Větší hodnota zvyšuje čitelnost na displejích s nízkým rozlišením, zatímco menší hodnota snižuje velikost obrázku.
* **BarCodeImageFormat.Png** vytváří bezztrátový obrázek, zachovávající ostré hrany potřebné pro spolehlivé skenování.

Spuštěním programu se na ploše vytvoří soubor `GS1MicroPdf417.png`. Otevřením souboru uvidíte hustý černobílý čárový kód, který kóduje GTIN `12345678901234` a sériové číslo `ABC123`.

## Jak generovat čárový kód pomocí GS1 MicroPDF417

Pokud jste v formátování GS1 noví, zde jsou základní pravidla:

| GS1 AI | Význam                     | Příklad               |
|--------|----------------------------|-----------------------|
| (01)   | Global Trade Item Number   | 12345678901234        |
| (21)   | Serial number (optional)   | ABC123                |

Když spojíte AI s jejich hodnotami, zabalíte každé AI do závorek a hodnoty umístíte přímo za ně. Výsledný řetězec lze předat **barcode generator c#** bez dalšího kódování.

### Časté úskalí

* **Chybějící závorky** – Generátor považuje řetězec za surová data a neaplikuje GS1 kontroly.
* **Překročení limitu délky** – MicroPDF417 podporuje až 155 znaků. Ořízněte zbytečné mezery.
* **Neplatné znaky** – Pro GTIN jsou povoleny pouze číselné znaky; sériové číslo může obsahovat velká písmena a číslice.

## Přizpůsobení obrázku čárového kódu z dat

Kromě základní X‑dimenze nabízí Aspose.BarCode mnoho vizuálních úprav. Níže je několik nastavení, která můžete použít v závislosti na požadavcích vašeho projektu.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Každé nastavení je volitelné; výchozí hodnoty již vytvářejí čistý, skenovatelný **barcode image**. Experimentujte s barvami a rozlišením až po ověření, že skenery stále dokážou kód přečíst.

## Ukládání čárového kódu v jiných formátech

Zatímco PNG je nejčastější formát pro web a mobil, můžete potřebovat JPEG, BMP nebo SVG. Metoda `Save` přijímá libovolnou hodnotu `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG snižuje velikost souboru, ale zavádí kompresní artefakty, které mohou ovlivnit čitelnost.
* SVG zachovává vektorovou kvalitu a je ideální pro responzivní webové designy.

## Ověření vygenerovaného čárového kódu

Rychlý způsob, jak potvrdit, že krok **create barcode image** byl úspěšný, je použít mobilní skener aplikaci podporující GS1 MicroPDF417. Naskenujte uložený PNG; aplikace by měla zobrazit:

```
GTIN: 12345678901234
Serial: ABC123
```

Pokud skener hlásí chybu, zkontrolujte formátování AI a hodnotu X‑dimenze.

## Kompletní příklad – samostatný konzolový program

Níže je kompletní program, který můžete zkopírovat, vložit a spustit bez úprav (kromě kroku instalace NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Po spuštění programu konzole vypíše úplnou cestu k souboru a PNG se objeví na vaší ploše. Tento příklad ukazuje **jak generovat data čárového kódu**, přizpůsobit vzhled a exportovat **obrázek čárového kódu z dat** v jednom soudržném pracovním postupu.

## Často kladené otázky

| Otázka | Odpověď |
|----------|--------|
| *Can I generate other GS1 symbologies?* | Yes. Replace `EncodeTypes.MicroPdf417` with `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, etc., and adjust the data string accordingly. |
| *What if my data exceeds the MicroPDF417 capacity?* | Switch to the regular PDF417 symbology, which supports longer payloads. |
| *Do I need a license for Aspose.BarCode?* | A free evaluation license works for development. For production, purchase a license to remove the evaluation watermark. |
| *Is the PNG suitable for printing on labels?* | Increase `ImageResolution` to 300 dpi or higher, and consider saving as TIFF for industrial printers. |

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí přístupu **barcode generator c#**, jak formátovat data pro scénář **create gs1 barcode**, a jak exportovat výsledek jako PNG nebo jiný typ obrázku. Kompletní příklad ukazuje každý krok – od přípravy dat po vizuální přizpůsobení – takže můžete integraci tvorby čárových kódů použít v jakékoli .NET aplikaci.

Dále prozkoumejte související témata, jako je **barcode image from data** pro QR kódy, přidávání více čárových kódů do jednoho PDF nebo automatizace hromadného generování pro inventární systémy. Experimentujte s různými hodnotami X‑dimenze a formáty obrázků, abyste našli optimální nastavení pro vaše konkrétní skenovací prostředí.

Šťastné programování a ať vaše aplikace začnou **vytvářet obrázky čárových kódů**, které spolehlivě fungují v reálném světě!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která navazují na techniky předvedené v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit obrázek čárového kódu s Aspose.Barcode v C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Jak vytvořit obrázek poštovního čárového kódu v C# pomocí Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Jak vytvořit obrázek PDF417 čárového kódu v C# – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}