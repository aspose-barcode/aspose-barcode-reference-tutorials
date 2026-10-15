---
category: general
date: 2026-10-14
description: Naučte se, jak generovat pdf417 pomocí Aspose.BarCode, přidat vlastní
  text, makro metadata a exportovat výsledek jako PNG v krok‑za‑krokem C# tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Naučte se, jak generovat pdf417 pomocí Aspose.BarCode. Tento průvodce
  ukazuje krok‑za‑krokem, jak přidat vlastní text, makro metadata a uložit barcode
  jako PNG obrázek.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Jak generovat pdf417 – kompletní průvodce C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Jak generovat pdf417 – kompletní průvodce C#
url: /cs/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat pdf417 – kompletní průvodce v C#

Pokud potřebujete **generovat pdf417** pro symbol MacroPdf417, tento tutoriál vás provede celým procesem. Uvidíte, jak nakonfigurovat makro‑specifické možnosti, vložit vlastní Unicode text a uložit čárový kód jako PNG obrázek. Na konci průvodce budete mít připravený úryvek C#, který můžete vložit do libovolného .NET projektu, ať už jde o konzolovou aplikaci, Windows službu nebo cloud‑based mikro‑službu.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.BarCode pro .NET (podporuje více než 70 symbologií).  
- **Mohu přidat Unicode znaky?** Ano – API plně podporuje UTF‑8 řetězce jako `"Åspóse.Barcóde©"`.  
- **Potřebuji licenci pro produkci?** Platná licence Aspose.BarCode je vyžadována pro neomezené používání; bezplatná zkušební verze funguje pro testování.  
- **Které verze .NET jsou podporovány?** .NET 6+, .NET 5, .NET Core 3.1 a .NET Framework 4.7+.  
- **Je PNG nejlepší formát pro tisk?** PNG zachovává bezztrátovou kvalitu a je ideální pro tisk čárových kódů ve vysokém rozlišení.

## Co je pdf417?
`PDF417` je vrstvený lineární čárový kód, který může kódovat až přibližně 1 700 znaků na symbol. Je široce používán pro dopravní jízdenky, identifikační karty a sledování zásob, protože může uložit velké množství dat v kompaktním, strojově čitelném formátu.

## Proč použít Aspose.BarCode pro generování pdf417?
Aspose.BarCode podporuje **více než 70 symbologií čárových kódů**, zpracovává soubory až do **2 GB** bez načítání celého dokumentu do paměti a garantuje **100 % shodu s ISO/IEC 15438**. V benchmarkových testech knihovna vytvoří plnohodnotný MacroPdf417 čárový kód za méně než **150 ms** na typickém vývojovém notebooku, což je dostatečně rychlé i pro scénáře s vysokým průtokem na serveru.

## Předpoklady

* **.NET 6.0 nebo novější** (kód také běží na .NET Framework 4.7+).  
* **Platná licence Aspose.BarCode pro .NET** (bezplatná zkušební verze funguje pro vývoj).  
* **Visual Studio 2022** nebo jakékoli jiné C# IDE, které preferujete.  
* Základní znalost syntaxe C# a objektově orientovaných konceptů.  

Přes **Aspose.BarCode** nejsou vyžadovány žádné další NuGet balíčky.

## Jak generovat pdf417 s makro možnostmi?

Načtěte `BarcodeGenerator` s výčtem `EncodeTypes.MacroPdf417`, nastavte velikost modulu, nakonfigurujte makro pole a nakonec uložte obrázek. Následující kroky ukazují přesné pořadí, které byste měli dodržet, abyste se vyhnuli běžným úskalím.

### Krok 1: nainstalujte NuGet balíček Aspose.BarCode

Přidejte svůj projekt ve Visual Studio a poté spusťte následující příkaz v Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Paket přidá jmenný prostor `Aspose.BarCode`, který obsahuje třídu `BarcodeGenerator` používanou v celém tomto tutoriálu.

### Krok 2: vytvořte generátor čárových kódů pro MacroPdf417

`BarcodeGenerator` je hlavní třída používaná k generování čárových kódů v Aspose.BarCode.  
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

`BarcodeGenerator` je hlavní třída Aspose.BarCode pro vytváření jakéhokoli čárového kódu; obsahuje všechna nastavení kódování a vykreslování.

### Krok 3: definujte základní velikost modulu

`XDimension` nastavuje šířku jednoho modulu (pixelu) v čárovém kódu.  
Velikost modulu řídí vizuální hustotu čárového kódu. Hodnota pixelu `2` poskytuje ostrý obrázek, který se dobře tiskne na standardních etiketových tiskárnách.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Zvýšení hodnoty zvětší čárový kód, zatímco snížení může způsobit problémy se skenováním na zařízeních s nízkým rozlišením.

### Krok 4: nakonfigurujte rozložení specifické pro PDF417 makro

`Columns` určuje počet datových sloupců v PDF417 čárovém kódu.  
MacroPdf417 vyžaduje několik dalších parametrů. Tato nastavení vám umožní rozdělit data do více souborů, identifikovat každý segment a ověřit integritu.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Vlastnost `Columns` ovlivňuje šířku čárového kódu, zatímco makro pole (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) umožňují následným systémům správně znovu sestavit původní data.

### Krok 5: přidejte další makro metadata

`MacroPdf417Terminator` označuje, zda je aktuální segment posledním v sérii makra.  
Aspose.BarCode vám umožňuje vložit volitelná makro pole jako kontrolní součet, velikost souboru, časové razítko a informace o odesílateli/příjemci. Tato pole jsou užitečná pro auditní stopy a detekci chyb.

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

Kontrolní součet chrání před chybami přenosu, zatímco časové razítko a pole odesílatele poskytují kontext pro následné zpracování. Nastavení `MacroPdf417Terminator` na `Set` signalizuje, že se jedná o poslední segment v sérii makra.

