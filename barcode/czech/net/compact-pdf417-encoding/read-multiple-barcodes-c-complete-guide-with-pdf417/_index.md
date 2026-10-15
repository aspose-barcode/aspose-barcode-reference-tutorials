---
category: general
date: 2026-10-04
description: Naučte se, jak dekódovat PDF417 a číst více čárových kódů v C# pomocí
  Aspose.BarCode. Tento průvodce vám ukáže, jak detekovat compact mode a zpracovat
  mnoho čárových kódů na jednom obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Naučte se, jak dekódovat PDF417 a číst více čárových kódů v C#. Tento
  průvodce krok za krokem pokrývá detekci compact mode, multi‑barcode zpracování a
  best practices.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Jak dekódovat PDF417 a číst více čárových kódů v C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Jak dekódovat PDF417 a číst více čárových kódů v C#
url: /cs/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekódovat PDF417 a číst více čárových kódů v C#

Už jste se někdy zamýšleli, jak **číst více čárových kódů C#** z jediného obrázku? Možná máte hromadu přepravních štítků, koláž vstupenek nebo dokument PDF417, který v jednom obrázku obsahuje několik kódů. V mé každodenní práci jsem narazil právě na tuto překážku — dokud jsem neobjevil `BarCodeReader` od Aspose.BarCode. Tento tutoriál vás provede dekódováním každého čárového kódu na obrázku, určením, zda je PDF417 v kompaktním (zkráceném) režimu, a čistým zpracováním výsledků.

## Rychlé odpovědi
- **Může Aspose.BarCode načíst více než jeden čárový kód najednou?** Ano, `ReadBarCodes()` vrací všechny detekované symboly v jednom volání.  
- **Co je kompaktní režim pro PDF417?** Jedná se o kódování zmenšené velikosti, které vynechává volitelné řádky výplně pro úsporu místa.  
- **Potřebuji licenci pro produkci?** Zkušební verze funguje ihned, ale placená licence odstraňuje vodoznaky a odemyká plný výkon.  
- **Které verze .NET jsou podporovány?** .NET 6+, .NET 5, .NET Core 3.1 a .NET Framework 4.6+.  
- **Je knihovna vlákny bezpečná?** Ne, vytvořte samostatnou instanci `BarCodeReader` pro každé vlákno.

## Co je dekódování PDF417?
Fráze „how to decode PDF417“ odkazuje na extrakci dat zakódovaných v čárovém kódu PDF417 pomocí softwaru. Aspose.BarCode poskytuje připravené API, které automaticky řeší opravu chyb, detekci symbolů a interpretaci kompaktního režimu, což vývojářům umožňuje získat původní text bez nutnosti zabývat se nízkoúrovňovým zpracováním obrazu.

## Proč použít Aspose.BarCode pro tento úkol?
Aspose.BarCode podporuje **50+ symbologií čárových kódů**, zpracovává **obrázky s více stovkami stránek** bez načítání celého souboru do paměti a dokáže dekódovat PDF417 jak v plné velikosti, tak v kompaktním režimu s **100 % přesností** na standardních testovacích sadách (ověřeno v benchmarku 2026). Kromě toho nabízí rozsáhlou dokumentaci a pravidelné aktualizace, což zajišťuje kompatibilitu s nejnovějšími verzemi .NET.

## Co budete potřebovat
Pro sledování tohoto tutoriálu potřebujete pouze aktuální .NET SDK, NuGet balíček Aspose.BarCode a obrázek obsahující PDF417 symboly. Kód funguje na Windows, Linuxu i macOS a nevyžaduje žádné další nativní knihovny, takže nastavení je jednoduché pro každého .NET vývojáře.

- **.NET 6.0** SDK nebo novější (kód funguje také s .NET Framework 4.6+, ale .NET 6 je optimální).  
- **Aspose.BarCode pro .NET** NuGet balíček (`Install-Package Aspose.BarCode`).  
- Ukázkový obrázek, který obsahuje **PDF417** čárové kódy — nejlépe takový, který kombinuje kompaktní a plno‑velikostní symboly. Tutoriál používá `CompactPdf417.png`, ale jakýkoli PNG/JPEG bude fungovat.  
- Vaše oblíbené IDE (Visual Studio, Rider nebo VS Code).  

To je vše — žádné extra DLL, žádné nativní závislosti. Aspose.BarCode je čistě spravovaný kód, takže jej můžete vložit do libovolného .NET projektu.

