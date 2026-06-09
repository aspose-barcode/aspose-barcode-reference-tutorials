---
date: 2026-06-09
description: Zjistěte, jak generovat datamatrix čárový kód pomocí Aspose.BarCode pro
  .NET, přizpůsobit poměry stran, režimy ECC a kódování datamatrix c40 pro efektivní
  tvorbu čárových kódů.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Konfigurace DataMatrix čárového kódu
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generování DataMatrix čárového kódu – Profesionální průvodce s Aspose.BarCode
url: /cs/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování DataMatrix čárového kódu – Průvodce pro Aspose.BarCode

Vítejte v naší komplexní sérii tutoriálů o **generování datamatrix čárového kódu** pomocí Aspose.BarCode pro .NET. Ať už jste zkušený vývojář ladící výstup čárových kódů nebo nováček, který se chce seznámit se základy, tento průvodce vás provede každým krokem – od základní konfigurace po pokročilé techniky kódování – abyste mohli dodávat spolehlivé, připravené ke skenování čárové kódy v jakékoli .NET aplikaci.

## Rychlé odpovědi
- **Jaký je hlavní účel?** Vytvářet a přizpůsobovat DataMatrix čárové kódy programově.  
- **Která knihovna se používá?** Aspose.BarCode for .NET.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze; pro produkční nasazení je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mohu přizpůsobit poměr stran?** Ano – viz sekce „Jak přizpůsobit poměr stran DataMatrix“.

## Co je generování DataMatrix čárového kódu?
DataMatrix čárový kód je dvourozměrná matice černých a bílých buněk, která může uložit až 2 300 alfanumerických znaků. Pomocí Aspose.BarCode můžete **generovat datamatrix čárový kód** jako obrázky, PDF nebo SVG přímo z vašeho .NET kódu, řídit velikost, úroveň opravy chyb a režim kódování tak, aby splňovaly jakýkoli průmyslový standard.

## Proč používat Aspose.BarCode pro DataMatrix?
Aspose.BarCode vykresluje DataMatrix symboly až do **600 dpi** bez pixelace, což zaručuje ostré skeny na vysoce rozlišených tiskárnách. Podporuje **více než 50 ECC a makro režimů** – včetně ECC 000‑140, ECC 200 a Macro 05/06 – takže si můžete vybrat optimální úroveň opravy chyb pro velikost vašich dat. API nabízí **ASCII, C40, Text, X12 a Bytes** kódovací možnosti, což vám umožní efektivně zabalit data. Integrace vyžaduje jen jeden NuGet balíček a žádné externí nativní knihovny.

## Jak přizpůsobit poměr stran DataMatrix
Vlastnost `AspectRatio` třídy `BarCodeGenerator` řídí poměr šířky k výšce generovaného DataMatrix symbolu. `BarCodeGenerator` je hlavní třída v Aspose.BarCode používaná k vytváření obrázků čárových kódů.  

**Přímá odpověď:** Nastavte `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (nebo libovolnou hodnotu mezi 0.5 a 2.0) před voláním `GenerateBarCodeImage()`. Knihovna automaticky přepočítá velikost modulů, aby zachovala spolehlivost skenování při respektování požadovaného poměru.

### Krok za krokem
1. **Instancovat** `BarCodeGenerator` s `EncodeTypes.DataMatrix`.  
2. **Upravit** `AspectRatio` na požadovanou hodnotu.  
3. **Vygenerovat** obrázek a ověřit pomocí skeneru nebo vestavěného čtečky Aspose.

## Jak generovat DataMatrix ECC 000‑140 čárové kódy
ECC 000‑140 je ideální pro krátké řetězce dat, kde je vyžadován kompaktní symbol, a nabízí až 140 kódových slov pro opravu chyb. `DataMatrixEccMode.Ecc000140` vybírá schéma opravy chyb ECC 000‑140 pro DataMatrix.  

**Přímá odpověď:** Použijte `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` před vykreslením. Tím se přepne enkodér na algoritmus ECC 000‑140, což vytvoří nejmenší možnou matici pro daná data při zachování robustní opravy chyb.

### Praktický tip
Při kódování číselných dat pod 20 znaků ECC 000‑140 často vytvoří matici 10 × 10, což šetří cenný prostor na štítku.

## Jak generovat DataMatrix ECC 200 čárové kódy
ECC 200 je nejrozšířenější režim DataMatrix, podporuje až 2 335 alfanumerických znaků a nabízí vynikající opravu chyb. `DataMatrixEccMode.Ecc200` vybírá schéma opravy chyb ECC 200 pro DataMatrix.  

**Přímá odpověď:** Nastavte `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` a svůj obsah předáte pomocí `CodeText`. Knihovna pak automaticky vybere optimální velikost matice.

### Kdy upřednostnit ECC 200
Použijte ECC 200 pro delší řetězce, smíšená data nebo když potřebujete nejvyšší odolnost proti poškození – až **30 %** symbolu může být obnoveno.

## Jak ovládnout kódování DataMatrix v ASCII
ASCII režim kóduje znaky pomocí jednoho bajtu na znak, což je nejefektivnější pro čistý text. `DataMatrixEncodeMode.Ascii` říká generátoru, aby použil ASCII kódování pro DataMatrix symbol.  

**Přímá odpověď:** Přiřaďte `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` a nastavte `CodeText` na váš ASCII řetězec. Engine data sbalí bez nadbytečného zatížení, čímž vytvoří nejmenší možnou matici pro čistý ASCII obsah.

### Příklad scénáře
Skladové SKU složené z velkých písmen a číslic (např. “AB1234”) se perfektně hodí do ASCII režimu a často vede k matici 12 × 12.

## Jak generovat DataMatrix režim (Auto)
Auto režim umožňuje Aspose.BarCode analyzovat vstup a automaticky vybrat nejefektivnější kódování (ASCII, C40, Text, X12 nebo Bytes). `DataMatrixEncodeMode.Auto` aktivuje tuto funkci automatického výběru.  

**Přímá odpověď:** Nastavte `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Knihovna vyhodnotí payload, vybere optimální režim a vykreslí čárový kód v jediném kroku.

