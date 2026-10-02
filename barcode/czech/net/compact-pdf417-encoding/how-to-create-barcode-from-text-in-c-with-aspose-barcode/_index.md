---
category: general
date: 2026-10-02
description: Vytvořte čárový kód z textu v C# pomocí Aspose.BarCode. Naučte se, jak
  generovat čárový kód PDF417, a podívejte se, jak generovat čárový kód PDF417 v kompaktním
  režimu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: cs
lastmod: 2026-10-02
og_description: Vytvořte čárový kód z textu v C# pomocí Aspose.BarCode. Tento návod
  ukazuje, jak vygenerovat čárový kód PDF417 a jak vygenerovat čárový kód PDF417 v
  kompaktním režimu.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Vytvoření čárového kódu z textu v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak vytvořit čárový kód z textu v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód z textu v C# pomocí Aspose.BarCode

Pokud potřebujete **vytvořit čárový kód z textu** v .NET aplikaci, tento průvodce vás provede kompletním procesem. Uvidíte připravený příklad, který **generuje PDF417 čárový kód** a také odpovídá na otázku **jak vygenerovat PDF417 čárový kód** v kompaktním rozložení.

Programové generování čárových kódů odstraňuje ruční kroky a zaručuje konzistenci napříč všemi dokumenty. Na konci tohoto tutoriálu budete mít PNG soubor obsahující PDF417 čárový kód, který můžete vložit do faktur, vstupenek nebo identifikačních karet.

## Co budete potřebovat

- .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.7.2+)
- Visual Studio 2022 nebo jakýkoli editor podporující C#
- NuGet licence pro **Aspose.BarCode for .NET** (pro testování stačí bezplatná zkušební verze)

> **Pro tip:** Přidejte NuGet balíček přes CLI, aby byl projekt čistý:  
> `dotnet add package Aspose.BarCode`

## Krok 1: Nastavení konzolového projektu

Vytvořte novou konzolovou aplikaci a odkažte knihovnu Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Příkaz `dotnet new console` vygeneruje soubor `Program.cs`, který nahradíme kompletním příkladem níže.

## Krok 2: Jak vytvořit čárový kód z textu – hlavní kód

Otevřete `Program.cs` a nahraďte jeho obsah následujícím kódem. Každý řádek je okomentován, aby bylo jasné, proč je potřeba.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Proč je každé nastavení důležité

| Nastavení | Účel |
|-----------|------|
| `EncodeTypes.Pdf417` | Volí symbologii PDF417, která dokáže uložit velké množství dat ve dvourozměrném matici. |
| `XDimension.Pixels = 2` | Řídí šířku každého modulu; hodnota 2 pixely poskytuje rovnováhu mezi čitelností a velikostí souboru. |
| `Pdf417.Columns = 3` | Snižuje počet sloupců, čímž činí čárový kód kompaktnějším bez ztráty dat. |
| `Pdf417.Truncate = true` | Aktivuje kompaktní režim, odstraňuje zbytečné odsazení a zkracuje čárový kód. |
| `BarCodeImageFormat.Png` | PNG zachovává bezztrátovou kvalitu, ideální pro další zpracování nebo tisk. |

## Krok 3: Generování PDF417 čárového kódu – spuštění příkladu

Sestavte a spusťte projekt:

```bash
dotnet run
```

Po dokončení běhu uvidíte:

```
Barcode saved to CompactPdf417.png
```

Otevřete `CompactPdf417.png`, abyste si prohlédli výsledek. Obrázek obsahuje PDF417 čárový kód, který kóduje řetězec **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: vytvořit čárový kód z textu – PDF417 čárový kód uložený jako PNG*

## Krok 4: Jak vygenerovat PDF417 čárový kód s vlastní korekcí chyb (volitelné)

Pokud je vaše skenovací prostředí hlučné, můžete zvýšit úroveň korekce chyb:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Zvýšení úrovně chybové korekce zvětší čárový kód, ale zlepší odolnost vůči poškození.

## Krok 5: Běžné úskalí a řešení okrajových případů

1. **Neplatné znaky** – PDF417 podporuje Unicode, ale některé starší skenery mohou odmítnout ne‑ASCII symboly. Otestujte s vaším cílovým hardwarem.
2. **Oprávnění k souborovým cestám** – Ujistěte se, že adresář, do kterého zapisujete, je zapisovatelný; jinak `Save` vyhodí `UnauthorizedAccessException`.
3. **Velikost obrázku** – Velmi vysoké hodnoty `XDimension` produkují velké PNG soubory. Pro většinu scénářů na obrazovce držte velikost pixelu mezi 1 a 4.

## Shrnutí

Nyní víte, jak **vytvořit čárový kód z textu** v C# pomocí Aspose.BarCode, jak **generovat PDF417 čárový kód** v kompaktním rozložení a přesné kroky pro **jak vygenerovat PDF417 čárový kód** s vlastními nastaveními. Kompletní, spustitelný kód výše můžete zkopírovat do libovolného .NET projektu a přizpůsobit různým vstupním textům nebo výstupním formátům (např. JPEG, BMP).

## Další kroky

- Prozkoumejte další symbologie, jako QR Code nebo Code128, změnou `EncodeTypes`.
- Integrovat vygenerovaný PNG do PDF pomocí Aspose.PDF pro end‑to‑end tvorbu dokumentů.
- Experimentujte s `generator.Parameters.Barcode.Pdf417.Rows` pro řízení vertikální hustoty.

Neváhejte upravit příklad, vložit čárový kód do vlastních aplikací a sdílet své výsledky s komunitou. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční kódové příklady s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}