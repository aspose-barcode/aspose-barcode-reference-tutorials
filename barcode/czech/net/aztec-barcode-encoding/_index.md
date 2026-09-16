---
date: 2026-05-19
description: Naučte se, jak vytvořit Aztec barcode pomocí Aspose.BarCode pro .NET,
  přizpůsobit aspect ratios, kódovat bytes nebo text a master symbol modes.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec Barcode Encoding
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak vytvořit Aztec čárový kód pomocí Aspose.BarCode pro .NET
url: /cs/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kódování Aztec čárových kódů

Jste připraveni ponořit se do světa kódování Aztec čárových kódů a naučit se, jak **vytvářet Aztec čárové kódy** pomocí Aspose.BarCode pro .NET? Tato knihovna vám poskytuje plnou kontrolu nad velikostí, korekcí chyb a reprezentací dat, což ji činí ideální pro vše od mobilního prodeje vstupenek po sledování zásob.

## Rychlé odpovědi
- **Jaká knihovna podporuje Aztec čárové kódy?** Aspose.BarCode for .NET  
- **Mohu změnit poměr stran?** Ano, pomocí vlastnosti `AspectRatio`  
- **Je možné kódování na úrovni bajtů?** Rozhodně – použijte metodu `EncodeBytes`  
- **Jaké úrovně korekce chyb jsou k dispozici?** Úrovně 0 – 4 (vyšší = více redundance)  
- **Potřebuji licenci pro produkci?** Ano, komerční licence odstraňuje omezení evaluační verze  

## Co je Aztec čárový kód?
Aztec čárový kód je dvourozměrný maticový kód, který může zakódovat až 3 000 číselných nebo 2 300 alfanumerických znaků. Obsahuje centrální vyhledávací vzor, který umožňuje rychlé skenování i při tisku symbolu s nízkým rozlišením. Díky umístění vzoru uprostřed lze kód číst z libovolného směru, což jej činí vysoce spolehlivým pro mobilní a průmyslové aplikace.

## Jak přizpůsobit poměr stran Aztec čárového kódu?
`BarcodeGenerator` je hlavní třída používaná k vytváření čárových kódů v Aspose.BarCode. Nastavte vlastnost `AspectRatio` na objektu `BarcodeGenerator` na požadovaný poměr šířky k výšce a poté vygenerujte obrázek. Úprava poměru stran pomáhá umístit čárový kód do omezených UI prostorů nebo rozvržení štítků bez ztráty spolehlivosti skenování a také vám umožní dodržet brandingové směrnice nebo specifické požadavky tiskárny.

### Kroky pro přizpůsobení poměru stran
1. **Vytvořte instanci `BarcodeGenerator`** s `EncodeTypes.Aztec`.  
2. **Přiřaďte svá data** (text, bajty nebo číselný řetězec).  
3. **Nastavte `AspectRatio`** – například `1.5` pro širší čáru.  
4. **Vygenerujte obrázek** pomocí `Save` nebo `GetBarCodeImage`.  

## Jak zakódovat surové bajty do Aztec čárového kódu?
`EncodeBytes` je metoda, která přijímá pole bajtů a převádí jej na Aztec matici. Předávejte pole bajtů metodě `EncodeBytes` třídy `BarcodeGenerator`. API automaticky převádí binární data do kompaktní Aztec matice a zachovává každý bit. To je ideální pro vložení šifrovaných nákladů, binárních identifikátorů nebo komprimovaných souborů přímo do čárového kódu.

