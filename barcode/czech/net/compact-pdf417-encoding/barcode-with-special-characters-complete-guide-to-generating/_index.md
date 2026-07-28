---
category: general
date: 2026-07-27
description: Tutoriál o čárových kódech se speciálními znaky ukazuje, jak generovat
  PDF417 čárové kódy pomocí Aspose. Naučte se krok za krokem vytvářet a zpracovávat
  Unicode data.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: cs
lastmod: 2026-07-27
og_description: Návod na čárový kód se speciálními znaky vysvětluje, jak generovat
  čárové kódy PDF417 pomocí Aspose, a pokrývá zpracování Unicode a makro metadata.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Čárový kód se speciálními znaky – Generujte PDF417 pomocí Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Čárový kód se speciálními znaky – Kompletní průvodce generováním PDF417 pomocí
  Aspose
url: /cs/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čárový kód se speciálními znaky – Kompletní průvodce generováním PDF417 pomocí Aspose

Už jste se někdy zamysleli, jak vytvořit **čárový kód se speciálními znaky**, který obsahuje diakritiku, symboly nebo dokonce copyrightové značky? Nejste sami. Mnoho vývojářů narazí na problém, když jejich data obsahují znaky jako “Å”, “é” nebo “©”, a standardní příklady málokdy ukazují, jak s nimi pracovat. V tomto tutoriálu projdeme konkrétním příkladem, který nejenže tento problém řeší, ale také ukazuje **jak generovat PDF417** čárové kódy pomocí knihovny Aspose.BarCode.

Začneme nastavením jednoduché .NET konzolové aplikace a poté se ponoříme do kódu, který vytváří PDF417 čárový kód obsahující řetězec `"Åspóse.Barcóde©"`. Během toho uvidíte, proč je každé nastavení důležité, jak nakonfigurovat macro‑PDF417 metadata a na co si dát pozor při práci s Unicode. Na konci budete připraveni **vytvořit čárový kód pomocí Aspose** ve všech svých projektech, ať už jde o inventarizaci, ticketing nebo sledování zabezpečených dokumentů.

## Požadavky

- .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.7+)
- Visual Studio 2022 (nebo jakékoli IDE, které preferujete)
- Platná licence Aspose.BarCode pro .NET (můžete začít s bezplatnou zkušební verzí)
- Základní znalost syntaxe C#

Pokud vám některý z těchto bodů není známý, nepanikařte — stačí nainstalovat .NET SDK a stáhnout NuGet balíček `Aspose.BarCode` a budete připraveni.

## Krok 1: Nainstalujte Aspose.BarCode a nastavte projekt

Pro generování **čárového kódu se speciálními znaky** potřebujete nejprve knihovnu Aspose.BarCode. Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Tím se stáhne nejnovější verze (k červenci 2026, verze 23.12), která podporuje plnou práci s Unicode přímo. Po obnovení balíčku vytvořte nový C# soubor s názvem `Program.cs` a přidejte obvyklé `using` direktivy:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Proč `using Aspose.BarCode.Generation`? Poskytuje nám přístup ke třídě `BarcodeGenerator`, jádru **jak generovat PDF417** čárových kódů s Aspose.

## Krok 2: Inicializujte generátor čárových kódů s Unicode textem

Nyní přichází část, která skutečně vytváří **čárový kód se speciálními znaky**. Všimněte si, že řetězec předávaný konstruktoru obsahuje “Å”, “ó” a “©”. Aspose automaticky detekuje Unicode rozsah, takže nepotřebujete žádné další kroky kódování — stačí předat obyčejný .NET řetězec:

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`EncodeTypes.MacroPdf417` říká Aspose, že chceme PDF417 čárový kód, který může nést makro informace (užitečné pro rozdělení velkých dat). Generátor nyní obsahuje **čárový kód se speciálními znaky**, připravený k dalším úpravám.

## Krok 3: Doladění vzhledu a makro metadat

Jednoduchý čárový kód funguje, ale většina reálných scénářů vyžaduje kontrolu nad velikostí, počtem sloupců a makro poli. Níže upravujeme X‑dimenzi, počet sloupců a poté nastavíme několik vlastností macro‑PDF417. Každý řádek je okomentován, abyste viděli *proč* je důležitý.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Rychlá tip: pokud se vám vygenerovaný čárový kód zdá příliš široký, snižte hodnotu `Columns` nebo zvýšte `XDimension`. Obě ovlivňují konečnou velikost obrázku, což je klíčové při vkládání čárového kódu do PDF nebo tištěných štítků.

