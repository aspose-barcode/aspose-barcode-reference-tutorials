---
date: 2026-01-02
description: Naučte se, jak používat generátor čárových kódů Aztec s Aspose.BarCode
  pro .NET – krok za krokem průvodce nastavením režimu symbolu Aztec (Auto, FullRange,
  Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: generátor čárových kódů Aztec – Ovládání režimu symbolu Aztec s Aspose.BarCode
  pro .NET
url: /cs/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# generátor čárových kódů aztec – Ovládání režimu Aztec Symbol s Aspose.BarCode pro .NET

Pokud chcete do svých .NET aplikací začlenit výkonné možnosti generování čárových kódů, **barcode generator aztec** od Aspose.BarCode pro .NET je fantastické řešení. V tomto tutoriálu se podrobně ponoříme do režimu Aztec Symbol, ukážeme **jak nastavit aztec** možnosti a provedeme vás praktickými ukázkami kódu, které můžete přímo vložit do svého projektu.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `BarcodeGenerator` z `Aspose.BarCode.Generation`.
- **Které Symbolové režimy jsou k dispozici?** Auto, FullRange, Compact a Rune.
- **Potřebuji licenci?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.
- **Mohu změnit text kódu?** Ano, nastavte `gen.CodeText` před uložením.
- **Jaké formáty obrázků jsou podporovány?** PNG, JPEG, BMP, GIF, TIFF a další.

## Co je generátor čárových kódů aztec?
Generátor čárových kódů aztec vytváří dvourozměrné Aztec kódy, kompaktní maticový čárový kód, který může uložit velké množství dat v malém prostoru. Je ideální pro mobilní vstupenky, URL adresy a binární data, kde je prostor omezený.

## Proč používat Aspose.BarCode pro .NET?
- **Plná podpora .NET** – funguje s .NET Framework, .NET Core a .NET 5/6.
- **Bohatá sada funkcí** – více symbolových režimů, korekce chyb a rozsáhlé přizpůsobení.
- **Žádné externí závislosti** – generujte čárové kódy kompletně v‑procesu.
- **Cross‑platform** – běží na Windows, Linuxu a macOS.

## Předpoklady

- Znalost vývoje v .NET.  
- Nainstalovaný Visual Studio na vašem počítači.  
- Kopie Aspose.BarCode pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/barcode/net/).

Nyní, když jste připraveni, pojďme prozkoumat možnosti režimu Aztec Symbol.

## Jak nastavit režim Aztec Symbol s generátorem čárových kódů aztec

### Importování jmenných prostorů

Nejprve přidejte požadovaný jmenný prostor na začátek vašeho souboru C#:

```csharp
using Aspose.BarCode.Generation;
```

Po importu jmenného prostoru můžete začít vytvářet Aztec čárové kódy.

### Krok 1: Nastavení generátoru čárových kódů

Inicializujte generátor s typem kódování Aztec a poskytněte text, který chcete zakódovat:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Tip:** Použijte řetězec kompatibilní s UTF‑8 pro mezinárodní znaky, jak je ukázáno výše.

### Krok 2: Nastavení Symbolového režimu na Auto

Režim **Auto** umožňuje knihovně rozhodnout o optimální velikosti na základě délky dat:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Vygenerovaný PNG bude uložen do složky, kterou jste určili.

### Krok 3: Nastavení Symbolového režimu na FullRange

Pokud chcete, aby knihovna použila celý rozsah velikostí Aztec symbolů, zvolte **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Krok 4: Nastavení Symbolového režimu na Compact

Pro kompaktnější čárový kód, který si stále zachovává dobrou čitelnost, použijte **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Krok 5: Nastavení Symbolového režimu na Rune

Režim **Rune** je určen pro speciální případy, kde je vyžadován odlišný vizuální styl:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| Obrázek čárového kódu je prázdný | Ověřte, že `path` ukazuje na existující zapisovatelný adresář. |
| Nepodporované znaky | Používejte pouze znaky podporované standardem Aztec nebo přepněte na kódování UTF‑8. |
| Nesprávná velikost symbolu | Experimentujte s `AztecSymbolMode.Auto`, aby knihovna vybrala nejlepší velikost. |

## Často kladené otázky

**Q: Jaký je účel režimu Aztec Symbol při generování čárových kódů?**  
A: Umožňuje vám řídit vizuální hustotu a úroveň korekce chyb Aztec kódu, přizpůsobit čárový kód vašim požadavkům na prostor a čitelnost.

**Q: Mohu změnit text kódu pro Aztec čárové kódy v Aspose.BarCode pro .NET?**  
A: Ano, jednoduše přiřaďte nový řetězec do `gen.CodeText` před voláním `Save`.

**Q: Existuje bezplatná zkušební verze Aspose.BarCode pro .NET?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Kde najdu úplnou dokumentaci pro Aspose.BarCode pro .NET?**  
A: Kompletní reference API je k dispozici [zde](https://reference.aspose.com/barcode/net/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?**  
A: Dočasnou licenci lze požádat prostřednictvím [tohoto odkazu](https://purchase.aspose.com/temporary-license/).

## Závěr

V tomto průvodci jsme pokryli vše, co potřebujete vědět k použití **barcode generator aztec** s Aspose.BarCode pro .NET, od nastavení generátoru po ovládání jednotlivých Symbolových režimů (Auto, FullRange, Compact, Rune). S těmito příklady můžete nyní rychle a spolehlivě vložit univerzální Aztec čárové kódy do jakékoli .NET aplikace.

Pokud máte další otázky, neváhejte se připojit ke komunitě Aspose.BarCode na jejich [fórumu podpory](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-02  
**Testováno s:** Aspose.BarCode 24.10 pro .NET  
**Autor:** Aspose