---
category: general
date: 2026-10-15
description: Naučte se, jak v C# generovat čárový kód PDF417 pomocí parametrů Macro‑PDF417,
  nastavit rozměry čárového kódu a uložit jako PNG. Kompletní příklad kódu je zahrnut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: cs
lastmod: 2026-10-15
og_description: Jak vygenerovat čárový kód PDF417 v C# s kompletní konfigurací Macro‑PDF417,
  řízením rozměrů a výstupem PNG. Sledujte kompletní příklad.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Jak vygenerovat čárový kód PDF417 v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Jak generovat čárový kód PDF417 v C# s nastavením Macro‑PDF417
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód PDF417 v C# s nastavením Macro‑PDF417

Pokud potřebujete **jak vygenerovat PDF417 čárový kód** pro workflow dokumentů, tento návod vám ukáže přesné kroky. Uvidíte, jak nastavit parametry Macro‑PDF417, nastavit rozměry čárového kódu a exportovat výsledek jako PNG obrázek — vše v jednom spustitelném C# programu.

Generování PDF417 čárového kódu nevyžaduje více knihoven ani složité post‑processing. Pomocí Aspose.Barcode pro .NET můžete ovládat každý aspekt čárového kódu, od šířky modulu po kontrolní součet, a vytvořit vysoce kvalitní obrázek připravený k tisku nebo skenování.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 (nebo novější) SDK nainstalovaný  
* Visual Studio 2022 nebo libovolné C# IDE dle preference  
* NuGet balíček Aspose.Barcode pro .NET (`Install-Package Aspose.Barcode`)  

Tyto předpoklady zajistí, že kód se zkompiluje bez další konfigurace.

## Krok 1: Vytvořte generátor čárového kódu pro Macro‑PDF417

První operace vytvoří instanci `BarcodeGenerator`, která cílí na formát `EncodeTypes.MacroPdf417`. Konstruktor přijímá data, která chcete zakódovat — v tomto případě řetězec `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Vytvoření generátoru nastaví interní objekt `Parameters`, který použijete k úpravě **C# PDF417 barcode** vlastností.

## Krok 2: Nastavte základní vzhled čárového kódu — rozměry čárového kódu

Řízení vizuální velikosti čárového kódu zlepšuje spolehlivost skenování. Vlastnost `XDimension.Pixels` určuje šířku modulu (tečky), zatímco `Pdf417.Columns` určuje, kolik sloupců čárový kód bude obsahovat.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Nastavení těchto rozměrů zajišťuje, že čárový kód se vejde do typických velikostí štítků a splňuje specifikace skenerů.

## Krok 3: Poskytněte identifikaci souboru pro Macro‑PDF417

Macro‑PDF417 rozšiřuje standardní PDF417 čárový kód o metadata na úrovni souboru. Musíte přiřadit jedinečné ID souboru, ID segmentu, celkový počet segmentů a čitelný název souboru.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Tyto **Macro PDF417 parameters** umožňují downstream systémům rekonstruovat původní soubor z více segmentů čárových kódů.

## Krok 4: Přidejte další macro metadata — zahrňte kontrolní součet čárového kódu

Kromě identifikace může Macro‑PDF417 uložit kontrolní součet, velikost souboru, časové razítko, adresáta, odesílatele a ukončovací příznak. Poskytnutí kontrolního součtu zlepšuje kontrolu integrity dat během dekódování.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Zahrnutí **barcode checksum** a dalších metadat dělá čárový kód samodeskribujícím, což je cenné pro automatizované pipeline zpracování dokumentů.

## Krok 5: Uložte vygenerovaný čárový kód jako PNG obrázek — vyberte formát obrázku čárového kódu

Poslední krok zapíše čárový kód do souboru. Metoda `Save` přijímá cestu k souboru a výčtový typ `BarCodeImageFormat`. PNG poskytuje bezztrátovou kompresi, zachovává ostré hrany pro spolehlivé skenování.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Po spuštění se soubor `MacroPdf417.png` nachází v určené složce a obsahuje ostrý PDF417 čárový kód připravený k vložení do PDF, tisku na štítky nebo zobrazení na obrazovkách.

## Očekávaný výstup

Otevření `C:/Barcodes/MacroPdf417.png` zobrazí obdélníkový čárový kód s kódovaným textem „Sample text“. Čárový kód obsahuje macro metadata, která jste nastavili, a můžete je ověřit libovolným PDF417 skenerem podporujícím Macro‑PDF417. Rozměry obrázku odrážejí šířku modulu (2 px) a počet sloupců (5), což vede ke kompaktnímu, ale čitelnému čárovému kódu.

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Různá délka dat** | Nahraďte `"Sample text"` libovolným UTF‑8 řetězcem; generátor automaticky upraví velikost čárového kódu. |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` na 3 nebo 4 pro větší moduly, užitečné pro tiskárny s nízkým rozlišením. |
| **Více segmentů** | Změňte `MacroPdf417SegmentsCount` tak, aby odpovídal celkovému počtu částí čárových kódů, které plánujete vytvořit. |
| **Alternativní formát obrázku** | Použijte `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp`, pokud váš downstream systém preferuje tyto formáty. |
| **Vlastní úroveň opravy chyb** | Upravte `generator.Parameters.Barcode.Pdf417.ErrorLevel` (rozsah 0‑8) pro kompromis mezi hustotou dat a tolerancí chyb. |

**Tip:** Vždy ověřte vygenerovaný čárový kód fyzickým skenerem před nasazením do produkce. Skenery mohou mít firmware‑specifické limity na šířku modulu nebo počet sloupců.

## Kompletní zdrojový kód

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Spuštěním tohoto programu se vytvoří `MacroPdf417.png` ve složce `C:/Barcodes`. Konzole potvrdí úspěšné vygenerování.

## Závěr

Nyní víte **jak vygenerovat PDF417 čárový kód** v C# s plnou kontrolou Macro‑PDF417, **jak nastavit rozměry čárového kódu**, **jak vložit kontrolní součet čárového kódu** a další macro metadata a **jak exportovat výsledek** pomocí zvoleného **formátu obrázku čárového kódu**. Kompletní příklad můžete zkopírovat do libovolného .NET projektu, upravit pro různé datové payloady a integrovat do větších pipeline automatizace dokumentů.

### Další kroky

* Prozkoumejte **C# PDF417 barcode** úrovně opravy chyb pro zlepšení spolehlivosti skenování.  
* Kombinujte více Macro‑PDF417 segmentů pro kódování velkých souborů, jako jsou PDF nebo obrázky.  
* Přepněte **barcode image format** na SVG pro škálovatelnou vektorovou grafiku ve webových aplikacích.  

Neváhejte experimentovat s parametry a sdílet své výsledky v komentářích nebo na komunitních fórech. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}