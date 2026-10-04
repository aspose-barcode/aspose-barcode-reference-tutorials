---
category: general
date: 2026-10-04
description: Rychle vytvořte čárový kód PDF417 v C#. Naučte se, jak generovat čárový
  kód PDF417 a jak uložit obrázek čárového kódu jako PNG pomocí Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Vytvořte čárový kód PDF417 v C# s Aspose.Barcode. Tento tutoriál vám
  ukáže, jak generovat kompaktní čárový kód PDF417, nastavit jeho vzhled a uložit
  jej jako PNG obrázek pro mobilní skenování nebo tisk štítků.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Vytvořte čárový kód PDF417 v C# – kompletní průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-04'
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
- Aspose.Barcode
title: Vytvořte čárový kód PDF417 v C# – průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte čárový kód PDF417 v C# – krok za krokem

Pokud potřebujete **vytvořit čárový kód PDF417** v aplikaci .NET, tento průvodce vám ukáže, jak přesně vygenerovat čárový kód PDF417 a jak uložit obrázek čárového kódu jako soubor PNG. Výsledkem bude kompaktní obrázek, který se skvěle hodí pro mobilní skenování, systémy vstupenek nebo tiskárny štítků.

## Rychlé odpovědi
- **Která knihovna zajišťuje generování PDF417?** Aspose.Barcode for .NET.  
- **Do jakého formátu vzorek ukládá?** PNG, pomocí `BarCodeImageFormat.Png`.  
- **Kolik řádků kódu je potřeba?** Přibližně 10 řádků po nastavení projektu.  
- **Mohu přizpůsobit velikost a zkrácení?** Ano – vlastnosti `Columns`, `Rows` a `Truncate`.  
- **Je kód kompatibilní s .NET‑6?** Ano, plně, a také funguje s .NET Framework 4.7+.

## Co potřebujete k vytvoření čárového kódu PDF417 v C#?
Na začátek potřebujete aktuální .NET SDK, IDE jako Visual Studio 2022 a **Aspose.Barcode for .NET** NuGet balíček. Tyto nástroje umožní, aby se ukázkový kód zkompiloval a spustil bez další konfigurace.

- .NET 6.0 SDK nebo novější (funguje také s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakýkoli editor podporující C#
- Přístup k internetu pro stažení NuGet balíčku Aspose.Barcode

## Jak nastavit .NET projekt pro generování čárového kódu PDF417?
Vytvořte nový konzolový projekt, přidejte balíček Aspose.Barcode a otevřete vygenerovaný `Program.cs`. Tím připravíte čisté pracovní prostředí, kde můžete vytvořit generátor čárových kódů a zapsat výstupní soubor.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Jak můžete vygenerovat čárový kód PDF417 pomocí Aspose.Barcode?
`BarcodeGenerator` je třída Aspose.Barcode, která vytváří obrázky čárových kódů z poskytnutých dat a symbologie. Zvolíte symbologii PDF417, zadáte text k zakódování a případně upravíte velikost nebo nastavení korekce chyb.

```bash
   dotnet add package Aspose.Barcode
   ```

### Proč je to důležité
* **EncodeTypes.Pdf417** říká knihovně, aby použila standard PDF417, který podporuje velké objemy dat a korekci chyb.
* Poskytnutí Unicode znaků dokazuje, že generátor zvládá vstup mimo ASCII bez další konfigurace.

## Jak nakonfigurovat vzhled čárového kódu PDF417?
Můžete řídit velikost modulu, počet sloupců a zda čárový kód používá kompaktní (zkrácený) režim. Tato nastavení přímo ovlivňují čitelnost na malých obrazovkách a celkovou velikost souboru PNG.

`generator.Parameters.Barcode.XDimension` nastavuje šířku jednoho modulu, zatímco `Columns` a `Rows` definují rozměry matice. Nastavením `Truncate` na `true` odstraníte tiché zóny pro kompaktnější obrázek.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Praktický tip
Pokud potřebujete vyšší čárový kód při omezeném horizontálním prostoru, zvyšte `Columns`. Nastavení `Truncate` na `true` snižuje celkovou výšku odstraněním tichých zón, což je ideální pro mobilní obrazovky.

## Jak uložit obrázek čárového kódu jako PNG?
`Save` je metoda třídy `BarcodeGenerator`, která zapíše vygenerovaný obrázek do souboru. Předáte cestu k souboru a `BarCodeImageFormat.Png` a vytvoříte PNG obrázek v jediném kroku.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Očekávaný výsledek
Spuštěním programu se v adresáři projektu vytvoří soubor `CompactPdf417.png`. Otevřením souboru uvidíte kompaktní PDF417 čárový kód, který kóduje řetězec *Åspóse.Barcóde©*. Obrázek lze vložit do HTML, PDF reportů nebo vytisknout na štítky.

## Jak můžete ověřit vygenerovaný soubor čárového kódu?
Po dokončení programu můžete rychlým příkazem ověřit, že soubor existuje. Tento jednoduchý kontrolní krok potvrzuje, že generování a uložení proběhly bez chyb.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Pokud se soubor objeví, proces **vytvoření čárového kódu PDF417** byl úspěšný.

## Jaké jsou běžné varianty a okrajové případy při generování čárových kódů PDF417?
Různé scénáře mohou vyžadovat úpravy nastavení generátoru. Níže je rychlá referenční tabulka, která ukazuje, jak řešit typické varianty.

| Situace | Úprava |
|-----------|------------|
| **Delší datový řetězec** | Zvyšte `Columns` nebo nastavte `Rows` tak, aby pojmuly více kódových slov. |
| **Jiný formát obrázku** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. |
| **Vyšší rozlišení** | Nastavte `generator.Parameters.ImageResolution` před voláním `Save`. |
| **Barva pozadí** | Použijte `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Zpracování výjimek** | Zabalte `generator.Save` do bloku `try/catch` pro zachycení I/O chyb. |

Tyto varianty vám umožní přizpůsobit čárový kód konkrétním zařízením nebo požadavkům na značku.

## Jaký je další krok po vytvoření čárového kódu?
Nyní, když můžete generovat a ukládat PDF417 čárový kód, můžete prozkoumat související možnosti, jako je generování QR kódů, vkládání čárových kódů do PDF dokumentů nebo přizpůsobení barev pro sladění se značkou. Všechny tyto funkce používají stejnou API `BarcodeGenerator`, takže můžete rozšířit ukázku s minimálním úsilím.

## Související návody
- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Často kladené otázky

**Q: Mohu tento kód použít ve webové aplikaci?**  
A: Ano. Stejná třída `BarcodeGenerator` funguje v projektech ASP.NET, MVC nebo Blazor; stačí zajistit, aby server měl oprávnění k zápisu do výstupní složky.

**Q: Podporuje Aspose.Barcode i jiné 2‑D symbologie?**  
A: Rozhodně. Podporováno je více než 30 typů 2‑D čárových kódů, včetně QR, DataMatrix a Aztec.

**Q: Jak velký čárový kód mohu vytvořit?**  
A: PDF417 může zakódovat až 1 850 znaků v jednom symbolu; můžete také rozdělit data do více řádků úpravou `Rows` a `Columns`.

**Q: Je licence vyžadována pro produkční použití?**  
A: Ano. K vyzkoušení je k dispozici bezplatná zkušební verze, ale pro nasazení do produkce je potřeba komerční licence.

**Q: Jaké verze .NET jsou kompatibilní?**  
A: Aspose.Barcode podporuje .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6/7.

---

**Poslední aktualizace:** 2026-10-04  
**Testováno s:** Aspose.Barcode 24.11 for .NET  
**Autor:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
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
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}