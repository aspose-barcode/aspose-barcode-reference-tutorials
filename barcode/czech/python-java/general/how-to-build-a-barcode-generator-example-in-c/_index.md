---
category: general
date: 2026-09-19
description: Příklad generátoru čárových kódů ukazující, jak změnit výšku, vytvořit
  DataBar Omni‑Directional a upravit rozměry čárového kódu pro výstup obrázku v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: cs
lastmod: 2026-09-19
og_description: příklad generátoru čárových kódů, který učí, jak změnit výšku, vytvořit
  DataBar Omni‑Directional a upravit rozměry čárového kódu pro PNG obrázek v C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Příklad generátoru čárových kódů v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit příklad generátoru čárových kódů v C#
url: /cs/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad generátoru čárových kódů v C# – kompletní programovací průvodce

Pokud potřebujete **příklad generátoru čárových kódů** pro projekt .NET, tento průvodce vám přesně ukáže, jak vytvořit, nakonfigurovat a uložit DataBar Omni‑Directional čárový kód pomocí C#. Naučíte se, jak změnit výšku, upravit rozměry čárového kódu a vytvořit vysoce kvalitní PNG obrázek – vše v jediné spustitelné konzolové aplikaci.

Níže uvedené kroky pokrývají vše od instalace požadovaného SDK až po ladění X‑dimenze a výšky čárového kódu. Na konci tutoriálu budete mít připravený generátor čárových kódů, který můžete integrovat do fakturace, inventarizace nebo jakéhokoli skenovacího workflow.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* Aktivní licenci pro **Aspose.BarCode for .NET** (zdarma zkušební verze stačí pro testování)  

Pokud dáváte přednost jiné knihovně, koncepty úpravy rozměrů a ukládání obrázku zůstávají stejné; stačí nahradit příslušné API volání.

## Krok 1: Nastavte projekt a přidejte balíček Aspose.BarCode

Vytvořte nový konzolový projekt a odkažte knihovnu čárových kódů.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Příkaz `dotnet add package` stáhne nejnovější stabilní verzi Aspose.BarCode, která obsahuje plnou podporu pro symboly DataBar Omni‑Directional.

## Krok 2: Napište kompletní příklad generátoru čárových kódů

Otevřete **Program.cs** a nahraďte jeho obsah následujícím kódem. Tento blok obsahuje celý **příklad generátoru čárových kódů** – žádné chybějící části.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Proč je každý řádek důležitý

* **Vytvoření generátoru čárových kódů** – Konstruktor `BarcodeGenerator` spojuje typ kódování (`EncodeTypes.DatabarOmniDirectional`) s daty, která chcete zakódovat. Toto je jádro kroku **jak vytvořit databar**.  
* **Úprava rozměrů čárového kódu** – Vlastnost `XDimension.Pixels` určuje šířku nejtenčího pruhu. Změna této hodnoty ovlivňuje celkovou velikost a spolehlivost skenování.  
* **Jak změnit výšku** – Vlastnost `BarHeight.Pixels` řídí vertikální velikost. Zvýšení výšky zlepšuje čitelnost pro ruční skenery, zatímco snížení šetří místo na malých štítcích.  
* **Volitelné úpravy** – Nastavení barev popředí/pozadí nebo úrovní korekce chyb je volitelné, ale ukazuje, jak rozšířit koncept **úprava rozměrů čárového kódu**.  
* **Vytvoření obrázku čárového kódu C#** – Metoda `Save` zapíše čárový kód na disk. Použití `BarCodeImageFormat.Png` zajišťuje bezztrátovou kompresi, což je ideální pro většinu aplikací.

## Krok 3: Sestavte a spusťte příklad

Zkompilujte a spusťte program:

```bash
dotnet run
```

Měli byste vidět výstup v konzoli:

```
Barcode saved to DatabarOmniDirectional.png
```

Soubor s názvem **DatabarOmniDirectional.png** se objeví ve složce projektu. Otevřením obrázku uvidíte ostrý DataBar Omni‑Directional čárový kód připravený ke skenování.

