---
category: general
date: 2026-07-24
description: Jednoduše upravte velikost čárového kódu v C# a zjistěte, jak generovat
  PDF417 čárové kódy pomocí Aspose.BarCode pro ostré, škálovatelné obrázky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode size
- how to generate pdf417
- Aspose.BarCode MicroPdf417
- C# barcode generation
- barcode image resolution
language: cs
lastmod: 2026-07-24
og_description: Upravte velikost čárového kódu pomocí jednoduchého příkladu v C# a
  naučte se generovat čárové kódy PDF417 pomocí Aspose.BarCode. Postupujte podle krok‑za‑krokem
  průvodce pro dokonalé výsledky.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with adjusted size in
  C#
og_title: Upravit velikost čárového kódu – průvodce C# pro generování PDF417 čárových
  kódů
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: adjust barcode size easily with C# and discover how to generate PDF417
    barcodes using Aspose.BarCode for crisp, scalable images.
  headline: adjust barcode size – C# guide to generate PDF417 barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- PDF417
title: Upravit velikost čárového kódu – C# průvodce generováním PDF417 čárových kódů
url: /cs/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# upravit velikost čárového kódu – Kompletní C# tutoriál pro generování PDF417 čárových kódů

Už jste někdy zkusili **upravit velikost čárového kódu** a skončili s rozmazanými nebo nečitelními obrázky? Nejste v tom sami. V mnoha projektech—ať už jde o systém vstupenek, tiskárnu štítků ve skladu nebo mobilní aplikaci—získání správných rozměrů pro PDF417 čárový kód může rozhodnout o úspěchu uživatelského zážitku.

Dobrá zpráva? S několika řádky C# a knihovnou Aspose.BarCode můžete **upravit velikost čárového kódu** přesně a také se naučit **jak generovat PDF417** čárové kódy, které vypadají ostře na jakékoli obrazovce. Níže najdete kompletní, spustitelný příklad spolu s vysvětlením, proč má každé nastavení význam.

## Požadavky — Co budete potřebovat

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode podporuje oba, ale novější runtime poskytují lepší výkon. |
| Visual Studio 2022 (or any IDE you prefer) | Dobré IDE vám pomůže okamžitě vidět chyby kompilace. |
| NuGet package `Aspose.BarCode` (latest version) | Jedná se o engine, který skutečně vytváří MicroPdf417 čárový kód. |
| Write permission to a folder where the PNG will be saved | Metoda `Save` vyhodí výjimku, pokud nemůže soubor zapsat. |

You can install the package from the NuGet console:

```powershell
Install-Package Aspose.BarCode
```

To je vše—žádné extra DLL soubory, žádné nativní závislosti. Jakmile je balíček na místě, jste připraveni **upravit velikost čárového kódu** a začít generovat PDF417 obrázky.

## Krok 1: Vytvořte generátor MicroPdf417 čárového kódu (jak generovat pdf417)

První věc, kterou uděláte, když chcete **jak generovat pdf417**, je vytvořit instanci `BarcodeGenerator`. Konstruktor přijímá dva argumenty: typ čárového kódu a text, který chcete zakódovat. V tomto případě používáme `EncodeTypes.MicroPdf417`, což je kompaktní varianta klasického PDF417.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and sample text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,               // Barcode type
    "Åspóse.Barcóde©");                    // Text to encode (Unicode supported)
```

> **Tip:** Text může obsahovat jakýkoli Unicode znak, ale mějte na paměti maximální kapacitu dat MicroPdf417—přibližně 150 znaků. Překročení této hodnoty automaticky přepne na plno‑velikostní PDF417, což změní rozměry.

## Krok 2: Upravit X‑dimenzi (jak upravit velikost čárového kódu)

**X‑dimenze** určuje šířku jednoho modulu (nejmenší černý nebo bílý pruh). Ve výchozím nastavení Aspose používá 3 pixely, což je často příliš hrubé pro vysoce rozlišený tisk. Nastavení na `2` pixely poskytuje jemnější mřížku bez ztráty čitelnosti.

```csharp
// Step 2: Set module width to 2 pixels for a tighter, sharper barcode
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Proč je to důležité? Menší X‑dimenze vede k vyššímu DPI při následném exportu obrázku, což se projeví ostřejšími hranami na obrazovce nebo tiskárně. Naopak, pokud potřebujete větší čárový kód pro vzdálený skener, zvyšte hodnotu na `4` nebo `5`.

## Krok 3: Vyberte počet sloupců (jak generovat pdf417)

MicroPdf417 vám umožňuje řídit rozvržení pomocí vlastnosti `Columns`. Více sloupců znamená širší, ale kratší čárový kód; méně sloupců jej dělá vyšším a užším. Pro většinu tiskáren štítků je rozvržení **4‑sloupcové** dobrá rovnováha.

```csharp
// Step 3: Define a 4‑column layout to keep the barcode compact
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

Pokud se někdy zamyslíte **jak generovat pdf417** s vlastním tvarem, stačí upravit toto číslo. Knihovna automaticky přepočítá počet řádků tak, aby odpovídal datům, takže nemusíte řádky počítat ručně.

## Krok 4: Uložit čárový kód jako PNG (jak generovat pdf417)

Nakonec zapíšeme obrázek na disk. PNG je bezztrátový formát, který zachovává přesný pixelový vzor, který jste právě doladili.

```csharp
using Aspose.BarCode;

