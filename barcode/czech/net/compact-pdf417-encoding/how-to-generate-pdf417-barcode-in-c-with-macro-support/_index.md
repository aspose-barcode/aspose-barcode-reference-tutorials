---
category: general
date: 2026-10-21
description: Naučte se, jak v C# generovat čárový kód PDF417 pomocí Aspose.BarCode.
  Podrobné kroky zahrnují nastavení čárového kódu PDF417, vytvoření makro PDF417 čárového
  kódu a uložení jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: cs
lastmod: 2026-10-21
og_description: Jak vygenerovat čárový kód PDF417 v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto krok‑za‑krokem tutoriálu, abyste nakonfigurovali nastavení čárového
  kódu PDF417, vytvořili makro čárový kód PDF417 a exportovali jej do PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Jak generovat čárový kód PDF417 v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Jak v C# generovat čárový kód PDF417 s podporou makra
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárový kód v C# s podporou makra

Pokud potřebujete v C# generovat PDF417 čárový kód, tento průvodce vám ukáže kompletní, připravené řešení. Ať už vytváříte systém logistických štítků nebo kódujete velké bloky dat, uvidíte, jak nastavit parametry PDF417 čárového kódu, vytvořit makro PDF417 čárový kód a uložit výsledek jako PNG obrázek.

Generování PDF417 čárového kódu nevyžaduje manipulaci s bity na nízké úrovni. Použitím třídy **barcode generator C#** z Aspose.BarCode se můžete soustředit na obchodní logiku, zatímco knihovna se postará o kódování, opravu chyb a vykreslování obrázku.

## Co budete potřebovat

- **.NET 6.0** nebo novější (kód funguje také s .NET Framework 4.6+)
- **Aspose.BarCode for .NET** NuGet balíček (`Install-Package Aspose.BarCode`)
- Vývojové prostředí, např. Visual Studio 2022 nebo Visual Studio Code
- Oprávnění k zápisu do složky, kde bude PNG obrázek uložen

Tyto předpoklady zajišťují, že ukázkový kód se zkompiluje a spustí bez další konfigurace.

## Jak generovat PDF417 čárový kód – přehled krok za krokem

Níže je stručná mapa procesu:

1. **Vytvořit instanci `BarcodeGenerator`** pomocí `EncodeTypes.MacroPdf417`.
2. **Upravit základní vzhled čárového kódu** (velikost modulu, barvy atd.).
3. **Nastavit specifické parametry PDF417**, včetně polí souvisejících s makrem.
4. **Uložit vygenerovaný obrázek čárového kódu** pomocí `BarCodeImageFormat PNG`.

Každý krok je podrobně vysvětlen, včetně kompletních úryvků kódu, které můžete přímo zkopírovat do konzolové aplikace.

## Krok 1: Nastavení vývojového prostředí