### Výhody
Auto režim snižuje vývojové úsilí a zaručuje nejmenší možný symbol pro smíšená data, což zlepšuje rychlost skenování.

## Jak použít kódovací režim DataMatrix (Bytes)
Bytes režim je určen pro binární data, jako jsou šifrované payloady nebo komprimované soubory. `DataMatrixEncodeMode.Bytes` instruuje generátor, aby každému bajtu přikládal surová data.  

**Přímá odpověď:** Použijte `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` a jako `CodeText` poskytněte řetězec kódovaný Base64. Enkodér zachází s každým bajtem jako s čistými daty a zachovává přesnou binární reprezentaci.

### Případ použití
Vložení 128‑bitového GUID nebo malého šifrovaného tokenu přímo do DataMatrix symbolu.

## Jak ovládnout kódovací režim DataMatrix (C40)
C40 režim komprimuje alfanumerická data velkými písmeny, dosahuje až **40 %** úspory velikosti oproti ASCII. `DataMatrixEncodeMode.C40` aktivuje tento kompresní algoritmus.  

**Přímá odpověď:** Nastavte `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` a zadejte řetězec velkými písmeny (např. “HELLO WORLD”). Engine sbalí tři znaky do dvou kódových slov, čímž zmenší finální matici.

### Tip pro profesionály
C40 funguje nejlépe, když payload převážně obsahuje velká písmena, číslice a mezery. Pro smíšený případ zvažte Auto režim.

## Jak nastavit text kódu DataMatrix
Vlastnost `CodeText` definuje přesná data uložená v čárovém kódu. Může obsahovat prostý text, číselné řetězce nebo dokonce XML payloady. `CodeText` je hlavní řetězcová vlastnost `BarCodeGenerator`, která drží payload čárového kódu.  

**Přímá odpověď:** Přiřaďte `generator.Parameters.Barcode.CodeText = "YourDataHere"` před vykreslením. Vlastnost přijímá libovolný UTF‑8 řetězec až do maximální délky podporované zvoleným ECC režimem.

### Pokročilý tip
Kombinujte `CodeText` s `ExtendedDataMatrix` pro vložení dodatečných metadat bez zvětšení viditelné velikosti matice.

## Jak ovládnout konfiguraci DataMatrix makra
Makro režimy (Macro 05 a Macro 06) umožňují vložit sekundární DataMatrix symbol do primárního, což je užitečné pro propojení s externími zdroji dat. `DataMatrixMacroMode.Macro05` a `DataMatrixMacroMode.Macro06` aktivují tyto makro funkce.  

