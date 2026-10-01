---
date: 2026-08-02
description: Podrobný návod krok za krokem, jak číst čárový kód DataMatrix v C# a
  generovat obrázek čárového kódu v C# pomocí Aspose.BarCode pro .NET s automatickým
  kódováním.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Režim kódování DataMatrix (Auto)
og_description: Naučte se, jak číst čárový kód DataMatrix v C# a generovat jej v režimu
  Auto pomocí Aspose.BarCode pro .NET. Tento tutoriál pokrývá nastavení, kód a řešení
  problémů.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Jak číst čárový kód DataMatrix v C# – Auto režim
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Jak číst čárový kód DataMatrix v C# – Auto režim
url: /cs/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst DataMatrix čárový kód C# – Auto režim

V dnešním rychle se rozvíjejícím digitálním světě je **jak číst datamatrix** rychle a spolehlivě nezbytné pro sledování zásob, bezpečnou manipulaci s dokumenty a mnoho dalších podnikových scénářů. Tento tutoriál vás provede generováním DataMatrix čárového kódu v režimu *Auto* pomocí Aspose.BarCode pro .NET a poté ukáže, jak tento čárový kód načíst zpět v C#. Ať už sledujete průvodce tutoriálem čárových kódů nebo potřebujete připravený ukázkový kód, skončíte s řešením připraveným pro produkci, které můžete vložit do libovolného .NET projektu.

## Rychlé odpovědi
- **Co dělá režim „Auto“?** Umožňuje Aspose.BarCode automaticky vybrat nejlepší kódovací schéma pro vaše data.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro .NET (k dispozici bezplatná zkušební verze).  
- **Mohu čárový kód načíst ve stejné aplikaci?** Ano – použijte `BarCodeReader` s `DecodeType.DataMatrix`.  
- **Potřebuji licenci pro produkci?** Pro produkční použití je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` je třída Aspose.BarCode pro skenování obrázků a získávání informací o čárových kódech.

## Co je čtení DataMatrix čárového kódu v C#?
Čtení DataMatrix čárového kódu v C# znamená dekódování dvourozměrné matice černých a bílých modulů zpět do původního textu nebo dat. Aspose.BarCode abstrahuje nízkoúrovňové zpracování obrazu, takže se můžete soustředit na obchodní logiku, zatímco knihovna automaticky zajišťuje opravu chyb, výběr velikosti symbolu a podporu Unicode.

## Proč použít Aspose.BarCode k vytvoření obrázku čárového kódu v C#?
Aspose.BarCode automaticky vybírá optimální kódování, podporuje **více než 30 symbologií čárových kódů** a může generovat DataMatrix symboly až do **1558 × 1558 modulů** – mnohem větší než u většiny konkurentů. Běží na Windows, Linuxu a macOS bez nativních závislostí, což vám poskytuje jednotné, multiplatformní API jak pro generování, tak pro čtení.

## Požadavky

1. **.NET prostředí** – Nainstalujte nejnovější .NET runtime z [.NET webu](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode pro .NET** – Stáhněte knihovnu z [webu](https://releases.aspose.com/barcode/net/).  

## Importování jmenných prostorů
Jmenný prostor `Aspose.BarCode` obsahuje všechny třídy, které potřebujete pro vytváření a čtení čárových kódů. Importujte jej na začátek souboru před jakýkoli jiný kód.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Nyní, když jsou jmenné prostory na místě, projděme kód krok za krokem.

## Krok 1: Nastavení cesty ke složce
Vyberte složku, kam bude uložen vygenerovaný PNG (nebo jakýkoli podporovaný formát). Tato cesta může být absolutní nebo relativní k vašemu projektu.

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` složkou, kterou preferujete. Udržení výstupní složky konfigurovatelné činí tutoriál znovupoužitelným v různých prostředích.

## Krok 2: Vytvoření DataMatrix čárového kódu v Auto režimu
`DataMatrixEncodeMode.Auto` říká generátoru, aby automaticky vybral optimální kódovací schéma pro poskytnutá data.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Klidně nahraďte ukázkový text libovolným řetězcem, pro který potřebujete **jak generovat datamatrix**. Auto režim automaticky přepne mezi Base‑256, ASCII nebo jinými schématy, aby dosáhl co nejmenšího možného symbolu.

## Krok 3: Čtení čárového kódu (čtení DataMatrix čárového kódu v C#)
`BarCodeReader` je třída Aspose.BarCode pro skenování obrázků a získávání informací o čárových kódech. Podporuje čtení ze streamů, souborů a bitmapových objektů, což ji činí ideální pro scénáře **čtení čárového kódu ze souboru**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Tento úryvek dekóduje obrázek, který jsme právě vygenerovali, a vypíše původní text do konzole, čímž demonstruje kompletní cyklus od generování po čtení.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Žádný čárový kód nebyl detekován** | Rozlišení obrázku je příliš nízké | Zvyšte `XDimension.Pixels` (např. na 6) |
| **Špatné znaky** | Nesprávné ECI kódování | Nastavte `ECIEncoding` tak, aby odpovídalo vašim datům (UTF‑8, ASCII, atd.) |
| **Výjimka při `ReadBarCodes`** | Bitmap byl uvolněn před čtením | Udržujte instanci `Bitmap` živou až po čtení |

## Často kladené otázky

**Q: Co je kódovací režim DataMatrix „Auto“?**  
A: Umožňuje Aspose.BarCode automaticky vybrat optimální kódovací metodu pro poskytnutá data, což zjednodušuje proces **jak generovat datamatrix**.

**Q: Mohu přizpůsobit rozměry vygenerovaného čárového kódu?**  
A: Ano – upravte `generator.Parameters.Barcode.XDimension.Pixels` pro změnu velikosti modulu.

**Q: Je Aspose.BarCode pro .NET vhodný pro komerční použití?**  
A: Rozhodně. Zakupte licenci na [webu](https://purchase.aspose.com/buy).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete si vyzkoušet Aspose.BarCode s bezplatnou zkušební verzí na [tomto odkazu](https://releases.aspose.com/).

**Q: Jaké možnosti kódování jsou k dispozici pro DataMatrix čárové kódy?**  
A: Aspose.BarCode podporuje UTF‑8, ASCII a další ECI kódování; požadovanou hodnotu nastavte pomocí `ECIEncoding`.

## Závěr

Nyní máte kompletní, připravený příklad pro produkci, který **čte DataMatrix čárový kód v C#**, generuje čárový kód v Auto režimu a ověřuje výsledek – vše pomocí Aspose.BarCode pro .NET. Experimentujte s různými texty, velikostmi a nastavením ECI, aby vyhovovaly vašemu konkrétnímu scénáři, a odkazujte na oficiální [dokumentaci](https://reference.aspose.com/barcode/net/) pro podrobnější přizpůsobení.

---

**Poslední aktualizace:** 2026-08-02  
**Testováno s:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/)
- [Konfigurace strukturovaného připojení DataMatrix s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Programování čtečky DataMatrix s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}