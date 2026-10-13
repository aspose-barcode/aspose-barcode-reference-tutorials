---
category: general
date: 2026-10-02
description: Vytvořte obrázek poštovního čárového kódu v C# s Aspose.BarCode. Naučte
  se generovat čárové kódy Planet a RM4SCC, přizpůsobit vyplněné pruhy a uložit soubory
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: cs
lastmod: 2026-10-02
og_description: Vytvořte obrázek poštovního čárového kódu v C# pomocí Aspose.BarCode.
  Tento tutoriál ukazuje, jak generovat čárové kódy Planet a RM4SCC, upravit výplň
  čar a exportovat soubory PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Vytvořte obrázek poštovního čárového kódu v C# – průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit obrázek poštovního čárového kódu v C# pomocí Aspose.BarCode
url: /cs/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek poštovního čárového kódu v C# pomocí Aspose.BarCode

Pokud potřebujete **vytvořit obrázek poštovního čárového kódu** v C#, Aspose.BarCode poskytuje čisté API, které se postará o těžkou práci. Ať už budujete systém poštovních štítků nebo službu pro ověřování adres, tento průvodce vám ukáže přesně, jak generovat čárové kódy Planet a RM4SCC, přepínat mezi vyplněnými a prázdnými pruhy a exportovat výsledek jako soubory PNG.

Naučíte se, jak nastavit velikost čárového kódu, řídit chování vyplnění pruhů a uložit obrázek na disk – vše v jediném spustitelném programu. Kromě knihovny Aspose.BarCode pro .NET nejsou potřeba žádné externí nástroje.

