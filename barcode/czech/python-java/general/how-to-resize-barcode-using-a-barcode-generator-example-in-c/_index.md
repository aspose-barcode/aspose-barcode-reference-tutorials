---
category: general
date: 2026-10-08
description: Naučte se, jak změnit velikost obrázků čárových kódů pomocí příkladu
  generátoru čárových kódů v C#, úpravou výšky čáry z 30 px na 60 px pomocí několika
  řádků kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: cs
lastmod: 2026-10-08
og_description: Jak rychle změnit velikost čárového kódu pomocí příkladu generátoru
  čárových kódů v C#. Nastavte výšku čáry, uložte soubory PNG a vyhněte se běžným
  chybám.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Jak změnit velikost čárového kódu v C# – krok za krokem příklad generátoru
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Jak změnit velikost čárového kódu pomocí příkladu generátoru čárových kódů
  v C#
url: /cs/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost čárového kódu pomocí příkladu generátoru čárových kódů v C#

Pokud potřebujete **jak změnit velikost čárového kódu** obrázků v projektu .NET, tento průvodce ukazuje kompletní řešení. Uvidíte stručný **příklad generátoru čárových kódů C#**, který mění výšku čáry z 30 px na 60 px a ukládá každou verzi jako soubor PNG.

Změna velikosti čárového kódu je často vyžadována, když se stejná data musí zobrazovat na účtenkách, štítcích nebo produktových stránkách v různých vizuálních měřítcích. Místo úpravy rastrového obrázku v externím editoru můžete rozměry čárového kódu upravit programově, přičemž zachováte integritu dat.

V tomto tutoriálu se naučíte:

* Nastavit generátor čárových kódů DataBar Omni‑Directional.
* Upravit parametry X‑dimenze a výšky čáry.
* Uložit dva obrázky s odlišnými výškami.
* Pochopit, proč změna výšky čáry funguje a na jaké okrajové případy si dát pozor.

