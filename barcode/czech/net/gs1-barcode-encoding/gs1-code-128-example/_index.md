---
date: 2026-09-08
description: Naučte se, jak vytvořit čárový kód code 128 a generovat čárové kódy GS1
  v C# s Aspose.BarCode pro .NET. Průvodce krok za krokem, předpoklady a úpravy bez
  kódu.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Příklad GS1 Code 128
og_description: Naučte se, jak vytvořit čárový kód code 128 a generovat čárové kódy
  GS1 v C# s Aspose.BarCode pro .NET. Postupujte podle průvodce krok za krokem a rychle
  generujte a ukládejte obrázky čárových kódů.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Jak vytvořit čárový kód code 128 s GS1 pomocí Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Jak vytvořit čárový kód code 128 s GS1 pomocí Aspose.BarCode
url: /cs/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód code 128 s GS1 pomocí Aspose.BarCode

V tomto tutoriálu se naučíte, jak **vytvořit čárový kód code 128**, který splňuje standard GS1 pomocí knihovny Aspose.BarCode pro .NET. Ať už potřebujete čárový kód pro inventář, přepravu nebo pokladnu, tento průvodce vás provede každým krokem – od nastavení vývojového prostředí až po uložení finálního obrázku – takže můžete během několika minut začít generovat spolehlivé čárové kódy.

## Rychlé odpovědi
- **Jaká je hlavní třída pro generování čárového kódu?** `BarcodeGenerator` vytváří a konfiguruje obrázek čárového kódu.  
- **Jakou symbologii používá GS1 Code 128?** Používá typ `EncodeTypes.Code128` s GS1‑specifickým formátováním dat.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Mohu změnit formát obrázku?** Ano – uložte jako PNG, JPEG, BMP nebo TIFF změnou přípony souboru.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ a .NET 6+.

## Co je vytvoření čárového kódu code 128?
`create code 128 barcode` odkazuje na generování lineárního čárového kódu, který kóduje alfanumerická data pomocí symbologie Code 128, která je široce používána v logistice, protože podporuje celý ASCII soubor a může vkládat GS1 identifikátory aplikací. Čárový kód může ukládat identifikátory produktů, sériová čísla a další vlastní data, což jej činí vhodným pro širokou škálu obchodních scénářů.

## Proč použít Aspose.BarCode pro GS1 Code 128?
Aspose.BarCode podporuje **více než 30 symbologií čárových kódů** a dokáže vykreslit obrázky až do **10 000 × 10 000 px** bez ztráty kvality, což je vhodné pro tisk štítků ve vysokém rozlišení. Knihovna také automaticky ověřuje struktury dat GS1, čímž snižuje riziko poškozených čárových kódů ve výrobních linkách. Navíc nabízí rozsáhlé možnosti přizpůsobení velikosti, barvy a rozvržení, což pomáhá splnit přísné průmyslové standardy.

## Požadavky
Před začátkem se ujistěte, že máte následující:

1. **Vývojové prostředí .NET** – Visual Studio 2022, Rider nebo jakékoli IDE, které podporuje .NET 6+.  
2. **Aspose.BarCode pro .NET** – stáhněte jej ze **stránky ke stažení Aspose.BarCode pro .NET** na adrese [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) a přidejte NuGet balíček `Aspose.BarCode` do svého projektu.  
3. **Základní znalost C#** – měli byste být zvyklí vytvářet konzolové nebo Windows aplikace.  
4. **Porozumění GS1 Code 128** – volitelné, ale užitečné; GS1 používá identifikátory aplikací (AI) jako `(01)` pro GTIN a `(21)` pro sériová čísla.

## Jak vytvořit čárový kód code 128 krok za krokem

Načtěte knihovnu, nakonfigurujte typ čárového kódu, nastavte data GS1, přizpůsobte rozměry a nakonec uložte obrázek. Přímá odpověď na otázku „jak vytvořit čárový kód code 128?“ je: **vytvořit instanci `BarcodeGenerator` s `EncodeTypes.Code128` a GS1‑formátovanými daty, upravit `XDimension` podle potřeby a poté zavolat `Save` s požadovaným názvem souboru a formátem**. Následující sekce rozebírají každý krok.

