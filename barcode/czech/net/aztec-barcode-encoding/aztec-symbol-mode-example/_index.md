---
date: 2026-05-24
description: Naučte se, jak vytvořit aztec čárový kód .NET pomocí Aspose.BarCode pro
  .NET, zahrnující režimy symbolů Auto, FullRange, Compact a Rune, s podrobným krok‑za‑krokem
  návodem.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Příklad režimu symbolu Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vytvořte Aztec čárový kód .NET pomocí Aspose.BarCode
url: /cs/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ovládání režimu symbolu Aztec s Aspose.BarCode pro .NET

Pokud chcete **create aztec barcode .net** rychle a spolehlivě, Aspose.BarCode pro .NET vám poskytuje plnohodnotné API, které funguje na .NET Framework, .NET Core a .NET 5/6+. V tomto tutoriálu prozkoumáme čtyři režimy symbolu Aztec — Auto, FullRange, Compact a Rune — a ukážeme vám přesně, jak mezi nimi přepínat a výsledek uložit jako obrázek. Na konci budete schopni vložit Aztec čárové kódy do jakékoli .NET aplikace pomocí několika řádků kódu.

## Rychlé odpovědi
- **Jaká knihovna generuje Aztec čárové kódy v .NET?** Aspose.BarCode for .NET.  
- **Kolik symbolových režimů Aztec podporuje?** Čtyři: Auto, FullRange, Compact, and Rune.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro hodnocení; pro produkční nasazení je vyžadována komerční licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, a .NET 6+.  
- **Mohu výstup generovat jako PNG, JPEG nebo SVG?** Ano—jakýkoli standardní formát obrázku je podporován.

## Co je create aztec barcode .net?
`create aztec barcode .net` odkazuje na proces generování dvourozměrného čárového kódu Aztec pomocí API Aspose.BarCode v .NET prostředí. API automaticky zpracovává kódování, výběr režimu symbolu a vykreslování obrázku, což vývojářům umožňuje vytvářet vysoce kvalitní čárové kódy bez nutnosti zabývat se nízkoúrovňovými detaily, jako jsou výpočty korekce chyb nebo manipulace s pixely.

## Proč používat Aspose.BarCode pro Aztec čárové kódy?
Aspose.BarCode podporuje **30+ symbologií čárových kódů** a dokáže vykreslovat obrázky až do **10 000 × 10 000 px** bez načítání celého souboru do paměti. Zpracuje 500‑stránkový dokument za méně než **2 sekundy** na typickém serveru, což jej činí ideálním pro scénáře s vysokou propustností v podnicích.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

