---
category: general
date: 2026-10-28
description: Jak generovat čárový kód s vlastním textem pomocí Aspose.BarCode – krok
  za krokem průvodce pro .NET vývojáře k vytvoření obrázků čárových kódů Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: cs
lastmod: 2026-10-28
og_description: Jak vygenerovat čárový kód s vlastním textem v .NET pomocí Aspose.BarCode.
  Postupujte podle tohoto kompletního průvodce, abyste vytvořili a uložili makro PDF417
  čárový kód.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Jak generovat čárový kód s vlastním textem – tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Jak vygenerovat čárový kód s vlastním textem pomocí Aspose.BarCode pro .NET
url: /cs/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód s vlastním textem pomocí Aspose.BarCode pro .NET

Generování čárového kódu s vlastním textem je častý požadavek, když potřebujete vložit identifikátory, časová razítka nebo jiné metadata přímo do vizuálního kódu. Tento tutoriál vám ukáže, jak vygenerovat čárový kód Macro PDF417, který nese vlastní text a kompletní sadu metadat, pomocí knihovny **Aspose.BarCode** pro .NET.

Naučíte se, jak nakonfigurovat generátor, použít vlastní text, nastavit specifická pole Macro PDF417 a uložit výsledek jako PNG obrázek. Žádné externí nástroje nejsou potřeba – stačí balíček Aspose.BarCode NuGet a vývojové prostředí .NET.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* **Aspose.BarCode for .NET** NuGet balíček (`Install-Package Aspose.BarCode`)  

Tyto požadavky zajišťují, že kód se zkompiluje a spustí bez další konfigurace.

## Krok 1: Instalace balíčku Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi Aspose.BarCode do vašeho projektu a poskytne vám přístup ke třídě `BarcodeGenerator` a všem souvisejícím parametrům.

## Krok 2: Vytvoření nové konzolové aplikace

Vytvořte minimální konzolovou aplikaci, která bude obsahovat logiku generování čárového kódu:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Proč je každý řádek důležitý

* **EncodeTypes.MacroPdf417** – vybírá symbologii Macro PDF417, která podporuje segmentovaná data a metadata.  
* **XDimension.Pixels** – řídí velikost každého modulu; hodnota 2 pixely poskytuje čistý, čitelný obrázek.  
* **Pdf417.Columns** – snižuje celkovou šířku, čímž je čárový kód kompaktnější pro tištěné štítky.  
* **MacroPdf417* properties** – vkládá informace na úrovni souboru (ID, počet segmentů, časová razítka atd.) přímo do čárového kódu. Tato schopnost je unikátní pro Macro PDF417 a často se používá v logistice nebo systémech správy dokumentů.  
* **Save(..., BarCodeImageFormat.Png)** – zapisuje bezztrátový PNG soubor, zachovává ostré hrany čárového kódu pro spolehlivé skenování.

## Krok 3: Spuštění programu a ověření výstupu

Sestavte a spusťte konzolovou aplikaci:

```bash
dotnet run
```

Program vytvoří soubor `ExtPDF417Meta.png` v pracovním adresáři projektu. Otevřením souboru se zobrazí čárový kód Macro PDF417, který kóduje text **„Åspóse.Barcóde©“** spolu s metadaty, která jste zadali.

**Očekávaný výstup** – PNG obrázek podobný tomu níže:

![příklad výstupu generování čárového kódu PNG obrázek zobrazující čárový kód Macro PDF417](ExtPDF417Meta.png)

*Alt text obrázku (“příklad výstupu generování čárového kódu PNG obrázek”) posiluje hlavní klíčové slovo pro přístupnost a SEO.*

## Běžné varianty a okrajové případy

### Použití jiného typu čárového kódu

Pokud potřebujete **generovat čárový kód s vlastním textem** pro QR kód místo Macro PDF417, nahraďte `EncodeTypes.MacroPdf417` za `EncodeTypes.QR`. Zbytek struktury parametrů zůstává stejný, ale QR kódy nepodporují pole Macro metadata.

### Práce s Unicode znaky

Příklad již obsahuje Unicode znaky (`Å`, `ó`, `©`). Aspose.BarCode zpracovává UTF‑8 vstup přímo, ale měli byste zajistit, aby zdrojový soubor byl uložen s kódováním UTF‑8, aby nedošlo k varováním při kompilaci.

### Ukládání do jiných formátů obrázků

Aspose.BarCode podporuje BMP, JPEG, TIFF a SVG kromě PNG. Změňte hodnotu výčtu `BarCodeImageFormat` podle potřeby:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Velké datové sady

Macro PDF417 může rozdělit data do více segmentů. Když text překročí kapacitu jednoho segmentu, zvyšte `MacroPdf417SegmentID` a udržujte `MacroPdf417SegmentsCount` konzistentní napříč všemi vygenerovanými částmi. Tento přístup je nezbytný pro scénáře **create barcode aspose**, kde je náklad větší než může pojmout jeden čárový kód.

### Ošetření chyb

Zabalte logiku generování do bloku try‑catch, aby se zobrazily runtime chyby, jako jsou neplatné cesty k souborům nebo nepodporované znaky:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Profesionální tipy pro spolehlivé generování čárových kódů

* **Ověřte čárový kód** po vytvoření pomocí `BarCodeReader`. Tento dodatečný krok potvrzuje, že kódovaná data odpovídají vašim očekáváním.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* *Udržujte X‑dimension mezi 2 – 4 pixely* pro většinu skenerů. Menší hodnoty mohou vést k nečitelnosti na zařízeních s nízkým rozlišením.

* *Vyhněte se příliš dlouhým názvům souborů* v `MacroPdf417FileName`. Specifikace omezuje toto pole na 32 znaků.

* *Používejte konzistentní časová razítka* (UTC) při generování více segmentů, aby se usnadnilo následné zpracování.

## Závěr

Nyní víte **jak vygenerovat čárový kód** s vlastním textem pomocí Aspose.BarCode pro .NET, jak nakonfigurovat metadata Macro PDF417 a jak uložit výsledek jako PNG obrázek. Kompletní, spustitelný příklad demonstruje každý potřebný krok – od instalace NuGet balíčku po práci s Unicode znaky a uložení výstupu.

Odtud můžete:

* **Generovat čárový kód s vlastním textem** pro jiné symbologie (QR, DataMatrix, atd.)  
* **Vytvořit Aspose čárový kód** workflowy, které dávkově zpracovávají tisíce obrázků  
* Integrovat kód generování čárových kódů do služeb ASP.NET Core, Windows služeb nebo Azure Functions  

Experimentujte s různými parametry, prozkoumejte další pole metadat a začleňte čárový kód do vašich pipeline pro automatizaci dokumentů. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}