## Požadavky

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
* Visual Studio 2022 nebo jakékoli IDE kompatibilní s C#
* Licencovaná nebo zkušební kopie **Aspose.BarCode for .NET** (k dispozici přes NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Přehled řešení

Tutoriál je rozdělen do tří logických kroků:

1. **Vytvořit Planet čárový kód s výchozími (vyplněnými) pruhy** – ukazuje typický vzhled pro poštovní služby.
2. **Vytvořit Planet čárový kód s prázdnými pruhy** – užitečné, když tiskový proces očekává nevyplněné pruhy.
3. **Vytvořit RM4SCC čárový kód s vyplněnými pruhy** – další běžný poštovní formát používaný v mnoha zemích.

Každý krok následuje stejný vzor: vytvořit instanci `BarcodeGenerator`, nastavit `XDimension` (šířka jednoho pruhu v pixelech), volitelně upravit `FilledBars` a zavolat `Save` pro zápis PNG souboru.

---

## Vytvořit obrázek poštovního čárového kódu pomocí Aspose.BarCode

Níže je kompletní, samostatný program. Uložte jej jako `Program.cs` a spusťte z příkazové řádky nebo vašeho IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Proč je každý řádek důležitý

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – Enum `EncodeTypes.Planet` říká Aspose.BarCode, aby použil symbologii *Planet*, což je standardní poštovní čárový kód v mnoha zemích. Toto je jádro toho, jak **generovat planet barcode** obrázky.
* **`XDimension.Pixels = 4`** – Šířka jednoho pruhu ovlivňuje jak spolehlivost skenování, tak vizuální velikost. Hodnota 4 px funguje dobře pro většinu tiskáren štítků; můžete ji zvýšit pro výstupy s vyšším rozlišením.
* **`FilledBars = false`** – Ve výchozím nastavení jsou pruhy vyplněny. Nastavením na `false` vytvoříte styl „prázdného pruhu“, který vyžadují některé poštovní specifikace.
* **`Save(..., BarCodeImageFormat.Png)`** – PNG zachovává bezztrátovou kvalitu, což je ideální pro obrázky čárových kódů, které musí být čteny skenery.

### Očekávaný výstup

Po spuštění programu složka `YOUR_DIRECTORY` obsahuje tři PNG soubory:

| Název souboru                         | Popis |
|--------------------------------------|--------------------|
| `PostalPlanetFilledBars.png`         | Planet čárový kód s plnými černými pruhy |
| `PostalPlanetEmptyBars.png`          | Planet čárový kód, kde jsou pruhy obrysy (prázdné) |
| `PostalRM4SCCFilledBars.png`         | RM4SCC čárový kód s plnými pruhy |

Můžete otevřít kterýkoli z těchto obrázků v prohlížeči obrázků nebo je vložit přímo do PDF/HTML štítku.

---

## Další úpravy čárového kódu (volitelné)

### Změna formátu obrázku

Pokud potřebujete jiný formát (např. JPEG pro webové doručení), nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. Mějte na paměti, že JPEG zavádí kompresní artefakty, které mohou ovlivnit výkon skeneru.

### Úprava velikosti obrázku bez škálování

Místo změny `XDimension` můžete řídit celkové rozměry obrázku pomocí `Parameters.Image.Height` a `Parameters.Image.Width`. To je užitečné, když máte pevnou velikost štítku.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Použití jiné symbologie čárového kódu

Aspose.BarCode podporuje desítky poštovních symbologií (např. **USPS Intelligent Mail**, **Japan Post**). Pro **generování planet barcode** alternativy nahraďte `EncodeTypes.Planet` požadovanou hodnotou enumu.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Zpracování neplatných dat

Poštovní čárové kódy mají přísná pravidla délky dat. Pokud předáte řetězec, který nesplňuje specifikaci, Aspose.BarCode vyhodí `ArgumentException`. Zabalte vytvoření generátoru do bloku `try/catch`, abyste poskytli uživatelsky přívětivou chybovou zprávu.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Časté úskalí a tipy pro profesionály

| Úskalí | Proč se to děje | Tip |
|--------|----------------|-----|
| **Použití příliš malé XDimension** | Pruhy se stanou tenčími než minimální rozlišení skeneru, což způsobuje chyby při čtení. | Začněte s `Pixels = 4` a testujte na cílové tiskárně; v případě potřeby zvyšte. |
| **Ukládání do složky jen pro čtení** | `Save` vyhodí `UnauthorizedAccessException`. | Ujistěte se, že `outputDir` ukazuje na zapisovatelnou lokaci, nebo použijte `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Opomenutí uvolnění generátoru** | Velké obrázky mohou držet neřízené prostředky. | Zabalte generátor do `using` bloku nebo zavolejte `Dispose()` po `Save`. |
| **Míchání formátů čárových kódů v jednom obrázku** | Některé tiskárny očekávají na štítku jedinou symbologii. | Generujte každý čárový kód samostatně a v případě potřeby je spojte pomocí grafické knihovny. |

## Ověření vygenerovaných čárových kódů

Pro potvrzení, že čárové kódy jsou platné, můžete použít zdarma dostupný web **Aspose.BarCode Demo** nebo jakoukoli standardní aplikaci pro skenování čárových kódů. Načtěte PNG soubory a naskenujte je; dekódovaná hodnota by měla být `123456` pro oba příklady Planet i RM4SCC.

## Závěr

V tomto tutoriálu jste se naučili, jak **vytvořit obrázky poštovních čárových kódů** v C# pomocí Aspose.BarCode. Viděli jste, jak **generovat planet barcode** obrázky s vyplněnými i prázdnými pruhy, jak vytvořit RM4SCC čárový kód a jak přizpůsobit velikost, formát a zpracování chyb. S kompletním, spustitelným kódem můžete nyní integrovat generování poštovních čárových kódů do jakékoli .NET aplikace.

**Další kroky**

* Prozkoumejte další poštovní symbologie, jako je `EncodeTypes.USPSIntelligentMail` (sekundární klíčové slovo: postal barcode PNG).

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit obrázek poštovního čárového kódu v C# – Kompletní průvodce krok za krokem](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Generovat poštovní čárový kód v C# – Kompletní průvodce s Planet čárovým kódem](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Jak generovat poštovní čárový kód v C# pomocí Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}