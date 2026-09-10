---
date: 2026-06-14
description: Naučte se, jak generovat čárové kódy DotCode pomocí Aspose.BarCode for
  .NET, zahrnující aspect ratio, encoding modes, extended text a reader initialization.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Jak generovat čárové kódy DotCode – Průvodce konfigurací
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak generovat čárové kódy DotCode – Průvodce konfigurací
url: /cs/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárové kódy DotCode – Průvodce konfigurací

## Úvod
**Jak generovat DotCode** čárové kódy rychle a spolehlivě je běžná požadavka pro vývojáře vytvářející řešení pro inventář, sledování nebo mobilní skenování. V tomto tutoriálu vás provedeme všemi konfiguračními možnostmi, které Aspose.BarCode pro .NET nabízí pro symboly DotCode — úpravy poměru stran, režimy kódování Auto a Bytes, zpracování rozšířeného textu kódu, inicializaci čtečky, rozvržení řádků/sloupců a režim strukturovaného připojení. Na konci budete schopni vytvořit perfektně veliké, vysoce husté obrázky DotCode, které splňují průmyslové standardy a bez problémů se integrují do jakékoli .NET aplikace.

## Rychlé odpovědi
- **Jaká je hlavní třída pro vytvoření čárového kódu DotCode?** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **Která vlastnost řídí poměr stran?** `BarCodeImageAspectRatio`.
- **Mohu přepínat mezi kódováním Auto a Bytes?** Ano, pomocí vlastnosti `EncodeMode`.
- **Je pro DotCode vyžadována samostatná čtečka?** Ne, stejný `BarcodeGenerator` může dekódovat při volání `ReadBarcode`.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Jak generovat čárové kódy DotCode pomocí Aspose.BarCode pro .NET?
`BarcodeGenerator` je hlavní třída v Aspose.BarCode pro vytváření obrázků čárových kódů. Načtěte `BarcodeGenerator` s `EncodeTypes.DotCode`, nastavte požadované vlastnosti (poměr stran, režim kódování, řádky/sloupce atd.) a zavolejte `GenerateBarCodeImage()` — knihovna vrátí připravený `System.Drawing.Image` nebo pole bajtů. Tento jednosměrný postup zpracovává všechny nízkoúrovňové detaily kódování, podporuje výstupní formáty jako PNG, JPEG a SVG a může vykreslovat obrázky až do 10 000 × 10 000 px bez nadměrné spotřeby paměti.

## Co je čárový kód DotCode?
Čárový kód DotCode je vysoce hustá, čtvercová 2D symbologie, která ukládá až 1 200 číselných nebo 800 alfanumerických znaků v kompaktní mřížce teček. Je optimalizován pro označování malých balíků a mobilní skenování, poskytuje rychlé čtecí rychlosti i na nízkém rozlišení kamer.

## Proč používat DotCode s Aspose.BarCode?
Aspose.BarCode podporuje **20+** typů 2D čárových kódů, včetně DotCode, a může zpracovávat soubory větší než **200 MB** bez načítání celého obrázku do paměti. Knihovna zaručuje **99,9 %** přesnost skenování na standardních smartphone kamerách a poskytuje vestavěné úrovně korekce chyb pro minimalizaci selhání čtení.

## Předpoklady
- .NET Framework 4.5 nebo vyšší, nebo .NET Core 3.1 / .NET 5+.
- Aspose.BarCode pro .NET (doporučena nejnovější verze).
- Dočasný nebo plný licenční klíč (zkušební verze funguje pro vývoj).

## Přizpůsobení poměru stran DotCode
**Poměr stran** určuje, jak natažená nebo zploštělá se zdá matice DotCode. Použijte vlastnost `BarCodeImageAspectRatio` k nastavení hodnoty mezi **0.5** (vyšší) a **2.0** (širší). Poměr **1.0** dává dokonale čtvercový symbol, což je výchozí nastavení a funguje nejlépe pro většinu skenerů.

> **Tip:** Při tisku na úzkých štítcích poměr **0.75** často zlepšuje čitelnost bez ztráty kapacity dat.

## Režim kódování DotCode (Auto)
V režimu **Auto** knihovna analyzuje vstupní řetězec a automaticky vybere nejefektivnější kódování (číslicové, alfanumerické nebo bajtové). To maximalizuje hustotu dat a snižuje celkovou velikost symbolu.

> **Přímá odpověď:** Nastavte `EncodeMode = EncodeModes.Auto` na `BarcodeGenerator`, aby Aspose.BarCode rozhodl o optimálním kódování vašich dat, což zajistí nejmenší možný DotCode při zachování všech znaků.

## Režim kódování DotCode (Bytes)
Když potřebujete uložit binární data nebo předkódované pole bajtů, zvolte režim **Bytes**. To nutí generátor zacházet se vstupem jako s raw bajty, obcházející automatickou detekci znakové sady.

> **Přímá odpověď:** Použijte `EncodeMode = EncodeModes.Bytes` a poskytněte `byte[]` payload pro vložení binárních informací, jako jsou šifrované identifikátory nebo komprimované soubory, přímo do symbolu DotCode.

## Konfigurace rozšířeného textu kódu DotCode
Rozšířený text kódu vám umožňuje připojit doplňující informace, které nejsou součástí hlavního datového payloadu, ale mohou být zobrazeny vedle čárového kódu v reportech nebo GUI. Nastavte vlastnost `ExtendedCodeText` na libovolný řetězec (až **256** znaků) a vyberte písmo pomocí `ExtendedCodeTextFont`.