### Kroky pro kódování bajtů
1. **Připravte pole bajtů** (např. `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instancujte `BarcodeGenerator`** s `EncodeTypes.Aztec`.  
3. **Zavolejte `EncodeBytes(data)`** pro načtení binárního obsahu.  
4. **Vykreslete čárový kód** pomocí `Save` nebo `GetBarCodeImage`.  

## Jak zakódovat text do Aztec čárového kódu?
`CodeText` je vlastnost, která obsahuje čistý text k zakódování. Použijte vlastnost `CodeText` třídy `BarcodeGenerator` k zadání čistého textu. Knihovna automaticky vybere optimální režim kódování (číselný, alfanumerický nebo bajtový) a použije odpovídající úroveň korekce chyb. To usnadňuje vložení URL, ID produktů nebo jakéhokoli čitelného řetězce.

### Kroky pro kódování textu
1. **Vytvořte generátor** s `EncodeTypes.Aztec`.  
2. **Nastavte `CodeText`** na řetězec, který chcete zakódovat.  
3. **Volitelně upravte `ErrorLevel`** pro vyšší odolnost.  
4. **Vygenerujte obrázek** pomocí `Save` nebo `GetBarCodeImage`.  

## Jak generovat Aztec čárové kódy s různými úrovněmi korekce chyb?
`ErrorLevel` je vlastnost, která řídí množství redundantních dat přidaných do čárového kódu. Před vykreslením upravte vlastnost `ErrorLevel` (0‑4). Vyšší úrovně zvyšují množství redundantních dat, což umožňuje čtení čárového kódu i při poškození až 30 % symbolu. To je klíčové pro drsné prostředí, jako je průmyslové označování nebo venkovní značení.

### Kroky pro nastavení korekce chyb
1. **Instancujte `BarcodeGenerator`** pro Aztec.  
2. **Přiřaďte svá data** (text nebo bajty).  
3. **Nastavte `ErrorLevel`** – např. `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Vykreslete čárový kód** ve vašem preferovaném výstupním formátu.  

## Jaké jsou různé režimy Aztec Symbol a jak je použít?
`SymbolMode` je nastavení, které určuje velikost matice a kapacitu dat generovaného Aztec kódu. Režim Aztec Symbol určuje velikost matice a kapacitu dat. Knihovna nabízí čtyři režimy: **Auto**, **FullRange**, **Compact** a **Rune**.

- **Auto** – generátor vybere nejmenší možnou velikost.  
- **FullRange** – umožňuje maximální velikost matice pro velmi velké datové sady.  
- **Compact** – vytváří menší, hustší symbol ideální pro omezený prostor.  
- **Rune** – specializovaný režim pro kódování Unicode run.

Režim vyberete pomocí `Generator.Parameters.Barcode.Aztec.SymbolMode`. Každý režim vyvažuje velikost, čitelnost a kapacitu dat, což vám umožní přizpůsobit čárový kód omezením vaší aplikace.

## Tutoriály kódování Aztec čárových kódů
Níže jsou vyhrazené podrobné návody, které se hlouběji věnují jednotlivým výše zmíněným tématům. Klikněte na kterýkoli odkaz a prozkoumejte kompletní ukázky kódu, předpoklady a tipy na osvědčené postupy.

### [Přizpůsobení poměru stran Aztec čárového kódu](./aztec-aspect-ratio-customization/)
Naučte se, jak přizpůsobit poměry stran Aztec čárových kódů pomocí Aspose.BarCode pro .NET. Vytvořte jedinečné, flexibilní čárové kódy pro vaše .NET aplikace.

### [Kódování bajtů Aztec](./aztec-bytes-encoding/)
Naučte se provádět kódování bajtů Aztec pomocí Aspose.BarCode pro .NET. Obsahuje podrobný návod, předpoklady a ukázky kódu.

### [Kódování textu Aztec kódu](./aztec-code-text-encoding/)
Objevte sílu kódování textu Aztec kódu pomocí Aspose.BarCode pro .NET. Naučte se vytvářet a rozpoznávat Aztec kódy ve vašich .NET aplikacích.

### [Generování Aztec čárových kódů s chybovou úrovní](./aztec-error-level-example/)
Naučte se generovat Aztec čárové kódy s různými úrovněmi chyb pomocí Aspose.BarCode pro .NET. Kompletní návod na tvorbu čárových kódů.

### [Ovládání režimu Aztec Symbol](./aztec-symbol-mode-example/)
Prozkoumejte režim Aztec Symbol v Aspose.BarCode pro .NET a naučte se snadno generovat univerzální čárové kódy. Prakticky si vyzkoušejte režimy Auto, FullRange, Compact a Rune v tomto komplexním tutoriálu.

## Často kladené otázky

**Q: Které verze .NET jsou podporovány knihovnou Aspose.BarCode pro kódování Aztec?**  
A: Knihovna funguje s .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 a novějšími.

**Q: Mohu vytvořit vysoce rozlišený Aztec čárový kód pro tisk?**  
A: Ano—nastavte vlastnost `Resolution` (např. 300 dpi) před uložením obrázku, abyste získali kvalitu připravenou k tisku.

**Q: Jak velký datový náklad může Aztec čárový kód pojmout?**  
A: Až 3 000 číselných nebo 2 300 alfanumerických znaků, nebo přibližně 1 800 bajtů surových dat v režimu Compact.

**Q: Je možné přečíst Aztec čárový kód, který byl otočen?**  
A: Rozhodně—dekodér Aspose.BarCode automaticky detekuje orientaci a během čtení ji koriguje.

**Q: Potřebuji licenci pro vývoj a testování?**  
A: Pro testování je k dispozici bezplatná evaluační licence; pro nasazení do produkce je vyžadována komerční licence.

---

**Poslední aktualizace:** 2026-05-19  
**Testováno s:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Kódování bajtů Aztec pomocí generátoru čárových kódů .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Jak vytvořit Aztec čárový kód s korekcí chyb v .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}