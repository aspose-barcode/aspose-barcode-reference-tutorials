---
category: general
date: 2026-10-09
description: Naučte se, jak vytvořit PDF417 čárový kód v C# pomocí Aspose.BarCode
  – generujte Macro PDF417 s plnou podporou metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Naučte se, jak vytvořit PDF417 čárový kód v C# pomocí Aspose.BarCode
  – generujte Macro PDF417 s plnou podporou metadata, včetně file ID, segment data,
  timestamp a dalších.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Jak vytvořit PDF417 čárový kód v C# s Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Jak vytvořit PDF417 čárový kód v C# s Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód v C# pomocí Aspose.BarCode

Pokud potřebujete **vytvořit PDF417 čárový kód v C#** rychle a spolehlivě, tento tutoriál vás provede kompletním procesem pomocí Aspose.BarCode. Uvidíte všechna potřebná nastavení, od základních rozměrů po kompletní sadu polí metadat Macro PDF417, a skončíte s PNG obrázkem připraveným pro následné zpracování.

## Rychlé odpovědi
- **Která knihovna generuje PDF417 čárové kódy?** Aspose.BarCode pro .NET.  
- **V jakém formátu výstup příkladu?** Bezeztrátový PNG obrázek.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro ukázku; pro produkční nasazení je vyžadována komerční licence.  
- **Která verze .NET je podporována?** .NET 6.0 nebo novější.  
- **Mohu přidat metadata do čárového kódu?** Ano – Macro PDF417 podporuje ID souboru, počet segmentů, časové razítka a další.

## Co je PDF417 čárový kód?
PDF417 čárový kód je vrstvená lineární symbologie, která může zakódovat až přibližně 1 KB dat na symbol a podporuje volitelná makro metadata pro soubory rozdělené do více segmentů. Skládá se z několika řad vrstvených lineárních vzorů, což umožňuje vysokou kapacitu dat při zachování čitelnosti standardními 2‑D skenery. Formát také obsahuje úrovně opravy chyb pro zvýšení spolehlivosti a volitelná makro funkce umožňuje rozdělení velkých souborů na několik čárových kódů s metadaty, která pomáhají při jejich opětovném sestavení.

## Proč použít Aspose.BarCode pro PDF417?
Aspose.BarCode podporuje **více než 50 symbologií čárových kódů** a dokáže generovat Macro PDF417 čárové kódy až s **2 000 sloupci**, přičemž zpracovává soubory větší než **10 MB** bez načítání celého obsahu do paměti. Tato kvantifikovaná schopnost zajišťuje plynulý provoz scénářů s vysokou propustností v podnicích a poskytuje rozsáhlé možnosti přizpůsobení.

## Předpoklady

- .NET 6.0 (nebo novější) nainstalovaný  
- Visual Studio 2022 nebo jakékoli IDE kompatibilní s C#  
- Platná licence pro **Aspose.BarCode pro .NET** (bezplatná zkušební verze funguje pro tento příklad)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## Jak vytvořit PDF417 čárový kód v C#?

`BarcodeGenerator` je hlavní třída pro vytváření obrázků čárových kódů.  
`EncodeTypes.MacroPdf417` vybírá symbologii Macro PDF417 pro generování čárového kódu.  
`Save` zapíše vygenerovaný čárový kód do souboru obrázku.

Načtěte `BarcodeGenerator` s výčtem `EncodeTypes.MacroPdf417` a vaším cílovým textem, poté zavolejte `Save` – to je kompletní tok tvorby ve třech řádcích. Generátor automaticky zpracovává Unicode a příkaz `using` zajišťuje uvolnění neřízených prostředků po uložení obrázku.

### Krok 1: vytvořit instanci generátoru čárových kódů v C#

`BarcodeGenerator` třída vytváří a konfiguruje obrázky čárových kódů.  

Instancujte `BarcodeGenerator` s hodnotou výčtu `EncodeTypes.MacroPdf417` a textem, který chcete zakódovat. Text může obsahovat Unicode znaky, které knihovna zpracovává automaticky.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Proč je to důležité*: `EncodeTypes.MacroPdf417` říká enginu, aby vytvořil symbol Macro PDF417, který podporuje segmentovaná data a další metadata na úrovni souboru. Příkaz `using` zajišťuje uvolnění neřízených prostředků po uložení obrázku.

### Krok 2: definovat základní vzhled čárového kódu

`XDimension.Pixels` nastavuje velikost každého modulu čárového kódu v pixelech.

Macro PDF417 čárový kód se skládá ze čtvercových modulů. Ovládání velikosti modulu a počtu sloupců ovlivňuje jak čitelnost, tak velikost souboru.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Proč je to důležité*: `XDimension.Pixels` určuje vizuální hustotu; hodnota 2 pixely funguje dobře pro zobrazení na obrazovce při zachování malého obrázku. Přizpůsobte počet sloupců tak, aby vyhovoval vašim rozvrhovým omezením — více sloupců vytvoří širší, kratší čárový kód.

