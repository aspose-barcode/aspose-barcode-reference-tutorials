---
category: general
date: 2026-11-17
description: Naučte se, jak generovat čárový kód PDF417, nastavit jeho velikost a
  vykreslit jej do obrázku pomocí C#. Kompletní průvodce krok za krokem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: cs
lastmod: 2026-11-17
og_description: Vygenerujte čárový kód PDF417 v C# a vykreslete jej do obrázku. Postupujte
  podle tohoto návodu pro nastavení velikosti čárového kódu a uložení souboru PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Vytvořte čárový kód PDF417 a vykreslete jej jako PNG – průvodce C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Jak vygenerovat čárový kód PDF417 a vykreslit jej jako PNG
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód PDF417 a vykreslit jej jako PNG

Pokud potřebujete **vygenerovat čárový kód PDF417** v .NET aplikaci, tento tutoriál vám ukáže přesně jak. Uvidíte, jak nastavit velikost čárového kódu, nakonfigurovat rozvržení a **vykreslit čárový kód do obrázku** pomocí několika řádků C# kódu.

Generování čárového kódu PDF417 je běžné, když chcete zakódovat velké množství dat pro skenování na mobilních zařízeních nebo tiskárnách. Na konci tohoto průvodce budete mít připravený PNG soubor, který můžete vložit do reportů, e‑mailů nebo webových stránek.

## Požadavky

Než začnete, ujistěte se, že máte:

- .NET 6.0 SDK nebo novější nainstalovaný  
- C# IDE, například Visual Studio 2022 (funguje jakýkoli editor)  
- NuGet balíček **Aspose.BarCode for .NET** (nebo jakoukoli kompatibilní knihovnu, která poskytuje `BarcodeGenerator`)  

Balíček můžete přidat pomocí:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvořte C# konzolový projekt

Nejprve nastavte minimální konzolovou aplikaci, která bude hostit kód pro generování čárového kódu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Tip:** Udržujte metodu `Main` stručnou a delegujte těžkou práci na pomocné metody. Zlepší to čitelnost a usnadní jednotkové testování.

## Krok 2: Vygenerujte PDF417 čárový kód s vlastní velikostí

Nyní **vygenerujeme PDF417 čárový kód** a specifikujeme velikost modulu (X‑dimenze). X‑dimenze určuje, jak široký je každý malý čtvereček čárového kódu, čímž efektivně nastavuje celkovou velikost čárového kódu.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Proč nastavit X‑dimenzi?

Krok **jak nastavit velikost čárového kódu** je důležitý, protože příliš malá X‑dimenze může způsobit, že čárový kód bude nečitelný na nízkorozlišovacích skenerech, zatímco příliš velká hodnota plýtvá prostorem. Hodnota `2` pixelů funguje dobře pro většinu displejů a tiskových scénářů.

## Krok 3: Zavolejte metodu generování z `Main`

Propojte vše dohromady voláním `GeneratePdf417` s požadovaným textem a místem uložení.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Spuštěním programu se vytvoří soubor `LayoutPdf417.png` obsahující čárový kód:

![Generated PDF417 barcode](/images/layout-pdf417.png "PDF417 barcode generated by the tutorial code"){: .align-center alt="Vygenerovaný PDF417 čárový kód uložený jako PNG"}

> **Očekávaný výstup:** PNG soubor o velikosti přibližně 200 × 100 px (v závislosti na nastavení sloupců/řádků), který zobrazuje jasný PDF417 vzor připravený ke skenování.

## Krok 4: Ověřte, že čárový kód funguje

Aby byl čárový kód platný:

1. Otevřete PNG soubor v libovolném prohlížeči obrázků.  
2. Použijte aplikaci pro skenování čárových kódů na chytrém telefonu, která podporuje PDF417 (např. Google Lens, QR & Barcode Scanner).  
3. Naskenujte obrázek; aplikace by měla vrátit text *Layout demo*.

Pokud skenování selže, zkontrolujte X‑dimenzi a hodnoty sloupců/řádků — větší moduly zlepšují čitelnost na nízkorozlišovacích kamerách.

## Běžné varianty a okrajové případy

| Scénář | Úprava |
|----------|------------|
| **Více dat** (např. URL) | Zvyšte `Columns` nebo `Rows` pro ubytování dalších kódových slov. |
| **Vysoké rozlišení tisku** | Zvyšte `XDimension.Pixels` na 3‑4 px pro ostřejší čáry. |
| **Průhledné pozadí** | Použijte `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Jiný formát obrázku** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp` podle potřeby. |

Tyto varianty odpovídají na otázku **jak vygenerovat PDF417** pro různé požadavky při zachování stejné základní logiky.

## Závěr

Nyní víte, jak **vygenerovat PDF417 čárový kód**, **nastavit velikost čárového kódu** a **vykreslit čárový kód do obrázku** pomocí C#. Kompletní, spustitelný příklad vytvoří PNG soubor, který lze vložit kamkoli, kde potřebujete strojově čitelný čárový kód.

Dále prozkoumejte související témata, jako je **vkládání PNG do PDF** (vyhledejte *render barcode to PDF*), nebo **generování dalších 2‑D čárových kódů** jako QR kódy. Přizpůsobte parametry rozvržení vašemu UI designu a experimentujte s barevnými možnostmi pro branding.

Šťastné programování a nechte své čárové kódy udělat těžkou práci!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to generate PDF417 barcode in C# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}