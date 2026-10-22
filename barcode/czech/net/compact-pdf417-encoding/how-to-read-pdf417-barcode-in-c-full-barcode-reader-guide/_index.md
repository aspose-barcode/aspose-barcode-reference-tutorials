---
category: general
date: 2026-10-21
description: Jak načíst čárový kód PDF417 v C# pomocí čtečky čárových kódů z obrázku.
  Postupujte podle tohoto krok‑za‑krokem příkladu čtečky čárových kódů v C# pro spolehlivé
  dekódování.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: cs
lastmod: 2026-10-21
og_description: Jak číst čárový kód PDF417 v C# s kompletním příkladem čtečky čárových
  kódů. Naučte se dekódovat obrázky Macro PDF417 a získat přístup ke všem rozšířeným
  polím.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Jak číst čárový kód PDF417 v C# – podrobný průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak číst čárový kód PDF417 v C# – kompletní průvodce čtečkou čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód PDF417 v C# – kompletní průvodce čtečkou čárových kódů

Pokud potřebujete **jak číst PDF417 čárový kód** v .NET aplikaci, tento průvodce vám ukáže připravené řešení. Uvidíte, jak **číst čárový kód z obrázku C#** pomocí populární knihovny a získat všechny atributy Macro PDF417 bez dalšího nástroje.

Tutoriál pokrývá vše, co je potřeba pro **C# příklad čtečky čárových kódů**: nastavení projektu, procházení kódu a tipy pro řešení okrajových případů. Na konci můžete vložit kód do konzolového projektu a okamžitě začít dekódovat PDF417 obrázky.

## Co budete potřebovat

Než začnete, ověřte následující předpoklady:

| Požadavek | Důvod |
|-----------|-------|
| .NET 6.0 SDK nebo novější | Poskytuje runtime pro C# konzolovou aplikaci |
| Visual Studio 2022 (nebo jakékoli C# IDE) | Umožňuje snadné vytvoření projektu a ladění |
| Aspose.BarCode pro .NET (balíček NuGet) | Poskytuje třídy `BarCodeReader` a `DecodeType` |
| Obrázek Macro PDF417 (např. `MacroPdf417.png`) | Slouží jako vstup pro dekódování |

Knihovnu můžete nainstalovat pomocí dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Jak číst PDF417 čárový kód z obrázku v C#

Jádro workflow **číst čárový kód z obrázku C#** se skládá ze tří akcí:

1. Inicializovat `BarCodeReader` pro konkrétní `DecodeType`.
2. Projít vrácenou kolekci `BarCodeResult`.
3. Přistupovat k základním i rozšířeným PDF417 polím.

Níže je kompletní, spustitelný kód. Uložte jej jako `Program.cs` uvnitř konzolového projektu.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Vysvětlení jednotlivých kroků

* **Krok 1 – Inicializace čtečky**  
  Konstruktor `BarCodeReader` přijímá cestu k souboru obrázku a `DecodeType`. `DecodeType.MacroPdf417` říká knihovně, aby hledala symboly Macro PDF417, které obsahují další metadata nad rámec běžných PDF417 čárových kódů.

* **Krok 2 – ReadBarCodes()**  
  Tato metoda vrací `IEnumerable<BarCodeResult>`, která může obsahovat více čárových kódů, pokud obrázek obsahuje více než jeden. Smyčka `foreach` zajišťuje, že každý detekovaný symbol je zpracován.

* **Krok 3 – Základní informace**  
  `CodeTypeName` určuje formát čárového kódu (např. “MacroPDF417”). `CodeText` obsahuje surový řetězec dat zakódovaný v symbolu.

* **Krok 4 – Rozšířená pole**  
  Macro PDF417 přidává sadu rozšířených vlastností pod `barcodeResult.Extended.Pdf417`. Tato pole vystavují data na úrovni souboru, jako jsou `FileID`, `SegmentID` a `FileName`. Přímý přístup vám umožní znovu sestavit více‑segmentové dokumenty nebo ověřit integritu.

#### Očekávaný výstup v konzoli

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Přesné hodnoty odrážejí obsah zakódovaný ve vašem `MacroPdf417.png`. Pokud obrázek obsahuje jediný segment, `SegmentsCount` bude 1 a `SegmentID` bude 0.

## Nastavení prostředí C# čtečky čárových kódů

Spolehlivý **C# příklad čtečky čárových kódů** závisí na čisté konfiguraci projektu:

1. **Vytvořte nový konzolový projekt**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Přidejte balíček Aspose.BarCode** (jak bylo ukázáno výše).  
3. **Zkopírujte soubor obrázku** do složky projektu nebo na něj odkažte absolutní cestou.  
4. **Sestavte a spusťte**  
   ```bash
   dotnet run
   ```

Pokud sestavení selže s chybou chybějící reference, ověřte, že `using Aspose.BarCode;` odpovídá nainstalované verzi balíčku. API knihovny je stabilní napříč .NET 6 a .NET 8, takže můžete runtime aktualizovat bez změn kódu.

## Dekódování Macro PDF417 čárového kódu

Když zavoláte `ReadBarCodes()`, knihovna interně provádí následující kroky:

* **Předzpracování obrázku** – převádí bitmapu na binární matici, opravuje rotaci a šum.  
* **Detekce vzoru** – skenuje start/stop vzory PDF417 a získává šířku modulu.  
* **Korekce chyb** – aplikuje Reed‑Solomon kódy pro obnovu poškozených kódových slov.  
* **Extrahování makra** – parsuje rozšířený hlavičkový segment PDF417 a naplní objekt `Extended.Pdf417`.

Porozumění tomuto pipeline vám pomůže rozhodnout, kdy upravit možnosti dekodéru. Například pokud jsou vaše obrázky nízkého kontrastu, můžete povolit vlastnost `BarCodeReader` `ReadQuality` (dostupnou v novějších verzích) pro zlepšení míry detekce.

## Interpretace rozšířených PDF417 polí

Rozšířená pole mapují přímo na specifikaci Macro PDF417:

| Pole | Význam |
|------|--------|
| `MacroPdf417FileID` | Jedinečný identifikátor celého souboru napříč všemi segmenty |
| `MacroPdf417SegmentID` | Index aktuálního segmentu od nuly |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů, které tvoří soubor |
| `MacroPdf417FileName` | Původní název souboru uložený během kódování |
| `MacroPdf417Checksum` | 16‑bitový kontrolní součet pro ověření integrity |
| `MacroPdf417FileSize` | Velikost původního souboru v bajtech |
| `MacroPdf417TimeStamp` | UTC časové razítko, kdy byl čárový kód vygenerován |
| `MacroPdf417Addressee` | Určený příjemce dokumentu |
| `MacroPdf417Sender` | Odesílatel dokumentu |
| `MacroPdf417Terminator` | Literální řetězec “END” označující poslední segment |

Tyto hodnoty můžete použít k rekonstrukci více‑segmentového PDF, ověření, že žádný segment nechybí, nebo k zaznamenání auditních informací pro účely shody.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Žádný výstup se neobjeví | Nesprávná cesta k obrázku nebo nepodporovaný formát | Použijte absolutní cestu a ujistěte se, že soubor je PNG/JPEG podporovaný Aspose.BarCode |
| `CodeType` ukazuje “PDF417” místo “MacroPDF417” | Obrázek obsahuje běžný PDF417 symbol, ne makro variantu | Ověřte, že zdrojový čárový kód je kódován s rozšířeními Macro PDF417 |
| Některá pole jsou prázdná | Čárový kód byl vygenerován bez těchto makro polí | Kódujte čárový kód s kompletním makro nákladem, nebo v kódu ošetřete null hodnoty |
| Dekodér vyhazuje `ArgumentException` | Špatně zadaný `DecodeType` | Změňte `DecodeType.MacroPdf417` na `DecodeType.Pdf417`, pokud potřebujete jen standardní PDF417 data |

**Tip:** Zabalte přístup k polím do kontrol null, pokud očekáváte ne‑makro čárové kódy. Objekt `Extended.Pdf417` vrací výchozí hodnoty (např. `0` pro číselná pole), když data chybí.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Shrnutí kompletního funkčního příkladu

Když spojíte vše dohromady, finální program se skládá z using direktiv, metody `Main` a čtyřkrokové smyčky ukázané dříve. Žádné další konfigurační soubory nejsou potřeba. Zkompilujte a spusťte projekt a uvidíte výstup v konzoli se všemi vlastnostmi Macro PDF417.

## Závěr

Nyní už víte **jak číst PDF417 čárový kód** v C# pomocí stručného **C# příkladu čtečky čárových kódů**. Průvodce vás provedl nastavením prostředí, implementací kódu a interpretací každého rozšířeného pole Macro PDF417. S tímto základem můžete integrovat skenování čárových kódů do inventárních systémů, workflow správy dokumentů nebo mobilních backendů.

### Další

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to read PDF417 in C# – complete barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}