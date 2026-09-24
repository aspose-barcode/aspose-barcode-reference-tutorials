---
category: general
date: 2026-08-09
description: Příklad Aspose Barcode ukazující, jak v C# použít generátor čárových
  kódů k vytvoření Macro PDF417 s plnou podporou metadat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: cs
lastmod: 2026-08-09
og_description: Příklad čárového kódu Aspose ukazuje použití generátoru čárových kódů
  v C# k vytvoření makro PDF417 čárového kódu, který obsahuje ID souboru, data segmentu,
  časové razítko a další metadata.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Příklad čárového kódu Aspose – vytvořit Macro PDF417 v C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Příklad čárového kódu Aspose: generování Macro PDF417 v C#'
url: /cs/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad Aspose barcode: generování Macro PDF417 v C#

Pokud potřebujete **aspose barcode example**, který vytvoří čárový kód Macro PDF417, tento průvodce vám ukáže, jak to provést pomocí **barcode generator C#**. Uvidíte všechna potřebná nastavení, od základních rozměrů po kompletní sadu polí metadat Macro PDF417, a získáte PNG obrázek připravený pro další zpracování.

Tutoriál pokrývá celý pracovní postup, vysvětluje, proč je každý parametr důležitý, a poskytuje připravený kód, který lze okamžitě spustit. Žádné externí odkazy nejsou potřeba; můžete kód zkopírovat, upravit hodnoty a spustit ho ihned.

## Požadavky

Než začnete, ujistěte se, že máte:

- .NET 6.0 (nebo novější) nainstalováno  
- Visual Studio 2022 nebo jakékoli IDE kompatibilní s C#  
- Platnou licenci pro **Aspose.BarCode for .NET** (pro tento příklad funguje bezplatná zkušební verze)  

Přidejte do svého projektu NuGet balíček Aspose.BarCode:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvoření instance barcode generator C# 

Prvním krokem je vytvořit instanci `BarcodeGenerator` s hodnotou výčtu `EncodeTypes.MacroPdf417` a textem, který chcete zakódovat. Text může obsahovat Unicode znaky, které knihovna zpracuje automaticky.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Proč je to důležité*: `EncodeTypes.MacroPdf417` říká enginu, aby vytvořil symbol Macro PDF417, který podporuje segmentovaná data a další metadata na úrovni souboru. `using` blok zajišťuje uvolnění neřízených prostředků po uložení obrázku.

## Krok 2: Definování základního vzhledu čárového kódu

Macro PDF417 čárový kód se skládá ze čtvercových modulů. Ovládání velikosti modulu a počtu sloupců ovlivňuje čitelnost i velikost souboru.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Proč je to důležité*: `XDimension.Pixels` určuje vizuální hustotu; hodnota 2 pixelů dobře funguje pro zobrazení na obrazovce a zároveň udržuje obrázek malý. Upravením počtu sloupců přizpůsobíte kód vašim rozměrům – více sloupců vytvoří širší a kratší čárový kód.

## Krok 3: Nastavení specifických metadat Macro PDF417

Macro PDF417 rozšiřuje standardní formát PDF417 o pole, která umožňují rekonstrukci velkých souborů z více segmentů čárových kódů. Každé pole je volitelné, ale jejich nastavení ukazuje plné možnosti API.

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
- `MacroPdf417FileID` propojuje všechny segmenty patřící ke stejnému logickému souboru.  
- `MacroPdf417SegmentID` a `MacroPdf417SegmentsCount` umožňují dekodéru správně seřadit fragmenty.  
- `MacroPdf417Checksum` poskytuje rychlou kontrolu integrity bez nutnosti dekódovat celý payload.  
- `MacroPdf417FileSize` a `MacroPdf417TimeStamp` umožňují následným systémům ověřit, že rekonstruovaný soubor odpovídá originálu.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` jsou užitečné v logistických nebo dokumentových scénářích.  
- Nastavením `MacroPdf417Terminator` na `Set` označíte tento čárový kód jako poslední segment, což zjednodušuje algoritmus rekonstrukce.

## Krok 4: Uložení vygenerovaného obrázku čárového kódu

Nakonec zapíšete čárový kód do PNG souboru. Můžete zvolit libovolný podporovaný formát (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Proč je to důležité*: PNG zachovává bezztrátová data pixelů, což zajišťuje, že skenery přečtou přesně ten modulový vzor, který jste nastavili. Změna formátu může ovlivnit vizuální kvalitu a velikost souboru.

### Očekávaný výstup

Po spuštění kompletního programu se vytvoří soubor **ExtPDF417Meta.png**. Otevřením obrázku uvidíte obdélníkový Macro PDF417 čárový kód s textem „Åspóse.Barcóde©“ zakódovaným, a vizuální hustota odpovídá nastavené 2‑pixelové X‑dimenzi. Naskenováním obrázku čtečkou kompatibilní s PDF417 získáte všechna metadata definovaná v kroku 3.

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

- **Různé formáty obrázků**: Nahraďte `BarCodeImageFormat.Png` hodnotou `Jpeg`, `Bmp` nebo `Tiff`, pokud váš následný systém upřednostňuje jiný formát.  
- **Změna velikosti modulu**: Větší hodnoty `XDimension.Pixels` zlepšují spolehlivost skenování na nízkém rozlišení, ale zvětšují velikost obrázku.  
- **Více segmentů**: Pro vytvoření souboru s více segmenty vygenerujte sérii čárových kódů, inkrementujte `MacroPdf417SegmentID` u každého a ponechte `MacroPdf417FileID` konstantní. Pouze poslední segment by měl mít nastavený `MacroPdf417Terminator`.  
- **Podpora Unicode**: Generátor automaticky kóduje Unicode znaky; ujistěte se, že váš vstupní řetězec používá kódování UTF‑8, pokud jej čtete z externího souboru.  
- **Zpracování chyb**: Zabalte `using` blok do try‑catch a zachyťte `BarCodeException` pro neplatné parametry (např. počet sloupců mimo rozsah).

## Praktické tipy

- **Výkon**: Znovu použijte jedinou instanci `BarcodeGenerator` při vytváření mnoha čárových kódů se stejným nastavením; mezi ukládáními měňte pouze vlastnost `CodeText`.  
- **Odhad velikosti souboru**: Pole `MacroPdf417FileSize` by mělo odpovídat počtu bajtů původního payloadu; nesoulad může způsobit selhání validace v následných systémech.  
- **Testování**: Ověřte vygenerované čárové kódy jak pomocí vestavěného dekodéru Aspose (`BarCodeReader`), tak pomocí třetí strany, abyste zajistili interoperabilitu.

## Závěr

Tento **aspose barcode example

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich vlastních projektech.

- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro Code 16K pomocí Aspose.BarCode pro .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}