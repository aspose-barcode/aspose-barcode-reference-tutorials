---
category: general
date: 2026-08-09
description: Rychle generujte čárový kód PDF417 v C#. Naučte se, jak generovat PDF417
  s kompaktním režimem, řízením sloupců a výstupem PNG pomocí API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: cs
lastmod: 2026-08-09
og_description: Vygenerujte čárový kód PDF417 v C# pomocí stručného příkladu. Tento
  průvodce vám ukáže, jak nastavit kompaktní režim, nastavit sloupce a uložit výsledek
  jako PNG obrázek.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Vytvořte čárový kód PDF417 v C# – kompletní návod
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Generování čárového kódu PDF417 v C# – krok za krokem
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu v C# – krok za krokem

Pokud potřebujete **vygenerovat PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný program, který vytvoří kompaktní PDF417 čárový kód, přizpůsobí jeho velikost a uloží obrázek jako PNG soubor.

Generování PDF417 čárového kódu je běžná potřeba pro mobilní vstupenky, sledování zásob a zabezpečení dokumentů. Tento průvodce pokrývá základní konfigurační možnosti, vysvětluje, proč je každé nastavení důležité, a poskytuje praktické tipy pro reálné nasazení.

## Předpoklady

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný  
* C# IDE, např. Visual Studio 2022 nebo Visual Studio Code  
* NuGet balíček **Aspose.BarCode for .NET** (verze 23.10 nebo novější)  

Balíček můžete nainstalovat pomocí následujícího CLI příkazu:

```bash
dotnet add package Aspose.BarCode
```

Níže uvedený kód předpokládá, že je balíček referencován a že máte oprávnění zapisovat do výstupního adresáře.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte nový konzolový projekt a přidejte požadované `using` direktivy. Tyto jmenné prostory zpřístupňují třídu `BarcodeGenerator` a výčtový typ pro formát obrázku.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Proč je to důležité:** Import správných jmenných prostorů zajišťuje, že kompilátor najde typ `BarcodeGenerator` a výčet `BarCodeImageFormat`. Chybějící jmenný prostor vede k chybě kompilace, která zastaví proces generování čárového kódu.

## Krok 2: Inicializace `BarcodeGenerator` s kódováním PDF417

Konstruktor `BarcodeGenerator` přijímá dva argumenty: symbologii čárového kódu (`EncodeTypes.Pdf417`) a text, který chcete zakódovat. PDF417 podporuje širokou škálu znaků, včetně Unicode symbolů.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Vysvětlení:**  
* `EncodeTypes.Pdf417` říká knihovně, aby použila standard PDF417.  
* Ukázkový text obsahuje diakritické znaky a symbol copyrightu pro demonstraci práce s Unicode.  

Pokud potřebujete zakódovat jen číselná data, můžete předat prostý řetězec jako `"1234567890"`.

## Krok 3: Úprava X‑dimenze pro vyšší rozlišení

X‑dimenze řídí šířku jednoho modulu čárového kódu (nejmenšího černého nebo bílého prvku). Nastavení menší hodnoty v pixelech vede k obrázku s vyšším rozlišením.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč to upravit?** Výchozí X‑dimenze 3–4 pixelů může vytvořit čárový kód, který vypadá hrubě na obrazovkách s vysokým DPI. Snížení na **2 pixely** vyvažuje čitelnost a velikost souboru, zejména když později zapnete kompaktní režim.

## Krok 4: Nastavení počtu sloupců

PDF417 umožňuje určit, kolik sloupců má čárový kód obsahovat. Méně sloupců dělá čárový kód užší, ale vyšší, zatímco více sloupců vytvoří širší, kratší kód.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Praktický tip:** Pro mobilní vstupenky, které musí zapadnout do úzké etikety, funguje počet sloupců **3–5** dobře. Počet sloupců zvyšte, pokud máte hodně dat a chcete kratší čárový kód.

