---
category: general
date: 2026-07-18
description: Jak nastavit úroveň chyb v PDF417 čárovém kódu pomocí Aspose.BarCode.
  Naučte se generovat PDF417 čárový kód s vlastním textem a během několika minut upravit
  korekci chyb.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: cs
lastmod: 2026-07-18
og_description: jak rychle nastavit úroveň chyb v čárovém kódu PDF417. Tento tutoriál
  vás provede generováním čárového kódu PDF417 s vlastním textem a různými úrovněmi
  korekce chyb.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Jak nastavit úroveň chyb v čárovém kódu PDF417 – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Jak nastavit úroveň chyb v PDF417 čárovém kódu – kompletní průvodce
url: /cs/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit úroveň chyb v PDF417 čárovém kódu – Kompletní průvodce

Už jste se někdy zamýšleli **jak nastavit chybu** při generování PDF417 čárového kódu? Nejste sami — většina vývojářů narazí na tento problém, když potřebují odolnější čárový kód pro skenování v drsných podmínkách. Dobrá zpráva? Nastavení úrovně korekce chyb je s Aspose.BarCode hračka a zároveň se naučíte **jak generovat PDF417** s vlastním textem.

V tomto tutoriálu projdeme každý krok, od vytvoření generátoru čárových kódů se speciálními znaky až po uložení dvou PNG souborů, které ukazují různé úrovně korekce chyb. Na konci budete pohodlně ovládat **generování PDF417 čárového kódu**, úpravu jeho X‑dimenze, počtu sloupců a, co je nejdůležitější, **nastavování úrovní chyb**, které vyhovují vašemu případu použití.

## Požadavky

- .NET 6.0 nebo novější (kód funguje také s .NET Framework)
- Aspose.BarCode pro .NET nainstalováno (`Install-Package Aspose.BarCode` přes NuGet)
- Složka na disku, kam lze zapisovat obrázky (nahraďte `YOUR_DIRECTORY/` ve vzorku)
- Základní znalost C# — pokud jste už dříve použili `Console.WriteLine`, jste připraveni

> **Tip:** Pokud cílíte na mobilní skenování, zaměřte se na vyšší úroveň chyb (Level 5), aby odolala špíně, poškrábání nebo podmínkám s nízkým osvětlením.

## Krok 1: Vytvořte generátor čárových kódů s vlastním textem

Prvním, co potřebujete, je instance `BarcodeGenerator`, která ví, že má vytvářet **PDF417 barcode** a nese přesně ten text, který chcete zakódovat. Všimněte si použití diakritických znaků a symbolu © — to dokazuje, že generátor zvládá Unicode přímo z krabice.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Proč je to důležité:* Příznak `EncodeTypes.Pdf417` říká Aspose, že pracujete s 2‑D vrstveným čárovým kódem, zatímco řetězcový argument se stane datovým nákladem. Pokud tento krok přeskočíte, skončíte s výchozím čárovým kódem Code128 místo vysokokapacitního PDF417, který potřebujete.

## Krok 2: Doladit vizuální parametry

PDF417 čárový kód není jen data; je to také vizuální vzor. Úprava **X‑dimenze** (šířka nejmenšího pruhu) a počtu **sloupců** vám umožní řídit fyzickou velikost a čitelnost čárového kódu.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Proč je to důležité:* Menší X‑dimenze vytváří kompaktnější obrázek, ale může být nečitelné na skenerech s nízkým rozlišením. Tři sloupce poskytují vyvážený poměr stran pro většinu velikostí štítků.

## Krok 3: Nastavte úroveň korekce chyb na 2 a uložte

Korekce chyb je jádrem **jak nastavit chybu** pro PDF417. Výčtový typ `Pdf417ErrorLevel` se pohybuje od `Level0` (žádná extra data) po `Level5` (maximální redundance). Zde začínáme s **Level 2**, která přidává mírnou míru odolnosti vůči chybám, aniž by příliš zvětšila obrázek.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Po spuštění tohoto úryvku najdete ve své složce soubor `Pdf417ErrorLevel2.png`. Otevřete jej a měli byste vidět čistý, třísloupcový čárový kód, který stále obsahuje slušné množství redundance.

## Krok 4: Zvyšte korekci chyb na Level 5 a uložte znovu

Někdy potřebujete, aby čárový kód přežil agresivnější poškození — například ve skladu, kde jsou štítky poškrábány. Přepnutím na **Level 5** maximalizujete korekci chyb za cenu mírně většího obrázku.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory vedle sebe: jeden s mírnou korekcí chyb, druhý s maximální. Porovnejte je; verze Level 5 bude mít více tmavých modulů, což algoritmus přidává k ochraně dat.

![příklad nastavení úrovně chyb v PDF417 čárovém kódu – ukazuje dva PNG soubory s různými úrovněmi korekce chyb](image.png)

## Očekávaný výstup

| Název souboru                | Úroveň chyby | Přibližné rozměry (px) |
|-------------------------------|-------------|--------------------------|
| `Pdf417ErrorLevel2.png`       | Level 2     | 150 × 80                 |
| `Pdf417ErrorLevel5.png`       | Level 5     | 180 × 95                 |

Oba obrázky kódují řetězec **“Åspóse.Barcóde©”** a lze je načíst libovolným standardním PDF417 čtečkou (např. ZXing, Scandit). Obrázek Level 5 odolá až ~30 % poškození, zatímco Level 2 odolá přibližně ~15 %.

## Časté otázky a okrajové případy

### Co když můj text obsahuje zalomení řádku?

PDF417 automaticky kóduje znaky pro nový řádek (`\n`). Stačí je zahrnout do řetězce:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Můžu použít jiný formát obrázku?

Určitě. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Svg` podle vašeho následného workflow.

### Ovlivňuje změna X‑dimenze korekci chyb?

Nezávisle, ano. Větší X‑dimenze vytváří větší moduly, což může zlepšit spolehlivost skenování, ale **nemění** logickou úroveň korekce chyb. Pro nejlepší výsledky upravujte oba parametry nezávisle.

### Jak generovat PDF417 čárový kód ve webovém API?

Zabalte stejný kód do ASP.NET Core kontroleru a streamujte PNG zpět jako `FileResult`. Jádrová logika zůstává beze změny, což znamená, že **jak generovat PDF417** zůstává konzistentní napříč desktopovými i webovými prostředími.

## Shrnutí

Probrali jsme **jak nastavit chybu** pro PDF417 čárový kód, ukázali **jak generovat PDF417** s vlastním Unicode textem a ukázali vám, jak doladit vizuální nastavení jako X‑dimenzi a počet sloupců. Výměnou `Pdf417ErrorLevel.Level2` za `Level5` můžete řídit kompromis mezi velikostí obrázku a odolností.

## Další kroky

- Experimentujte s **čárovým kódem s vlastním textem**, který obsahuje URL nebo ID produktů.
- Vyzkoušejte různé počty sloupců (`generator.Parameters.Barcode.Pdf417.Columns = 5`), abyste viděli, jak se tvar mění.
- Kombinujte PDF417 s jinými typy čárových kódů ve stejném dokumentu pro multimodální skenovací řešení.
- Prozkoumejte oficiální dokumentaci Aspose na [oficiální dokumentaci](https://docs.aspose.com/barcode/net/) pro pokročilé funkce, jako je macro PDF417 nebo kompaktní režim.

Neváhejte zanechat komentář, pokud narazíte na potíže, nebo sdílet své vlastní naskenované výsledky. Šťastné tvoření čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vytvořit Aztec čárový kód s korekcí chyb v .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}