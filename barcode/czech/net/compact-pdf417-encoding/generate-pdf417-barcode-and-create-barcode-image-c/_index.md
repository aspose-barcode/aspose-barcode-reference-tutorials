---
category: general
date: 2026-10-08
description: Vytvořte čárový kód PDF417 v C# a naučte se, jak efektivně generovat
  obrázky PDF417 pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: cs
lastmod: 2026-10-08
og_description: Generujte čárový kód PDF417 v C# s podrobným návodem krok za krokem.
  Naučte se, jak generovat PDF417 a uložit obrázek čárového kódu jako PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Generujte čárový kód PDF417 a vytvořte jeho obrázek v C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Generovat PDF417 čárový kód a vytvořit obrázek čárového kódu v C#
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu a vytvoření obrázku čárového kódu C#

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který vytvoří čárový kód, přizpůsobí jeho rozložení a uloží výsledek jako PNG obrázek.

Generování PDF417 čárového kódu je běžnou požadavkem pro přepravní štítky, palubní vstupenky a systémy inventarizace. Na konci tohoto průvodce budete schopni **generovat PDF417** s detailní kontrolou nad velikostí a rozložením a také se naučíte **vytvořit obrázek čárového kódu C#**, který lze zobrazit v uživatelském rozhraní nebo odeslat na tiskárnu.

## Požadavky

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7.2+)
- Visual Studio 2022 nebo jakékoli IDE kompatibilní s C#
- Aspose.BarCode pro .NET (zdarma zkušební verze nebo licencovaná verze)  
  Nainstalujte jej pomocí NuGet:

```bash
dotnet add package Aspose.BarCode
```

Žádná další konfigurace není vyžadována; knihovna interně zpracovává PNG kódování.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte nový konzolový projekt a přidejte potřebné `using` direktivy. Tento blok obsahuje vše, co potřebujete ke kompilaci příkladu.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Proč je tento krok důležitý*: Import jmenného prostoru `Aspose.BarCode.Generation` vám poskytuje přístup k `BarcodeGenerator`, `EncodeTypes` a parametrickým objektům používaným k přizpůsobení čárového kódu.

## Krok 2: Generování PDF417 čárového kódu s požadovaným textem

V metodě `Main` vytvořte instanci `BarcodeGenerator` s `EncodeTypes.Pdf417`. Konstruktor přijímá typ čárového kódu a text, který chcete zakódovat.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Vysvětlení*: `EncodeTypes.Pdf417` říká knihovně, aby vytvořila symbologii PDF417. Řetězec `"Layout demo"` se stane datovým nákladem zakódovaným v čárovém kódu.

## Krok 3: Jemné doladění velikosti čárového kódu pomocí X‑dimenze

X‑dimenze řídí šířku jednoho modulu (nejmenšího černobílého čtverce). Nastavení v pixelech poskytuje přesnou kontrolu nad konečnou velikostí obrázku.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Proč je to důležité*: Menší X‑dimenze vede k kompaktnějšímu čárovému kódu, což je užitečné, když máte omezený prostor na štítku nebo v UI prvku.

## Krok 4: Přizpůsobení rozložení PDF417 (sloupce a řádky)

PDF417 vám umožňuje určit počet sloupců a řádků. Úprava těchto hodnot mění poměr stran čárového kódu.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Vysvětlení*: Se 4 sloupci a 9 řádky se čárový kód stane vyšším než širokým, což odpovídá mnoha formátům tisku vstupenek.

## Krok 5: Uložení vygenerovaného čárového kódu jako PNG obrázek

Nakonec zapište čárový kód do souboru. Výčtový typ `BarCodeImageFormat.Png` zajišťuje bezztrátovou kompresi.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Co se zde děje*: `Save` vytvoří soubor obrázku na disku. Můžete nahradit `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp`, pokud je vyžadován jiný formát.

### Kompletní příklad v jednom bloku

Níže je kompletní, připravený k spuštění program. Nahraďte `YOUR_DIRECTORY` skutečnou cestou ke složce na vašem počítači.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Spusťte program (`dotnet run`) a otevřete vzniklý soubor `LayoutPdf417.png`. Měli byste vidět čistý PDF417 čárový kód, který kóduje text *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Vygenerovaný PDF417 čárový kód uložený jako PNG"}

*Očekávaný výstup*: PNG soubor o rozměrech přibližně 150 × 300 pixelů (velikost se mění podle X‑dimenze) obsahující skenovatelný PDF417 čárový kód.

## Běžné varianty a okrajové případy

| Scénář | Jak přizpůsobit kód |
|--------|--------------------|
| **Různé datové zatížení** | Změňte druhý argument `BarcodeGenerator` (`"Layout demo"` → libovolný řetězec, až 1 800 znaků). |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` (např. `4`) nebo nastavte `Resolution` pomocí `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Průhledné pozadí** | Použijte `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Vložení do Windows Forms PictureBox** | Místo `Save` zavolejte `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Zpracování chyb** | Zabalte kód generování do bloku `try…catch` pro zachycení `BarCodeException` při nepodporovaných znacích. |

## Profesionální tipy

- **Ověřte čárový kód**: Po uložení můžete načíst PNG pomocí SDK čtečky čárových kódů a ověřit, že data odpovídají původnímu řetězci.
- **Výkon**: Opětovné použití jedné instance `BarcodeGenerator` pro více čárových kódů snižuje režii alokace.
- **Bezpečnost**: Pokud zakódovaná data obsahují citlivé informace, zvažte jejich šifrování před předáním generátoru.

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód** v C# a **vytvořit soubory obrázku čárového kódu C#**, které splňují požadavky na vlastní rozložení. Kompletní příklad ukazuje inicializaci generátoru, ladění velikosti a rozložení a uložení výsledku jako PNG. Odtud můžete prozkoumat další funkce, jako je přizpůsobení barev, vkládání log, nebo hromadné generování více čárových kódů pro masový tisk.

---

*Další kroky*:
- Experimentujte s dalšími symbologií (Code128, QR) pomocí stejné třídy `BarcodeGenerator`.
- Naučte se číst PDF417 čárové kódy pomocí `BarCodeReader` z Aspose.BarCode.
- Integrujte vygenerovaný PNG do pohledů ASP.NET Core MVC pro dynamické vykreslování čárových kódů.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak uložit čárový kód a generovat PDF417 s Aspose v C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Jak generovat PDF417 čárový kód s Aspose – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generovat PDF417 čárový kód v C# s vlastními rozměry](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}