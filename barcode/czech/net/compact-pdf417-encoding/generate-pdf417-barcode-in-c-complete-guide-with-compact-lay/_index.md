---
category: general
date: 2026-08-19
description: Rychle generujte čárový kód PDF417 v C#. Naučte se, jak generovat čárový
  kód PDF417 v C# pomocí Aspose.BarCode s kompaktním režimem a vlastními nastaveními.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: cs
lastmod: 2026-08-19
og_description: Vytvořte čárový kód PDF417 v C# pomocí Aspose.BarCode. Tento tutoriál
  ukazuje, jak v C# generovat čárový kód PDF417 v kompaktním režimu, nastavit X‑rozměr
  a uložit jako PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Vytvořte čárový kód PDF417 v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generování čárového kódu PDF417 v C# – kompletní průvodce s kompaktním rozložením
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování PDF417 čárového kódu v C# – kompletní průvodce

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám přesně ukáže, jak na to. Uvidíte stručný, připravený pro produkci příklad, který vytvoří kompaktní PDF417 čárový kód, přizpůsobí X‑dimenzi a uloží výsledek jako PNG obrázek.

Generování PDF417 čárového kódu je běžné, když potřebujete zakódovat velké množství dat—například informace o vstupenkách, přepravní manifesty nebo identifikační dokumenty—do strojově čitelného formátu. Použití Aspose.BarCode proces zjednodušuje a kód funguje s .NET 6+ nebo .NET Framework 4.7.2 a novějšími.

V tomto průvodci se naučíte:

* Nainstalovat NuGet balíček Aspose.BarCode.
* Napsat samostatný C# program, který **generuje PDF417 čárový kód** s malým počtem sloupců a v kompaktním (zkráceném) režimu.
* Upravit šířku čáry (X‑dimenzi) pro ostřejší vykreslení.
* Uložit čárový kód jako PNG soubor.
* Prozkoumat varianty, okrajové případy a tipy pro nejlepší praxi.

## Požadavky

Než začnete, ujistěte se, že máte:

* Visual Studio 2022 (nebo jakékoli C# IDE) s nainstalovaným .NET 6 SDK.
* Přístup k internetu pro stažení **Aspose.BarCode** NuGet balíčku.
* Oprávnění k zápisu do složky, kam bude PNG soubor uložen.

Žádné další knihovny nejsou potřeba; Aspose.BarCode interně zpracovává kódování obrázku.

## Krok 1: Přidejte balíček Aspose.BarCode

Otevřete svůj projekt ve Visual Studiu, klikněte pravým tlačítkem na řešení a vyberte **Manage NuGet Packages**. Vyhledejte `Aspose.BarCode` a nainstalujte nejnovější stabilní verzi.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Udržujte balíček aktuální. Nová vydání často obsahují vylepšení výkonu a podporu nejnovějších .NET runtime.

## Krok 2: Vytvořte minimální konzolovou aplikaci

Vytvořte nový C# konzolový projekt, pokud ještě žádný nemáte:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Nahraďte obsah souboru `Program.cs` následujícím kompletním příkladem. Tento program demonstruje **jak generovat PDF417 čárový kód C#** od začátku až do konce.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Proč je každý řádek důležitý

* **`EncodeTypes.Pdf417`** – vybírá symbologii PDF417, která podporuje až ~1,1 KB dat.
* **`XDimension.Pixels = 2`** – nastavuje základní šířku čáry. Menší hodnoty činí čárový kód tenčím; větší hodnoty zlepšují čitelnost na zařízeních s nízkým rozlišením.
* **`Pdf417.Columns = 3`** – omezuje počet sloupců, což nutí generátor použít více řádků a výsledkem je vyšší, ale užší čárový kód.
* **`Pdf417.Truncate = true`** – aktivuje kompaktní režim, odstraňuje stopovací vzor a zmenšuje obrázek, aniž by došlo ke ztrátě integrity dat.
* **`Save(..., BarCodeImageFormat.Png)`** – zapíše PNG soubor. Můžete také zvolit `Jpeg`, `Bmp` nebo `Svg` podle následných potřeb.

Spusťte program:

```bash
dotnet run
```

Měli byste vidět výstup v konzoli potvrzující umístění souboru a složka bude obsahovat `CompactPdf417.png`. Otevření PNG ukáže jasný, kompaktní PDF417 čárový kód, který kóduje Unicode řetězec.

## Krok 3: Ověřte čárový kód (volitelné, ale doporučené)

Aby byl čárový kód čitelný, můžete použít jakoukoli standardní PDF417 skener aplikaci na chytrém telefonu nebo knihovnu dekodéru na desktopu. Zakódovaný text by měl přesně odpovídat původnímu řetězci `data`, včetně speciálních znaků.

Pokud narazíte na problémy s dekódováním:

* Zvyšte `XDimension` na 3 nebo 4 pixely.
* Snižte počet sloupců (např. nastavte `Columns = 2`).
* Vypněte `Truncate` (`Truncate = false`) a přidejte stopovací vzor.

Tyto úpravy mění poměr velikosti a čitelnosti, což je užitečné pro tiskárny nebo skenery s nízkým rozlišením.

## Krok 4: Prozkoumejte běžné varianty

### 4️⃣ Vytvořte vysoce hustý PDF417 pro tisk

Pokud potřebujete čárový kód, který se vejde na malý štítek, zvyšte počet sloupců a snižte X‑dimenzi:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Změňte výstupní formát na SVG pro vektorové škálování

SVG výstup se škáluje bez ztráty kvality, ideální pro responzivní webové stránky.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Zakódujte binární data (např. pole bajtů)

Pokud potřebujete vložit binární payload, nejprve jej převeďte na Base64 řetězec:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Čárový kód nyní nese binární informace a dekodér musí provést opačný krok Base64.

## Často kladené otázky

| Otázka | Odpověď |
|----------|--------|
| **Mohu generovat PDF417 bez Aspose?** | Ano, existují jiné knihovny jako ZXing.Net nebo Dynamsoft, ale Aspose.BarCode nabízí bohatší kontrolu rozvržení (sloupce, zkrácení) a lepší podporu Unicode. |
| **Jaká je maximální délka dat?** | PDF417 může kódovat až 1 108 bajtů (≈ 1 KB) binárních dat. Pokud tuto hranici překročíte, zvažte rozdělení dat do více čárových kódů. |
| **Je kompaktní režim v souladu se standardy?** | Zkrácený PDF417 je součástí specifikace ISO/IEC 15438 a je široce podporován, ale ověřte, že váš cílový skener jej explicitně podporuje. |
| **Jak změním barvu pozadí?** | Nastavte `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` a `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` před uložením. |

## Závěr

Nyní víte **jak generovat PDF417 čárový kód C#** pomocí Aspose.BarCode, jak jemně doladit X‑dimenzi, povolit kompaktní režim a exportovat výsledek jako PNG obrázek. Kompletní, spustitelný příklad můžete zkopírovat do libovolného .NET projektu a ukázané varianty vám umožní přizpůsobit čárový kód pro tisk, web nebo binární payload scénáře.

Další kroky, které můžete prozkoumat:

* Integrovat generování čárového kódu do ASP.NET Core API, které vrací obrázek na vyžádání.
* Kombinovat PDF417 s QR kódy na stejném štítku pro dvojformátové skenování.
* Použít třídu Aspose.BarCode `Reader` k dekódování vygenerovaného obrázku a programově ověřit data.

Šťastné programování a užijte si flexibilitu, kterou **generování PDF417 čárových kódů** přináší vašim aplikacím!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční kódové příklady s podrobným vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat obrázek čárového kódu s přizpůsobením doplňkového prostoru pomocí Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}