> **Pro tip:** Kombinujte rozšířený text s menší velikostí písma (např. 8 pt), aby byl vizuální dopad nízký a přitom poskytoval čitelný kontext pro člověka.

## Inicializace čtečky DotCode
`BarCodeReader` je třída používaná k dekódování čárových kódů z obrázků nebo streamů. Čtení obrázku DotCode je stejně jednoduché jako generování. Vytvořte instanci `BarCodeReader` s obrazovým streamem a specifikujte `EncodeTypes.DotCode`. Zavolejte `ReadBarCode()`, abyste získali dekódovaný řetězec.

> **Přímá odpověď:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – tento jediný blok dekóduje symbol bez externích závislostí.

## Konfigurace řádků a sloupců DotCode
DotCode umožňuje explicitní kontrolu nad počtem řádků a sloupců, což ovlivňuje velikost symbolu a kapacitu korekce chyb. Použijte vlastnosti `Rows` a `Columns` k nastavení hodnot mezi **10** a **144**. Větší matice zvyšují kapacitu dat a odolnost.

> **Nejlepší praxe:** Pro inventární štítky, které musí odolávat hrubému zacházení, nastavte **Rows = 64** a **Columns = 64**, aby se přidala další redundance.

## Konfigurace režimu Structured Append pro DotCode
Structured Append umožňuje rozdělení velkého payloadu na více symbolů DotCode, které lze číst sekvenčně. Nastavte `StructuredAppend = true` a definujte `StructuredAppendCount` a `StructuredAppendIndex` pro každou část.

> **Přímá odpověď:** Aktivujte `StructuredAppend` na každém `BarcodeGenerator`, přiřaďte jedinečný index (začínající od 1) a nastavte celkový počet; knihovna automaticky vloží potřebné propojující informace.

## Časté problémy a řešení
- **Čárový kód nečitelný na obrazovkách s nízkým rozlišením:** Zvyšte vlastnost `Resolution` na alespoň **300 dpi** před generováním.
- **Upozornění na oříznutí dat:** Ověřte, že délka vstupu nepřekračuje maximum pro vybrané řádky/sloupce; upravte velikost nebo přepněte do režimu Bytes, pokud je to potřeba.
- **Vypršení licence během vývoje:** Použijte dočasnou licenci získanou z portálu Aspose; před nasazením do produkce ji nahraďte trvalým klíčem.

## Často kladené otázky

**Q: Mohu generovat čárové kódy DotCode ve formátu SVG?**  
A: Ano, nastavte `BarCodeImageFormat = BarCodeImageFormat.Svg` na generátoru, abyste získali výstup ve škálovatelném vektorovém formátu.

**Q: Je možné vložit logo do symbolu DotCode?**  
A: Aspose.BarCode nepodporuje přímé vkládání loga pro DotCode, ale můžete po generování překrýt obrázek pomocí standardních grafických knihoven.

**Q: Jak funguje korekce chyb u DotCode?**  
A: Symbologie obsahuje vestavěnou Reed‑Solomon korekci chyb; zvýšením řádků/sloupců se automaticky zvyšuje úroveň korekce.

**Q: Potřebuji samostatnou knihovnu pro čtení DotCode z PDF?**  
A: Ne, stejný `BarCodeReader` může extrahovat DotCode z PDF stránek, obrázků nebo streamů bez dalších nástrojů.

**Q: Jaká je maximální velikost dat pro jeden symbol DotCode?**  
A: Až **1 200** číselných nebo **800** alfanumerických znaků, v závislosti na zvolené konfiguraci řádků/sloupců.

---

**Last Updated:** 2026-06-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

## Tutoriály konfigurace čárových kódů DotCode
### [Přizpůsobit poměr stran DotCode](./dotcode-aspect-ratio-customization/)
Learn to customize DotCode barcode aspect ratio using Aspose.BarCode for .NET. Create tailored barcodes for your applications effortlessly.
### [Režim kódování DotCode (Auto)](./dotcode-encoding-mode-auto/)
Explore DotCode Encoding Mode (Auto) in Aspose.BarCode for .NET, a powerful tool for barcode generation. Learn how to generate DotCode barcodes step by step. Check out the documentation, download the library, and get temporary licenses.
### [Režim kódování DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Learn DotCode Encoding with Aspose.BarCode for .NET: Step-by-step guide to generate barcodes.
### [Konfigurace rozšířeného textu kódu DotCode](./dotcode-extended-code-text-configuration/)
Generate DotCode Extended Code Text Configuration with ease using Aspose.BarCode for .NET. Follow our step-by-step guide for efficient barcode creation.
### [Inicializace čtečky DotCode](./dotcode-reader-initialization/)
Learn how to initialize DotCode Reader using Aspose.BarCode for .NET. Create DotCode barcodes with ease for various applications.
### [Konfigurace řádků a sloupců DotCode](./dotcode-rows-columns-configuration/)
Learn to configure DotCode Rows and Columns with Aspose.BarCode for .NET. Generate precise and customizable 2D barcodes effortlessly.
### [Konfigurace režimu Structured Append pro DotCode](./dotcode-structured-append-mode-configuration/)
Learn to configure DotCode Structured Append Mode with Aspose.BarCode for .NET and create efficient barcodes.

## Související tutoriály

- [Přizpůsobit poměr stran DotCode s Aspose.BarCode pro .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Konfigurace rozšířeného textu kódu DotCode s Aspose.BarCode pro .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Režim kódování DotCode (Auto) v Aspose.BarCode pro .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}