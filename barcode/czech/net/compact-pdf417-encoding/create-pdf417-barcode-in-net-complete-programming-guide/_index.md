---
category: general
date: 2026-07-27
description: Rychle vytvořte čárový kód PDF417 v .NET. Naučte se, jak generovat čárový
  kód, upravit jeho velikost a použít generátor čárových kódů v .NET pro kompaktní
  výstup PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- barcode generator .net
- how to generate barcode
- adjust barcode size
- generate pdf417 barcode
language: cs
lastmod: 2026-07-27
og_description: Vytvořte dnes PDF417 čárový kód v .NET. Postupujte podle tohoto návodu,
  abyste vygenerovali čárový kód, upravili jeho velikost a ovládli generátor čárových
  kódů v .NET pro kompaktní výsledky.
og_image_alt: Screenshot showing a compact PDF417 barcode generated with .NET code
og_title: Vytvořte PDF417 čárový kód v .NET – Kompletní krok za krokem tutoriál
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create PDF417 barcode quickly with .NET. Learn how to generate barcode,
    adjust barcode size, and use a barcode generator .NET for compact PDF417 output.
  headline: Create PDF417 Barcode in .NET – Complete Programming Guide
  type: TechArticle
tags:
- barcode
- pdf417
- .net
- Aspose
title: Vytvořte PDF417 čárový kód v .NET – Kompletní programovací průvodce
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-net-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PDF417 barcode v .NET – Kompletní programovací průvodce

Už jste někdy potřebovali **vytvořit PDF417 barcode** v .NET aplikaci, ale nevedeli jste, kde začít? Nejste v tom sami — vývojáři se neustále ptají, *jak generovat barcode*, který zapadne do konkrétního rozvržení, aniž by zvětšil velikost souboru.  

V tomto tutoriálu vás provedeme praktickým příkladem, který ukazuje, jak **vytvořit PDF417 barcode** pomocí populární knihovny **barcode generator .NET**, upravit rozměry a vytvořit kompaktní PNG obrázek. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do libovolného C# projektu.

## Co se naučíte

- Nainstalovat a odkazovat na balíček **barcode generator .NET** (Aspose.BarCode)
- Nastavit enkodér **PDF417** s vlastním textem
- **Upravit velikost čárového kódu** změnou X‑dimenze a počtu sloupců
- Povolit **compact mode** (příznak `Truncate`) pro udržení malé velikosti obrázku
- Uložit výsledek jako PNG soubor a ověřit výstup

Předchozí zkušenost s čárovými kódy není vyžadována; základní znalost C# stačí. Pojďme na to.

---

## Krok 1: Připravte svůj projekt a přidejte knihovnu pro čárové kódy

Než budeme moci **vytvořit PDF417 barcode**, potřebujeme knihovnu, která umí pracovat se symbologií PDF417. Aspose.BarCode pro .NET je solidní volba, protože podporuje všechny parametry, které později upravíme.

```csharp
// Add the NuGet package (run this in the Package Manager Console)
> Install-Package Aspose.BarCode

// In your C# file, bring the namespaces into scope
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

> **Tip:** Pokud používáte .NET 6 nebo novější, můžete balíček také přidat pomocí CLI: `dotnet add package Aspose.BarCode`.

Nastavení balíčku je jednorázový krok a poté budete připraveni **generovat PDF417 barcode** na jakékoli platformě, která běží na .NET.

## Krok 2: Inicializujte PDF417 generátor s vašimi daty

Nyní, když je knihovna odkazována, můžeme vytvořit instanci `BarcodeGenerator`. Konstruktor přijímá dva argumenty: typ kódování a text, který chcete vložit. Zde skutečně **vytvoříme PDF417 barcode**.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
// Note the special characters – the library handles Unicode out of the box.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Verify that the generator was created successfully
if (generator == null)
{
    throw new InvalidOperationException("Failed to initialise the barcode generator.");
}
```

Proč je to důležité: PDF417 je vrstvený lineární čárový kód, který může uložit spoustu dat. Tím, že mu předáte Unicode, již ukazujete, že **barcode generator .NET** dokáže zpracovat mezinárodní znaky — něco, v čem mnohé starší knihovny selhávají.

## Krok 3: **Upravit velikost čárového kódu** – X‑Dimension, Columns a Compact Mode

Častým úskalím při **jak generovat barcode** je, že skončíte s obrovským obrázkem, který se nevejde na štítek nebo obrazovku. Dobrou zprávou je, že Aspose API vám poskytuje jemnou kontrolu.

```csharp
// Step 3A: Set the X‑dimension (module width) in pixels – this directly affects barcode width
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module, a good balance for most screens

// Step 3B: Configure PDF417‑specific options
generator.Parameters.Barcode.Pdf417.Columns = 3;    // Fewer columns → narrower barcode
generator.Parameters.Barcode.Pdf417.Truncate = true; // Compact mode – drops empty rows

// Optional: If you need a taller barcode, increase the rows (default is 3‑5)
generator.Parameters.Barcode.Pdf417.Rows = 5;
```

