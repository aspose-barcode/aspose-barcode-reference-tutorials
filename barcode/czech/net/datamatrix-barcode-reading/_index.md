---
date: 2026-09-28
description: Naučte se, jak snadno číst datamatrix a jak generovat datamatrix čárové
  kódy pomocí Aspose.BarCode pro .NET. Prozkoumejte programování čtečky, strukturované
  připojení a návody na generování.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Čtení DataMatrix čárových kódů
og_description: Jak číst datamatrix čárové kódy pomocí Aspose.BarCode pro .NET – rychlý,
  multiplatformní návod zahrnující čtení, strukturované připojení a generování. (150‑160
  znaků)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Jak číst datamatrix čárové kódy pomocí Aspose.BarCode pro .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Jak číst datamatrix čárové kódy pomocí Aspose.BarCode pro .NET
url: /cs/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst DataMatrix čárové kódy

Pokud potřebujete **jak číst datamatrix** efektivně v prostředí .NET, tento průvodce vám poskytne krok‑za‑krokem návod na čtení, konfiguraci structured append a generování DataMatrix čárových kódů pomocí Aspose.BarCode pro .NET. Uvidíte, proč je knihovna špičkovou volbou, co musíte předem připravit a kde najdete nejužitečnější ukázky kódu.

## Rychlé odpovědi
- **Co je DataMatrix?** Dvourozměrný matice čárový kód, který ukládá velké množství dat v malém prostoru.  
- **Která knihovna vám pomůže číst DataMatrix v .NET?** Aspose.BarCode for .NET.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Mohu také generovat DataMatrix čárové kódy?** Ano—použijte stejné API k **jak generovat datamatrix** čárovým kódům s vlastními nastaveními.  
- **Podporované platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 na Windows, Linux a macOS.

## Co je čtení DataMatrix čárových kódů?
Čtení DataMatrix čárového kódu extrahuje zakódovaný text nebo binární data z obrázku, PDF stránky nebo živého video snímku. Dekodér Aspose.BarCode pracuje přímo s objekty `System.Drawing.Image`, `Stream` nebo `PdfPage`, takže jej můžete napájet ze souborů, paměťových streamů nebo zachycení z kamery bez dalších konverzních kroků.

## Proč používat Aspose.BarCode pro DataMatrix?
Aspose.BarCode zpracovává až **5 000 čárových kódů za sekundu** na standardním 2,5 GHz procesoru, podporuje **více než 50 vstupních formátů** a nevyžaduje **žádné externí nativní závislosti**. Knihovna běží na Windows, Linuxu a macOS, podporuje úrovně opravy chyb od ECC 000 do ECC 200 a nabízí vestavěnou podporu structured‑append — vše při zachování využití paměti pod 20 MB pro dávku 1 000 stránek.

## Předpoklady
- .NET Framework 4.5+ nebo .NET Core 3.1+ (jakákoli recentní verze .NET).  
- Nainstalovaný NuGet balíček Aspose.BarCode pro .NET.  
- Základní znalost C# a IDE jako Visual Studio nebo Rider.

## Programování čtečky DataMatrix: bezproblémová integrace

### Jak číst DataMatrix čárový kód v .NET?
`BarcodeReader` je třída Aspose.BarCode, která dekóduje čárové kódy z obrázků, streamů nebo PDF stránek.  
Načtěte obrázek nebo PDF stránku, vytvořte `BarcodeReader`, povolte příznak `ReadMultipleBarcodes`, pokud očekáváte více než jeden kód, a zavolejte `Read`. Metoda vrátí kolekci `BarCodeResult` obsahující dekódovanou hodnotu, typ symbologie a skóre důvěry.  
`BarCodeResult` představuje jeden dekódovaný čárový kód, včetně jeho hodnoty, typu symbologie a skóre důvěry.

### Jak povolit zpracování structured append?
Nastavte vlastnost `ReadStructuredAppend` na `true` před voláním `Read`. Čtečka automaticky spojí fragmenty, které patří ke stejné logické zprávě, a vrátí jeden sloučený výsledek.

## Konfigurace structured append pro DataMatrix: precizní organizace dat
Structured Append umožňuje rozdělit jednu logickou zprávu na více DataMatrix symbolů. Když tuto funkci povolíte, Aspose.BarCode sestaví fragmenty na základě čísel sekvence vložených do každého symbolu. To je ideální pro kódování dlouhých URL, velkých binárních bloků nebo vícestránkových dokumentů.

## Generování DataMatrix čárových kódů: uvolněte kreativitu s Aspose.BarCode pro .NET
`BarcodeGenerator` je třída Aspose.BarCode používaná k generování obrázků čárových kódů s nastavitelnými parametry. Stejná třída `BarcodeGenerator`, kterou používáte pro čtení, také vytváří DataMatrix symboly. Můžete řídit velikost modulu, okraj, úroveň ECC a dokonce vložit logo. Generátor vytváří soubory PNG, JPEG, SVG nebo PDF, což vám poskytuje plnou flexibilitu pro web, tisk nebo mobilní scénáře.

## Tutoriály čtení DataMatrix čárových kódů
### [Programování čtečky DataMatrix](./datamatrix-reader-programming/)
Prozkoumejte programování čtečky DataMatrix s Aspose.BarCode pro .NET. Naučte se generovat a číst DataMatrix čárové kódy ve vašich .NET aplikacích pomocí tohoto komplexního průvodce.
### [Konfigurace Structured Append pro DataMatrix](./datamatrix-structured-append-configuration/)
Naučte se vytvářet a číst konfiguraci structured append pro DataMatrix v .NET pomocí Aspose.BarCode pro vysoce efektivní organizaci dat.
### [Generovat DataMatrix čárové kódy](./datamatrix-versions/)
Naučte se generovat DataMatrix čárové kódy v .NET pomocí Aspose.BarCode pro .NET. Vlastní rozměry, podpora ECC a další.

## Často kladené otázky

**Q: Mohu použít Aspose.BarCode pro komerční projekty?**  
A: Ano. Pro produkční použití je vyžadována platná komerční licence, ale je k dispozici bezplatná zkušební verze pro vyhodnocení.

**Q: Podporuje knihovna čtení DataMatrix z PDF souborů?**  
A: Rozhodně. Můžete načíst PDF stránku jako obrazový stream a předat ji přímo čtečce čárových kódů.

**Q: Jak zvládnu Structured Append, když je čárový kód rozdělen na více obrázků?**  
A: API automaticky sestaví fragmenty, pokud před dekódováním povolíte vlastnost `ReadStructuredAppend`.

**Q: Jaké úrovně opravy chyb jsou k dispozici při generování DataMatrix čárového kódu?**  
A: Můžete si vybrat z ECC 000, 050, 080, 100, 140 a 200 podle požadované hustoty dat a odolnosti.

**Q: Existuje způsob, jak zlepšit výkon čtení u velkých dávkách obrázků?**  
A: Ano—použijte `BarcodeReader` s nastaveným `ReadMultipleBarcodes` na `true` a zpracovávejte obrázky ve paralelních vláknech.

**Poslední aktualizace:** 2026-09-28  
**Testováno s:** Aspose.BarCode pro .NET 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/net/datamatrix-barcode-configuration/)
- [Jak číst DataMatrix Append s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Generovat DataMatrix čárový kód v ASCII režimu s Aspose.BarCode pro .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}