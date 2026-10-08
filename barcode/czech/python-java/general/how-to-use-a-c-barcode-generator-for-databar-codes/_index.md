---
category: general
date: 2026-09-23
description: Návod na generátor čárových kódů v C# ukazuje, jak pomocí knihovny Aspose.BarCode
  vytvářet obrázky čárových kódů s vlastním poměrem stran.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: cs
lastmod: 2026-09-23
og_description: Průvodce generátorem čárových kódů v C# vás provede tím, jak generovat
  obrázky čárových kódů, upravovat poměry stran a exportovat soubory PNG pomocí Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Vytvořte vysoce kvalitní čárové kódy pomocí generátoru čárových kódů v C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Jak použít generátor čárových kódů v C# pro DataBar kódy
url: /cs/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat generátor čárových kódů v C# pro DataBar kódy

Pokud potřebujete **c# barcode generator**, který dokáže vytvářet DataBar stacked Omni‑Directional symboly, tento průvodce vám poskytne kompletní, připravené řešení. Uvidíte, jak generovat obrázky čárových kódů, ovládat X‑dimenzi a měnit poměr stran, aniž byste opustili IDE.

Generování čárových kódů je běžná potřeba pro inventární systémy, přepravní štítky a aplikace v místech prodeje. Na konci tohoto tutoriálu budete umět vytvořit PNG soubory s libovolným poměrem stran, který si zvolíte, a pochopíte, jak přizpůsobit kód pro jiné typy čárových kódů.

## Prerequisites

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakýkoli C# editor, který preferujete)  
* Odkaz na NuGet balíček **Aspose.BarCode** – knihovna, která poskytuje třídu `BarcodeGenerator`  

Nemusíte používat samostatnou grafickou knihovnu; Aspose.BarCode interně zajišťuje kódování obrázků.

## Step 1: Install the Aspose.BarCode NuGet package

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi knihovny do souboru projektu, čímž zpřístupní třídu `BarcodeGenerator` pro použití.

## Step 2: Define the output folder

Vyberte složku, do které budou uloženy vygenerované PNG soubory. Použití absolutní nebo relativní cesty funguje stejně, ale relativní cesta udržuje projekt přenosný.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Programové vytvoření adresáře zabraňuje chybám za běhu, pokud složka chybí.

## Step 3: Instantiate the C# barcode generator with sample data

Konstruktor `BarcodeGenerator` vyžaduje dva argumenty: typ čárového kódu a datový řetězec. Pro DataBar stacked Omni‑Directional symbol použijete `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Datový řetězec následuje formát GS1 Application Identifier. Výčtový typ `EncodeTypes` obsahuje více než 150 standardů čárových kódů; můžete přepnout na jiný typ změnou hodnoty výčtu.

## Step 4: Set the X‑dimension (pixel size) for the barcode

X‑dimenze řídí šířku nejúzkého pruhu. Hodnota pixelu 2 poskytuje ostrý, vysoce rozlišený obrázek vhodný pro většinu obrazovek.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Úprava X‑dimenze je volitelná, ale dává vám jemnou kontrolu nad vizuální hustotou čárového kódu.

## Step 5: Generate a barcode with an aspect ratio of 15 and save it as PNG

Vlastnost `AspectRatio` patří do podobjektu `DataBar`. Změna této hodnoty protahuje nebo stlačuje čárový kód vertikálně při zachování zakódovaných dat.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapíše čárový kód na zadanou cestu souboru. Výčtový typ `BarCodeImageFormat.Png` zajišťuje bezztrátovou kompresi.

![příklad výstupu generátoru čárových kódů v C#](generated_barcode_example.png)

*Obrázek: čárový kód vygenerovaný s poměrem stran 15.*

## Step 6: Change the aspect ratio to 30 and generate a second image

Opětovné použití stejné instance `BarcodeGenerator` zabraňuje alokaci nového objektu. Stačí aktualizovat `AspectRatio` a znovu zavolat `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory, které se liší jen vertikálním měřítkem. Tato technika je užitečná, když potřebujete stejná data vykreslená pro různé velikosti štítků.

## Common variations and edge cases

### Switching to another barcode type

Pokud potřebujete QR kód, Code 128 nebo PDF417, nahraďte hodnotu výčtu v konstruktoru:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Všechny ostatní kroky konfigurace (X‑dimenze, ukládání) zůstávají stejné.

### Handling unsupported characters

`BarcodeGenerator` ověřuje vstupní řetězec vůči vybrané symbologii. Zadání neplatného znaku vyvolá `ArgumentException`. Zabalte vytvoření do bloku try‑catch, abyste poskytli přátelskou chybovou zprávu:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exporting to other image formats

Aspose.BarCode podporuje BMP, JPEG, TIFF a SVG. Podle toho změňte druhý argument metody `Save`:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### High‑resolution output for printing

Při tisku na vysokodPI tiskárnách zvyšte X‑dimenzi a případně nastavte vlastnost `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Tato nastavení vytvářejí větší soubory, ale zachovávají ostré hrany na fyzických médiích.

## Expected output

Spuštěním kompletního programu se vytvoří následující soubory ve složce `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – DataBar kód standardní výšky  
* `DatabarAspectRatio30.png` – vertikálně natažená verze  

Oba obrázky obsahují stejná zakódovaná GS1 data a můžete je ověřit pomocí libovolné aplikace pro skenování čárových kódů.

## Full source code

Zkopírujte níže uvedený kód do nového konzolového projektu (`dotnet new console`) a spusťte jej. Program vypisuje stavové zprávy do konzole a zapisuje PNG soubory na disk.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Spuštěním programu získáte výstup v konzoli podobný tomuto:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusion

Nyní máte **c# barcode generator**, který dokáže vytvářet DataBar stacked Omni‑Directional symboly, upravovat X‑dimenzi a exportovat PNG soubory s vlastním poměrem stran. Stejný vzor funguje pro jakoukoli jinou symbologii čárových kódů podporovanou Aspose.BarCode, což usnadňuje integraci tvorby čárových kódů do inventárních, přepravních nebo prodejních řešení.

Pokud chcete dál zkoumat, zkuste:

* Generování QR kódů nebo symbolů PDF417 (`how to generate barcode` pro mobilní aplikace)  
* Export do SVG pro škálovatelnou webovou grafiku  
* Vkládání vygenerovaných obrázků přímo do PDF faktur pomocí Aspose.PDF  

Experimentujte s různými hodnotami `AspectRatio`, velikostmi X‑dimenze a výstupními formáty, aby odpovídaly přesně


## What Should You Learn Next?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak upravit velikost čárového kódu – poměr stran Codablock F s Aspose.BarCode pro .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}