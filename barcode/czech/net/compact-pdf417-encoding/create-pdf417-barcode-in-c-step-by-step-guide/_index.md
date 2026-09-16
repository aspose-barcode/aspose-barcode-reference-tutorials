---
category: general
date: 2026-08-03
description: Rychle vytvořte čárový kód PDF417 v C#. Naučte se, jak generovat čárový
  kód PDF417 a jak uložit obrázek čárového kódu jako PNG pomocí Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: cs
lastmod: 2026-08-03
og_description: Vytvořte čárový kód PDF417 v C# pomocí Aspose.Barcode. Postupujte
  podle tohoto návodu k vygenerování čárového kódu PDF417 a k efektivnímu uložení
  obrázku čárového kódu.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Vytvořte PDF417 čárový kód v C# – kompletní programovací tutoriál
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Vytvořte čárový kód PDF417 v C# – průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu PDF417 v C# – krok za krokem

Pokud potřebujete **vytvořit čárový kód PDF417** v .NET aplikaci, tento návod vám přesně ukáže, jak vygenerovat čárový kód PDF417 a jak uložit obrázek čárového kódu. Výsledkem bude soubor PNG, který lze použít v reportech, vstupenkách nebo mobilních skenovacích aplikacích.

Návod pokrývá vše od nastavení projektu až po finální soubor PNG. Není potřeba žádná externí dokumentace; stačí postupovat podle kroků a spustit kód.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
* Visual Studio 2022 nebo jakékoli IDE podporující C#
* Přístup k internetu pro instalaci balíčku **Aspose.Barcode for .NET** NuGet

Tyto předpoklady zajišťují, že kód se zkompiluje bez další konfigurace.

## Vytvoření čárového kódu PDF417 – nastavení projektu

1. Otevřete příkazový řádek a vytvořte nový konzolový projekt:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Přidejte knihovnu Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Otevřete vygenerovaný soubor `Program.cs`. `using` direktivy v horní části vám poskytují přístup ke třídám čárových kódů:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Projekt je nyní připraven **vytvořit čárový kód PDF417**.

## Jak vygenerovat čárový kód PDF417 pomocí Aspose.Barcode

Jádro tvorby čárového kódu se nachází ve třídě `BarcodeGenerator`. Zadejte symbologii (`EncodeTypes.Pdf417`) a data, která chcete zakódovat.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Proč je to důležité

* **EncodeTypes.Pdf417** říká knihovně, aby použila standard PDF417, který podporuje velké objemy dat a korekci chyb.
* Poskytnutí Unicode znaků dokazuje, že generátor zvládá vstup mimo ASCII bez další konfigurace.

## Jak nastavit vzhled čárového kódu

Můžete řídit velikost jednotlivých modulů, počet sloupců a zda čárový kód používá kompaktní (zkrácený) režim. Tato nastavení ovlivňují jak čitelnost, tak velikost souboru.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Praktický tip

Pokud potřebujete vyšší čárový kód pro omezený horizontální prostor, zvyšte `Columns`. Nastavení `Truncate` na `true` snižuje celkovou výšku odstraněním tichých zón, což je ideální pro mobilní obrazovky.

## Jak uložit obrázek čárového kódu jako PNG

Po nastavení generátoru zavolejte `Save` s cestou k souboru a požadovaným formátem obrázku. Metoda zapíše obrázek přímo na disk.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Očekávaný výsledek

Spuštěním programu se v adresáři projektu vytvoří soubor `CompactPdf417.png`. Otevřením souboru uvidíte kompaktní PDF417 čárový kód, který kóduje řetězec *Åspóse.Barcóde©*. Obrázek lze vložit do HTML, PDF reportů nebo vytisknout na štítky.

## Kompletní zdrojový kód

Níže je kompletní spustitelný program. Zkopírujte jej do `Program.cs` a spusťte `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Ověření výstupu

Po dokončení programu můžete rychlým příkazem ověřit, že soubor existuje:

```bash
dotnet run && ls -l CompactPdf417.png
```

Pokud se soubor zobrazí, proces **vytvoření čárového kódu PDF417** byl úspěšný.

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Delší řetězec dat** | Zvyšte `Columns` nebo nastavte `Rows`, aby pojaly více kódových slov. |
| **Jiný formát obrázku** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. |
| **Vyšší rozlišení** | Nastavte `generator.Parameters.ImageResolution` před voláním `Save`. |
| **Barva pozadí** | Použijte `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Zpracování výjimek** | Zabalte `generator.Save` do bloku `try/catch` pro zachycení I/O chyb. |

Tyto varianty vám umožní přizpůsobit čárový kód konkrétním zařízením nebo požadavkům na značku.

## Závěr

Nyní víte, jak **vytvořit čárový kód PDF417** v C# pomocí Aspose.Barcode, nastavit jeho vzhled a **uložit obrázek čárového kódu** jako soubor PNG. Kompletní příklad ukazuje každý potřebný krok, od nastavení projektu až po ověření, takže můžete integraci generování čárových kódů použít v jakémkoli .NET řešení.

Dále zvažte prozkoumání souvisejících témat, jako je **jak generovat QR kódy**, **vkládání čárových kódů do PDF dokumentů** nebo **přizpůsobení barev čárových kódů**. Každé z nich staví na stejném API generátoru, což vám umožní rozšířit skenovací schopnosti vaší aplikace s minimálním úsilím. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}