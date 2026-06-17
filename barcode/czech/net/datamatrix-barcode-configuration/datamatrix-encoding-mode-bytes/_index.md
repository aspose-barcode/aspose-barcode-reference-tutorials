---
date: 2026-05-30
description: Naučte se, jak generovat DataMatrix čárový kód v režimu Bytes a číst
  DataMatrix čárový kód pomocí Aspose.BarCode pro .NET – krok za krokem průvodce čárovými
  kódy.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Režim kódování DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generovat DataMatrix čárový kód v režimu Bytes pomocí Aspose.BarCode pro .NET
url: /cs/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generovat DataMatrix čárový kód v režimu Bytes s Aspose.BarCode pro .NET

V tomto tutoriálu se naučíte, jak **vytvořit DataMatrix čárový kód** pomocí režimu kódování Bytes a poté **načíst DataMatrix čárový kód** zpět pomocí Aspose.BarCode pro .NET. Ať už budujete systém pro správu skladu nebo mobilní aplikaci pro prodej vstupenek, níže uvedený krok‑za‑krokem průvodce čárovými kódy vám přesně ukáže, jak nastavit parametry generátoru čárových kódů, vytvořit vysoce kvalitní obrázek a znovu jej dekódovat — vše během několika řádků C#.

## Rychlé odpovědi
- **Mohu v .NET vygenerovat DataMatrix čárový kód?** Ano, použijte `BarcodeGenerator` s `EncodeTypes.DataMatrix` a nastavte `DataMatrixEncodeMode.Bytes`.
- **Která metoda čte čárový kód?** `BarCodeReader` načte obrázek a vrátí zakódovaný text.
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kolik bajtů mohu zakódovat?** Až 1 555 bajtů v jednom symbolu DataMatrix.

## Co je generování DataMatrix čárového kódu?
**Generování DataMatrix čárového kódu** znamená vytvoření dvourozměrného, čtvercového čárového kódu, který může ukládat binární data. Aspose.BarCode vykresluje symbol jako obrázek PNG, JPG nebo SVG, který může dekódovat jakýkoli skener. Je široce používán pro sledování zásob, správu dokumentů a autentizaci, protože poskytuje vysokou hustotu dat a schopnosti korekce chyb, což jej činí spolehlivým i na nízkokvalitních výtiscích.

## Proč použít režim kódování Bytes?
Režim Bytes vám umožňuje vložit surová binární data (až 1 555 bajtů) bez jejich převodu na text, což je ideální pro sériová čísla, GUIDy nebo šifrované náklady. Aspose.BarCode podporuje **více než 30 čárových kódů** a může zpracovávat **vícesetstránkové dokumenty** bez načítání celého souboru do paměti, což zajišťuje vysoký výkon i v scénářích s vysokou propustností.

## Předpoklady

Než se ponoříme do procesu kódování, musíte mít připraveny následující předpoklady:

1. Aspose.BarCode pro .NET: Pro zahájení musíte mít nainstalovanou knihovnu Aspose.BarCode pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/barcode/net/). Další produkty Aspose najdete také [zde](https://releases.aspose.com/).
2. Vaše vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí, včetně Visual Studio nebo jiného IDE dle vašeho výběru.
3. Základní znalost C#: Tento tutoriál předpokládá, že máte základní povědomí o programování v C#.

Pro pomoc navštivte [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

S těmito předpoklady jste připraveni začít kódovat data ve formátu DataMatrix pomocí režimu Bytes.

## Importujte jmenné prostory

Pro použití Aspose.BarCode pro .NET importujte požadované jmenné prostory na začátku vašeho souboru C#:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Nyní, když je prostředí připravené, projděte si přesně kroky k **vytvoření DataMatrix čárového kódu** a následnému jeho načtení.

## Jak vygenerovat DataMatrix čárový kód v režimu Bytes?

Načtěte `BarcodeGenerator`, nastavte režim kódování na Bytes, nakonfigurujte volitelný zobrazovaný text, uložte obrázek a nakonec použijte `BarCodeReader` k ověření výsledku — vše v šesti stručných krocích. Tento přístup zaručuje spolehlivý čárový kód, který splňuje standard ISO/IEC 16022.

### Krok 1: Inicializace BarcodeGenerator

`BarcodeGenerator` je hlavní třída používaná k vytváření obrázků čárových kódů pro danou symbologii a data.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Krok 2: Nastavte DataMatrix režim kódování na Bytes

`DataMatrixEncodeMode.Bytes` říká generátoru, aby vstup považoval za surové binární bajty místo textu.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Krok 3: Nastavte zobrazovaný text

Vlastnost `CodeText` nastavuje lidsky čitelný text zobrazovaný pod symbolem čárového kódu.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Krok 4: Uložte obrázek čárového kódu

Metoda `Save` zapíše vygenerovaný čárový kód do souboru obrázku ve specifikovaném formátu.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Krok 5: Pokuste se rozpoznat

`BarCodeReader` čte obrázky čárových kódů a extrahuje zakódovaná data.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Krok 6: Procházejte a zobrazte výsledky

Procházejte `reader.ReadBarCodes()` pro přístup k jednotlivým detekovaným čárovým kódům a jejich `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

S těmito kroky jste úspěšně **vytvořili DataMatrix čárový kód** v režimu Bytes a ověřili jej pomocí Aspose.BarCode pro .NET. Knihovna abstrahuje nízkoúrovňové detaily kódování, takže se můžete soustředit na obchodní logiku místo matematiky čárových kódů.

## Časté problémy a řešení

- **Zakódovaná data jsou oříznuta** – Ujistěte se, že pole bajtů nepřesahuje 1 555 bajtů; jinak knihovna automaticky přepne na větší velikost symbolu nebo vyhodí výjimku.
- **Obrázek je rozmazaný** – Uložte obrázek ve vyšším rozlišení (např. 300 dpi) nastavením `generator.Parameters.ImageResolution` před voláním `Save`.
- **Reader vrací null** – Ověřte, že cesta k obrázku je správná a soubor není poškozený; také potvrďte, že `BarCodeReader` je vytvořen s `DecodeType.DataMatrix`.

## Často kladené otázky

**Q: Co je režim kódování DataMatrix?**  
A: Režim kódování DataMatrix určuje, jak jsou vstupní data transformována do dvourozměrného vzoru; režim Bytes ukládá surové binární bajty přímo.

**Q: Jak mohu získat bezplatnou zkušební verzi Aspose.BarCode pro .NET?**  
A: Bezplatnou zkušební verzi Aspose.BarCode pro .NET můžete získat [zde](https://releases.aspose.com/).

**Q: Kde najdu dokumentaci k Aspose.BarCode pro .NET?**  
A: Dokumentace k Aspose.BarCode pro .NET je k dispozici [zde](https://reference.aspose.com/barcode/net/).

**Q: Je Aspose.BarCode pro .NET vhodný pro komerční použití?**  
A: Ano, Aspose.BarCode pro .NET je vhodný pro komerční použití. Licenci můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Mohu použít dočasnou licenci pro Aspose.BarCode pro .NET?**  
A: Ano, dočasnou licenci pro Aspose.BarCode pro .NET můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Mistrovské kódování DataMatrix v ASCII s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Čtení DataMatrix čárového kódu C# – Generování DataMatrix režimu (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}