### Krok 1: nastavte cestu k adresáři
Definujte složku, kde bude uložen vygenerovaný obrázek. Udržování cesty konfigurovatelné umožňuje opakované použití kódu v různých prostředích.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Nahraďte `"Your Directory Path"` absolutní nebo relativní cestou, do které může vaše aplikace zapisovat, například `@"C:\Barcodes"` nebo `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Krok 2: vytvořte GS1 Code 128 čárový kód
Vytvořte generátor čárových kódů, specifikujte symbologii a poskytněte GS1‑formátovaná data. Řetězec dat musí obsahovat identifikátory aplikací uzavřené v závorkách.

```csharp
string path = "Your Directory Path";
```

Příklad používá GTIN `(01)12345678901231`, sériové číslo `(21)ASPOSE` a další vlastní AI `(30)9876`. Aspose.BarCode automaticky vloží požadovaný znak FNC1 pro soulad s GS1.

### Krok 3: přizpůsobte parametry čárového kódu
Upravte vizuální parametry, jako je `XDimension` (šířka úzkého pruhu), pro řízení hustoty čárového kódu. Můžete také měnit výšku, barvy a okraje.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Nastavení `XDimension = 2` vytvoří čárový kód, který je snadno čitelný většinou ručních čteček a zároveň udržuje velikost obrázku na rozumné úrovni.

### Krok 4: uložte obrázek čárového kódu
Uložte vygenerovaný čárový kód na disk. Můžete zvolit PNG pro bezztrátovou kvalitu, JPEG pro menší soubory nebo TIFF pro tiskové workflowy. Metoda `Save` zapíše soubor obrázku ve formátu určeném příponou souboru.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Nahraďte `GS1Code128Example.png` libovolným platným názvem souboru a příponou, která odpovídá požadovanému výstupnímu formátu.

### Krok 5: ověřte čárový kód (volitelné)
Po uložení můžete načíst obrázek zpět do aplikace nebo použít čtečku čárových kódů k ověření, že zakódovaná data odpovídají původnímu řetězci. Tento krok je užitečný během vývoje a automatizovaného testování.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Časté problémy a tipy pro odstraňování potíží
- **FNC1 nebyl detekován** – Ujistěte se, že řetězec dat začíná otevírací závorkou a obsahuje platné GS1 AI; knihovna automaticky vloží FNC1 pouze pro rozpoznané vzory.  
- **Obrázek nebyl uložen** – Ověřte, že cílový adresář existuje a aplikace má oprávnění k zápisu. Použijte `Directory.CreateDirectory(path)` pro jeho vytvoření za běhu.  
- **Čárový kód je příliš hustý** – Snižte `XDimension` nebo zvýšte výšku obrázku, aby čtečky měly více prostoru pro čtení úzkých pruhů.  
- **Nepodporované znaky** – Code 128 může kódovat pouze celý ASCII soubor; vyhněte se Unicode znakům mimo tento rozsah.

## Často kladené otázky

**Q: Mohu generovat čárové kódy ve webovém API bez instalace kompletního .NET Framework?**  
A: Ano, Aspose.BarCode funguje s .NET Core a .NET 5/6, takže můžete vystavit lehký REST endpoint, který na požádání vrací obrázky čárových kódů.

**Q: Podporuje knihovna hromadné generování více čárových kódů?**  
A: Rozhodně. Projděte kolekci řetězců dat, vytvořte instanci `BarcodeGenerator` pro každý a zavolejte `Save` uvnitř smyčky. Knihovna je thread‑safe pro paralelní zpracování.

**Q: Existuje způsob, jak vložit čárový kód přímo do PDF?**  
A: Použijte Aspose.PDF k vytvoření PDF dokumentu a poté zavolejte `PdfPage.AddImage` s proudem obrázku čárového kódu. Tím se vyhnete zápisu mezilehlých souborů na disk.

**Q: Jak mohu zajistit, že čárový kód splňuje standardy kvality ISO/GS1?**  
A: Nastavte `BarcodeGenerator.Options.Barcode.XDimension` na alespoň 0,33 mm a povolte `BarHeight` podle velikosti štítku. Aspose.BarCode ověřuje formát AI a při neplatných datech vyvolá výjimku.

**Q: Jaké licenční možnosti jsou k dispozici pro produkční použití?**  
A: Aspose nabízí trvalé, předplatné a cloud‑based licenční modely. Zkušební licence funguje pro hodnocení, ale placená licence odstraňuje vodoznak pro hodnocení a odemkne všechny funkce.

## Další zdroje

- **Dokumentace** – Přístup k úplné referenci API na [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Stáhnout** – Získejte nejnovější verzi knihovny z [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Bezplatná zkušební verze** – Začněte 30‑denní zkušební verzi na [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Zakoupit** – Kupte komerční licenci na [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Podpora** – Připojte se ke komunitnímu fóru na [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) pro pomoc s odstraňováním potíží.

---

**Poslední aktualizace:** 2026-09-08  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit ITF-14 čárový kód .NET – komplexní tutoriály Aspose.BarCode](/barcode/net/)
- [Generovat jednorozměrné Databar 2D čárové kódy pomocí Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}