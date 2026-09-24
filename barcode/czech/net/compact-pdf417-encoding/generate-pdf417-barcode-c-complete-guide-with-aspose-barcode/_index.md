---
category: general
date: 2026-08-03
description: Generujte čárový kód PDF417 v C# pomocí Aspose.BarCode. Naučte se krok
  za krokem, jak přidat metadata Macro PDF417 a uložit jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: cs
lastmod: 2026-08-03
og_description: Generujte čárový kód PDF417 v C# pomocí Aspose.BarCode. Tento tutoriál
  ukazuje, jak vložit metadata Macro PDF417 a exportovat výsledek jako PNG obrázek.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Generování čárového kódu PDF417 v C# – krok za krokem tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Generování PDF417 čárového kódu v C# – kompletní průvodce s Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu C# – kompletní průvodce

Pokud potřebujete **generovat PDF417 čárový kód C#** pro logistický nebo dokumentační systém, tento tutoriál vám přesně ukáže, jak to provést pomocí Aspose.BarCode. Uvidíte, jak nakonfigurovat čárový kód, vložit metadata Macro PDF417 a uložit výsledek jako PNG obrázek během několika řádků kódu.

Generování PDF417 čárového kódu v C# často znamená zpracování dalších informací, jako jsou identifikátory souborů, čísla segmentů nebo časová razítka. Tento průvodce pokrývá tyto detaily, takže nemusíte prohledávat roztříštěnou dokumentaci. Na konci článku budete mít připravený program, který vytváří kompatibilní obrázek Macro PDF417 čárového kódu.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+)
- Aspose.BarCode pro .NET (v23.9 nebo novější) – nainstalujte přes NuGet `Install-Package Aspose.BarCode`
- Vývojové prostředí jako Visual Studio 2022 nebo Visual Studio Code
- Základní znalost syntaxe C#

> **Tip:** Používejte nejnovější verzi Aspose.BarCode, abyste získali opravy chyb a podporu nejnovějších specifikací PDF417.

## Jak generovat PDF417 čárový kód C# pomocí Aspose.BarCode

Proces se skládá ze čtyř logických kroků. Každý krok je uzavřen v přehledném bloku kódu, takže jej můžete okamžitě zkopírovat, vložit a spustit.

### Krok 1: Vytvořte generátor Macro PDF417 čárového kódu

Nejprve vytvořte instanci `BarcodeGenerator` s výčtem `EncodeTypes.MacroPdf417`. Konstruktor také přijímá text, který chcete zakódovat – v tomto příkladu používáme řetězec obsahující Unicode znaky pro demonstraci podpory plné šířky.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Proč je to důležité*: Typ `MacroPdf417` říká Aspose.BarCode, aby symbol považoval za makro čárový kód, který může nést další metadata na úrovni souboru. Bez tohoto příznaku by později nastavená pole byla ignorována.

### Krok 2: Upravit základní vzhled čárového kódu

Dále definujte vizuální velikost čárového kódu. `XDimension.Pixels` řídí šířku jednoho modulu (nejmenšího černobílého čtverce), zatímco `Pdf417.Columns` ovlivňuje celkový tvar nastavením počtu sloupců.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Proč je to důležité*: Menší `XDimension` poskytuje vyšší rozlišení obrázku, což je užitečné, když je čárový kód skenován ze obrazovky. Změna počtu sloupců může pomoci umístit čárový kód do omezeného prostoru, aniž by se snížila kapacita dat.

### Krok 3: Vyplnit metadata Macro PDF417

Macro PDF417 vám umožňuje vložit informace na úrovni souboru, na které se spoléhá mnoho back‑office systémů (např. ID souboru, ID segmentu, časové razítko). Následující vlastnosti ilustrují nejčastější pole.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Proč je to důležité*: Každé pole přímo mapuje na segment specifikace makro čárového kódu. Například `MacroPdf417FileID` jednoznačně identifikuje logický soubor, zatímco `MacroPdf417SegmentsCount` říká skeneru, kolik částí má očekávat. Poskytnutí přesných metadat zajišťuje, že následné systémy dokážou originální dokument bez chyby zrekonstruovat.

