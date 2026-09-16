---
category: general
date: 2026-09-16
description: Naučte se, jak generovat čárový kód a nastavit jeho velikost v C#. Krok
  za krokem průvodce s použitím Aspose.BarCode k vytvoření obrázku Micro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: cs
lastmod: 2026-09-16
og_description: Jak generovat čárový kód v C# a nastavit velikost čárového kódu pomocí
  Aspose.BarCode. Sledujte tento stručný návod k vytvoření Micro PDF417 PNG.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Jak generovat čárový kód v C# – kompletní průvodce Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak vygenerovat čárový kód v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód v C# pomocí Aspose.BarCode

Pokud potřebujete vědět **jak generovat čárový kód** v .NET projektu, tento tutoriál vás provede celým procesem pomocí knihovny Aspose.BarCode. Také se naučíte, jak **nastavit velikost čárového kódu**, aby obrázek odpovídal vašemu UI nebo požadavkům na tisk.

Průvodce pokrývá vše od instalace NuGet balíčku po konfiguraci symbolu Micro PDF417 a jeho uložení jako PNG souboru. Na konci budete mít spustitelný ukázkový kód, který můžete vložit do libovolné C# konzole nebo webové aplikace.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)
- Visual Studio 2022 nebo jakékoli IDE podporující C#
- Přístup k internetu pro stažení **Aspose.BarCode** NuGet balíčku  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Základní znalost syntaxe C#

## Jak generovat čárový kód pomocí Aspose.BarCode

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která ví, jakou symbologii použít a jaká data kódovat.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Proč je to důležité:** `EncodeTypes.MicroPdf417` říká knihovně, aby vytvořila kompaktní variantu PDF417, ideální pro malé štítky nebo otisky podobné QR kódu. Řetězec `"Micro data"` se stane lidsky čitelným nákladem vloženým do čárového kódu.

## Nastavte velikost a rozměry čárového kódu

Čitelný čárový kód musí mít správný rozměr modulu (X) a dostatek sloupců pro uložení dat. Zde **nastavíte velikost čárového kódu**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** řídí šířku nejmenšího pruhu (tzv. „modulu“). Hodnota `2` pixely funguje dobře pro zobrazení na obrazovce; zvýšte ji pro tisk ve vysokém rozlišení.
- **Pdf417.Columns** omezuje počet vertikálních sloupců. Formát Micro PDF417 podporuje maximálně 7 sloupců; `4` poskytuje vyváženou velikost bez ztráty kapacity dat.

> **Tip:** Pokud vygenerovaný obrázek vypadá příliš malý, zvyšte `XDimension.Pixels` na `3` nebo `4`. Naopak, pokud máte málo místa v UI, můžete ji snížit na `1`, ale ujistěte se, že skener, který plánujete použít, dokáže symbol stále přečíst.

## Uložte obrázek čárového kódu

Po nastavení velikosti jednoduše instruujete generátor, aby obrázek zapsal na disk.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Metoda `Save` přijímá libovolný formát podporovaný Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG je bezztrátový, zachovává ostré hrany potřebné pro spolehlivé skenování.

**Očekávaný výstup:** Soubor s názvem `micro.png` se objeví v pracovním adresáři projektu. Po otevření zobrazí malý, vysoce kontrastní Micro PDF417 čárový kód připravený k testování s libovolným standardním skenerem.

## Kompletní příklad

Sestavením všech částí dohromady získáte samostatný program, který můžete spustit okamžitě.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Spusťte program (`dotnet run` z konzole) a uvidíte potvrzovací zprávu. Vygenerovaný PNG lze vložit do reportů, vytisknout na produktové štítky nebo zobrazit na webové stránce.

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|---|---|
| **Mohu generovat jiné typy čárových kódů?** | Ano. Nahraďte `EncodeTypes.MicroPdf417` libovolnou hodnotou z výčtu `EncodeTypes` (např. `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Co když potřebuji větší obrázek?** | Zvyšte `XDimension.Pixels` nebo použijte `generator.Parameters.Image.Width/Height` k vynucení konkrétní velikosti v pixelech. |
| **Podporuje knihovna průhledná pozadí?** | Nastavte `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` před voláním `Save`. |
| **Jak načíst čárový kód zpět?** | Použijte `Aspose.BarCode.BarCodeReader` na uloženém obrázku; automaticky detekuje symbologii. |
| **Je PNG vhodný pro tisk?** | PNG je bezztrátový, ale pro CMYK tisk zvažte uložení jako TIFF (`BarCodeImageFormat.Tiff`). |

## Závěr

Nyní víte **jak generovat čárový kód** v C# a jak **nastavit velikost čárového kódu** pomocí Aspose.BarCode. Kompletní příklad demonstruje vytvoření symbolu Micro PDF417, úpravu jeho rozměrů a export PNG souboru. S tímto základem můžete zkoumat další symbologie, přizpůsobovat barvy nebo integrovat generování čárových kódů do služeb ASP.NET Core.

### Další kroky

- Zkuste vygenerovat QR kód (`EncodeTypes.QR`) a porovnat velikosti modulů.  
- Experimentujte s `generator.Parameters.Image` pro přidání okrajů nebo změnu DPI pro tiskové výstupy.  
- Kombinujte generování čárových kódů s **Aspose.PDF** pro vložení obrázku přímo do PDF reportu.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat obrázek PDF417 čárového kódu v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak vygenerovat PDF417 čárový kód s Aspose – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak vygenerovat čárový kód v C# – Kompletní průvodce Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}