## Jak změnit výšku po vytvoření

Pokud potřebujete generovat čárové kódy s různou výškou, zabalte přiřazení výšky do metody:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Volání `SetBarHeight(generator, 45);` před `Save` umožní **jak změnit výšku** dynamicky na základě vstupu uživatele nebo konfiguračních souborů.

## Jak vytvořit DataBar Omni‑Directional čárové kódy s různými daty

Symbologie DataBar Omni‑Directional podporuje GTIN‑14, GTIN‑13 a další číselné identifikátory. Pro zakódování jiné hodnoty stačí nahradit řetězec v konstruktoru:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Pamatujte, že data musí být číselná a správně formátovaná; jinak generátor vyhodí `BarcodeException`.

## Úprava rozměrů čárového kódu pro různé tiskové scénáře

Různé tiskárny a velikosti štítků vyžadují odlišné X‑dimenze a výšky. Použijte následující tabulku jako rychlou referenci:

| Scénář                         | X‑Dimension (pixels) | Bar Height (pixels) |
|--------------------------------|----------------------|---------------------|
| Malý štítek (25 mm × 15 mm)    | 1                    | 20                  |
| Střední štítek (50 mm × 30 mm) | 2                    | 30                  |
| Velký štítek (100 mm × 50 mm)  | 3                    | 45                  |

Tyto hodnoty aplikujte nastavením `generator.Parameters.Barcode.XDimension.Pixels` a `BarHeight.Pixels`.

## Pro tip: ověřte vygenerovaný čárový kód

Před odesláním štítku můžete programově ověřit jeho čitelnost:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Tento úryvek ukazuje rychlou **úpravu rozměrů čárového kódu** kontrolu, která zajišťuje, že čárový kód splňuje požadavky na skenování.

## Časté úskalí a jak se jim vyhnout

| Úskalí                                 | Proč k tomu dochází                         | Oprava                                                                 |
|----------------------------------------|---------------------------------------------|------------------------------------------------------------------------|
| Použití ne‑číselných dat pro DataBar    | DataBar očekává číselné GTIN formáty        | Ujistěte se, že řetězec odpovídá vzoru `(01)XXXXXXXXXXXXX`.            |
| Nastavení X‑dimenze na 0 nebo záporné  | Knihovna vyhodí `ArgumentOutOfRangeException`| Použijte minimum 1 pixel; nejprve otestujte na cílové tiskárně.        |
| Ukládání do složky jen pro čtení       | `UnauthorizedAccessException` při `Save`   | Vyberte zapisovatelný adresář nebo spusťte aplikaci s potřebnými právy.|
| Zapomenutí uvolnit `BarCodeReader`     | Únik paměti v dlouho běžících službách      | Zabalte čtečku do `using` bloku nebo zavolejte `Dispose()` ručně.      |

Řešení těchto problémů včas šetří čas ladění a zvyšuje stabilitu v produkci.

## Kompletní přehled zdrojového kódu

Níže je kompletní, připravený k zkopírování program, který implementuje **příklad generátoru čárových kódů** od začátku až do konce.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Spuštěním tohoto programu vznikne PNG soubor, který vypadá takto (ilustrační):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Alt text obrázku*: **DataBar Omni‑Directional barcode generated in C#** (odpovídá `og_image_alt`).

## Závěr

Nyní máte **příklad generátoru čárových kódů**, který ukazuje, jak změnit výšku, jak vytvořit DataBar Omni‑Directional symboly a jak **upravit rozměry čárového kódu** pro optimální skenování. Kompletní C# kód ukládá PNG obrázek, ověřuje jej a může být rozšířen pro hromadnou generaci nebo integraci do webových služeb.

Dále prozkoumejte související témata, jako je **vytváření QR kódů s Aspose.BarCode**, **hromadné zpracování více hodnot čárových kódů** nebo **vkládání čárových kódů do PDF dokumentů**. Každé z nich staví na stejných základech, které jsou v tomto průvodci pokryty.

Šťastné programování a ať jsou vaše čárové kódy vždy skenovatelné!


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}