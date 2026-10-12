---
category: general
date: 2026-10-12
description: Jak rychle generovat čárový kód v C#. Naučte se vytvořit prázdný čárový
  kód a přizpůsobit šířku čáry pro čitelné poštovní čárové kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: cs
lastmod: 2026-10-12
og_description: Jak generovat čárový kód v C# pomocí Aspose.BarCode. Tento průvodce
  vám ukáže, jak vytvořit prázdný čárový kód a upravit rozměry čar podle poštovních
  standardů.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: Jak generovat obrázky čárových kódů v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak generovat obrázky čárových kódů v C# pomocí Aspose.BarCode
url: /cs/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat obrázky čárových kódů v C# pomocí Aspose.BarCode

Pokud potřebujete **jak generovat čárový kód** obrázky z řetězce v .NET aplikaci, tento průvodce poskytuje kompletní, připravené‑k‑spuštění řešení. Uvidíte, jak generovat standardní čárové kódy Planet a RM4SCC, upravit šířku čáry pro čitelnost a **vytvořit prázdný čárový kód** varianty, kde jsou čáry nevyplněné. Kód funguje s nejnovější verzí Aspose.BarCode pro .NET (v.24.10) a běží na .NET 6 nebo novějším.

Generování čárových kódů je běžná potřeba pro přepravní štítky, inventární systémy a platformy pro vstupenky. Na konci tohoto tutoriálu budete schopni programově vytvořit jak vyplněné, tak prázdné čárové kódy, aniž byste potřebovali externí nástroje.

## Prerequisites

Než začnete, ujistěte se, že máte:

* .NET 6 SDK (nebo jakákoli novější verze .NET)
* Visual Studio 2022 nebo VS Code
* Platná licence Aspose.BarCode pro .NET (bezplatná zkušební verze funguje pro testování)
* Základní znalost C# konzolových aplikací

Můžete nainstalovat NuGet balíček Aspose.BarCode pomocí:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavte minimální konzolový projekt

Vytvořte nový konzolový projekt a přidejte požadované `using` direktivy. Následující kód je samostatný příklad; zkopírujte jej do `Program.cs` a spusťte.

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
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Proč je tento krok důležitý

* **Projektová struktura** zajišťuje, že je tutoriál spustitelný bez další konfigurace.
* Namespace `using Aspose.BarCode.Generation;` a `using Aspose.BarCode;` zpřístupňují třídu `BarcodeGenerator` a formáty obrázků.
* Programové vytvoření výstupní složky zabraňuje chybám „adresář nenalezen“ při prvním spuštění.

## Krok 2: Vygenerujte vyplněný čárový kód Planet

První volání `GeneratePlanetBarcode` předává `filled: true`. To vytvoří standardní čárový kód Planet, kde je každá čára vykreslena jako plný černý obdélník.

* **Výsledný soubor:** `PostalPlanetFilledBars.png`
* **Vizuální náznak:** Čáry jsou černé, odpovídají poštovním specifikacím pro tištěnou poštu.

### Očekávaný výstup

Spuštěním programu se vytvoří obrázek podobný tomu níže (skutečný obrázek zde není zobrazen, ale po otevření souboru uvidíte jasný, 6‑ciferný čárový kód).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Krok 3: Vytvořte prázdný čárový kód (Planet s nevyplněnými čárami)

Pro **vytvořit prázdný čárový kód** se stejná metoda volá s `filled: false`. Vlastnost `FilledBars` říká Aspose.BarCode, aby kreslil jen obrysy čar a zanechal vnitřek průhledný.

* **Výsledný soubor:** `PostalPlanetEmptyBars.png`
* **Použití:** Prázdné čárové kódy jsou užitečné, když chcete, aby pozadí zobrazovalo logo nebo barvu a přitom zachovávalo čitelnost čárového kódu.

### Očekávaný výstup

Vygenerovaný PNG obsahuje pouze obrysy čar:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Krok 4: Vygenerujte vyplněný čárový kód RM4SCC

RM4SCC je nizozemský poštovní standard čárových kódů. Příklad používá stejnou X‑dimenzi (4 pixely), aby zachoval vizuální konzistenci s čárovými kódy Planet.

* **Výsledný soubor:** `PostalRM4SCCFilledBars.png`
* **Proč RM4SCC?** Kóduje číselná data v kompaktním formátu, který akceptuje mnoho evropských poštovních služeb.

### Očekávaný výstup

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Praktické tipy a běžné úskalí

| Tip | Explanation |
|-----|-------------|
| **Konzistentní X‑dimenze** | Použití stejné hodnoty `XDimension.Pixels` napříč různými symbologiemi zajišťuje jednotný vzhled na tištěných štítcích. |
| **Nepožívejte stejnou instanci generátoru** | Změna `FilledBars` u existujícího generátoru může vést k neočekávaným výsledkům; vytvořte novou instanci `BarcodeGenerator` pro každý odlišný čárový kód. |
| **Ověřte formát obrázku** | PNG je bezztrátový a ideální pro čárové kódy; komprese JPEG může rozmazat tenké čáry, což způsobí selhání skenování. |
| **Zpracování licence** | Pokud spustíte kód bez licence, vygenerované obrázky budou obsahovat vodoznak. Licenci aplikujte co nejdříve v `Main` pomocí `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Bezpečnost vláken** | `BarcodeGenerator` **není** bezpečný pro více vláken. Vytvořte samostatné instance pro každé vlákno, pokud generujete čárové kódy paralelně. |

## Okrajové případy, na které můžete narazit

* **Omezení délky dat** – Čárové kódy Planet akceptují až 6 číselných znaků. Zadání více znaků vyvolá `ArgumentException`. Ověřte délku vstupu před voláním generátoru.
* **Není‑číslicová data** – RM4SCC také očekává číselný vstup. Pro alfanumerická data potřebujete jinou symbologii (např. Code128). Stejný vzor nastavení `FilledBars` funguje pro jakýkoli typ čárového kódu, který to podporuje.
* **Vysoké rozlišení tisku** – Pokud potřebujete čárové kódy větší než velikost na obrazovce, zvyšte `XDimension.Pixels` (např. 8 nebo 10) a volitelně nastavte `Resolution` v `generator.Parameters.Image`. To udrží čáry ostré při tisku 300 dpi.

## Přehled celého zdrojového souboru

Níže je celý zdrojový soubor znovu pro rychlé zkopírování. Obsahuje všechny kroky, komentáře a volitelný úryvek licence (zakomentovaný).

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
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Závěr

Nyní víte **jak generovat čárový kód** obrázky v C# pomocí Aspose.BarCode a můžete **vytvořit prázdný čárový kód** varianty přepínáním vlastnosti `FilledBars`. Tutoriál pokryl:

* Nastavení konzolového projektu a instalaci balíčku Aspose.BarCode
* Generování vyplněných čárových kódů Planet a RM4SCC
* Vytvoření prázdného (pouze obrysového) čárového kódu Planet
* Úpravu šířky čáry pro čitelnost a řešení běžných úskalí

Dále prozkoumejte další symbologie (Code128, QR, DataMatrix) a experimentujte s barvou, velikostí a formáty obrázků. Integrace generování čárových kódů do webového API nebo Windows služby následuje stejný vzor — stačí nahradit konzolovou metodu `Main` vstupním bodem vaší aplikace.

Šťastné programování a ať vaše aplikace začnou skenovat!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak vytvořit obrázek poštovního čárového kódu v C# pomocí Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Jak vygenerovat poštovní čárový kód v C# s vlastními rozměry](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [Jak vygenerovat obrázek čárového kódu s Aspose.BarCode v C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}