Vytvořte nový konzolový projekt a přidejte odkaz na Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Otevřete `Program.cs` a přidejte požadované jmenné prostory:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Tyto importy vám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`.

## Krok 2: Vytvoření generátoru makro PDF417 čárového kódu

První řádek implementace vytváří objekt **Macro PDF417 barcode**. Výčtový typ `EncodeTypes.MacroPdf417` říká knihovně, aby použila makro variantu PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Proč je to důležité:** Použití `EncodeTypes.MacroPdf417` umožňuje makro pole (`FileID`, `SegmentID` atd.), která vám umožní rozdělit velký payload na více obrázků čárových kódů při zachování pořadí.

## Krok 3: Úprava základního vzhledu čárového kódu

Před úpravou specifických parametrů PDF417 nastavte šířku modulu (pixelu). Hodnota `2` poskytuje čistý, snadno skenovatelný obrázek bez nadměrné velikosti souboru.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Zde můžete také změnit barvy popředí/pozadí, pokud vaše UI vyžaduje jinou paletu.

## Krok 4: Nastavení specifických parametrů PDF417

Nastavení **PDF417 čárového kódu** jsou dostupná přes `generator.Parameters.Barcode.Pdf417`. Níže jsou zobrazeny nejdůležitější makro pole:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Porozumění jednotlivým vlastnostem

| Vlastnost | Účel | Typický rozsah |
|----------|------|----------------|
| `Columns` | Řídí, kolik datových sloupců obsahuje každý řádek. Více sloupců snižuje počet řádků, ale zvyšuje šířku. | 1 – 30 |
| `MacroPdf417FileID` | 32‑bitový identifikátor, který seskupuje všechny segmenty stejného logického souboru. Musí být stejný pro každý segment. | Libovolné kladné celé číslo |
| `MacroPdf417SegmentID` | Index aktuálního segmentu začínající od nuly. Zvyšujte pro každý následující čárový kód. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů, které tvoří celý soubor. Všechny segmenty musí být vygenerovány. | ≥ 1 |
| `MacroPdf417FileName` | Volitelný popisný název (max 255 znaků). Užitečné pro ladění. | Alfanumerický řetězec |

> **Tip:** Udržujte `Columns` mezi 3 a 7 pro většinu štítkových tiskáren. Větší hodnoty mohou překročit tisknutelnou šířku na zařízeních s nízkým rozlišením.

## Krok 5: Uložení čárového kódu jako PNG obrázek

Nakonec zapište čárový kód na disk pomocí `BarCodeImageFormat PNG`. PNG zachovává bezztrátovou kvalitu, což je nezbytné pro spolehlivé skenování.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Po dokončení programu najdete `MacroPdf417.png` ve složce projektu. Otevřením souboru uvidíte čistý Macro PDF417 čárový kód připravený k tisku.

### Očekávaný výstup

Vygenerovaný obrázek vypadá podobně jako příklad níže (ilustrační):

![Příklad makro PDF417 čárového kódu](macro-pdf417-barcode.png "Makro PDF417 čárový kód vygenerovaný C# kódem")

*Text alternativního popisu obrázku je “Makro PDF417 čárový kód vygenerovaný C# kódem”, splňující požadavky na přístupnost a SEO.*

## Časté problémy a řešení

| Problém | Symptom | Řešení |
|---------|---------|--------|
| **Nesprávné `EncodeTypes`** | Čárový kód se vykreslí jako QR kód nebo prostý text. | Ujistěte se, že používáte `EncodeTypes.MacroPdf417` (ne `EncodeTypes.Pdf417`). |
| **Neshodující se ID segmentů** | Skener hlásí „chybějící segment“. | Zvyšujte `MacroPdf417SegmentID` sekvenčně a udržujte `SegmentsCount` konzistentní ve všech souborech. |
| **Příliš velká velikost modulu** | Čárový kód se stane příliš širokým pro štítek. | Snižte `XDimension.Pixels` nebo zmenšete `Columns`. |
| **Chyby cesty k souboru** | `UnauthorizedAccessException` při ukládání. | Ukládejte do složky, kterou vlastníte, např. `Environment.CurrentDirectory`. |
| **Chybějící NuGet balíček** | Chyba při kompilaci: `BarcodeGenerator` nebyl nalezen. | Spusťte `dotnet add package Aspose.BarCode` před sestavením. |

Řešení těchto problémů včas šetří čas při integraci generování čárových kódů do větších pracovních postupů.

## Rozšíření příkladu

Nyní, když můžete vygenerovat jeden Macro PDF417 čárový kód, zvažte následující kroky:

- **Dávkové generování**: Procházet kolekci datových úseků a při každé iteraci aktualizovat `MacroPdf417SegmentID`.
- **Různé formáty obrázků**: Nahradit `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp`, pokud váš downstream systém preferuje tyto formáty.
- **Vkládání do PDF**: Použít Aspose.PDF k umístění PNG do PDF zprávy pro distribuci.
- **Ověření skenování**: Otestovat vygenerované čárové kódy pomocí hardwarového skeneru nebo mobilní aplikace, která podporuje Macro PDF417.

Tyto varianty zachovávají základní **nastavení PDF417 čárového kódu** beze změny, zatímco přizpůsobují výstup potřebám vašeho projektu.

## Závěr

Nyní víte **jak generovat PDF417 čárový kód** v C# pomocí Aspose.BarCode, od vytvoření `BarcodeGenerator` s `EncodeTypes.MacroPdf417` po nastavení makro polí a uložení výsledku jako `BarCodeImageFormat PNG`. Kompletní, spustitelný kód demonstruje doporučený přístup, vysvětluje, proč je každé nastavení důležité, a upozorňuje na časté problémy, na které můžete narazit.

Neváhejte experimentovat s počtem sloupců, barvami nebo výstupními formáty a integrovat generátor do vlastních aplikací pro spolehlivé kódování dat s vysokou hustotou.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárové kódy v C# s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Jak vytvořit makro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak uložit čárový kód a generovat PDF417 s Aspose v C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}