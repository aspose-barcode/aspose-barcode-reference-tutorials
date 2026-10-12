---
category: general
date: 2026-09-19
description: Vytvořte PDF417 čárový kód v C# a naučte se, jak generovat obrázek čárového
  kódu, nastavit jeho rozměry a uložit jej jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: cs
lastmod: 2026-09-19
og_description: Vytvořte čárový kód PDF417 v C# a zjistěte, jak vygenerovat obrázek
  čárového kódu, nastavit jeho rozměry a uložit jej jako soubor PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Vytvořte PDF417 čárový kód a exportujte PNG v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Jak vytvořit čárový kód PDF417 a exportovat PNG v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód a exportovat PNG v C#

Pokud potřebujete **vytvořit PDF417 čárový kód** v .NET aplikaci, tento průvodce vám ukáže, jak vygenerovat obrázek čárového kódu, upravit jeho rozměry a uložit jej jako soubor PNG. Uvidíte kompletní, spustitelný příklad, který používá knihovnu Aspose.BarCode, takže můžete kód přímo zkopírovat do svého projektu.

Generování obrázku čárového kódu je běžnou požadavkem pro systémy vstupenek, sledování zásob a mobilní palubní vstupenky. Na konci tohoto tutoriálu pochopíte **jak vygenerovat obrázek čárového kódu**, **jak nastavit rozměry čárového kódu** a **jak vytvořit PNG soubory čárového kódu**, které splňují vaše standardy vizuální kvality.

## Požadavky

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+).
* Vývojové prostředí, jako je Visual Studio 2022 nebo VS Code.
* Platná licence pro knihovnu **Aspose.BarCode for .NET** (pro tento příklad funguje i bezplatná zkušební verze).
* Základní znalost syntaxe C#.

Nainstalujte NuGet balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte novou konzolovou aplikaci nebo přidejte kód do existujícího projektu. Importujte požadované jmenné prostory na začátku souboru:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `BarcodeGenerator` a výčtu `EncodeTypes`.

## Krok 2: Jak vytvořit PDF417 čárový kód – základní konfigurace generátoru

První operací je vytvořit instanci `BarcodeGenerator` s typem kódování `Pdf417` a textem, který chcete zakódovat. Tento objekt představuje čárový kód, který později vykreslíte.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Proč je to důležité*: `EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417, což je vrstvený lineární čárový kód schopný uložit velké množství dat. Druhý argument (“Sample”) je náklad, který se zobrazí při skenování čárového kódu.

## Krok 3: Jak nastavit rozměry čárového kódu – jemné ladění hustoty a rozvržení

PDF417 čárový kód se skládá z řádků a sloupců modulů. Úpravou X‑dimenze (šířky modulu) a počtu řádků/sloupců můžete řídit vizuální hustotu a celkovou velikost obrázku.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Proč je to důležité*:
* **X‑dimension** určuje, jak široký je každý malý čtvereček (modul). Menší hodnota vede k kompaktnějšímu čárovému kódu, ale může být obtížnější pro skenery s nízkým rozlišením.
* **Columns** a **Rows** ovlivňují kapacitu dat a fyzický tvar. Zvýšením počtu sloupců se čárový kód rozšíří, zvýšením řádků se prodlouží. Můžete experimentovat s hodnotami až do limitů uvedených v komentářích.

**Tip**: Pokud čárový kód vypadá na obrazovce s vysokým DPI příliš hustě, zvyšte `XDimension.Pixels` na 3 nebo 4. Naopak pro malý štítek můžete nastavit 1 pixel a snížit počet sloupců.

## Krok 4: Jak vygenerovat obrázek čárového kódu – vykreslení do paměťového bitmapu

Po nakonfigurování generátoru můžete čárový kód vykreslit do objektu obrázku. Tento krok je volitelný, pokud potřebujete soubor uložit přímo, ale vystavení bitmapy vám umožní provést další zpracování (např. přidání loga nebo kreslení rámečku).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` vrací `System.Drawing.Image`, který můžete podle potřeby manipulovat pomocí GDI+.

