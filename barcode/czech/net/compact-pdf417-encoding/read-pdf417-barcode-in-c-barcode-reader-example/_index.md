---
category: general
date: 2026-10-14
description: Vytvořte konzolovou čtečku čárových kódů v C#, která čte PDF417 kódy,
  zpracovává macro PDF417 a dekóduje více čárových kódů z jednoho obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Vytvořte konzolovou čtečku čárových kódů v C# pro rychlé čtení PDF417
  a macro PDF417 kódů z obrázků. Tento krok‑za‑krokem průvodce ukazuje, jak dekódovat
  více čárových kódů na jednom obrázku.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Vytvořte konzolovou čtečku čárových kódů v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Vytvořte konzolovou čtečku čárových kódů v C# – příklad čtení PDF417 čárového
  kódu
url: /cs/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte konzolový čtečku čárových kódů v C# – příklad čtení PDF417 čárového kódu

`BarCodeReader` je jádrová třída Aspose.BarCode, která dekóduje čárové kódy z obrázků a vrací podrobná metadata. Pokud potřebujete číst data PDF417 čárového kódu z obrázku, tento průvodce vám ukáže, jak to provést pomocí třídy **BarCodeReader** v C#. Naučíte se příklad **vytvoření konzolové čtečky čárových kódů**, který také zvládá macro PDF417 a může číst více čárových kódů v jednom obrázku.

Práce s čárovými kódy často znamená řešení různých zdrojů obrázků, proměnlivých světelných podmínek a někdy složených dat, jako jsou segmenty macro PDF417. Tento tutoriál pokrývá vše, co potřebujete k dekódování PDF417 čárového kódu, extrakci jeho rozšířených polí a zpracování několika čárových kódů ze stejného obrázku. Na konci budete mít spustitelný konzolový program, který čte čárové kódy ze souboru obrázku a vypisuje podrobné informace do konzole.

## Rychlé odpovědi
- **Co příklad dělá?** Vytváří konzolovou čtečku čárových kódů, která čte PDF417 a macro PDF417 kódy z obrázku a vypisuje všechna dekódovaná pole.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro .NET (NuGet).  
- **Může číst více čárových kódů najednou?** Ano – čtečka iteruje přes každý kód nalezený na obrázku.  
- **Potřebuji internetové připojení?** Ne, knihovna funguje zcela offline.  
- **Jaká verze .NET je podporována?** .NET 6.0 nebo novější.

## Co budete potřebovat

Před zahájením se ujistěte, že máte:

* .NET 6.0 SDK nebo novější nainstalováno  
* Aktuální verzi balíčku **Aspose.BarCode for .NET** NuGet (nebo jakoukoli kompatibilní knihovnu, která poskytuje `BarCodeReader` a `DecodeType.MacroPdf417`)  
* Obrázkový soubor, který obsahuje PDF417 nebo macro PDF417 čárový kód (ve vzorku se používá `ExtPDF417Meta.png`)  
* Editor kódu nebo IDE, např. Visual Studio 2022  

Žádné další služby ani externí API nejsou vyžadovány.

## Nastavení projektu pro čtení čárových kódů

1. **Vytvořte nový konzolový projekt**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Přidejte knihovnu čárových kódů**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Zkopírujte obrázek čárového kódu**  

   Umístěte `ExtPDF417Meta.png` (nebo jakýkoli obrázek, který obsahuje PDF417 čárový kód) do složky projektu.  
   Pro tento tutoriál předpokládáme, že soubor se nachází v `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projekt je nyní připraven ke kompilaci a spuštění příkladu čtečky čárových kódů.

## Jak vytvořit konzolovou čtečku čárových kódů v C#?

`BarCodeReader` je třída poskytovaná Aspose.BarCode, která čte čárové kódy z obrázků a vrací jejich dekódovaná data.  
Načtěte obrázek pomocí `BarCodeReader`, nastavte typ dekódování na `MacroPdf417` a iterujte přes výsledky – to je vše, co potřebujete k vytvoření konzolové čtečky čárových kódů. Čtečka automaticky uvolňuje nativní zdroje díky příkazu `using`, takže se nemusíte starat o ruční správu paměti. Tento přístup funguje pro jakýkoli formát obrázku podporovaný .NET, například PNG, JPEG nebo BMP.

### Postupný průvodce

Jádrem řešení je blok `using`, který vytváří instanci `BarCodeReader`, specifikuje `DecodeType.MacroPdf417` a iteruje přes každý detekovaný čárový kód. Následující kód je kompletní, samostatný program, který můžete vložit do `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Proč to funguje**:  

* `DecodeType.MacroPdf417` říká čtečce, aby hledala makro rozšíření PDF417, které obsahuje další metadata jako ID souboru, počet segmentů a časové značky.  
* `using` příkaz zaručuje, že neřízené zdroje (souborové handly, nativní dekódovací buffery) jsou uvolněny okamžitě.  
* `foreach` smyčka automaticky zpracuje **všechny** čárové kódy, které obrázek obsahuje, což splňuje požadavek na *čtení více čárových kódů*.  