### Krok 3: nastavit specifická metadata Macro PDF417

`MacroPdf417FileID` identifikuje soubor, ke kterému patří všechny segmenty čárového kódu.

Macro PDF417 rozšiřuje standardní formát PDF417 o pole, která umožňují rekonstrukci velkých souborů z více segmentů čárových kódů. Každé pole je volitelné, ale jejich nastavení demonstruje plné možnosti API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Proč je to důležité*:  
- `MacroPdf417FileID` spojuje všechny segmenty patřící ke stejnému logickému souboru.  
- `MacroPdf417SegmentID` a `MacroPdf417SegmentsCount` umožňují dekodéru správně přeuspořádat fragmenty.  
- `MacroPdf417Checksum` poskytuje rychlou kontrolu integrity bez dekódování celého obsahu.  
- `MacroPdf417FileSize` a `MacroPdf417TimeStamp` umožňují následným systémům ověřit, že rekonstruovaný soubor odpovídá originálu.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` jsou užitečné v logistických nebo dokumentových scénářích.  
- Nastavení `MacroPdf417Terminator` na `Set` označuje tento čárový kód jako poslední segment, což zjednodušuje algoritmus rekonstrukce.

### Krok 4: uložit vygenerovaný obrázek čárového kódu

`Save` zapíše obrázek čárového kódu na zadanou cestu souboru.

Nakonec uložte čárový kód do PNG souboru. Můžete zvolit libovolný podporovaný formát (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Proč je to důležité*: PNG zachovává bezeztrátová data pixelů, což zajišťuje, že skenery přečtou přesně ten modulový vzor, který jste nastavili. Změna formátu může ovlivnit vizuální kvalitu a velikost souboru.

#### Očekávaný výstup

Spuštěním kompletního programu se vytvoří soubor pojmenovaný **ExtPDF417Meta.png**. Otevřením obrázku uvidíte obdélníkový Macro PDF417 čárový kód s kódovaným textem “Åspóse.Barcóde©” a vizuální hustota odpovídá nastavené 2‑pixelové X dimenzi. Skenování obrázku čtečkou kompatibilní s PDF417 vrátí všechna metadata pole definovaná v Kroku 3.

## Kompletní funkční příklad

Zkopírujte níže uvedený kód do nového konzolového projektu (`dotnet new console`) a nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, která existuje na vašem počítači.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Spusťte program (`dotnet run`). Po dokončení ověřte, že se PNG soubor objevil na zadaném umístění. Použijte libovolnou aplikaci pro čtení čárových kódů, která podporuje Macro PDF417, a potvrďte, že metadata jsou správně vložena.

## Běžné varianty a okrajové případy

- **Různé formáty obrázků**: Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Tiff`, pokud váš následný systém preferuje jiný formát.  
- **Změna velikosti modulu**: Větší hodnoty `XDimension.Pixels` zlepšují spolehlivost skenování na nízkorozlišovacích skenerech, ale zvětšují velikost obrázku.  
- **Více segmentů**: Pro vytvoření souboru s více segmenty vygenerujte sérii čárových kódů, inkrementujte `MacroPdf417SegmentID` pro každý a udržujte `MacroPdf417FileID` konstantní. Pouze poslední segment by měl mít nastavený `MacroPdf417Terminator`.  
- **Podpora Unicode**: Generátor automaticky kóduje Unicode znaky; ujistěte se, že váš zdrojový řetězec používá kódování UTF‑8, pokud jej čtete z externího souboru.  
- **Zpracování chyb**: Zabalte blok `using` do try‑catch pro zachycení `BarCodeException` při neplatných parametrech (např. počet sloupců mimo rozsah).

## Profesionální tipy

- **Výkon**: Znovu použijte jedinou instanci `BarcodeGenerator` při vytváření mnoha čárových kódů se stejným nastavením; mezi uložením měňte pouze vlastnost `CodeText`.  
- **Odhad velikosti souboru**: Pole `MacroPdf417FileSize` by mělo odpovídat počtu bajtů originálního obsahu; nesoulad může způsobit selhání validace v následných systémech.  
- **Testování**: Ověřte vygenerované čárové kódy pomocí vestavěného dekodéru Aspose (`BarCodeReader`) i pomocí třetí strany skeneru, aby byla zajištěna interoperabilita.

## Závěr

Tento příklad **Aspose.BarCode** vám ukazuje, jak **vytvořit PDF417 čárový kód v C#** s plnou podporou Macro metadat, což vám poskytuje pevný základ pro budování robustních datových výměnných kanálů založených na čárových kódech.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro Code 16K pomocí Aspose.BarCode pro .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Poslední aktualizace:** 2026-10-09  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vygenerovat PDF417 čárový kód jako obrázek v C s Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Tutoriál generátoru čárových kódů – Jak vygenerovat PDF417 čárový kód](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}