![Read multiple barcodes C# – snímek konzole zobrazující stav kompaktního režimu pro PDF417 čárové kódy](image.png "Read multiple barcodes C# – snímek konzole zobrazující stav kompaktního režimu pro PDF417 čárové kódy")
[Read multiple barcodes C# – snímek konzole zobrazující stav kompaktního režimu pro PDF417 čárové kódy](image.png "Read multiple barcodes C# – snímek konzole zobrazující stav kompaktního režimu pro PDF417 čárové kódy")

## Jak číst více čárových kódů v C#?
Načtěte obrázek pomocí `BarCodeReader`, zavolejte `ReadBarCodes()` a iterujte přes vrácenou kolekci. Metoda automaticky objeví každý čárový kód, bez ohledu na jeho polohu nebo orientaci, a vrátí pole `BarCodeResult[]`, které můžete zpracovat v jednoduchém `foreach` cyklu. Tento přístup eliminuje potřebu několika skenů nebo ručního výběru oblastí.

## Definice BarCodeReader
Třída `BarCodeReader` je jádrovou komponentou Aspose.BarCode, která skenuje obrázek a extrahuje data čárových kódů pro všechny podporované symbologie.

## Definice ReadBarCodes()
`ReadBarCodes()` je metoda třídy `BarCodeReader`, která vrací pole objektů `BarCodeResult`, z nichž každý představuje detekovaný čárový kód ve vstupním obrázku.

## Krok 1 – instalace a odkaz na knihovnu BarCodeReader C# 
Nejprve potřebujete třídu **BarCodeReader C#**, která pohání dekódování. Otevřete terminál (nebo Package Manager Console) a spusťte:

```powershell
dotnet add package Aspose.BarCode
```

Nebo, pokud jste ve správci NuGet ve Visual Studio, stačí vyhledat *Aspose.BarCode* a kliknout **Install**. Tím se stáhne nejnovější stabilní verze (k červenci 2026 je to 23.9), která podporuje PDF417, QR, DataMatrix a desítky dalších symbologií.

Proč je to důležité: knihovna abstrahuje těžkou práci s obrazovým zpracováním, korekcí chyb a rozpoznáváním symbolů. Můžete si napsat vlastní skener, ale strávíte týdny řešením okrajových případů. Aspose vám poskytuje osvědčenou **C# barcode library**, která je aktualizována pro moderní .NET runtime.

## Krok 2 – nastavení minimálního konzolového projektu
Vytvořte nový konzolový projekt, abychom se mohli soustředit na logiku čárových kódů bez jakéhokoli UI šumu:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Nahraďte vygenerovaný `Program.cs` úplným příkladem níže. Klidně ponechte výchozí jmenný prostor nebo jej přejmenujte — není potřeba nic speciálního.

## Krok 3 – napsat kompletní implementaci „read multiple barcodes C#“
Níže je **kompletní, spustitelný** ukázkový kód. Pokrývá všechny čtyři kroky z původního úryvku, přidává ošetření chyb a vypisuje užitečnou diagnostiku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Proč tento kód funguje
`BarCodeReader` je hlavní komponenta z **BarCodeReader C#** API. Otevře obrázek, provede předzpracování a hledá symboly zadaného typu. `ReadBarCodes()` vrací pole, ne jen jeden výsledek. To je klíč k **čtení více čárových kódů C#** — metoda automaticky sbírá všechny nalezené shody. Příznak `result.Extended.Pdf417.IsTruncated` nám říká, zda je PDF417 v *kompaktním* (také nazývaném zkráceném) režimu. Tento příznak existuje jen pro PDF417, takže používáme operátor podmíněného přístupu (`?.`), abychom se vyhnuli výjimkám, pokud se objeví jiná symbologie. Smyčka `foreach` vypisuje jak dekódovaný text, tak stav kompaktnosti, což poskytuje rychlou kontrolu.

## Krok 4 – zpracování různých typů čárových kódů (volitelné)
Pokud váš obrázek může obsahovat i jiné typy než PDF417, jednoduše změňte druhý argument `BarCodeReader` na `DecodeType.AllSupported`. Smyčka zůstane stejná, ale budete muset ošetřit možnost, že `result.Extended` bude pro ne‑PDF417 symboly null:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Krok 5 – okrajové případy a tipy pro nejlepší praxi
### 1️⃣ Nebyly detekovány žádné čárové kódy  
Pokud `ReadBarCodes()` vrátí prázdné pole, nejčastější příčiny jsou:

- Špatná cesta k souboru nebo chybějící oprávnění ke čtení.  
- Kvalita obrazu je příliš nízká (rozmazání, nízký kontrast). Zvažte předzpracování pomocí `reader.ImagePreprocessingOptions` (např. `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Extrémně velké obrázky  
Zpracování 10 MP fotografie může být náročné na paměť. Můžete omezit oblast skenování:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Vlákna‑bezpečnost  
`BarCodeReader` implementuje `IDisposable` a **není** vlákny‑bezpečný. Vytvořte samostatné instance pro každé vlákno, pokud potřebujete paralelní zpracování.

### 4️⃣ Licencování  
Aspose.BarCode funguje v režimu zkušební verze ihned, ale na výstupním obrázku uvidíte vodoznak. Pro produkci nastavte licenci co nejdříve:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logování  
Když tento kód integrujete do větší služby, nahraďte `Console.WriteLine` strukturovaným loggerem (Serilog, NLog). Tím můžete zachytit `CodeText`, `CodeType` a `IsTruncated` jako pole pro následnou analytiku.

## Často kladené otázky
**Q: Mohu dekódovat PDF417, který používá kompaktní režim?**  
A: Ano. Vlastnost `IsTruncated` v rozšířeném výsledku PDF417 okamžitě říká, zda je čárový kód kompaktní.

**Q: Co když obrázek obsahuje jak QR, tak PDF417 kódy?**  
A: Použijte `DecodeType.AllSupported` při vytváření `BarCodeReader`. Čtečka vrátí výsledky pro každou detekovanou symbologii ve stejném poli.

**Q: Musím čtečku ručně uvolnit?**  
A: Rozhodně. Zabalte `BarCodeReader` do bloku `using` nebo zavolejte `Dispose()`, aby se rychle uvolnily nativní zdroje.

**Q: Jak velký soubor může Aspose.BarCode zpracovat?**  
A: Knihovna dokáže zpracovat obrázky až do **200 MP** (přibližně 20 000 × 20 000 pixelů) bez načítání celého bitmapu do paměti, díky svému dlaždicovému skenovacímu enginu.

**Q: Je pro každé nasazení vyžadována samostatná licence?**  
A: Jediný licenční soubor může být použit na více serverech, pokud celkový počet současně běžících instancí nepřesáhne zakoupený počet licencí.

## Související články
- [Jak generovat PDF417 čárové kódy – kompaktní kódování PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak vytvořit čárový kód – kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Poslední aktualizace:** 2026-10-04  
**Testováno s:** Aspose.BarCode 23.9 for .NET  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}