---
category: general
date: 2026-11-17
description: Naučte se, jak vytvořit čárový kód PDF417 v C# – kompletní průvodce,
  jak generovat čárový kód ze řetězce pomocí generátoru čárových kódů v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: cs
lastmod: 2026-11-17
og_description: Vytvořte PDF417 čárový kód v C# rychle. Tento tutoriál ukazuje, jak
  vygenerovat čárový kód ze řetězce pomocí generátoru čárových kódů v C# a obsahuje
  kompletní zdrojový kód.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Vytvořte čárový kód PDF417 v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Jak vytvořit PDF417 čárový kód v C# pomocí generátoru čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód PDF417 v C# pomocí generátoru čárových kódů

Pokud potřebujete **vytvořit čárový kód PDF417** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Naučíte se **jak generovat čárový kód** z prostého řetězce, nakonfigurovat velikost symbolu a uložit výsledek jako PNG soubor – vše pomocí spolehlivého generátoru čárových kódů v C#.

Programové generování čárových kódů odstraňuje ruční kroky a zajišťuje konzistentní kvalitu. V tomto tutoriálu pokryjeme vše od nastavení projektu až po finální obrázek, takže můžete dnes integrovat tvorbu čárových kódů do jakéhokoli C# řešení.

## Požadavky

* .NET 6.0 SDK nebo novější (kód funguje s .NET Core a .NET Framework)
* Visual Studio 2022 (nebo jakékoli IDE podporující C#)
* Licence nebo bezplatná zkušební verze **Aspose.BarCode for .NET** – knihovna použitá v příkladech
* Základní znalost syntaxe C#

Žádné další balíčky nejsou potřeba; NuGet balíček `Aspose.BarCode` obsahuje všechny třídy, které budete potřebovat.

## Krok 1 – Nastavení generátoru čárových kódů v C#

Prvním krokem, který uděláte při **vytváření čárového kódu PDF417**, je vytvořit instanci objektu `BarcodeGenerator`. Tento objekt představuje **c# generátor čárových kódů**, který bude zajišťovat kódování, vykreslování a ukládání.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Proč je to důležité*: Výčtový typ `EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417, což je stejný standard používaný pro identifikační karty a přepravní štítky. Řetězec `"(01)12345678901234"` je příklad **generování čárového kódu z řetězce**, který také ukazuje, jak **vytvořit GS1 čárový kód** data.

## Krok 2 – Nastavení X‑dimenze (šířka modulu)

X‑dimenze určuje šířku nejmenšího pruhu (modulu). Běžná hodnota pro vykreslování na obrazovce je 2 pixely.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Explicitní nastavení X‑dimenze zabraňuje generátoru použít výchozí hodnotu, která by mohla vytvořit čárový kód příliš malý pro některé skenery.

## Krok 3 – Definování počtu sloupců

PDF417 vám umožňuje upravit počet sloupců, což ovlivňuje jak tvar čárového kódu, tak kapacitu dat. Pro kompaktní štítek dobře fungují čtyři sloupce.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Pokud potřebujete vyšší čárový kód, zvyšte počet sloupců; knihovna automaticky vypočítá potřebný počet řádků.

## Krok 4 – Uložení čárového kódu jako obrázek

Nakonec exportujte čárový kód do PNG souboru. PNG zachovává ostré hrany a podporuje průhlednost.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Spuštěním programu se vytvoří `output/Gs1Pdf417.png`. Otevřete soubor v libovolném prohlížeči obrázků – uvidíte čistý **PDF417 čárový kód**, který kóduje GS1 data, která jste zadali.

### Očekávaný výstup

![Vygenerovaný PDF417 čárový kód zobrazující GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Vygenerovaný PDF417 čárový kód vytvořený pomocí generátoru čárových kódů v C#"}

*Obrázek výše ukazuje výsledek kompletního ukázkového kódu. Čárový kód lze načíst libovolným čtečkou kompatibilní s PDF417.*

## Další možnosti a běžné varianty

### Změna formátu obrázku

Pokud dáváte přednost JPEG nebo BMP, stačí nahradit `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp`. Zbytek kódu zůstane stejný.

### Úprava úrovně korekce chyb

PDF417 podporuje úrovně korekce chyb 0‑8. Vyšší úrovně zvyšují redundanci, ale také zvětšují čárový kód.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generování dalších GS1 čárových kódů

Stejný `BarcodeGenerator` může vytvořit **vytvořit GS1 čárový kód** pro jiné symbologie, jako jsou `EncodeTypes.Gs1DataMatrix` nebo `EncodeTypes.Gs1Qr`. Stačí vyměnit hodnotu výčtu:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Zpracování prázdných nebo null dat

Když **generujete čárový kód z řetězce**, vždy ověřte vstup:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Tím se zabrání výjimkám za běhu a zajistí, že čárový kód splňuje pravidla formátování GS1.

## Kompletní, spustitelný příklad

Níže je celý program, který můžete zkopírovat a vložit do nového konzolového projektu. Obsahuje všechny potřebné `using` direktivy, vytvoření složky a ošetření chyb.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Spusťte program** (`dotnet run`) a najdete `Gs1Pdf417.png` ve složce *output*. Naskenujte jej libovolnou PDF417 čtečkou a ověřte, že GTIN `(01)12345678901234` je správně zakódován.

## Často kladené otázky

**Q: Mohu tento kód použít na .NET Framework 4.6?**  
A: Ano. Knihovna Aspose.BarCode cílí na .NET Standard 2.0, který je kompatibilní s .NET Framework 4.6 a novějším.

**Q: Co když potřebuji obrázek s vyšším rozlišením?**  
A: Nastavte vlastnost `Resolution` před uložením:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Je čárový kód stále platný bez identifikátoru aplikace GS1?**  
A: Bude to standardní PDF417 čárový kód, ale nebude rozpoznán jako symbol vyhovující GS1. Přidejte předponu `(01)`, když potřebujete **vytvořit GS1 čárový kód** soulad.

## Závěr

Nyní víte, jak **vytvořit PDF417 čárový kód** v C# pomocí robustního **c# generátoru čárových kódů**. Tutoriál pokryl:

* Instanciaci `BarcodeGenerator` s GS1 daty
* Nastavení X‑dimenze a počtu sloupců
* Uložení výsledku jako PNG obrázek
* Rozšíření řešení o korekci chyb, různé formáty a validaci vstupu

S tímto základem můžete generovat libovolný PDF417 nebo GS1 čárový kód přímo z řetězce, vložit jej do reportů nebo odeslat do tiskáren. Prozkoumejte Aspose.BarCode API a přidejte barvy, okraje nebo kombinujte více čárových kódů do jednoho obrázku.

**Další kroky**: zkuste generovat **vytvořit GS1 čárový kód** pro DataMatrix, experimentujte s dynamickým výpočtem sloupců nebo integrujte generátor do ASP.NET Core webové služby, která na vyžádání vrací obrázky čárových kódů.

Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód v C# – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Jak vytvořit micro PDF417 čárový kód a generovat PNG v C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Jak vytvořit macro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}