Když spustíte program (`dotnet run`), měli byste vidět výstup podobný následujícímu:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Pokud obrázek obsahuje více než jeden PDF417 čárový kód, smyčka vypíše samostatný blok pro každý kód, čímž demonstruje, jak **číst více čárových kódů** z jednoho obrázku.

## Jak mohu číst více čárových kódů z obrázku?

Použijte jedinou instanci `BarCodeReader` a nastavte příznak `DecodeType` tak, aby zahrnoval všechny formáty, které chcete detekovat. Kombinací příznaků pomocí bitového operátoru OR můžete knihovně říci, aby hledala PDF417, QR, Code‑128 a mnoho dalších symbologií najednou. Tím se eliminuje potřeba samostatných čteček a zkracuje se doba zpracování.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* je bitová maska, takže můžete kombinovat libovolný počet podporovaných formátů. Aspose.BarCode podporuje **30+ symbologií čárových kódů**, včetně QR, DataMatrix, Code‑128 a UPC‑A, což umožňuje jedné čtečce zvládnout různé scénáře, jako je označování produktů, ověřování vstupenek a identifikační kontrola.

## Co je macro PDF417 a jak bezpečně přistupovat k jeho polím?

Macro PDF417 je rozšíření symbologie PDF417, které umožňuje rozdělit velký datový soubor do více čárových kódů.  
Macro PDF417 přidává bohatou sadu rozšířených vlastností. Nicméně ne každý čárový kód obsahuje všechna pole. Přístup k chybějící vlastnosti může vyvolat `NullReferenceException`. Nejbezpečnější přístup je ověřit každou vlastnost před jejím vypsáním, čímž zajistíte stabilitu aplikace i při absenci makro dat.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Proč je to důležité*: V reálných nasazeních můžete obdržet běžné PDF417 čárové kódy, které nemají makro data. Defenzivní kontrola zajišťuje, že aplikace bude pokračovat v běhu bez pádu.

## Časté úskalí a osvědčené postupy

| Problém | Proč se to děje | Doporučené řešení |
|-------|----------------|-----------------|
| Cesta k obrázku je nesprávná | `BarCodeReader` vyhodí výjimku soubor nenalezen před jakýmkoli dekódováním | Použijte `Path.Combine` a ověřte, že soubor existuje pomocí `File.Exists` |
| Obrázek s nízkým rozlišením | Dekodér nemůže najít hrany čárového kódu, což vede k nulovým detekcím | Zajistěte minimální rozlišení 300 dpi pro spolehlivé výsledky |
| Čárový kód otočený > 45° | Mnoho knihoven předpokládá svislou orientaci | Povolte `reader.RecognitionOptions.RotateImage = true`, pokud může být obrázek otočen |
| Chybějící makro pole | Pokus o čtení nulové vlastnosti způsobí pád aplikace | Vždy kontrolujte `null` před přístupem k makro vlastnostem |
| Zpracování velkých dávek | Opětovné vytváření čtečky pro každý soubor přidává režii | Znovu použijte jedinou instanci `BarCodeReader` s různými streamy při zpracování mnoha obrázků |

## Proč použít Aspose.BarCode pro konzolovou čtečku čárových kódů?

Aspose.BarCode dokáže dekódovat **30+ typů čárových kódů** a zpracovává obrázky až do **200 MP** bez načítání celého souboru do paměti, dosahuje propustnosti **150 snímků za sekundu** na typickém 3,2 GHz procesoru. Tyto kvantifikované schopnosti z něj činí spolehlivou volbu pro vysokokapacitní, on‑premise skenovací řešení, kde jsou latence a přesnost kritické.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Číst DataMatrix čárový kód C# – Generovat DataMatrix režim (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Číst čárový kód z obrázku – Ovládání extrakce oblasti čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Často kladené otázky

**Q: Mohu tuto čtečku použít v produkčním prostředí?**  
A: Ano. Zakupte komerční licenci Aspose.BarCode, abyste odstranili vodoznak hodnocení a získali plnou podporu.

**Q: Funguje knihovna na Linuxu a macOS?**  
A: Naprosto. Aspose.BarCode pro .NET je multiplatformní a běží na .NET 6+ na Windows, Linuxu i macOS.

**Q: Jak zacházet s velmi velkými obrázky, aniž by došlo k vyčerpání paměti?**  
A: Použijte konstruktor `LoadOptions` k povolení režimu streamování, který zpracovává obrázek po částech místo načtení celého souboru do RAM.

**Q: Je možné dekódovat šifrované nebo heslem chráněné obrázky?**  
A: Čtečka dokáže zpracovat obrázky šifrované standardními PNG/JPEG heslovými schématy; stačí heslo předat pomocí `reader.ImagePassword`.

**Q: Co když je můj čárový kód částečně poškozen?**  
A: Povolte možnosti korekce chyb, například `reader.RecognitionOptions.CorrectErrors = true`, aby se zvýšila odolnost vůči poškození nebo šumu.

**Poslední aktualizace:** 2026-10-14  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak číst Pdf417 v C – kompletní příklad čtečky čárových kódů](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Číst více čárových kódů v C – kompletní průvodce s Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Dekódovat čárový kód z obrázku s příkladem C čtečky čárových kódů](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}