### Krok 6: uložte čárový kód jako PNG obrázek

`Save` zapíše vygenerovaný obrázek čárového kódu do souboru ve specifikovaném formátu.  
Nakonec zapíše vygenerovaný čárový kód na disk. PNG zachovává bezztrátovou kvalitu, což je ideální pro skenování.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Když kód skončí, soubor `ExtPDF417Meta.png` obsahuje vysoce rozlišený MacroPdf417 čárový kód, který kóduje vlastní text a všechna makro metadata.

#### Očekávaný výstup

Po otevření `ExtPDF417Meta.png` se zobrazí vertikálně orientovaný čárový kód s jasně definovanými řádky a sloupci. Skenování obrázku libovolným PDF417 čtečkou vrátí původní řetězec **Åspóse.Barcóde©** a makro pole, která jste nakonfigurovali (ID souboru, ID segmentu, kontrolní součet atd.).

## Jak generovat pdf417 bez makro možností?

Pro vytvoření standardního PDF417 čárového kódu stačí nastavit symbologii na `EncodeTypes.Pdf417`, poskytnout text k zakódování, volitelně upravit parametry velikosti jako `XDimension` a `Columns` a poté zavolat `Save`. Tento přístup vynechává všechna makro‑specifická vlastnosti a vytváří jednosegmentový čárový kód vhodný pro většinu aplikací.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Tento úryvek ukazuje **jak rychle generovat pdf417**, když není vyžadována makro funkčnost. Přímá odpověď: vytvořte `BarcodeGenerator` s `EncodeTypes.Pdf417`, nastavte `CodeText`, volitelně upravte `XDimension` a `Columns` a poté zavolejte `Save` s požadovaným formátem obrázku.

## Běžné úskalí a tipy pro profesionály

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| Čárový kód je příliš malý na skenování | X‑dimension nastavena na 1 pixel nebo sloupce příliš vysoké | Použijte alespoň `2` pixely pro `XDimension` a udržujte sloupce mezi `3` a `9` pro typické velikosti etiket |
| Unicode znaky se zobrazují jako � | Neshoda kódování v souboru projektu | Ujistěte se, že soubor projektu je uložen jako UTF‑8 a zdrojový soubor obsahuje správný BOM |
| Makro pole jsou ignorována skenerem | `MacroPdf417Terminator` není nastaven pro poslední segment | Nastavte `MacroPdf417Terminator = Pdf417MacroTerminator.Set` na posledním segmentu |
| Soubor obrázku je poškozen | Výstupní stream není řádně uzavřen | Použijte příkaz `using` (jak je ukázáno) k zajištění uvolnění generátoru |

## Kompletní, spustitelný příklad

`BarcodeGenerator` je třída, která vytváří obrázek čárového kódu.  
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

## Často kladené otázky

**Q: Mohu použít tento kód v ASP.NET Core web API?**  
A: Ano. Stejná třída `BarcodeGenerator` funguje v jakémkoli .NET runtime, včetně ASP.NET Core, pokud je odkazována sestava `Aspose.BarCode`.

**Q: Podporuje Aspose.BarCode jiné formáty obrázků?**  
A: Rozhodně. Můžete uložit do PNG, JPEG, BMP, TIFF a dokonce SVG předáním odpovídající hodnoty výčtu `BarCodeImageFormat` metodě `Save`.

**Q: Jak velká může být zakódovaná data?**  
A: Jeden PDF417 symbol může obsahovat až 1 700 znaků; s MacroPdf417 můžete data rozdělit do více segmentů, což efektivně podporuje neomezenou délku.

**Q: Existuje způsob, jak přidat barvu do čárového kódu?**  
A: Ano. Nastavte vlastnosti `ForeColor` a `BackColor` třídy `BarcodeGenerator` před voláním `Save`, abyste vytvořili barevné čárové kódy.

**Q: Co když potřebuji vložit čárový kód přímo do PDF?**  
A: Použijte Aspose.PDF k vložení vygenerovaného PNG nebo SVG obrázku na stránku PDF, nebo použijte vestavěnou funkci exportu PDF v Aspose.BarCode.

## Závěr

Nyní víte **jak generovat pdf417** pro symbologii MacroPdf417, vložit vlastní Unicode text, nakonfigurovat makro metadata a exportovat výsledek jako PNG obrázek. Stejný vzor vám umožní vytvořit jednoduchý PDF417 čárový kód, když makro možnosti nejsou vyžadovány, a můžete kód přizpůsobit dalším formátům čárových kódů podporovaným Aspose.BarCode. Experimentujte s různými hodnotami `XDimension`, počty sloupců a kombinacemi makro polí, abyste vyladili čárový kód pro konkrétní tiskárnu nebo skener.

Dále prozkoumejte související témata, jako je **vytvořit vlastní text čárového kódu** pro QR kódy, přidání barevných filtrů pomocí parametrů `Color`, nebo vkládání čárových kódů přímo do PDF dokumentů pomocí Aspose.PDF. Flexibilita Aspose.BarCode vám umožní zvládnout vše od jednoduchých jednorázových čárových kódů po složité více‑segmentové makro čárové kódy s pouhými několika řádky C#.

Šťastné programování a užijte si spolehlivost, kterou Aspose.BarCode přináší vašim .NET řešením pro čárové kódy!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat DataMatrix čárový kód s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generovat čárový kód v Javě – Nastavit text kódu pomocí Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Poslední aktualizace:** 2026-10-14  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit Macro Pdf417 čárový kód s Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Upravit velikost čárového kódu C – Průvodce generováním Pdf417 čárových kódů](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Číst čárový kód z obrázku C – Kompletní průvodce s Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}