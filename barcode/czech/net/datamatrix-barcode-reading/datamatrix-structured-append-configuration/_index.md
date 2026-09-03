---
date: 2026-06-14
description: Naučte se, jak číst datamatrix a generovat strukturované append čárové
  kódy v .NET pomocí Aspose.BarCode, rychlé a spolehlivé knihovny čárových kódů.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Konfigurace strukturovaného Append pro DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak číst DataMatrix Append s Aspose.BarCode pro .NET
url: /cs/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurace strukturovaného připojení DataMatrix s Aspose.BarCode pro .NET

Pokud jste vývojář, který hledá **how to read datamatrix** pomocí strukturovaného připojení ve svých .NET aplikacích, Aspose.BarCode pro .NET je vaše řešení. V tomto krok‑za‑krokem průvodci vás provedeme generováním a dekódováním DataMatrix čárových kódů, které jsou rozděleny do více symbolů. Na konci tohoto tutoriálu budete pohodlně vytvářet, konfigurovat a číst DataMatrix strukturované připojení čárové kódy s Aspose.BarCode pro .NET.

## Rychlé odpovědi
- **Která knihovna zpracovává strukturované připojení DataMatrix?** Aspose.BarCode for .NET.
- **Kolik symbolů může obsahovat jedna sekvence strukturovaného připojení?** Up to 16 DataMatrix symbols.
- **Potřebuji licenci pro vývoj?** A free trial works for development and testing.
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mohu číst čárový kód bez souboru obrázku?** Yes, you can decode from a byte array or stream.

## Co je how to read datamatrix?
**how to read datamatrix** odkazuje na proces dekódování DataMatrix symbolů a, pokud je to relevantní, spojování částí sekvence strukturovaného připojení pro získání původního datového payloadu. Aspose.BarCode poskytuje vestavěnou podporu pro tento pracovní tok, automaticky zpracovává pořadí symbolů a spojování dat.

## Proč použít Aspose.BarCode pro strukturované připojení DataMatrix?
Aspose.BarCode podporuje **30+ symbologií čárových kódů** a dokáže dekódovat obrázky až do **10 000 × 10 000 px** za méně než **200 ms** na typickém serverovém hardware. Knihovna také nabízí **nasazení bez závislostí**, což znamená, že nepotřebujete další nativní DLL soubory, a funguje napříč Windows, Linux a macOS .NET runtime.

## Požadavky

Before diving into the tutorial, you'll need:

1. Aspose.BarCode for .NET Library – stáhněte ji z [zde](https://releases.aspose.com/barcode/net/).
2. Můžete také procházet další produkty Aspose [zde](https://releases.aspose.com/).
3. Vývojové prostředí .NET, například Visual Studio 2022 nebo Visual Studio Code s rozšířením C#.

Nyní začněme vytvářet a číst DataMatrix strukturované připojení čárové kódy.

## Importovat jmenné prostory

Prvním krokem je importovat jmenné prostory, které zpřístupňují API čárových kódů.

Třída `BarCodeWriter` je vstupním bodem Aspose.BarCode pro vytváření čárových kódů, zatímco `BarCodeReader` zajišťuje dekódování.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Nyní, když jste importovali požadované jmenné prostory, vytvořme strukturovaný‑append čárový kód.

## Jak číst DataMatrix strukturované připojení čárové kódy?

Načtěte vygenerovaný obrázek (nebo stream) do `BarCodeReader`, povolte možnost `ReadStructuredAppend` a zavolejte `ReadBarcode`. Čtečka automaticky vrátí kombinovaná data a zobrazí podrobnosti sekvence, jako jsou `StructuredAppendFileId`, `StructuredAppendTotalCount` a `StructuredAppendSegmentId`. Kombinovaný výsledek je vrácen jako jediný řetězec a můžete také získat jednotlivé identifikátory segmentů pomocí vlastnosti `StructuredAppendSegmentId` čtečky pro vlastní zpracování.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

V tomto kroku používáme čtečku k získání ID čárového kódu, celkového počtu a ID souboru, čímž potvrzujeme, že konfigurace strukturovaného‑append byla správně interpretována.

## Krok 1: Nastavení konfigurace DataMatrix strukturovaného připojení

Pro vytvoření DataMatrix strukturovaného připojení čárového kódu je třeba nastavit jeho konfiguraci. To zahrnuje definování cesty k adresáři, ID čárového kódu, počtu čárových kódů a ID souboru.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

V tomto kroku jsme nakonfigurovali DataMatrix čárový kód s požadovanými parametry.

## Časté problémy a řešení

- **Nesprávné pořadí segmentů:** Ujistěte se, že hodnoty `StructuredAppendSegmentId` jsou sekvenční počínaje 0; jinak čtečka nemůže data správně znovu sestavit.
- **Nesoulad celkového počtu:** `StructuredAppendTotalCount` musí být stejný pro všechny symboly; nesoulad způsobí, že čtečka bude sekvenci považovat za neúplnou.
- **Kvalita obrazu:** Obrázky s nízkým rozlišením mohou způsobit selhání dekódování. Snažte se při vykreslování čárového kódu do bitmapy dosáhnout alespoň **300 dpi**.

## Často kladené otázky

### Q1: Co je DataMatrix strukturované připojení a proč se používá?

A1: DataMatrix strukturované připojení je funkce, která umožňuje rozdělit velké množství dat do více menších čárových kódů. To je zvláště užitečné, když máte omezený prostor pro jeden čárový kód nebo potřebujete data efektivně organizovat. Často se používá v logistice, zdravotnictví a výrobě.

### Q2: Mohu použít Aspose.BarCode pro .NET ve svém open‑source projektu?

A2: Ano, Aspose.BarCode pro .NET nabízí bezplatnou zkušební verzi, kterou můžete použít v open‑source projektech. Zkušební verzi najdete [zde](https://releases.aspose.com/).

### Q3: Existuje nějaká podpora komunity pro Aspose.BarCode pro .NET?

A3: Ano, můžete vyhledat podporu komunity a komunikovat s ostatními uživateli na fóru Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?

A4: Pokud potřebujete dočasnou licenci pro hodnocení nebo testování, můžete ji získat [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Podporuje Aspose.BarCode pro .NET i jiné typy čárových kódů?

A5: Ano, Aspose.BarCode pro .NET podporuje širokou škálu typů čárových kódů, včetně QR kódů, Code 128, EAN‑13 a mnoha dalších. Kompletní dokumentaci můžete prozkoumat [zde](https://reference.aspose.com/barcode/net/), abyste viděli úplný seznam podporovaných typů čárových kódů.

---

**Poslední aktualizace:** 2026-06-14  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Programování čtečky DataMatrix s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generování DataMatrix čárových kódů s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Mistrovská konfigurace DataMatrix makra s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}