## Krok 5: Jak vytvořit PNG čárového kódu – uložení finálního souboru obrázku

Nakonec zapište obrázek na disk ve formátu PNG. PNG zachovává bezztrátovou kvalitu, což je ideální pro skenovací aplikace.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Proč je to důležité*: Metoda `Save` za vás provede kódování a souborové I/O. Použití `BarCodeImageFormat.Png` zajišťuje, že výstup je přenosný, bezztrátový obrázek, který funguje napříč prohlížeči a mobilními zařízeními.

### Kompletní spustitelný příklad

Níže je kompletní program, který můžete vložit do `Program.cs` a spustit. Nahraďte `YOUR_DIRECTORY` existujícím adresářem ve vašem počítači.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Spuštěním programu vznikne soubor PNG, který vypadá takto:

![Generated PDF417 barcode example](https://example.com/placeholder-image.png "PDF417 barcode generated with custom dimensions saved as PNG")

*Alt text*: **Ukázkový PDF417 čárový kód vygenerovaný v C# s vlastními rozměry uložený jako PNG** – to splňuje požadavek **vytvořit PDF417 čárový kód** pro přístupnost obrázku.

## Běžné varianty a okrajové případy

| Situace | Doporučené úpravy |
|-----------|------------------------|
| **Velmi malý štítek** (např. 1 cm × 2 cm) | Nastavte `XDimension.Pixels = 1` a snižte `Columns` na 2‑3. Ověřte čitelnost skenerem. |
| **Vysoké rozlišení tisku** (300 dpi nebo více) | Zvyšte `XDimension.Pixels` na 3‑4 a případně zvýšte `Rows` pro větší kapacitu dat. |
| **Potřeba jiného formátu obrázku** (JPEG, BMP) | Změňte `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp`. |
| **Vložení do PDF** | Použijte `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` místo PNG. |
| **Dynamická data** (vstup uživatele) | Nahraďte statický řetězec `"Sample"` proměnnou, např. `userInput`. Ujistěte se, že délka textu nepřesahuje limity PDF417 (≈ 1 800 znaků). |

## Kontrolní seznam řešení problémů

* **Prázdný obrázek** – Ověřte, že výstupní adresář existuje a aplikace má oprávnění k zápisu.  
* **Čárový kód nečitelnost** – Zvyšte `XDimension.Pixels` nebo přidejte více sloupců/řádků; nízký kontrast pozadí může také způsobit selhání.  
* **Neočekávaná velikost** – Zkontrolujte hodnoty `Columns` a `Rows`; knihovna respektuje maximální limity uvedené v komentářích.  

## Další kroky

Nyní, když můžete **vytvořit PDF417 čárový kód**, zvažte prozkoumání těchto souvisejících témat:

* **Jak vygenerovat obrázek čárového kódu** v jiných formátech, jako je SVG pro webově škálovatelnou grafiku.  
* **Jak nastavit rozměry čárového kódu** pro QR kódy a symbologie DataMatrix.  
* **Jak vytvořit PNG čárového kódu** s vlastními barvami nebo vloženými logy pomocí `System.Drawing`.  

Tyto rozšíření vám umožní vytvořit plnohodnotnou službu generování čárových kódů, která může sloužit mobilním aplikacím, webovým portálům i desktopovým utilitám.

---

*Zjistili jste, jak vytvořit PDF417 čárový kód, přizpůsobit jeho rozměry, vykreslit obrázek čárového kódu a uložit jej jako PNG soubor pomocí C#. Použijte zde ukázané vzory i pro jiné typy čárových kódů a formáty obrázků, abyste rozšířili své automatizační možnosti.*

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat obrázek PDF417 čárového kódu v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak vytvořit PDF417 čárový kód s Aspose – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Jak uložit čárový kód v C# – Generovat PDF417 čárové kódy](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}