## Krok 4: Uložte čárový kód jako obrázek

Nakonec uložíme čárový kód do PNG souboru. Metoda `Save` automaticky vykreslí **čárový kód se speciálními znaky** do rastrového formátu, který můžete zobrazit na webu, vložit do reportu nebo poslat do tiskárny.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, která existuje na vašem počítači. Po dokončení programu byste měli vidět soubor `ExtPDF417Meta.png` obsahující ostrý PDF417 čárový kód, který kóduje Unicode řetězec.

### Očekávaný výstup

Pokud otevřete PNG, uvidíte obdélníkový čárový kód s řadou černých a bílých pruhů. Naskenováním pomocí PDF417‑kompatibilního skeneru (nebo mobilní aplikace jako “Barcode Scanner”) získáte přesně text `"Åspóse.Barcóde©"` spolu s nastavenými makro metadaty. Jinými slovy, čárový kód věrně zachovává speciální znaky — nedochází ke ztrátě dat.

## Časté otázky a okrajové případy

### Co když můj text obsahuje emoji nebo ne‑BMP znaky?

Aspose.BarCode podporuje plný UTF‑16, takže emoji fungují, pokud je cílový skener dokáže dekódovat. Stačí předat řetězec přímo; knihovna se postará o kódování interně.

### Musím nastavit konkrétní znakovou sadu?

Ne. Na rozdíl od starších SDK pro čárové kódy, které vyžadovaly nastavení `CodePage`, Aspose automaticky detekuje Unicode. Pokud však cílíte na starší zařízení, které rozumí jen ASCII, budete muset před generováním odstranit nebo nahradit speciální znaky.

### Jak se liší od běžného PDF417 čárového kódu?

Varianta `MacroPdf417` přidává extra pole (ID souboru, počet segmentů atd.), která pomáhají rozdělit velké datové bloky mezi více čárových kódů. Pokud je nepotřebujete, můžete přepnout na `EncodeTypes.Pdf417` a vynechat makro‑specifické vlastnosti.

### Můžu generovat čárový kód jako vektor (SVG) místo PNG?

Určitě. Změňte `BarCodeImageFormat` na `Svg`:

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

Vektorový výstup se škáluje bez ztráty kvality — užitečné pro tisk ve vysokém rozlišení.

## Kompletní funkční příklad

Níže je kompletní, připravený program. Zkopírujte a vložte jej do `Program.cs`, upravte výstupní cestu a stiskněte **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

Spuštěním tohoto programu se vypíše potvrzovací řádek a vytvoří se `ExtPDF417Meta.png` ve složce spustitelného souboru. Otevřete soubor, naskenujte jej a ověřte, že speciální znaky přežily celý proces.

## Profesionální tipy pro produkční nasazení

- **Ukládejte generátor do cache** pokud vytváříte mnoho čárových kódů v cyklu; opětovné používání stejné instance `BarcodeGenerator` snižuje zatížení paměti.
- **Nastavte `Resolution`** (`barcodeGenerator.Parameters.ImageResolution`), když potřebujete vyšší DPI pro tiskové materiály.
- **Validujte vstup**: odstraňte řídicí znaky, které by mohly narušit makro pole. Jednoduchý regex jako `^[\u0020-\u007E\u00A0-\u00FF]+$` funguje pro většinu případů Latin‑1.
- **Bezpečnost vláken**: každé vlákno by mělo mít vlastní `BarcodeGenerator`. Třída není thread‑safe.

## Závěr

Nyní máte pevný, kompletní návod na vytvoření **čárového kódu se speciálními znaky** pomocí Aspose a také jste viděli **jak generovat PDF417** čárové kódy, které nesou makro metadata. Příklad pokrývá vše od instalace NuGet balíčku po uložení finálního PNG a upozorňuje na běžné úskalí, jako je práce s Unicode a nastavení velikosti obrázku.

Jste připraveni na další krok? Zkuste změnit formát obrázku na SVG, experimentujte s většími datovými bloky

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Rozpoznávání PDF417 čárového kódu s čínskými znaky v Javě](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Rozpoznávání PDF417 čárového kódu s tureckými znaky v Javě](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}