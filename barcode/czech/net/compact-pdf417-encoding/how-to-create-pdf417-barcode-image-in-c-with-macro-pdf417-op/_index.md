---
category: general
date: 2026-09-13
description: Naučte se, jak vytvořit obrázek čárového kódu PDF417 v C# pomocí BarcodeGenerator
  a možností Macro PDF417. Krok za krokem kód, tipy a kompletní příklad.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: cs
lastmod: 2026-09-13
og_description: Vytvořte obrázek čárového kódu PDF417 v C# pomocí BarcodeGenerator.
  Postupujte podle tohoto podrobného tutoriálu, jak nastavit možnosti Macro PDF417
  a uložit čárový kód jako PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Vytvořte obrázek čárového kódu PDF417 v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Jak vytvořit obrázek čárového kódu PDF417 v C# s volbami Macro PDF417
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu PDF417 v C# s možnostmi Macro PDF417

Pokud potřebujete **vytvořit obrázek čárového kódu PDF417** v C#, tento návod vám přesně ukáže, jak na to pomocí **třídy BarcodeGenerator**. Ať už budujete systém sledování dokumentů nebo kódujete velké soubory, podrobné instrukce níže pokrývají vše od nastavení možností Macro PDF417 po uložení finálního PNG.

Generování čárového kódu je jednoduché, jakmile pochopíte klíčové parametry. V tomto tutoriálu se naučíte:

* Inicializovat `BarcodeGenerator` pro **Macro PDF417**.
* Upravit velikost modulu čárového kódu (`XDimension`).
* Nakonfigurovat nastavení specifické pro segment, jako je ID souboru, ID segmentu a kontrolní součet.
* Uložit výsledek jako **formát obrázku čárového kódu** (PNG), který lze zobrazit v jakémkoli UI.

Jedinou podmínkou je vývojové prostředí .NET (Visual Studio 2022 nebo novější) a NuGet balíček Aspose.BarCode pro .NET, který poskytuje API `BarcodeGenerator` použité v příkladech.

---

## Jak vytvořit obrázek čárového kódu PDF417 v C# – přehled

Vytvoření obrázku čárového kódu PDF417 se skládá ze čtyř logických kroků:

1. **Vytvořit generátor** – vytvořit instanci `BarcodeGenerator` s `EncodeTypes.MacroPdf417` a daty, která chcete kódovat.  
2. **Definovat velikost modulu** – nastavit `XDimension.Pixels` pro kontrolu fyzické šířky každého elementu čárového kódu.  
3. **Nastavit možnosti Macro PDF417** – specifikovat sloupce, identifikátory souboru, čísla segmentů a volitelný kontrolní součet.  
4. **Uložit čárový kód** – zapsat vygenerovaný obrázek na disk pomocí podporovaného **formátu obrázku čárového kódu**, například PNG.

Každý krok je podrobně vysvětlen níže s kompletním, spustitelným C# kódem.

---

## Krok 1: Inicializace BarcodeGenerator pro Macro PDF417

První řádek vytvoří objekt `BarcodeGenerator`, který ví, že má generovat **Macro PDF417** čárový kód. Konstruktor přijímá dva argumenty: typ kódování a řetězec s daty.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Proč je to důležité:**  
`EncodeTypes.MacroPdf417` říká knihovně, aby považovala čárový kód za více‑segmentový kontejner, což je nezbytné, když potřebujete rozdělit velký soubor na několik symbolů. Instance `BarcodeGenerator` je disposable, takže blok `using` zaručuje uvolnění všech neřízených prostředků po uložení obrázku.

---

## Krok 2: Nastavení velikosti modulu čárového kódu (XDimension)

`XDimension` řídí šířku v pixelech jednoho modulu čárového kódu (nejmenší černý nebo bílý pruh). Hodnota **2 pixely** poskytuje kompaktní, ale čitelný obrázek.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktický tip:**  
Pokud má váš cílový tiskárna nízké DPI, zvyšte počet pixelů (např. `3` nebo `4`), abyste předešli rozmazání. Naopak pro zobrazení na obrazovce můžete ponechat nízkou hodnotu, aby se snížila velikost souboru.

---

## Krok 3: Konfigurace specifických možností Macro PDF417

Macro PDF417 přidává metadata, která umožňují skeneru zrekonstruovat původní soubor z více segmentů čárového kódu. Nejčastěji používané možnosti jsou:

| Property | Význam |
|----------|--------|
| `Columns` | Počet sloupců v každém symbolu (ovlivňuje šířku). |
| `MacroPdf417FileID` | Jedinečný identifikátor celého souboru. |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná 1). |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů, které tvoří soubor. |
| `MacroPdf417FileName` | Původní název souboru (volitelné, pro zobrazení). |
| `MacroPdf417Checksum` | Volitelný 16‑bitový kontrolní součet pro ověření integrity. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Proč jsou tato nastavení důležitá:**  
- **Columns** ovlivňuje čitelnost a celkové rozměry obrázku.  
- **FileID** musí být stejný ve všech segmentech, aby dekodér věděl, že patří dohromady.  
- **SegmentID** a **SegmentsCount** umožňují skeneru správně seřadit jednotlivé části.  
- **FileName** a **Checksum** jsou volitelné, ale zlepšují uživatelský zážitek a integritu dat.

**Hraniční případ:** Pokud vygenerujete více než 999 segmentů, pole `SegmentID` přeteče; v takovém případě rozdělte data do více souborů.

---

## Krok 4: Uložení vygenerovaného čárového kódu jako PNG obrázek

Poslední krok zapíše čárový kód na disk. `BarCodeImageFormat.Png` vytváří bezztrátový obrázek, který funguje na webu, desktopu i mobilních platformách.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Alternativní formáty:**  
Místo `BarCodeImageFormat.Png` můžete použít `Jpeg`, `Bmp` nebo `Gif`, pokud váš downstream systém vyžaduje konkrétní formát. Mějte na paměti, že JPEG zavádí kompresní artefakty, které mohou snížit spolehlivost skenování.

**Očekávaný výstup:**  
Soubor `MacroPdf417.png` bude obsahovat vysoce kontrastní, více‑segmentový PDF417 čárový kód. Po otevření by měl vypadat podobně jako ilustrace níže.

![Příklad vytvoření obrázku PDF417 čárového kódu](image.png){: .align-center alt="Příklad vytvoření obrázku PDF417 čárového kódu vygenerovaného kódem C#"}

---

## Kompletní zdrojový kód – připravený ke zkopírování a spuštění

Níže je kompletní, samostatný program. Obsahuje potřebné `using` direktivy, metodu `Main` a komentáře, které vysvětlují každou ne‑zřejmou řádku.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Spuštění programu:**  

1. Vytvořte nový .NET 6 (nebo novější) konzolový projekt.  
2. Přidejte NuGet balíček Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Nahraďte vygenerovaný `Program.cs` výše uvedeným kódem.  
4. Upravit `outputPath` na složku, do které máte právo zapisovat.  
5. Sestavte a spusťte – konzole potvrdí umístění obrázku.

---

## Často kladené otázky a řešení problémů

| Otázka | Odpověď |
|--------|---------|
| *Co když je čárový kód příliš široký pro mou etiketu?* | Snižte `Columns` nebo zvyšte `XDimension.Pixels`, abyste vybalancovali šířku a čitelnost. |
| *Musím nastavit kontrolní součet?* | Kontrolní součet je volitelný |

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Vytvořit PDF417 čárový kód v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Vytvořit metadata PDF417 čárového kódu v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generovat čárový kód s textem – Kompletní PDF417 Macro průvodce](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}