> **Předpoklad** – Máte vývojové prostředí .NET (Visual Studio 2022 nebo novější) a knihovnu čárových kódů, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`. Kód funguje s nejnovější verzí knihovny k říjnu 2026.

## Požadavky pro příklad generátoru čárových kódů v C#

Než začnete, ujistěte se, že máte:

| Položka | Důvod |
|------|--------|
| .NET 6.0 SDK or newer | Poskytuje runtime a jazykové funkce použité ve vzorku. |
| Barcode library (e.g., Aspose.BarCode, Dynamsoft, or any library exposing `BarcodeGenerator`) | Poskytuje výčtový typ `EncodeTypes.DatabarOmniDirectional` a metody pro export obrázků. |
| A folder you can write to (e.g., `C:\Temp\Barcodes\`) | Ukázka ukládá PNG soubory do tohoto umístění. |
| Basic C# knowledge | Tutoriál předpokládá znalost tříd, vlastností a interpolace řetězců. |

Nainstalujte knihovnu přes NuGet, pokud jste tak ještě neučinili:

```bash
dotnet add package Aspose.BarCode
```

Nahraďte název balíčku tím, který skutečně používáte; rozhraní API zobrazené níže je běžné pro většinu SDK čárových kódů.

## Jak změnit velikost čárového kódu – krok 1: vytvořit generátor

Prvním krokem je vytvořit instanci `BarcodeGenerator` s požadovanou symbologií a datovým obsahem. V tomto příkladu generujeme čárový kód **DataBar Omni‑Directional**, který kóduje hodnotu GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Proč je to důležité:** Výčtový typ `EncodeTypes.DatabarOmniDirectional` říká knihovně, který standard čárového kódu použít. Datový řetězec následuje GS1 identifikátor aplikace `(01)` pro 14‑ciferný GTIN, což zajišťuje, že čárový kód splňuje globální obchodní standardy.

## Jak změnit velikost čárového kódu – krok 2: definovat šířku modulu a počáteční výšku čáry

Vizuelní velikost čárového kódu závisí na dvou parametrech:

* **X‑dimenze** – šířka nejmenší čáry (modulu). Měřeno v pixelech nebo milimetrech.
* **Výška čáry** – vertikální délka čar.

Nastavení těchto hodnot před uložením zaručuje, že vykreslený obrázek odpovídá požadovaným rozměrům.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Vysvětlení:** X‑dimenze 2 px poskytuje kompaktní čárový kód, který se stále spolehlivě načítá. Výška 30 px je běžná výchozí hodnota pro malé štítky. X‑dimenzi můžete upravit nezávisle na výšce, pokud potřebujete hustší nebo rozestavěnější vzor.

## Jak změnit velikost čárového kódu – krok 3: uložit první obrázek (výška 30 px)

Nyní exportujte čárový kód do souboru PNG. Metoda `Save` přijímá cestu k souboru a výčtový typ formátu obrázku.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Výsledek:** `DatabarBarHeight30Pixels.png` obsahuje čárový kód vysoký 30 px. Soubor můžete otevřít v libovolném prohlížeči obrázků a ověřit rozměry.

## Jak změnit velikost čárového kódu – krok 4: změnit výšku čáry na 60 px

Pro vytvoření větší verze jednoduše upravte vlastnost `BarHeight`. Generátor znovu použije stejná data a X‑dimenzi, takže vzor čárového kódu zůstane identický – mění se jen vizuální velikost.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Proč to funguje:** Vykreslovací engine čárových kódů vypočítává geometrii každé čáry na požádání. Aktualizace vlastnosti výšky před dalším voláním `Save` spustí novou rasterizaci s novými rozměry.

## Jak změnit velikost čárového kódu – krok 5: uložit druhý obrázek (výška 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory, jeden malý (30 px) a jeden větší (60 px), připravené k použití na různých velikostech štítků.

## Kompletní zdrojový kód pro příklad generátoru čárových kódů v C#

Níže je kompletní spustitelný program. Zkopírujte jej do nového konzolového projektu a okamžitě otestujte.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Očekávaný výstup v konzoli:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Po spuštění otevřete oba PNG soubory a podívejte se na vizuální rozdíl. Oba čárové kódy kódují stejnou hodnotu GTIN‑14 a budou skenovány identicky, bez ohledu na výšku.

## Proč je úprava výšky čáry bezpečná pro skenování

Skenery čárových kódů čtou vzor světelných a tmavých modulů, nikoli absolutní počet pixelů. Dokud **X‑dimenze** zůstává v toleranci skeneru (obvykle 0,5 mm až 2 mm v fyzických jednotkách), změna výšky neovlivní čitelnost. Knihovna automaticky škáluje moduly a zachovává požadované tiché zóny a zarovnávací vzory.

## Časté úskalí a jak se jim vyhnout

| Problém | Řešení |
|---------|------------|
| **Výstupní složka neexistuje** | Zavolejte `Directory.CreateDirectory(outputPath)` před uložením. |
| **Nesprávná X‑dimenze způsobující rozmazané skeny** | Udržujte `XDimension.Pixels` mezi 1 px a 4 px pro většinu tiskáren; testujte s fyzickým skenerem. |
| **Použití rastrového formátu pro velmi velké čárové kódy** | Přepněte na `BarCodeImageFormat.Svg` pro nekonečnou škálovatelnost bez pixelace. |
| **Zapomenutí resetovat `BarHeight` před druhým uložením** | Ujistěte se, že novou výšku přiřadíte **před** opětovným voláním `Save`. |

## Pro tip: generovat více velikostí ve smyčce

Pokud potřebujete řadu výšek (např. 30 px, 45 px, 60 px), jednoduchá smyčka `foreach` snižuje duplicitu:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Tento vzor se dobře škáluje pro dávkové zpracování katalogů produktů.

## Okrajové případy: různé formáty obrázků a nastavení DPI

* **SVG výstup** – Použijte `BarCodeImageFormat.Svg` k vytvoření vektorového souboru, který lze měnit velikost bez ztráty kvality.
* **High‑DPI PNG** – Nastavte `generator.Parameters.Image.DpiX` a `DpiY` na 300 nebo 600 pro tiskové obrázky; výška čáry bude i nadále měřena v pixelech, takže ji zvyšte úměrně.
* **Nestandardní symbologie** – Některé typy čárových kódů (např. QR Code) mají samostatnou vlastnost `Size` místo `BarHeight`. Prohlédněte si dokumentaci knihovny pro tyto případy.

## Testování změněné velikosti čárového kódu

1. Otevřete každý PNG v prohlížeči obrázků a ověřte rozměry v pixelech (např. 150 × 30 px vs. 150 × 60 px).  
2. Vytiskněte obrázky v měřítku 100 %.  
3. Naskenujte pomocí ručního skeneru čárových kódů nebo mobilní aplikace. Dekódovaná data by měla být

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Příklad generátoru čárových kódů v C# – nastavit šířku a výšku](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Jak změnit velikost čárového kódu v C# s Aspose.BarCode – krok za krokem](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Jak uložit obrázky čárových kódů pomocí Barcode Generator C# – krok za krokem](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}