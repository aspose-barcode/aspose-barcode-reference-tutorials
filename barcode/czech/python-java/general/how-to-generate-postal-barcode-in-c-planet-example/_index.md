---
category: general
date: 2026-10-28
description: Vygenerujte poštovní čárový kód v C# pomocí formátu Planet. Tento příklad
  planetárního čárového kódu ukazuje, jak nastavit šířku čárového kódu a uložit jak
  vyplněné, tak prázdné pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: cs
lastmod: 2026-10-28
og_description: Vygenerujte poštovní čárový kód v C# s kompletním příkladem planetárního
  čárového kódu. Naučte se nastavit šířku čárového kódu, vytvořit vyplněné pruhy a
  vytvořit obrázky s prázdnými pruhy.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Generování poštovního čárového kódu v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vygenerovat poštovní čárový kód v C# – příklad planet
url: /cs/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat poštovní čárový kód v C# – příklad Planet

Pokud potřebujete v C# generovat poštovní čárový kód, tento průvodce vás provede kompletním řešením. Uvidíte praktický příklad čárového kódu Planet, který kóduje číselný řetězec, umožňuje nastavit šířku čárového kódu a uloží jak obrázky s vyplněnými, tak prázdnými pruhy.

Vytvoření poštovního čárového kódu nevyžaduje složitý build pipeline. Na konci tohoto tutoriálu budete schopni integrovat generování čárových kódů do jakékoli .NET aplikace, přizpůsobit X‑dimenzi a zvolit, zda budou pruhy vyplněné nebo prázdné.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno  
* Vývojové prostředí C# (Visual Studio, VS Code nebo Rider)  
* NuGet balíček **Aspose.BarCode for .NET** (verze 23.10 nebo novější)  

Balíček můžete přidat pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

Níže uvedené úryvky kódu předpokládají, že jste na začátek souboru přidali `using Aspose.BarCode.Generation;`.

## Generování poštovního čárového kódu se symbologií Planet

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která používá symbologii Planet. Planet je poštovní formát čárového kódu používaný několika národními poštovními službami.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Proč je to důležité:**  
`EncodeTypes.Planet` říká knihovně, aby použila standard čárového kódu Planet, který kóduje číselná data v sérii pruhů a mezer. Konstruktor přijímá datový řetězec (`"123456"` v tomto případě), který chcete zakódovat.

Spuštěním programu se v pracovním adresáři spustitelného souboru vytvoří dva PNG soubory:

* **PostalPlanetFilledBars.png** – pruhy jsou vykresleny jako plné černé obdélníky.  
* **PostalPlanetEmptyBars.png** – pruhy jsou vykresleny jako bílé obdélníky s černým obrysem, což je užitečné při tisku na tmavém pozadí.

## Nastavení šířky čárového kódu (X‑dimenze) v pixelech

Vizální velikost čárového kódu je řízena X‑dimenzí, která určuje šířku jednoho pruhu. Úprava této hodnoty zajišťuje, že čárový kód bude správně skenovat při zamýšleném rozlišení tisku.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Proč byste to měli nastavit:**  
Větší X‑dimenze usnadňuje skenování čárového kódu nízkorozlišovacími skenery, zatímco menší hodnota snižuje celkovou velikost obrázku pro vysokohustotní tisk. Výchozí šířka je 2 pixely; 4 pixely jsou běžným kompromisem pro většinu stolních tiskáren.

Můžete experimentovat s různými hodnotami:

| Pixely | Typické použití |
|--------|-----------------|
| 2      | Štítky s vysokou hustotou |
| 4      | Standardní kancelářský tisk |
| 6‑8    | Velkoplošná značení |

**Tip:** Vždy otestujte vygenerovaný čárový kód s vaším cílovým skenerem po změně X‑dimenze.

## Příklad čárového kódu Planet – vyplněné vs prázdné pruhy

Čárový kód Planet může být vykreslen buď s plnými (vyplněnými) pruhy, nebo s obrysem (prázdnými) pruhy. Vlastnost `FilledBars` přepíná toto chování.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Proč byste mohli zvolit prázdné pruhy:**  
Prázdné pruhy zlepšují kontrast na tmavě tónovaném balení, protože bílý vnitřek každého pruhu vyniká na tmavém pozadí. Vyplněné pruhy jsou výchozí a dobře fungují na světle zbarvených médiích.

**Očekávaný výstup:**  

*Oba obrázky zobrazují stejná zakódovaná data (`123456`).* Jediný vizuální rozdíl je ve stylu pruhů. Níže je textový popis toho, co uvidíte:

* **Obrázek s vyplněnými pruhy:** Pevné černé svislé pruhy na bílém pozadí.  
* **Obrázek s prázdnými pruhy:** Černé obrysy tvořící stejný vzor, s bílými vnitřky.

PNG soubory můžete otevřít v libovolném prohlížeči obrázků a ověřit, že vzor odpovídá specifikaci Planet.

## Přizpůsobení dalších vlastností čárového kódu (volitelné)

Zatímco výše uvedené základní kroky pokrývají většinu scénářů, možná budete chtít doladit i další nastavení:

| Vlastnost | Popis | Typická hodnota |
|----------|-------|-----------------|
| `Barcode.Color` | Barva popředí pruhů | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Barva výplně pozadí | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Text čitelný pro člověka zobrazený pod čárovým kódem | Stejný jako zakódovaná data nebo vlastní popisek |
| `Barcode.ImageFormat` | Výstupní formát (PNG, JPEG, BMP, atd.) | `BarCodeImageFormat.Png` |

Příklad nastavení vlastní barvy popředí:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Tyto volitelné úpravy vám pomohou sladit se s firemní identitou nebo splnit konkrétní požadavky na tisk.

## Časté úskalí a jak se jim vyhnout

| Problém | Příčina | Řešení |
|---------|---------|--------|
| Čárový kód je nečitelný | X‑dimenze je příliš malá pro DPI tiskárny | Zvyšte `XDimension.Pixels` na 4 nebo vyšší |
| Soubor obrázku je poškozen | Chybějící oprávnění k zápisu v cílové složce | Použijte absolutní cestu nebo zajistěte, že adresář existuje |
| Použita špatná symbologie | Předání `EncodeTypes.Code128` místo `EncodeTypes.Planet` | Ověřte, že argument `EncodeTypes` odpovídá poštovnímu formátu |

**Tip:** Vždy vygenerujte testovací čárový kód a naskenujte jej s určeným hardwarem před nasazením do produkce.

## Kompletní, spustitelný příklad

Níže je samostatná konzolová aplikace, která zahrnuje všechny zmíněné kroky. Zkopírujte kód do nového .NET konzolového projektu a spusťte jej, abyste viděli dva PNG soubory v výstupním adresáři.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Kroky ověření:**  

1. Sestavte projekt (`dotnet build`).  
2. Spusťte spustitelný soubor (`dotnet run`).  
3. Najděte `PostalPlanetFilledBars.png` a `PostalPlanetEmptyBars.png` ve složce `bin/Debug/net6.0`.  
4. Otevřete každý obrázek; měli byste vidět sérii svislých pruhů představujících číselný řetězec


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit planet čárový kód s vyplněnými a prázdnými pruhy](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Jak nastavit šířku a vygenerovat Planet čárový kód v C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Vytvořit poštovní čárový kód v C# – kompletní příklad generátoru](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}