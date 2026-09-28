---
category: general
date: 2026-07-27
description: Rychle vytvořte čárový kód s daty v C#. Naučte se, jak vytvořit PDF417
  čárový kód v C# pomocí Aspose.BarCode, nastavit rozměry a uložit jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: cs
lastmod: 2026-07-27
og_description: Vytvořte čárový kód s daty v C# pomocí Aspose.BarCode. Tento návod
  ukazuje, jak vytvořit PDF417 čárový kód v C# s vlastními nastaveními a uložit jej
  jako PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Vytvořte čárový kód s daty v C# – Kompletní průvodce programováním
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Vytvořte čárový kód s daty v C# – krok za krokem průvodce
url: /cs/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu s daty v C# – Kompletní programový průvodce

Už jste někdy potřebovali **vytvořit čárový kód s daty** v .NET aplikaci, ale nebyli jste si jisti, které API volání použít? Nejste sami. Ať už označujete inventář, tisknete vstupenky nebo vkládáte informace do mobilního skenování, ovládání tvorby čárových kódů je užitečná dovednost pro každého vývojáře C#.

V tomto tutoriálu projdeme praktickým příkladem, který vám ukáže, jak **vytvořit PDF417 čárový kód c#** pomocí knihovny Aspose.BarCode, upravit šířku modulu, omezit počet sloupců a nakonec výsledek uložit do PNG souboru. Na konci budete mít plně funkční, připravený program pro konzoli, který můžete vložit do jakéhokoli projektu.

## Požadavky — Co budete potřebovat

- **.NET 6.0** nebo novější (kód funguje také s .NET Framework 4.7+)  
- **Aspose.BarCode for .NET** NuGet balíček (`Install-Package Aspose.BarCode`)  
- Editor kódu nebo IDE (Visual Studio, VS Code, Rider – vyberte si svůj oblíbený)  
- Oprávnění pro zápis do složky, kam bude PNG uloženo  

Žádné další konfigurační soubory nejsou vyžadovány; knihovna je samostatná.

## Krok 1: Nastavení projektu a import jmenných prostorů

Nejprve vytvořte nový konzolový projekt (nebo otevřete existující) a přidejte odkaz na Aspose.BarCode.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Proč je to důležité:** Importování správných jmenných prostorů vám poskytuje přístup k `BarcodeGenerator` a souvisejícím nastavením, aniž byste museli kvalifikovat každý typ. Také to činí kód přehlednějším pro budoucí údržbu.

## Krok 2: Inicializace generátoru čárových kódů s vašimi daty

Nyní skutečně **vytvoříme čárový kód s daty**. Konstruktor `BarcodeGenerator` přijímá dva argumenty: symbologii (`EncodeTypes.MicroPdf417`) a řetězec, který chcete zakódovat.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Tip:** Symbologie MicroPdf417 je kompaktní verze PDF417, ideální když potřebujete menší obrázek, ale stále chcete vysokou kapacitu dat. Knihovna podporuje Unicode bez dalších úprav, takže znaky jako “Å” a “©” fungují bez problémů.

## Krok 3: Doladění X‑dimenze (šířka modulu)

Pokud potřebujete ostřejší, vyšší rozlišení obrázku, můžete zmenšit šířku modulu. Nastavení na **2 pixely** vám poskytne jemnější mřížku, aniž by se zvětšila velikost souboru.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč upravovat X‑dimenzi?** Menší X‑dimenze zúží každou čáru, což zlepšuje čitelnost na vysoce rozlišených skenerech a zároveň udržuje celkovou velikost čárového kódu na rozumné úrovni.

## Krok 4: Omezení sloupců PDF417 (volitelné, ale běžné)

PDF417 vám umožňuje určit počet sloupců. Pro MicroPdf417 je maximální hodnota **4**, což udržuje čárový kód krátký a široký.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Hraniční případ:** Pokud nastavíte počet sloupců vyšší než povolené maximum, Aspose jej automaticky omezí, ale je dobrým postupem zůstat v dokumentovaném rozsahu, aby nedošlo k neočekávanému škálování.

## Krok 5: Uložení čárového kódu jako PNG obrázek

Nakonec zapište vygenerovaný obrázek na disk. Metoda `Save` přijímá úplnou cestu a požadovaný formát obrázku.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Pro tip:** PNG zachovává přesná pixelová data, což je pro čárové kódy zásadní. Pokud potřebujete vektorový formát pro škálování, můžete nahradit `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg`.

### Kompletní funkční příklad

Spojením všech částí získáte kompletní program připravený ke kopírování a vložení:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

Spuštěním tohoto programu vznikne PNG soubor, který vypadá zhruba takto:

![Čárový kód vytvořený s daty v C#](barcode-sample.png "Snímek obrazovky čárového kódu vytvořeného s daty v aplikaci C#")

*Obrázek výše je zástupný—váš skutečný čárový kód bude obsahovat přesný řetězec “Åspóse.Barcóde©”.*

## Časté otázky a hraniční případy

| Question | Answer |
|----------|--------|
| *Co když moje data přesáhnou kapacitu MicroPdf417?* | Přepněte na `EncodeTypes.Pdf417` (běžný PDF417), který podporuje až 1 800 znaků. |
| *Mohu změnit formát obrázku na JPEG?* | Ano—nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. Pamatujte, že JPEG je ztrátový; může ovlivnit spolehlivost skeneru. |
| *Musím zpracovávat Unicode ručně?* | Ne. Aspose.BarCode automaticky kóduje Unicode znaky, ale ujistěte se, že váš zdrojový soubor je uložen v kódování UTF‑8. |
| *Co když potřebuji průhledné pozadí?* | Před uložením nastavte `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;`. |
| *Existuje způsob, jak generovat čárový kód v paměti?* | Zavolejte `generator.GenerateBarCodeImage()`, abyste získali objekt `System.Drawing.Image`, který můžete přímo streamovat. |

## Shrnutí – Co jsme se naučili

Ukázali jsme, jak **vytvořit čárový kód s daty** v C# pomocí:

1. Inicializace `BarcodeGenerator` s MicroPdf417 a Unicode řetězcem.  
2. Doladění X‑dimenze pro vyšší rozlišení.  
3. Omezení počtu sloupců pro udržení kompaktnosti čárového kódu.  
4. Uložení výsledku jako PNG soubor.

Všechny tyto kroky dohromady odpovídají na hlavní dotaz “jak **vytvořit PDF417 čárový kód c#**” a zároveň vám ukazují, jak přizpůsobit běžné parametry.

## Další kroky a související témata

- **Přidejte čitelný text** pod čárový kód pomocí `generator.Parameters.Barcode.CodeTextParameters`.  
- **Vložte PNG do PDF** pomocí `Aspose.Pdf` pro tiskové zprávy.  
- **Generujte jiné symbologie** (QR, Code128, DataMatrix) výměnou `EncodeTypes`.  
- **Dávkové zpracování** – projděte CSV soubor s ID produktů a vytvořte složku s čárovými kódy.

Neváhejte experimentovat s počtem sloupců, úrovní opravy chyb a barevnými schématy. Jakmile se s tím seznámíte, můžete vytvořit plnohodnotná řešení označování, která se hladce integrují s inventárními nebo vstupenkovými systémy.

Šťastné programování a ať jsou vaše skeny vždy bez chyb!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Vytvořit DotCode čárový kód – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Vytvořit čárový kód PNG – poměr stran DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}