## Krok 5: Povolení kompaktního režimu pro oříznutí prázdných řádků

Kompaktní režim odstraňuje z matice čárového kódu zbytečné řádky, čímž snižuje celkovou velikost obrázku, aniž by ztratil zakódovaná data.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Kdy jej použít:** Pokud generujete čárové kódy pro ukládání nebo přenos přes síť, kompaktní režim může zmenšit PNG soubor až o 30 %. Některé starší skenery však nemusí podporovat oříznutý PDF417; otestujte s vaším cílovým hardwarem.

## Krok 6: Uložení čárového kódu jako PNG obrázku

Zvolte výstupní cestu a zavolejte `Save`. Výčet `BarCodeImageFormat.Png` vytvoří bezztrátový obrázek vhodný pro většinu aplikací.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Ověření výsledku:** Otevřete PNG soubor v libovolném prohlížeči obrázků. Měli byste vidět hustý, vysokokontrastní čárový kód, který odpovídá ukázkovému textu. Naskenováním obrázku čtečkou PDF417 (např. ZXing nebo mobilní aplikací) získáte původní řetězec `"Åspóse.Barcóde©"`.

![Generated PDF417 barcode image saved as PNG](compact-pdf417.png "Generated PDF417 barcode in C#")

*Obrázek výše demonstruje finální výstup kódu z tutoriálu.*

## Kompletní, spustitelný příklad

Když spojíme všechny části, získáme kompletní konzolový program, který můžete zkopírovat, vložit a spustit.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Očekávaný výstup

Po spuštění programu se vypíše:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Soubor `CompactPdf417.png` obsahuje kompaktní PDF417 čárový kód, který zakóduje poskytnutý Unicode řetězec. Naskenováním obrázku standardní čtečkou PDF417 získáte přesně stejný text.

## Běžné varianty a okrajové případy

| Situace | Úprava | Důvod |
|-----------|------------|--------|
| **Delší datový payload** (např. > 150 znaků) | Zvyšte `generator.Parameters.Barcode.Pdf417.Columns` na 6‑8 | Více sloupců zabrání tomu, aby čárový kód byl příliš vysoký. |
| **Potřeba průhledného pozadí** | Použijte `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Průhledný PNG se lépe integruje do UI překryvů. |
| **Generování JPEG pro web** | Změňte formát na `BarCodeImageFormat.Jpeg` a volitelně nastavte `ImageQuality` | JPEG snižuje velikost souboru na úkor bezztrátové věrnosti. |
| **Zpracování null nebo prázdného vstupu** | Ověřte vstup před vytvořením generátoru: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Zabrání výjimkám za běhu a zajistí smysluplné čárové kódy. |

## Tipy pro produkční nasazení

* **Zpracování výjimek:** Zabalte logiku generování do `try/catch` bloku a logujte chyby, jako je nedostatek místa na disku nebo neplatné parametry.  
* **Výkon:** Při generování mnoha čárových kódů se stejným nastavením znovu použijte jedinou instanci `BarcodeGenerator`; mezi ukládáními pouze aktualizujte vlastnost `CodeText`.  
* **Bezpečnost:** Pokud zakódovaný text obsahuje citlivé informace, zvažte jeho šifrování před předáním generátoru a dešifrování po načtení.  

## Závěr

Nyní víte, jak **vygenerovat PDF417 čárový kód** v C# pomocí knihovny Aspose.BarCode, nakonfigurovat kompaktní režim, řídit počet sloupců a exportovat výsledek jako PNG obrázek. Tento tutoriál pokryl každý krok od nastavení projektu po řešení okrajových případů a poskytl vám připravené řešení pro aplikace založené na čárových kódech.

Dále prozkoumejte související témata, jako je **vytváření QR kódů v C#**, **hromadné generování čárových kódů** a **integrace skenování čárových kódů do mobilních aplikací**. Všechna tato témata staví na stejných základech `BarcodeGenerator`, které jste právě zvládli.

Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}