- Znalost vývoje v .NET.  
- Nainstalovaný Visual Studio na vašem počítači.  
- Kopie Aspose.BarCode pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/barcode/net/). Můžete také prozkoumat další produkty Aspose [zde](https://releases.aspose.com/).

Nyní, když máte vše připravené, pojďme se ponořit do příkladů režimu symbolu Aztec.

## Importování jmenných prostorů

Nejprve budete muset importovat potřebné jmenné prostory pro práci s Aspose.BarCode pro .NET. Otevřete svůj projekt ve Visual Studiu a přidejte následující using příkazy na začátek souboru s kódem:

```csharp
using Aspose.BarCode.Generation;
```

S jmennými prostory na místě můžete nyní začít používat Aspose.BarCode pro .NET.

## Jak nastavit generátor čárových kódů pro Aztec kódy?

`BarcodeGenerator` třída je hlavní komponentou, která vytváří obrázky čárových kódů na základě vybrané symbologie a konfiguračních možností. Poskytuje jednoduché API pro určení typu čárového kódu, dat k zakódování a různých parametrů vykreslování před uložením výsledku do souboru obrázku.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

V tomto kroku jsme nastavili generátor a poskytli text kódu pro kódování.

## Jak nastavit režim symbolu Aztec na Auto?

`AztecSymbolMode` výčtová hodnota definuje čtyři možné režimy symbolu pro Aztec čárové kódy a možnost **Auto** umožňuje knihovně automaticky zvolit nejkompaktnější velikost při zachování všech požadavků na data a korekci chyb. Tento režim je ideální pro většinu scénářů, kdy chcete nejmenší možný čárový kód bez ručního ladění.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Tento krok zajišťuje, že režim symbolu Aztec je automaticky určen, a výsledný obrázek čárového kódu je uložen.

## Jak vynutit režim symbolu FullRange?

Když potřebujete maximální kapacitu dat, můžete vybrat hodnotu **FullRange** výčtu `AztecSymbolMode`. Tento režim zakazuje automatické zmenšování velikosti, což umožňuje čárovému kódu uložit celý rozsah znaků a dosáhnout nejvyšší možné informační hustoty, což je užitečné pro velké datové sady.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Tím se vytvoří čárový kód s režimem FullRange Aztec Symbol Mode.

## Jak vygenerovat kompaktní Aztec čárový kód?

Hodnota **Compact** výčtu `AztecSymbolMode` vytváří menší čárový kód snížením počtu vrstev použité v matici. To vede k úspornějšímu obrázku, což jej činí vhodným pro aplikace s omezeným zobrazovacím prostorem, jako jsou mobilní obrazovky nebo malé štítky.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Tento krok konfiguruje čárový kód tak, aby byl generován s kompaktním režimem Aztec Symbol Mode.

## Jak vytvořit Rune Aztec čárový kód?

Režim **Rune** je specializovaná varianta Aztec symbologie, která kóduje číselná data pomocí vlastního znakové sady, nabízí odlišný vizuální styl při zachování stejné síly korekce chyb jako ostatní režimy. Je užitečný, když potřebujete čárový kód, který zdůrazňuje číselné informace.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Tento krok změní text kódu na "123" a vygeneruje čárový kód s režimem Rune Aztec Symbol Mode.

## Časté problémy a řešení

- **Image not saving** – Ujistěte se, že výstupní složka existuje a aplikace má oprávnění k zápisu.  
- **Unexpected symbol size** – Ověřte, že jste někde v kódu nepřepsali `EncodeMode`.  
- **License exception** – Zkušební verze přidává vodoznak; použijte platnou licenci k jeho odstranění.

## Často kladené otázky

**Q: Jaký je účel režimu Aztec Symbol Mode při generování čárových kódů?**  
A: Režim Aztec Symbol Mode určuje, jak knihovna balí data do vrstev, což ovlivňuje velikost, kapacitu a čitelnost.

**Q: Mohu změnit text kódu pro Aztec čárové kódy v Aspose.BarCode pro .NET?**  
A: Ano, stačí přiřadit nový řetězec vlastnosti `CodeText` před voláním `Save`.

**Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.BarCode pro .NET [zde](https://releases.aspose.com/).

**Q: Kde najdu úplnou dokumentaci k Aspose.BarCode pro .NET?**  
A: Kompletní dokumentaci k Aspose.BarCode pro .NET najdete [zde](https://reference.aspose.com/barcode/net/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?**  
A: Dočasnou licenci pro Aspose.BarCode pro .NET můžete získat na [této stránce](https://purchase.aspose.com/temporary-license/).

## Závěr

V tomto tutoriálu jsme prozkoumali, jak **create aztec barcode .net** pomocí Aspose.BarCode, pokrývající režimy Auto, FullRange, Compact a Rune. Nyní máte pevný základ pro vložení univerzálních Aztec čárových kódů do jakékoli .NET aplikace, ať už běží na desktopu, webovém serveru nebo cloudové službě.

Pokud máte jakékoli otázky nebo potřebujete další pomoc, neváhejte se obrátit na komunitu Aspose.BarCode na jejich [support forum](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-05-24  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Kódování textu Aztec pomocí Aspose.BarCode pro .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Kódování bajtů Aztec pomocí generátoru čárových kódů .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Jak vytvořit Aztec čárový kód s korekcí chyb v .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}