### Krok 4: Uložit obrázek čárového kódu jako PNG

Nakonec zavolejte `Save`, aby se čárový kód zapsal na disk. PNG je bezztrátový formát, což ho činí ideálním pro skenování vysoké kvality.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Proč je to důležité*: Výčet `BarCodeImageFormat.Png` zaručuje, že výstupní soubor obsahuje přesně ty pixelové údaje, které jste nakonfigurovali. Pokud potřebujete vektorový formát pro škálování, nahraďte `Png` za `Svg` – Aspose.BarCode to podporuje přímo z krabice.

#### Očekávaný výstup

Spuštěním kompletního programu se vytvoří soubor pojmenovaný **ExtPDF417Meta.png**. Obrázek zobrazuje hustý, víceřádkový PDF417 symbol, který obsahuje text “Åspóse.Barcóde©” a makro metadata, jež jste zadali. Skenování čárového kódu pomocí PDF417‑kompatibilního čtečky vrátí původní text plus strukturovaný datový blok obsahující ID souboru, ID segmentu, časové razítko a další pole.

![Snímek vygenerovaného PDF417 čárového kódu](/images/pdf417-example.png){: .center-image alt="vygenerovat PDF417 čárový kód C# příklad výstupu"}

## Kompletní zdrojový kód (připravený ke kopírování)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Jak ověřit výsledek

1. Otevřete `ExtPDF417Meta.png` v libovolném prohlížeči obrázků.  
2. Použijte aplikaci pro skenování PDF417 (např. *Zebra Scanner* nebo *BarCode Reader* na Androidu/iOS).  
3. Potvrďte, že dekódované data obsahují původní text a blok podobný JSON s makro poli, která jste nastavili.

## Časté otázky a řešení okrajových případů

| Otázka | Odpověď |
|----------|--------|
| **Mohu generovat vektorový obrázek místo PNG?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg`. Zbytek kódu zůstane beze změny. |
| **Co když moje data překročí výchozí kapacitu?** | Zvyšte `Pdf417.Columns` nebo nastavte `Pdf417.Rows` ručně. Větší hodnoty umožňují více kódových slov na segment. |
| **Je Unicode podporováno v kódovaném textu?** | Ano. Příklad používá “Åspóse.Barcóde©”. Aspose.BarCode automaticky přepne na kódování UTF‑8, pokud je to potřeba. |
| **Potřebuji podepsat licenci pro Aspose.BarCode?** | Pro produkční nasazení byste měli použít licenci, aby se odstranila vodotisková značka z hodnocení. Zavolejte `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` před vytvořením generátoru. |
| **Jak zachytit chyby při ukládání souboru?** | Zabalte volání `Save` do bloku try/catch a zaznamenejte `IOException` nebo `BarCodeException` pro odstraňování problémů. |

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód C#** pomocí Aspose.BarCode, vložit kompletní metadata Macro PDF417 a exportovat výsledek jako vysoce kvalitní PNG obrázek. Kroky – vytvoření generátoru, úprava vzhledu, vyplnění metadat a uložení obrázku – tvoří znovupoužitelný vzor, který můžete přizpůsobit pro faktury, přepravní štítky nebo jakýkoli scénář vyžadující bohatá data v čárovém kódu.

### Další kroky

- Experimentujte s dalšími formáty čárových kódů (např. QR, Code128) změnou `EncodeTypes`.  
- Prozkoumejte `Pdf417.ErrorCorrectionLevel` pro zlepšení spolehlivosti skenování při špatném osvětlení.  
- Integrujte vygenerovaný obrázek do PDF zprávy pomocí Aspose.PDF pro kompletní automatizaci dokumentů.  

Neváhejte upravit pole metadat tak, aby odpovídala vašim obchodním pravidlům, a nechte generování čárových kódů stát se plynulou součástí vašich C# aplikací. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java knihovna čárových kódů – Přidat čárový kód do PDF pomocí Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}