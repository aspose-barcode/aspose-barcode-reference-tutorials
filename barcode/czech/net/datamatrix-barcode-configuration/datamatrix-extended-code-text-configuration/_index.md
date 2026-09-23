---
date: 2026-09-23
description: Naučte se, jak použít Aspose.BarCode k vygenerování čárového kódu DataMatrix
  s rozšířeným textem kódu v .NET, ideální pro aplikace v oblasti inventarizace a
  logistiky.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Konfigurace rozšířeného textu kódu DataMatrix
og_description: Jak použít Aspose.BarCode k vygenerování čárového kódu DataMatrix
  s rozšířeným textem kódu v .NET. Postupujte podle rychlého krok‑za‑krokem průvodce
  pro řešení v oblasti inventarizace a logistiky.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Jak použít Aspose.BarCode k vytvoření textu kódu DataMatrix v .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Jak použít Aspose.BarCode k vytvoření textu kódu DataMatrix v .NET
url: /cs/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít Aspose.BarCode k vytvoření textu DataMatrix kódu v .NET

Integrace čárových kódů do moderních .NET aplikací již není úzký úkol – je to základní požadavek pro inventarizaci, logistiku a mobilní skenovací řešení. V tomto průvodci se **naučíte, jak použít Aspose.BarCode** k nastavení DataMatrix čárového kódu s rozšířeným textem, vygenerování obrázku a jeho programové ověření. Uvidíte, proč je tento přístup ideální pro tvorbu čárových kódů pro inventář a jak zapadá do projektů .NET Core nebo .NET 6.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode for .NET  
- **Jaký typ čárového kódu?** DataMatrix with extended code text  
- **Mohu použít .NET Core / .NET 6?** Yes, the API is cross‑platform  
- **Potřebuji licenci pro testování?** A free trial works for development; a license is required for production  
- **Jak dlouho trvá implementace?** About 10‑15 minutes for a basic example  

## Co je Aspose.BarCode pro .NET?
Aspose.BarCode pro .NET je komerční knihovna, která umožňuje vývojářům generovat a rozpoznávat více než 30 symbologií čárových kódů, včetně DataMatrix, QR a Code 128, a vytvářet obrázky až do rozměrů 10 000 × 10 000 pixelů bez externích závislostí. Podporuje .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6/7.

## Proč použít rozšířený text DataMatrix?
Rozšířený text DataMatrix vám umožňuje vložit více kódovacích schémat – UTF‑8, C40, Text, X12 – do jednoho symbolu, což umožňuje až **3116 kódových slov** (přibližně 155 KB dat) v jednom kompaktním čtverci. Tato schopnost je ideální pro vícejazyčné označování produktů, sledování lékařských zařízení a inteligentní balení, kde je potřeba kombinovat alfanumerické ID s binárními daty.

## Požadavky

Před začátkem ověřte, že máte následující:

1. **Aspose.BarCode for .NET** – stáhněte jej z oficiální stránky **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Vývojové prostředí .NET** – Visual Studio, Rider nebo VS Code s .NET SDK.  
3. **Základní znalost C#** – měli byste být obeznámeni s třídami, jmennými prostory a direktivou `using`.

## Importovat jmenné prostory

Přidejte požadované jmenné prostory na začátek vašeho souboru C#, aby kompilátor věděl, kde najít třídy čárových kódů.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Tyto jmenné prostory vám poskytují přístup k funkcím generování i rozpoznávání čárových kódů.

## Jak nakonfigurovat rozšířený text DataMatrix?

Načtěte builder, přidejte požadované segmenty a nechte Aspose.BarCode automaticky zpracovat ECI značky. Tento přímý odstavec vám popisuje přesné kroky: vytvořte `DataMatrixExtCodetextBuilder`, přidejte segmenty Unicode, C40, prostý text a Text mode, a poté získejte kombinovaný řetězec pro generátor.

### Krok 1: Definovat výstupní složku

Určete, kam bude vygenerovaný obrázek čárového kódu uložen. Nahraďte zástupný text platnou cestou na vašem počítači.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Sestavit rozšířený text kódu

`DataMatrixExtCodetextBuilder` je pomocná třída, která sestavuje rozšířený text kódu podle specifikace DataMatrix. Automaticky vkládá požadované ECI (Extended Channel Interpretation) značky.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Tato kombinace ukazuje, jak můžete v jednom symbolu DataMatrix spojit Unicode znaky, kódování C40, prostý text a Text mode.

### Krok 3: Vygenerovat finální řetězec kódu

Po nastavení všech částí získejte kombinovaný řetězec, který Aspose.BarCode vloží do čárového kódu.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Krok 4: Vytvořit DataMatrix čárový kód

`BarcodeGenerator` je hlavní třída, která vytváří obrázky čárových kódů. Vytvořte její instanci s `EncodeTypes.DataMatrix` a rozšířeným textem kódu, poté nastavte vizuální parametry jako X‑dimenzi, formát obrázku a volitelný lidsky čitelný text.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Výše uvedený kód **vytváří čárový kód aspose .net** s požadovaným rozšířeným textem a ukládá jej jako PNG soubor.

### Krok 5: Ověřit čárový kód jeho načtením

`BarCodeReader` ověřuje, že vygenerovaný symbol lze správně dekódovat, což je nezbytné pro automatizované testovací pipeline a zajištění kvality.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Pokud je vše správně nastaveno, konzole vypíše přesný rozšířený text kódu, který jste vytvořili dříve.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Čárový kód nečitelný | X‑dimenze je příliš nízká | Zvyšte `XDimension.Pixels` (např. 4 → 6) |
| Zkreslené znaky | Nesprávné ECI kódování | Zajistěte, aby `ECIEncodings.UTF8` odpovídalo znakové sadě |
| Soubor neuložen | Neplatná cesta | Použijte absolutní cestu nebo zajistěte, aby složka existovala |
| Výjimka licence | Zkušební verze vypršela | Použijte dočasnou nebo plnou licenci (viz FAQ) |

## Často kladené otázky

### Q1: Co je Aspose.BarCode pro .NET?
A1: Aspose.BarCode pro .NET je výkonná knihovna, která umožňuje vývojářům generovat a rozpoznávat širokou škálu symbologií čárových kódů, včetně DataMatrix, QR, Code128 a dalších.

### Q2: Kde najdu dokumentaci k Aspose.BarCode pro .NET?
A2: Kompletní referenci API můžete získat na **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?
A3: Ano, bezplatnou zkušební verzi lze stáhnout z **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Jak získám dočasnou licenci pro testování?
A4: Dočasné licence jsou poskytovány pro evaluační účely a lze je požádat na **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Kde mohu získat podporu nebo položit otázky ohledně Aspose.BarCode pro .NET?
A5: Oficiální fórum Aspose.BarCode je nejlepší místo, kde získat pomoc: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

**Poslední aktualizace:** 2026-09-23  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/net/datamatrix-barcode-configuration/)
- [Vygenerovat DataMatrix čárový kód v ASCII režimu s Aspose.BarCode pro .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Vygenerovat Aztec čárový kód s textovým kódováním pomocí Aspose.BarCode pro .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}