// Step 4: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to: {outputPath}");
```

Když otevřete `MicroPdf417.png`, měli byste vidět čistý, vysoce rozlišený čárový kód, který odpovídá 2‑pixelové X‑dimenzi a 4‑sloupcovému rozvržení, které jste nastavili. Většina moderních skenerů jej přečte okamžitě, i z obrazovky.

![upravit velikost čárového kódu – ukázkový MicroPdf417 čárový kód](MicroPdf417.png "upravit velikost čárového kódu – ukázkový MicroPdf417 čárový kód")

*Popis obrázku (alt text):* **upravit velikost čárového kódu – ukázkový MicroPdf417 čárový kód vygenerovaný pomocí C#**.

## Kompletní funkční příklad (všechny kroky dohromady)

Níže je kompletní program, který můžete zkopírovat a vložit do nového projektu Console App. Obsahuje `using` direktivy, ošetření chyb a komentáře, které vysvětlují každý řádek.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the generator with MicroPdf417 and Unicode text
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417,
                    "Åspóse.Barcóde©");

                // 2️⃣ Adjust the X‑dimension for finer resolution (2 px)
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Set columns to 4 for a compact layout
                generator.Parameters.Barcode.Pdf417.Columns = 4;

                // 4️⃣ Choose where to save the PNG image
                string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
                string filePath = Path.Combine(desktop, "MicroPdf417.png");

                // 5️⃣ Save the image
                generator.Save(filePath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode generated and saved to: {filePath}");
            }
            catch (Exception ex)
            {
                // In production code you’d log this instead of writing to console
                Console.WriteLine($"❌ An error occurred: {ex.Message}");
            }
        }
    }
}
```

### Očekávaný výstup

Spuštění programu vypíše něco jako:

```
✅ Barcode generated and saved to: C:\Users\YourName\Desktop\MicroPdf417.png
```

Otevření PNG zobrazí ostrý MicroPdf417 čárový kód s přesnými rozměry, které jste zadali. Naskenujte jej libovolným PDF417 čtečkou (mobilní aplikace, skenery Zebra atd.) a získáte zpět původní řetězec `"Åspóse.Barcóde©"`.

## Časté otázky a okrajové případy

| Question | Answer |
|----------|--------|
| **Co když potřebuji větší obrázek?** | Zvyšte `XDimension.Pixels` (např. na `4`) nebo exportujte do formátu s vyšším rozlišením, jako je `BarCodeImageFormat.Tiff`. |
| **Mohu generovat plno‑velikostní PDF417 místo MicroPdf417?** | Ano—stačí nahradit `EncodeTypes.MicroPdf417` za `EncodeTypes.Pdf417`. Stejné vlastnosti `Columns` a `XDimension` stále platí. |
| **Je podpora Unicode spolehlivá?** | Ano. Aspose.BarCode interně kóduje Unicode znaky pomocí UTF‑8, ale pamatujte na limit kapacity dat MicroPdf417. |
| **Co když cílová složka neexistuje?** | `Metoda Save` vyhodí `DirectoryNotFoundException`. Zabalte volání do `try/catch` bloku (jak je ukázáno) nebo vytvořte složku pomocí `Directory.CreateDirectory`. |
| **Musím nastavit výšku čárového kódu ručně?** | Ne. Výška se automaticky vypočítá na základě počtu řádků potřebných pro data a počtu sloupců. |

## Tipy pro dokonale nastavené čárové kódy

- **Tip:** Při tisku na termální štítky nastavte DPI tiskárny na 300 dpi a ponechte `XDimension.Pixels` na `2`. To poskytuje fyzickou šířku modulu ≈0.17 mm, což většina skenerů ocení.
- **Dejte pozor na:** Překomprimování PNG (použití nízké kvality) může rozmazat hrany, čímž zruší účel jemné X‑dimenze.
- **Typická chyba:** Zapomenutí přidat `using Aspose.BarCode;` vede k chybám při kompilaci na výčtu `BarCodeImageFormat`.

## Další kroky — Mimo základy

Nyní, když znáte **upravit velikost čárového kódu** a **jak generovat PDF417**, můžete chtít prozkoumat:

- Přidání **barvy** do čárového kódu (`generator.Parameters.Barcode.Color = Color.Blue;`).
- Vložení čárového kódu přímo do PDF pomocí `Aspose.Pdf`.
- Generování **více čárových kódů** v dávkové operaci pro hromadný tisk štítků.
- Použití nastavení **úrovně opravy chyb** ke zlepšení spolehlivosti skenování v hlučném prostředí.

Každé z těchto témat staví na základních konceptech zde popsaných a stejný vzor—vytvořit generátor, upravit parametry, uložit—platí všude.

### TL;DR

Právě jste se naučili, jak **upravit velikost čárového kódu** v C# nastavením X‑dimenze a počtu sloupců, a nyní rozumíte **jak generovat PDF417** (konkrétně MicroPdf417) čárovým kódům pomocí Aspose.BarCode. Kompletní, spustitelný příklad výše vytváří ostrý PNG obrázek připravený pro jakýkoli následný workflow. Klidně experimentujte s parametry, zaměňte za plno‑velikostní PDF417 nebo integrujte kód do větší aplikace. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat čárový kód – Konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}