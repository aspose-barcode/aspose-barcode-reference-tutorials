---
date: 2026-08-17
description: Naučte se, jak vytvořit DataMatrix čárový kód s makroznaky pomocí Aspose.BarCode
  pro .NET a objevte, jak použít DataMatrix ve svých aplikacích.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Konfigurace makra DataMatrix
og_description: Naučte se, jak vytvořit DataMatrix čárový kód s makroznaky pomocí
  Aspose.BarCode pro .NET. Tento průvodce poskytuje krok‑za‑krokem kód, možnosti přizpůsobení
  a tipy pro ověření spolehlivého generování čárových kódů.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Vytvořte DataMatrix čárový kód s makroznaky pomocí Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Jak vytvořit DataMatrix čárový kód s makroznaky v .NET
url: /cs/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit DataMatrix čárový kód s makro znaky v .NET

## Úvod

Generování **DataMatrix čárového kódu** s makro znaky vám umožní vložit další referenční informace do malého čtvercového symbolu. V tomto tutoriálu se naučíte, jak **vytvořit DataMatrix čárový kód** s makro znaky pomocí Aspose.BarCode pro .NET, přizpůsobit velikost a úroveň opravy chyb a okamžitě ověřit výsledek. Na konci budete připraveni vložit makro‑povolující čárové kódy do produktových štítků, dokumentů nebo zdravotnických zařízení.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.BarCode for .NET  
- **Mohu vytvořit DataMatrix čárový kód s makro znaky?** Ano – nastavte vlastnost `MacroCharacters`.  
- **Potřebuji licenci pro produkci?** Platná licence Aspose je vyžadována pro produkční použití.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Je k dispozici bezplatná zkušební verze?** Rozhodně – stáhněte ji z oficiálního webu Aspose.

## Požadavky

Než se ponoříte do konfigurace makra, ujistěte se, že máte následující:

1. **Visual Studio** – jakákoli recentní edice bude fungovat.  
2. **Aspose.BarCode pro .NET** – stáhněte jej z [the download link](https://releases.aspose.com/barcode/net/).  
3. **Základní znalost .NET** – znalost C# a ekosystému .NET.

## Importovat jmenné prostory

Začínáme načítáním jmenných prostorů potřebných pro generování a rozpoznávání čárových kódů.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Co je „generování DataMatrix čárového kódu“ s makro znaky?

`MacroCharacters` umožňuje DataMatrix čárovým kódům zahrnout makro symboly, které odkazují na další data. Použitím makro znaků jako Macro05 nebo Macro06 může jeden čárový kód odkazovat na větší datovou sadu nebo sekvenci souvisejících čárových kódů, což je cenné v logistice, výrobě a sledování dokumentů, kde je vyžadováno kompaktní kódování propojených informací.

## Proč použít Aspose.BarCode pro generování DataMatrix čárového kódu?

Aspose.BarCode vám poskytuje přesnou kontrolu nad velikostí DataMatrix, úrovní opravy chyb a nastavením makra, podporuje více než 30 symbologií čárových kódů a zpracovává soubory až do 10 MB, aniž by načítal celý obrázek do paměti. Jeho multiplatformová .NET implementace funguje na .NET Framework, .NET Core a .NET 5/6 a obsahuje vestavěné rozpoznávání, takže můžete čárový kód okamžitě ověřit.

## Průvodce krok za krokem

### Krok 1: nastavení projektu

Vytvořte novou konzolovou aplikaci (nebo jakýkoli .NET projekt) ve Visual Studiu. Přidejte odkaz na DLL soubory Aspose.BarCode, které jste získali při stažení.

### Krok 2: konfigurace DataMatrix makra

Jádro tutoriálu – zde skutečně **vytvoříme DataMatrix čárový kód** s makro znakem.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Tip:** Nahraďte `"ASPOSE"` libovolným řetězcem, který potřebujete zakódovat. Makro znak (`Macro05`) informuje skenery, že tento čárový kód je součástí makro sekvence.

### Krok 3: přizpůsobení parametrů čárového kódu pro opravu chyb

Před uložením můžete upravit další nastavení:

- **XDimension** – řídí velikost každého modulu (pixel).  
- **Margin**, **ErrorCorrection** a **EncodingMode** – jsou všechny přístupné přes `gen.Parameters.Barcode.DataMatrix`.

### Krok 4: uložit čárový kód

Ukázkový kód výše uloží obrázek jako `DataMatrixMacro.png` do složky, kterou jste určili. PNG je bezztrátový formát, což je ideální pro další zpracování.

### Krok 5: rozpoznat čárový kód

`BarCodeReader` je třída Aspose.BarCode pro dekódování čárových kódů z obrázků. Pomocí `BarCodeReader` okamžitě načteme vygenerovaný obrázek a potvrdíme, že makro znak a data jsou správné. Toto ověření zpětného průchodu je zvláště užitečné během automatizovaného testování.

## Jak použít DataMatrix v reálných scénářích?

DataMatrix čárové kódy s makro znaky můžete použít pro označování produktů, propojení sériových čísel s centrální databází, sledování dokumentů vložením odkazu na digitální záznam a pro štítky zdravotnických zařízení, které ukládají data o pacientech nebo přístrojích do malého, skenovatelného symbolu. Tyto případy použití snižují ruční zadávání dat a zlepšují sledovatelnost.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Čárový kód není rozpoznán | Nesprávná `XDimension` nebo nízké rozlišení obrázku | Zvyšte `XDimension.Pixels` na 4‑6 a uložte jako PNG nebo TIFF |
| Makro znak je ignorován | Čtečka nepodporuje makro režim | Použijte skener/čtečku, která explicitně podporuje DataMatrix makro (např. novější verze ZXing) |
| Cesta nenalezena | Neplatná proměnná `path` | Ujistěte se, že adresář existuje, nebo použijte `Path.Combine` s `Environment.CurrentDirectory` |

## Často kladené otázky

**Q: Co je Aspose.BarCode pro .NET?**  
A: Aspose.BarCode pro .NET je výkonná knihovna, která umožňuje .NET vývojářům generovat a rozpoznávat čárové kódy v různých formátech, včetně DataMatrix, QR a dalších.

**Q: Proč bych měl používat DataMatrix čárové kódy?**  
A: DataMatrix čárové kódy jsou kompaktní, vysoce spolehlivé a mohou uložit velké množství dat, což je činí ideálními pro výrobu, logistiku a zdravotnictví.

**Q: Kde mohu najít dokumentaci k Aspose.BarCode pro .NET?**  
A: Dokumentaci najdete na [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.BarCode pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [the free trial link](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.BarCode pro .NET?**  
A: Pokud máte jakékoli otázky nebo potřebujete podporu, můžete navštívit fórum Aspose.BarCode pro .NET na [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-08-17  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit čárový kód aspose .net - Konfigurace textu DataMatrix kódu](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Konfigurace strukturovaného připojení DataMatrix s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}