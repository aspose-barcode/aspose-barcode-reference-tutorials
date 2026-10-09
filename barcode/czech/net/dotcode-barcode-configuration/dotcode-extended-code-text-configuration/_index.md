---
date: 2026-09-28
description: Naučte se, jak vytvořit 2d matrix čárový kód s Aspose.BarCode pro .NET
  – průvodce krok za krokem pro generování čárových kódů DotCode s rozšířeným textem
  kódu.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Konfigurace rozšířeného textu kódu DotCode
og_description: Naučte se vytvářet 2d matrix čárové kódy pomocí Aspose.BarCode pro
  .NET. Tento průvodce ukazuje krok za krokem, jak generovat čárové kódy DotCode s
  rozšířeným textem kódu.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Vytvořte 2d matrix čárový kód s Aspose.BarCode pro .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Jak vytvořit 2d matrix čárový kód pomocí Aspose.BarCode pro .NET
url: /cs/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit 2D maticový čárový kód pomocí Aspose.BarCode pro .NET

## Úvod

V oblasti generování a správy čárových kódů vyniká Aspose.BarCode pro .NET jako všestranné řešení, které podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat dokumenty o stovkách stránek, aniž by načítalo celý soubor do paměti. Ať už potřebujete čárové kódy pro sledování produktů, řízení zásob nebo aplikace bohaté na data, vytvoření **2D maticového čárového kódu** jako je DotCode s rozšířeným kódem textu vám umožní vložit jak textové, tak binární náklady do kompaktního čtvercového symbolu. Tento tutoriál vás provede krok za krokem tvorbou rozšířeného kódu textu a vykreslením finálního obrázku.

## Rychlé odpovědi
- **Co znamená „vytvořit rozšířený kód textu pro dotcode“?** Znamená to vytvořit DotCode čárový kód, který zahrnuje FNC1, ECICodetext, prostý text a oddělovače symbolů v jediném rozšířeném nákladu.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro .NET.  
- **Potřebuji licenci?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Jak dlouho trvá implementace?** Zhruba 10‑15 minut pro základní příklad.

## Jak vytvořit rozšířený kód textu pro dotcode

Načtěte svůj projekt, nastavte adresář, sestavte rozšířený kód textu a vygenerujte obrázek – vše během méně než dvanácti řádků kódu. Následující přímá odpověď shrnuje celý proces:

Načtěte `BarcodeGenerator` s `EncodeTypes.DotCode`, sestavte rozšířený kód textu pomocí `DotCodeExtendedCodetextBuilder` (přidáním FNC1, ECICodetext, prostého textu a oddělovačů FNC3) a poté zavolejte `Save` pro zápis PNG souboru. Tento postup vytvoří plně kompatibilní 2D maticový čárový kód v jediném volání.

## Co je rozšířený kód textu pro dotcode?

**Rozšířený kód textu pro dotcode** je složený řetězec, který kombinuje více datových segmentů – jako jsou identifikátory FNC1, ECICodetext, prostý text a oddělovače FNC3 – do jednoho nákladu, který DotCode dokáže dekódovat. Umožňuje kódování vícejazyčného textu, binárních blobů a strukturovaných dat v jediném 2D maticovém čárovém kódu, což je ideální pro řetězec dodavatelů, zdravotnictví a IoT scénáře.

## Proč použít Aspose.BarCode pro tento úkol?

Aspose.BarCode zpracovává **až 500 stránek za sekundu** na typickém serverovém hardware a podporuje **více než 30 symbologií čárových kódů**, včetně DotCode. Jeho API `GetExtendedCodetext` zaručuje správné umístění řídicích znaků, eliminuje chyby při ručním spojování řetězců a zajišťuje soulad s ISO/IEC 24724. Navíc nabízí vestavěnou korekci chyb a automatické zpracování tiché zóny, čímž snižuje potřebu ručního ladění.

## Požadavky