**Přímá odpověď:** Aktivujte makro režim pomocí `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (nebo `Macro06`) a nastavte vlastnosti `MacroPdf417` pro sekundární payload. Generátor vytvoří kompozitní symbol, který skenery interpretují jako dva propojené kódy.

### Reálný příklad
Vložení URL do makro části při zachování produktových identifikátorů v primární matici, což umožňuje bezproblémovou integraci web‑to‑barcode.

*Seznam tutoriálů Aspose.BarCode pro .NET*

## Tutoriály konfigurace DataMatrix čárových kódů
### [Přizpůsobení poměru stran DataMatrix](./datamatrix-aspect-ratio-customization/)
Naučte se přizpůsobit poměr stran DataMatrix čárových kódů pomocí Aspose.BarCode pro .NET. Praktický krok‑za‑krokem průvodce generováním čárových kódů.
### [Generovat DataMatrix ECC 000-140 čárové kódy](./datamatrix-ecc-000-140-configuration/)
Vytvořte DataMatrix ECC 000-140 čárové kódy snadno pomocí Aspose.BarCode pro .NET. Zvýšte efektivitu ve správě zásob a dalších oblastech.
### [Generovat DataMatrix ECC 200 čárové kódy](./datamatrix-ecc-200-configuration/)
Naučte se generovat DataMatrix ECC 200 čárové kódy v .NET pomocí Aspose.BarCode. Zefektivněte operace pomocí efektivního vytváření čárových kódů.
### [Ovládněte kódování DataMatrix v ASCII](./datamatrix-encoding-mode-ascii/)
Naučte se vytvářet DataMatrix čárové kódy v ASCII režimu pomocí Aspose.BarCode pro .NET. Praktický krok‑za‑krokem průvodce pro vývojáře.
### [Jak generovat DataMatrix režim (Auto)](./datamatrix-encoding-mode-auto/)
Naučte se generovat DataMatrix režim (Auto) s Aspose.BarCode pro .NET. Tento krok‑za‑krokem průvodce pokrývá vše od předpokladů po čtení čárových kódů.
### [DataMatrix kódovací režim (Bytes)](./datamatrix-encoding-mode-bytes/)
Naučte se kódovat data v DataMatrix formátu pomocí Bytes režimu s Aspose.BarCode pro .NET. Sledujte náš krok‑za‑krokem průvodce pro generování a rozpoznávání čárových kódů.
### [Ovládněte kódovací režim DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Naučte se DataMatrix kódovací režim (C40) s Aspose.BarCode pro .NET. Vytvářejte vlastní čárové kódy efektivně. Prozkoumejte krok‑za‑krokem průvodce.
### [Konfigurace rozšířeného textu DataMatrix kódu](./datamatrix-extended-code-text-configuration/)
Naučte se konfigurovat rozšířený text DataMatrix pomocí Aspose.BarCode pro .NET. Generujte, rozpoznávejte a integrujte čárové kódy ve vašich .NET aplikacích.
### [Ovládněte konfiguraci DataMatrix makra](./datamatrix-macro-configuration/)
Naučte se konfigurovat DataMatrix makro čárové kódy s Aspose.BarCode pro .NET. Generujte, přizpůsobujte a rozpoznávejte DataMatrix čárové kódy ve vašich .NET aplikacích.

## Často kladené otázky

**Q: Jak se rozhodnu, který ECC režim použít?**  
A: Zvolte ECC 000‑140 pro malé datové sady s omezenou opravou chyb, nebo ECC 200 pro větší data a vyšší spolehlivost. Makro režim přidává další datovou vrstvu pro propojení.

**Q: Mohu vložit vlastní text do DataMatrix čárového kódu?**  
A: Ano, nastavte vlastnost `CodeText` na váš vlastní řetězec a poté vyberte vhodný kódovací režim (ASCII, C40 atd.) pro kontrolu velikosti.

**Q: Existuje způsob, jak automaticky vybrat nejlepší kódovací režim?**  
A: Nastavte `EncodeMode` na `Auto`; Aspose.BarCode vyhodnotí payload a automaticky vybere nejefektivnější režim.

**Q: Jaké jsou výkonnostní úvahy při velkých dávkách čárových kódů?**  
A: Znovu použijte jedinou instanci `BarCodeGenerator`, povolte vícevláknové zpracování a generujte PNG obrázky pro bezztrátovou kvalitu nebo JPEG pro menší velikost souboru. Zpracování 10 000 symbolů obvykle trvá méně než 30 sekund na standardním 8‑jádrovém serveru.

**Q: Podporuje Aspose.BarCode .NET Core a .NET 5/6?**  
A: Rozhodně – knihovna je plně kompatibilní s .NET Framework, .NET Core i nejnovějšími .NET verzemi a nabízí stejnou sadu funkcí napříč všemi platformami.

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Související tutoriály

- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Ovládněte kódování DataMatrix v ASCII s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Vytvořit PNG čárový kód – Poměr stran DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}