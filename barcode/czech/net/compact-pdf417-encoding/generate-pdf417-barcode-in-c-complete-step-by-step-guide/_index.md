---
category: general
date: 2026-07-15
description: Rychle generujte čárový kód PDF417 pomocí C#. Naučte se, jak vytvořit
  čárový kód z textu, upravit jeho velikost a nastavit vlastní rozměry čárového kódu
  během několika minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: cs
lastmod: 2026-07-15
og_description: Okamžitě generujte PDF417 čárový kód v C#. Tento průvodce ukazuje,
  jak generovat čárový kód z textu, upravit jeho velikost a použít vlastní rozměry.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Generovat čárový kód PDF417 v C# – Kompletní programovací tutoriál
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Vytvořte čárový kód PDF417 v C# – Kompletní průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu v C# – Kompletní krok‑za‑krokem průvodce

Už jste někdy potřebovali **vygenerovat PDF417 čárový kód**, ale nebyli jste si jisti, které nastavení upravit? Nejste v tom jediní — mnoho vývojářů narazí na stejný problém, když poprvé pracují s 2‑D čárovými kódy. Dobrá zpráva? Několika řádky C# můžete převést libovolný řetězec na skenovatelný PDF417 obrázek, ovládat jeho přesnou velikost a dokonce definovat vlastní rozložení sloupců a řádků.

V tomto tutoriálu vás provedeme tím, jak **vygenerovat čárový kód z textu**, upravit velikost čárového kódu a nastavit vlastní rozměry čárového kódu — vše pomocí populární knihovny Aspose.BarCode. Na konci budete mít připravený ukázkový kód, který můžete vložit do libovolného .NET projektu.

![Příklad generování PDF417 čárového kódu](https://example.com/og-image.png "Příklad generování PDF417 čárového kódu")

## Co vytvoříte

- PDF417 čárový kód, který kóduje řetězec `Åspóse.Barcóde©`.
- Přesnou kontrolu nad X‑dimenzí (šířka pixelu každého modulu).
- Vlastní rozložení se 4 sloupci a 9 řádky.
- PNG soubor uložený na disk.

Žádné externí služby, žádné kouzelné hůlky — jen čistý C# kód, který můžete zkompilovat hned teď.

## Požadavky

- .NET 6.0 nebo novější (kód funguje také na .NET Framework 4.8).
- Visual Studio 2022 nebo jakékoli IDE podporující C#.
- Aspose.BarCode pro .NET (zdarma zkušební verze nebo licencovaná verze). Instalace přes NuGet:

```bash
dotnet add package Aspose.BarCode
```

To je vše — jakmile je balíček přidán do projektu, můžete začít.

## Krok 1 – Generování PDF417 čárového kódu s textovými daty

První, co potřebujeme, je instance `BarcodeGenerator`, která ví, že pracujeme se symbologií PDF417 a s konkrétním textem, který chceme zakódovat.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Proč je to důležité:**  
> `EncodeTypes.Pdf417` říká knihovně, aby použila 2‑D formát PDF417, zatímco druhý argument je **payload pro generování čárového kódu z textu**. Cokoliv sem předáte, se stane daty uloženými v matici čárového kódu.

## Krok 2 – Úprava velikosti čárového kódu (X‑dimenze)

Pokud jste někdy tiskli čárový kód, který na účtence vypadal příliš malý, znáte frustraci, když jej skener nezachytí. Vlastnost `XDimension` řídí šířku jednoho modulu (nejmenšího černého nebo bílého čtverečku) v pixelech.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Pro tip:**  
> Hodnota 2 px funguje dobře pro většinu scénářů na obrazovce. Pro vysoce rozlišené tisky můžete zvýšit na 3 nebo 4 px. Pamatujte, že větší X‑dimenze zvětšují celkovou velikost obrázku.

## Krok 3 – Nastavení vlastních rozměrů čárového kódu (sloupce a řádky)

PDF417 vám umožňuje určit, kolik sloupců a řádků má čárový kód zabírat. Zde vstupují do hry **vlastní rozměry čárového kódu**. Změna těchto hodnot vám může pomoci veškerý kód vejít do úzkého UI prostoru nebo splnit konkrétní velikost štítku.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Co se děje pod kapotou?**  
> Knihovna přerozdělí zakódovaná data po zadané mřížce. Méně sloupců znamená vyšší čárové kódy; více řádků je zkrátí. Pohrávejte si s čísly, dokud vizuální rovnováha nebude odpovídat vašim potřebám.

## Krok 4 – Uložení obrázku čárového kódu

Nyní, když máme vše nastavené, jednoduše požádáme generátor, aby zapsal PNG soubor. PNG je bezztrátový, takže ostrost modulů zůstane zachována.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Po spuštění programu byste měli vidět soubor na `C:\Barcodes\CustomLayout.png`, který vypadá podobně jako snímek výše. Naskenováním libovolným PDF417‑kompatibilním čtečkou získáte původní řetězec `Åspóse.Barcóde©`.

## Kompletní funkční příklad

Níže je kompletní program, který můžete zkopírovat a vložit do konzolové aplikace. Obsahuje všechny `using` direktivy a ošetření chyb, jaké byste očekávali v produkčním kódu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Očekávaný výstup

Spuštěním kódu se vypíše:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…a vytvoří se PNG, který lze otevřít v libovolném prohlížeči obrázků. Pokud jej naskenujete mobilní aplikací (např. „Barcode Scanner“ na iOS/Android), dekódovaný text bude přesně **Åspóse.Barcóde©**.

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Mohu použít jiný formát obrázku?** | Ano — `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` nebo `Svg` jsou všechny podporovány. Stačí změnit druhý argument metody `Save`. |
| **Co když můj text obsahuje Unicode znaky?** | Aspose.BarCode plně podporuje UTF‑8, takže příklad s `Å` a `©` funguje bez úprav. |
| **Jak změním úroveň opravy chyb?** | Použijte `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (úrovně 0‑8). Vyšší úrovně zvyšují redundanci, ale i velikost. |
| **Potřebuji průhledné pozadí — je to možné?** | Nastavte `generator.Parameters.Barcode.Image.TransparentBackground = true;` před uložením. |
| **Existuje způsob, jak vložit čárový kód přímo do PDF?** | Rozhodně. Nahraďte volání `Save` tímto: `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` a získáte jednorázový PDF obsahující čárový kód. |

## Závěr

Nyní už víte, jak **vygenerovat PDF417 čárový kód** v C# z libovolného řetězce, **upravit velikost čárového kódu** a použít **vlastní rozměry čárového kódu**, aby vyhovoval vašim rozvrhovým potřebám. Čtyřkrokový postup — inicializace, velikost, rozložení, uložení — pokrývá základní workflow pro většinu 2‑D čárových kódů.

Co dál? Zkuste vyměnit `EncodeTypes.Pdf417` za `EncodeTypes.QR` nebo `EncodeTypes.Code128` a podívejte se, jak se API přizpůsobí. Experimentujte s různými hodnotami `XDimension`, hrajte si s mřížkou sloupců/řádků nebo vložte obrázek do PDF reportu. Možnosti jsou prakticky neomezené a nyní máte pevný základ, na kterém můžete stavět.

Máte další otázky nebo jste při práci s PDF417 objevili chytrý trik? Zanechte komentář níže — přispějme společně do diskuze. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat čárový kód – typy jednorozměrných čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)
- [Generování DataMatrix čárového kódu – profesionální průvodce s Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}