- **Aspose.BarCode pro .NET** – stáhněte ze [dokumentace Aspose.BarCode pro .NET](https://reference.aspose.com/barcode/net/).  
- Vývojové prostředí .NET (doporučeno Visual Studio 2022 nebo novější).  
- Volitelně: dočasný licenční soubor pro hodnocení.

## Importovat jmenné prostory

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Tyto jmenné prostory zpřístupňují třídu `BarcodeGenerator` a pomocnou třídu `DotCodeExtendedCodetextBuilder` potřebnou pro příklad.

```csharp
using Aspose.BarCode.Generation;
```

Nyní, když máme požadavky pokryté, rozebráme proces generování DotCode Extended Code Text do krok‑za‑krokem průvodce.

## Krok 1: definovat cestu ke složce

Určete, kam bude vygenerovaný PNG uložen. Použijte absolutní nebo relativní cestu, do které může vaše aplikace zapisovat.

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` skutečnou cestou ve vašem systému.

## Krok 2: vytvořit rozšířený kód textu pro dotcode

Třída `DotCodeExtendedCodetextBuilder` sestavuje různé segmenty do jediného rozšířeného řetězce kódu textu.

Pro vytvoření DotCode Extended Code Text postupujte podle následujících podkroků:

### 2.1 přidat identifikátor formátu fnc1

Identifikátor formátu FNC1 označuje začátek nového datového pole. Je vyžadován pro GS1‑kompatibilní DotCode symboly.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 přidat ecicodetext

ECICodetext kóduje speciální znaky a mezinárodní text. V tomto příkladu kódujeme `"犬Right狗"` pomocí UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 přidat prostý kód textu

Můžete také přidat prostý text do DotCode Extended Code Text. Zde přidáváme `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 přidat symbolový oddělovač fnc3

Symbolový oddělovač FNC3 odděluje různé sekce kódu, což zlepšuje čitelnost pro skenery.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 přidat inicializaci čtečky fnc3

Tento krok přidává informaci o inicializaci čtečky FNC3, která říká skeneru, jak interpretovat následující data.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 vygenerovat kód textu

Nyní vygenerujte DotCode Extended Codetext zavoláním metody `GetExtendedCodetext` na objektu `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Krok 3: vygenerovat obrázek dotcode

Vykreslete obrázek čárového kódu z rozšířeného kódu textu.

#### 3.1 inicializovat generátor čárových kódů

Třída `BarcodeGenerator` je jádrem Aspose.BarCode pro vytváření jakéhokoli čárového kódu. Instanciujete ji s požadovanou symbologií (`EncodeTypes.DotCode`) a rozšířeným kódem textu, který jste právě sestavili.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Nakonec zavolejte `Save` pro zápis PNG souboru na disk. Obrázek je připraven k vložení do zpráv, mobilních aplikací nebo tištěných štítků.

## Časté problémy a řešení

- **Nesprávné kódování** – Ujistěte se, že při přidávání vícejazyčného textu používáte `ECIEncodings.UTF8`; jinak se znaky mohou zobrazit poškozené.  
- **Chyby přístupu k souboru** – Ověřte, že aplikace má oprávnění zapisovat do cílové složky.  
- **Chybějící tichá zóna** – Nastavte `gen.Parameters.Barcode.Margin`, pokud skenery vyžadují extra bílý prostor kolem symbolu.

## Často kladené otázky

**Q: Mohu použít vygenerovaný čárový kód v mobilní aplikaci?**  
A: Ano. PNG obrázek vytvořený generátorem lze vložit do iOS, Android nebo jakékoli multiplatformní mobilní aplikace.

**Q: Co když potřebuji kódovat binární data místo textu?**  
A: Použijte metodu `AddECICodetext` s odpovídajícím `ECIEncodings` (např. `ECIEncodings.Base64`) pro vložení binárního nákladu.

**Q: Jak změnit velikost čárového kódu, aniž by to ovlivnilo čitelnost?**  
A: Upravit vlastnost `XDimension.Pixels`; vyšší hodnoty zvětší modul, nižší hodnoty učiní čárový kód kompaktnějším.

**Q: Existuje způsob, jak přidat tichou zónu kolem čárového kódu?**  
A: Ano. Nastavte `gen.Parameters.Barcode.Margin` pro definování požadované tiché zóny v pixelech.

**Q: Podporuje knihovna .NET 8?**  
A: Nejnovější verze Aspose.BarCode jsou kompatibilní s .NET 8; stačí odkazovat na odpovídající verzi NuGet balíčku.

Pokud potřebujete další pomoc nebo máte otázky, neváhejte navštívit [dokumentaci Aspose.BarCode pro .NET](https://reference.aspose.com/barcode/net/) nebo se zapojit do komunity na [fóru podpory Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-09-28  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit DotCode čárový kód .NET (Auto režim) s Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem](/barcode/net/datamatrix-barcode-configuration/)
- [Jak vytvořit Aztec čárový kód s Aspose.BarCode pro .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}