**Co se děje pod kapotou?**  
- **X‑Dimension** určuje nejmenší šířku baru. Menší hodnoty zmenší čárový kód, ale mohou ovlivnit čitelnost na tiskárnách s nízkým rozlišením.  
- **Columns** řídí, na kolik vertikálních částí jsou data rozdělena. Méně sloupců = užší čárový kód, ale možná budete muset zvýšit počet řádků, aby všechna data zůstala.  
- **Truncate (compact mode)** odstraňuje nepoužité řádky, čímž snižuje konečnou velikost obrázku. Proto můžeme **generovat PDF417 barcode**, který se vejde do boxu 200 × 200 px.

## Krok 4: Uložte obrázek čárového kódu jako PNG (nebo jiný formát)

Po nastavení generátoru je posledním krokem zapsat obrázek na disk. PNG je bezztrátový, což jej činí ideálním pro ostré čárové kódy.

```csharp
// Step 4: Save the barcode image as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);

// Quick sanity check – open the file automatically (Windows only)
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
    Process.Start(new ProcessStartInfo(outputPath) { UseShellExecute = true });
}
```

**Očekávaný výstup:** PNG soubor 200 × 200 px zobrazující kompaktní PDF417 barcode, který kóduje řetězec `Åspóse.Barcóde©`. Naskenujte jej libovolným PDF417 čtečkou (mobilní aplikace fungují dobře) a získáte přesně tento text.

---

## Krok 5: Zabalte vše dohromady — znovupoužitelná pomocná metoda

Pokud zjistíte, že potřebujete **vytvořit PDF417 barcode** na více místech, vytáhněte logiku do pomocné metody. To také ukazuje **jak generovat barcode** čistým a udržovatelným způsobem.

```csharp
/// <summary>
/// Generates a compact PDF417 barcode image and returns the file path.
/// </summary>
/// <param name="data">The text to encode (Unicode supported).</param>
/// <param name="outputFile">Full path where the PNG will be saved.</param>
/// <param name="xDimPixels">Desired X‑dimension in pixels (default 2).</param>
/// <param name="columns">Number of columns (default 3).</param>
/// <returns>The absolute path to the generated PNG.</returns>
public static string GenerateCompactPdf417(string data, string outputFile, int xDimPixels = 2, int columns = 3)
{
    // Initialise generator
    var gen = new BarcodeGenerator(EncodeTypes.Pdf417, data);

    // Adjust size
    gen.Parameters.Barcode.XDimension.Pixels = xDimPixels;
    gen.Parameters.Barcode.Pdf417.Columns = columns;
    gen.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

    // Save image
    gen.Save(outputFile, BarCodeImageFormat.Png);
    return Path.GetFullPath(outputFile);
}
```

Nyní můžete zavolat:

```csharp
string path = GenerateCompactPdf417("Sample123", "MyPdf417.png");
Console.WriteLine($"Barcode saved to: {path}");
```

---

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Co když se čárový kód stane nečitelným po zmenšení X‑dimension?** | Zvyšte `XDimension` na 3 px nebo zvýšte DPI výstupního obrázku (`generator.Save(..., 300)` pro vyšší rozlišení). |
| **Mohu generovat jiné formáty (např. JPEG nebo BMP)?** | Ano — nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. PNG je doporučeno pro bezztrátovou kvalitu. |
| **Potřebuji licenci pro Aspose.BarCode?** | Knihovna funguje v evaluačním režimu s vodoznakem. Pro produkční použití zakupte licenci, která vodoznak odstraní a odemkne pokročilé funkce. |
| **Jak vložit čárový kód do PDF dokumentu?** | Použijte Aspose.PDF: vytvořte `PdfPage`, přidejte obrázek čárového kódu jako `ImageStamp` a uložte PDF. |
| **Co když moje data překročí maximální kapacitu PDF417?** | PDF417 může pojmout až ~1 850 znaků. Pokud překročíte tuto limit, zvažte rozdělení dat do více čárových kódů nebo použití symbologie s vyšší kapacitou, jako je DataMatrix. |

---

## Závěr

Právě jsme **vytvořili PDF417 barcode** v .NET od nuly, naučili se, jak **upravit velikost čárového kódu**, a viděli, jak knihovna **barcode generator .NET** usnadňuje použití compact mode. Úpravou X‑dimenze, počtu sloupců a příznaku `Truncate` můžete přizpůsobit čárový kód jakémukoli vizuálnímu omezení a zároveň zachovat spolehlivost skenování.

Další kroky? Zkuste změnit výstupní formát na SVG pro neomezenou škálovatelnost, nebo vložte PNG přímo do PDF zprávy pomocí Aspose.PDF. Můžete také prozkoumat jiné symbologie — QR, Code128 nebo DataMatrix — pomocí stejné třídy `BarcodeGenerator`.

Šťastné kódování a neváhejte zanechat komentář, pokud narazíte na potíže při **jak generovat barcode** pro váš konkrétní scénář!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat Aztec barcode s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}