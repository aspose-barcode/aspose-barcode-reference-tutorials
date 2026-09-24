---
category: general
date: 2026-08-12
description: Vytvořte čárový kód pomocí Aspose.BarCode a naučte se, jak v několika
  jednoduchých krocích vygenerovat PDF417 s vlastním textem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: cs
lastmod: 2026-08-12
og_description: Generujte čárový kód pomocí Aspose.BarCode. Tento tutoriál ukazuje,
  jak vygenerovat PDF417 s vlastním textem, makro metadaty a uložit výsledek jako
  PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Generování čárového kódu Aspose – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Generování čárového kódu Aspose – kompletní průvodce C#
url: /cs/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu aspose – kompletní průvodce v C#

Pokud potřebujete **generovat čárový kód aspose** pro symbol MacroPdf417, tento tutoriál vás provede celým procesem. Uvidíte, jak nakonfigurovat makro‑specifické možnosti, vložit vlastní text a uložit čárový kód jako PNG obrázek.

Generování čárového kódu pomocí Aspose.BarCode eliminuje ruční výpočty a zaručuje soulad se specifikací PDF417. V následujících krocích se také naučíte **jak generovat pdf417** s vlastními metadaty, jako je ID souboru, počet segmentů a časová razítka. Na konci průvodce budete mít připravený ukázkový kód, který můžete vložit do libovolného .NET projektu.

## Požadavky

* .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+)
* Platná licence Aspose.BarCode pro .NET (bezplatná zkušební verze funguje pro testování)
* Visual Studio 2022 nebo jakékoli C# IDE, které preferujete
* Základní znalost syntaxe C# a objektově orientovaných konceptů

Žádné další NuGet balíčky nejsou vyžadovány kromě **Aspose.BarCode**.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Otevřete svůj projekt ve Visual Studiu a poté spusťte následující příkaz v Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode`, který obsahuje třídu `BarcodeGenerator` používanou v celém tomto tutoriálu.

## Krok 2: Vytvoření generátoru čárového kódu pro MacroPdf417

První řádek vytvoří instanci `BarcodeGenerator`, která cílí na symbologii **MacroPdf417** a vloží vlastní text, který chcete zakódovat.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Proč je to důležité*: Výčtový typ `EncodeTypes.MacroPdf417` říká Aspose, aby považoval čárový kód za makro‑povolený symbol PDF417, který podporuje rozdělení velkých dat do více segmentů. Řetězec `"Åspóse.Barcóde©"` ukazuje, že generátor správně zachází s Unicode znaky.

## Krok 3: Definování základní velikosti modulu

Velikost modulu řídí vizuální hustotu čárového kódu. Hodnota pixelu `2` poskytuje ostrý obrázek, který se dobře tiskne na standardních štítcových tiskárnách.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Zvýšení hodnoty zvětší čárový kód, zatímco snížení může způsobit problémy se skenováním na zařízeních s nízkým rozlišením.

## Krok 4: Konfigurace makro‑specifických možností rozložení PDF417

MacroPdf417 vyžaduje několik dalších parametrů. Tato nastavení vám umožní rozdělit data do více souborů, identifikovat každý segment a ověřit integritu.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Proč je to důležité*: Vlastnost `Columns` ovlivňuje šířku čárového kódu, zatímco makro pole (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) umožňují následným systémům správně znovu složit původní data.

## Krok 5: Přidání dalších makro metadat

Aspose.BarCode vám umožňuje vložit volitelná makro pole, jako je kontrolní součet, velikost souboru, časové razítko a informace o odesílateli/příjemci. Tato pole jsou užitečná pro auditní stopy a detekci chyb.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Proč je to důležité*: Kontrolní součet chrání před chybami přenosu, zatímco časové razítko a pole odesílatele poskytují kontext pro následné zpracování. Nastavení `MacroPdf417Terminator` na `Set` signalizuje, že se jedná o poslední segment v makro sérii.

## Krok 6: Uložení čárového kódu jako PNG obrázek

Nakonec zapište vygenerovaný čárový kód na disk. PNG zachovává bezztrátovou kvalitu, což je ideální pro skenování.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Po dokončení kódu soubor `ExtPDF417Meta.png` obsahuje vysoce rozlišený MacroPdf417 čárový kód, který kóduje vlastní text a všechna makro metadata.

### Očekávaný výstup

Otevření `ExtPDF417Meta.png` ukazuje svisle orientovaný čárový kód s jasně definovanými řádky a sloupci. Skenování obrázku libovolným PDF417 čtečkou vrátí původní řetězec **Åspóse.Barcóde©** a makro pole, která jste nakonfigurovali (ID souboru, ID segmentu, kontrolní součet atd.).

## Jak generovat pdf417 bez makro možností (alternativní scénář)

Pokud potřebujete pouze standardní PDF417 čárový kód, vynechte makro vlastnosti a zachovejte základní konfiguraci:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Tento úryvek ukazuje **jak generovat pdf417** rychle, když makro funkčnost není vyžadována.

## Časté chyby a tipy profesionálů

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Čárový kód je příliš malý na skenování | X‑dimenze nastavena na 1 pixel nebo příliš vysoký počet sloupců | Použijte alespoň `2` pixely pro `XDimension` a udržujte počet sloupců mezi `3` a `9` pro typické velikosti štítků |
| Unicode znaky se zobrazují jako � | Neshoda kódování v souboru projektu | Ujistěte se, že soubor projektu je uložen jako UTF‑8 a zdrojový soubor obsahuje správný BOM |
| Makro pole jsou ignorována skenerem | `MacroPdf417Terminator` není nastaven pro poslední segment | Nastavte `MacroPdf417Terminator = Pdf417MacroTerminator.Set` na posledním segmentu |
| Obrázkový soubor je poškozen | Výstupní stream není řádně uzavřen | Použijte příkaz `using` (jak je ukázáno) k zajištění uvolnění generátoru |

## Kompletní, spustitelný příklad

Zkopírujte následující kód do nové konzolové aplikace a spusťte jej. Program vytvoří čárový kód, uloží jej a vypíše cestu k výstupu do konzole.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Spuštění programu vypíše řádek podobný:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Otevřete soubor a ověřte vizuální výstup.

## Závěr

Nyní víte, jak **generovat čárový kód aspose** pro symbologii MacroPdf417, vložit vlastní Unicode text, nakonfigurovat makro metadata a exportovat výsledek jako PNG obrázek. Stejný vzor vám umožní **jak generovat pdf417** bez makro možností a můžete kód přizpůsobit dalším formátům čárových kódů podporovaným Aspose.BarCode.

Dále prozkoumejte související témata, jako je **vytvořit vlastní text čárového kódu** pro QR kódy, přidávání barevných filtrů pomocí parametrů `Color`, nebo vkládání čárových kódů přímo do PDF dokumentů pomocí Aspose.PDF. Experimentujte s různými hodnotami `XDimension` a počty sloupců, abyste doladili čárový kód pro vaši konkrétní tiskárnu nebo skener.

Šťastné programování a užijte si spolehlivost, kterou Aspose.BarCode přináší vašim .NET řešením pro čárové kódy!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}