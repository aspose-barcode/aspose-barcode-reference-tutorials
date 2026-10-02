---
category: general
date: 2026-09-10
description: Rychle generujte čárový kód PDF417 v C#. Naučte se, jak generovat PDF417
  a jak změnit velikost čárového kódu pomocí Aspose.BarCode během několika řádků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: cs
lastmod: 2026-09-10
og_description: Okamžitě generujte čárový kód PDF417 v C#. Tento tutoriál ukazuje,
  jak generovat PDF417 a jak změnit velikost čárového kódu pomocí Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Generování čárového kódu PDF417 v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak vygenerovat čárový kód PDF417 v C# – krok za krokem
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód PDF417 v C# – krok za krokem

Pokud potřebujete **vygenerovat čárový kód PDF417** v .NET aplikaci, tento návod vám přesně ukáže, jak na to. Uvidíte stručný, připravený příklad, který vytvoří čárový kód PDF417, umožní vám ovládat jeho velikost a uloží výsledek jako PNG obrázek.

Generování čárového kódu PDF417 je běžná potřeba pro inventární systémy, palubní vstupenky a sledování dokumentů. V tomto tutoriálu také pokrýváme **jak změnit velikost čárového kódu**, aby se kód přizpůsobil různým požadavkům na tisk nebo zobrazení na obrazovce.

## Předpoklady

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)
* Visual Studio 2022 nebo jakékoli C# IDE
* NuGet balíček **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Základní znalost C# konzolových aplikací

## Nastavení projektu

1. Vytvořte nový konzolový projekt:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Přidejte referenci na Aspose.BarCode (viz předpoklady).  

3. Otevřete `Program.cs` a nahraďte jeho obsah úplným příkladem níže.

## Krok 1: Vygenerovat čárový kód PDF417

Prvním krokem je vytvořit instanci `BarcodeGenerator` nakonfigurovanou pro **PDF417** symbologii. Tento objekt je vstupním bodem pro všechny operace s čárovými kódy.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Proč je to důležité* – Hodnota výčtu `EncodeTypes.Pdf417` říká Aspose.BarCode, aby použil standard PDF417, zatímco druhý argument poskytuje data, která budou zakódována. Generátor nyní obsahuje kompletní objekt čárového kódu, který můžete před uložením přizpůsobit.

## Krok 2: Jak změnit velikost čárového kódu (velikost modulu)

Čárové kódy PDF417 se skládají z malých čtvercových modulů. Úprava velikosti modulu mění celkové rozměry obrázku, aniž by se změnila zakódovaná data.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Proč je to důležité* – Větší `XDimension` vytvoří větší čárový kód vhodný pro tisk ve vysokém rozlišení; menší hodnota je lepší pro zobrazení na obrazovce. Výchozí hodnota je obvykle 1 px, což může na moderních monitorech vypadat stísněně.

## Krok 3: Nastavení rozvržení – sloupce a řádky

PDF417 umožňuje definovat počet sloupců a řádků, což ovlivňuje jak tvar čárového kódu, tak jeho kapacitu korekce chyb.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Proč je to důležité* – Více sloupců činí čárový kód širším, více řádků jej prodlužuje. Přizpůsobte tyto hodnoty tak, aby odpovídaly dostupnému prostoru ve vašem UI nebo tištěné etiketě.

## Krok 4: Uložit obrázek čárového kódu

Nakonec zapíšete čárový kód do souboru. Zde používáme PNG, protože zachovává ostré hrany a podporuje průhlednost.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Spuštěním programu se vytvoří soubor `LayoutPdf417.png` ve výstupní složce projektu. Obrázek bude vypadat takto:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="generate PDF417 barcode example showing 4 columns and 9 rows"}

*Tip*: Pokud potřebujete jiný formát obrázku (JPEG, BMP, TIFF), nahraďte `BarCodeImageFormat.Png` odpovídající hodnotou výčtu.

## Jak generovat PDF417 – alternativní zdroje dat

Výše uvedený kód používá pevně zadaný řetězec `"Layout test"`. V reálných scénářích často získáváte data z databáze, souboru nebo vstupu uživatele.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Zbytek kroků (velikost, rozvržení, ukládání) zůstává beze změny. Toto ukazuje **jak generovat PDF417** z dynamických zdrojů bez další složitosti.

## Časté problémy a jak se jim vyhnout

| Problém | Proč se vyskytuje | Řešení |
|---------|-------------------|--------|
| Čárový kód je rozmazaný | `XDimension` nastaven příliš nízko pro výstupní rozlišení | Zvyšte `XDimension.Pixels` nebo uložte ve vektorovém formátu jako SVG (`BarCodeImageFormat.Svg`) |
| Text se nevejde do zvoleného rozvržení | Příliš mnoho znaků pro vybrané řádky/sloupce | Snižte počet řádků/sloupců nebo rozdělte data do více čárových kódů |
| Soubor obrázku nebyl vytvořen | Výstupní složka neexistuje nebo chybí oprávnění k zápisu | Zajistěte, aby složka existovala (`Directory.CreateDirectory`) a aplikace měla potřebná práva |

## Ověření čárového kódu

Po vygenerování obrázku jej můžete ověřit pomocí libovolné aplikace pro skenování PDF417 (na mobilních telefonech jsou k dispozici zdarma) nebo pomocí vestavěného čtečky Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Pokud výstup odpovídá původnímu textu, proces **generování čárového kódu PDF417** byl úspěšný.

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat a vložit do `Program.cs`. Obsahuje všechny using direktivy, ošetření chyb a komentáře.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Spuštěním tohoto programu se vypíše:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Nyní máte **kompletní, samostatné řešení** pro generování čárových kódů PDF417 a řízení jejich velikosti.

## Závěr

V tomto tutoriálu jste se naučili, jak **vygenerovat čárový kód PDF417** v C# pomocí Aspose.BarCode, jak **změnit velikost čárového kódu** úpravou X‑dimenze a jak konfigurovat sloupce a řádky pro kontrolu rozvržení. Také jste viděli, jak programově ověřit výsledek a jak přizpůsobit kód pro dynamická data.

Dále můžete zkusit:

* **Jak generovat PDF417** s laděním úrovně korekce chyb (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Export do **vektorových formátů** (SVG, EPS) pro neomezené škálování
* Vložení čárového kódu do PDF dokumentu pomocí **Aspose.PDF**

Experimentujte s různými velikostmi modulů a možnostmi rozvržení, aby vyhovovaly vašim konkrétním požadavkům na UI nebo tisk. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}