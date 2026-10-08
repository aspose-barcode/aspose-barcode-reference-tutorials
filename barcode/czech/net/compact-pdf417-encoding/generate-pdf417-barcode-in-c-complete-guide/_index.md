---
category: general
date: 2026-09-18
description: Zjistěte, jak rychle vytvořit PDF417 barcode image v C# a nastavit sloupce
  pro kompaktní barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Zjistěte, jak rychle vytvořit PDF417 barcode image v C# a nastavit
  sloupce pro kompaktní barcode. Aspose.BarCode to usnadňuje.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Vytvořte PDF417 barcode image – krok za krokem C# průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Jak vytvořit PDF417 barcode image v C# – kompletní průvodce
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu PDF417 v C# – kompletní průvodce

Pokud potřebujete **vytvořit obrázek čárového kódu PDF417** v .NET aplikaci, jste na správném místě. Ať už tisknete štítky palubních průkazů, kódujete údaje o zásobách nebo budujete mobilní ticketovací systém, PDF417 poskytuje vysoce kapacitní dvourozměrné čárové kódy. Tento průvodce vám ukáže, jak vygenerovat obrázek pomocí Aspose.BarCode a jak nastavit sloupce, aby čárový kód zůstal co nejkompaktnější.

## Rychlé odpovědi
- **Která knihovna vytváří PDF417 čárové kódy?** Aspose.BarCode pro .NET.
- **Kolik řádků kódu je potřeba?** Přibližně 10 řádků v konzolové aplikaci.
- **Mohu ovládat šířku čárového kódu?** Ano, nastavením vlastnosti `Columns`.
- **Jaký formát obrázku se doporučuje?** PNG pro bezztrátovou kvalitu.
- **Je .NET 6 podporováno?** Plně – knihovna funguje s .NET 6, .NET 7 a novějšími.

## Co je obrázek čárového kódu PDF417?
Obrázek čárového kódu PDF417 je dvourozměrná matice, která ukládá až 1 700 znaků na řádek, přičemž používá řádky a sloupce k hustému zabalení dat. Aspose.BarCode vykresluje tuto matici do standardních formátů obrázků, jako jsou PNG, JPEG nebo BMP. Lze jej uložit v různých formátech a je vhodný pro tisk na štítky, vstupenky nebo mobilní obrazovky.

## Proč nastavit sloupce pro kompaktní obrázek čárového kódu PDF417?
Nastavení sloupců vám umožní zmenšit šířku čárového kódu, což je nezbytné pro úzké štítky nebo UI prvky s omezeným prostorem. Aspose.BarCode podporuje 1‑30 sloupců a výběrem menšího počtu snižuje celkovou šířku obrázku až o 40 % při zachování integrity dat. Toto nastavení pomáhá umístit čárové kódy na malé štítky, aniž by se snížila čitelnost.

## Jak vytvořit obrázek čárového kódu PDF417 v C#?
Načtěte knihovnu `Aspose.BarCode`, nakonfigurujte `BarcodeGenerator` s `EncodeTypes.Pdf417`, nastavte `Columns` a `Truncate` a poté výsledek uložte jako PNG. Celý proces zahrnuje dva volání metod a vytvoří připravený soubor obrázku. Můžete také přizpůsobit rozměry, barvy a přidat čitelný text, aby vyhovoval potřebám vaší aplikace.

### Požadavky
- .NET 6+ SDK (nebo novější)
- Visual Studio 2022 nebo jakýkoli editor C#
- NuGet balíček `Aspose.BarCode`

### Implementace krok za krokem

## Krok 1: Nainstalujte NuGet balíček Aspose.BarCode
`Aspose.BarCode` je .NET knihovna pro generování a čtení různých symbologií čárových kódů.

```bash
dotnet add package Aspose.BarCode
```

Tento jediný řádek načte všechny typy, které budete potřebovat, včetně `BarcodeGenerator`, `EncodeTypes` a výčtu `BarCodeImageFormat`.

> **Tip:** Pokud cílíte na .NET Framework místo .NET 6, použijte klasický PowerShell příkaz `Install-Package Aspose.BarCode` v konzoli Package Manager.

## Krok 2: Vytvořte minimální konzolovou aplikaci
`BarcodeGenerator` vytváří obrázky čárových kódů na základě zadaných nastavení. `EncodeTypes` vyjmenovává podporované symbologie čárových kódů. `BarCodeImageFormat` vyjmenovává formáty obrázků.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Proč je to důležité:**  
- `EncodeTypes.Pdf417` říká knihovně, že chceme PDF417 čárový kód, ne QR nebo Code128.  
- `XDimension.Pixels` řídí rozlišení každého malého černého nebo bílého modulu.  
- Blok **jak nastavit sloupce** přímo ovlivňuje tvar **obrázku čárového kódu PDF417**.  
- `Truncate = true` odstraňuje všechny zbytečné prázdné řádky, což vám dává ten „kompaktní“ vzhled, který mnoho skenerů miluje.

## Krok 3: Ponořte se hlouběji – pochopení sloupců a zkrácení
### Jak nastavit sloupce
PDF417 uspořádává data v matici *řádků* × *sloupců*. Knihovna ve výchozím nastavení používá 5 sloupců, což funguje ve většině případů. Nicméně můžete potřebovat užší čárový kód, aby se vešel na štítek, nebo širší pro zlepšení spolehlivosti skenování. Vlastnost:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

přijímá hodnoty od **1** do **30** (přesný limit závisí na délce dat). Zde je rychlý přehled:

| Sloupce | Přibližná šířka (mm) | Kdy použít |
|---------|----------------------|------------|
| 1‑3     | Velmi úzký           | Malý štítek, omezený prostor |
| 4‑6     | Standardní           | Většina účtenek, vstupenek |
| 7‑10    | Širší                | Vysoce hustá data, lepší čitelnost |

### Truncate (kompaktní režim)
Nastavení `Truncate = true` říká enkodéru, aby ořízl všechny zbytečné prázdné řádky na konci. Výsledkem je **kompaktní obrázek čárového kódu PDF417**, který zabírá co nejmenší možnou plochu a přitom obsahuje všechna data. Pokud se vám objeví chyba „čárový kód je příliš velký pro štítek“, přepněte tento příznak.

## Krok 4: Spusťte aplikaci a ověřte výstup
Zkompilujte a spusťte:

```bash
dotnet run
```

V konzoli byste měli vidět zprávu potvrzující umístění uložení. Přejděte do složky a otevřete `CompactPdf417.png`. Obrázek bude vypadat zhruba takto:

![Vygenerovaný obrázek čárového kódu PDF417](./CompactPdf417.png "Vygenerovaný obrázek čárového kódu PDF417 – kompaktní PNG vytvořené pomocí Aspose.BarCode")

[Vygenerovaný obrázek čárového kódu PDF417](./CompactPdf417.png "Vygenerovaný obrázek čárového kódu PDF417 – kompaktní PNG vytvořené pomocí Aspose.BarCode")

*Text alternativy obrázku:* **Vygenerovaný obrázek čárového kódu PDF417** – kompaktní PNG soubor vytvořený kódem v tutoriálu.

Pokud váš skener dokáže obrázek přečíst, gratulujeme—úspěšně jste **vytvořili PDF417 čárový kód** a zvládli **jak nastavit sloupce** pro úhledný **obrázek čárového kódu PDF417**.

## Krok 5: Časté problémy a jak je opravit
| Příznak | Pravděpodobná příčina | Rychlá oprava |
|---------|-----------------------|----------------|
| Čárový kód je rozmazaný | `XDimension.Pixels` je příliš nízké (např. 1) | Zvyšte na 2‑3 pixely pro ostřejší obrázek. |
| Skener nedokáže číst | Příliš mnoho sloupců pro daná data | Snižte `Columns` nebo povolte `Truncate`. |
| Špatný formát souboru | Omylem uloženo jako `BarCodeImageFormat.Jpeg` | Použijte `BarCodeImageFormat.Png` pro bezztrátové výsledky. |
| Výjimka `ArgumentOutOfRangeException` | Počet sloupců překračuje povolený rozsah | Udržujte sloupce mezi 1‑30 a zajistěte, aby data pasovala. |

## Krok 6: Pokročilejší – přizpůsobení barev a přidání textu
Pokud chcete, aby čárový kód odpovídal paletě značky, můžete upravit barvy popředí a pozadí:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Nebo přidat pod čárový kód čitelný text:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Tyto doplňky jsou volitelné, ale ukazují, jak flexibilní může být workflow **vytvoření PDF417 čárového kódu**.

## Závěr
Prošli jsme kompletním příkladem od začátku do konce, který **vytváří PDF417 čárový kód** pomocí Aspose.BarCode, vysvětlili **jak nastavit sloupce** pro řízení rozměrů čárového kódu a uložili výsledek jako ostrý **obrázek čárového kódu PDF417** ve formátu PNG. Kód je samostatný, funguje s .NET 6+ a lze jej vložit do jakéhokoli existujícího projektu s minimální námahou.

Co dál? Zkuste kódovat větší náklady (např. JSON řetězce), experimentujte s různými formáty obrázků nebo integrujte generátor do webového API, které poskytuje čárové kódy na vyžádání. Možnosti jsou neomezené a nyní máte pevný základ, na kterém můžete stavět.

Šťastné programování a ať vaše čárové kódy vždy načtou na první pokus!

## Co byste se měli naučit dál?
Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat obrázek čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generovat čárový kód v Javě – Nastavit rozlišení obrázku s Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Často kladené otázky

**Q: Mohu použít vygenerovaný PNG na webové stránce bez další konverze?**  
A: Ano, PNG je nativně podporováno všemi moderními prohlížeči, takže můžete soubor vložit přímo pomocí značky `<img>`.

**Q: Kolik znaků může čárový kód PDF417 pojmout?**  
A: Až 1 700 znaků na řádek a až 30 řádků, což dává teoretické maximum přibližně 51 000 znaků, ačkoliv praktické limity závisí na schopnostech skeneru.

**Q: Vyžaduje Aspose.BarCode licenci pro vývoj?**  
A: Pro testování je k dispozici bezplatná zkušební licence; pro produkční nasazení je vyžadována komerční licence.

**Q: Je možné generovat PDF417 čárové kódy ve službě na pozadí?**  
A: Rozhodně. Knihovna je bezpečná pro více vláken při operacích jen pro čtení, takže můžete generovat čárové kódy v ASP.NET Core nebo Windows službách bez UI interakce.

**Q: Jaké formáty obrázků kromě PNG jsou podporovány?**  
A: BMP, JPEG, GIF, TIFF a SVG jsou všechny podporovány prostřednictvím výčtu `BarCodeImageFormat`.

---

**Poslední aktualizace:** 2026-09-18  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  






```bash
dotnet add package Aspose.BarCode
```

## Související tutoriály

- [Vytvořit PDF417 čárový kód s kompletním průvodcem Aspose](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generovat PDF417 obrázek čárového kódu v C s Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Vytvořit PDF417 čárový kód v C – krok za krokem](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}