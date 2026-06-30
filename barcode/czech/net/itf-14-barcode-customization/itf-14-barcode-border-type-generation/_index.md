---
date: 2026-02-20
description: Naučte se, jak změnit okraj ITF‑14 čárových kódů pomocí Aspose.BarCode
  pro .NET. Tento průvodce pokrývá generování čárových kódů pomocí C# a poskytuje
  praktické příklady.
linktitle: ITF-14 Barcode Border Type Generation
second_title: Aspose.BarCode .NET API
title: Jak změnit okraj – Generování typu okraje čárového kódu ITF-14
url: /cs/net/itf-14-barcode-customization/itf-14-barcode-border-type-generation/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit okraj – Generování typu okraje čárového kódu ITF-14

V tomto tutoriálu se dozvíte **jak změnit okraj** pro čárové kódy ITF-14 pomocí Aspose.BarCode pro .NET. Ať už budujete systém balení‑etiketování nebo potřebujete splnit konkrétní tiskové standardy, řízení typu okraje je nezbytné. Provedeme vás kompletním, spustitelným příkladem, který ukazuje **generování čárových kódů pomocí C#**, takže můžete generovat ITF-14 čárové kódy přesně tak, jak potřebujete.

## Rychlé odpovědi
- **Co ovlivňuje „typ okraje“?** Určuje, zda je čárový kód vykreslen bez okraje, s jednoduchým pruhem, s vnějším pruhem, s rámečkem nebo s rámečkem a vnějším pruhem.  
- **Která knihovna je použita?** Aspose.BarCode for .NET.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu to spustit na .NET Core?** Ano, API je kompatibilní s .NET Core, .NET 5+ a .NET 6+.  
- **Kolik řádků kódu?** Méně než 20 řádků pro vygenerování všech pěti variant okraje.

## Co znamená „jak změnit okraj“ v kontextu čárových kódů ITF-14?
Změna okraje znamená výběr jedné z možností `ITF14BorderType` (`None`, `Bar`, `BarOut`, `Frame`, `FrameOut`). Každá možnost mění vizuální rámování čárového kódu, což může být důležité pro čitelnost skenerem a estetické požadavky.

## Proč použít Aspose.BarCode pro generování čárových kódů pomocí C#?
Aspose.BarCode nabízí bohatou sadu funkcí přizpůsobení — barvy, velikosti, písma a typy okrajů, které prozkoumáme — a přitom zůstává API jednoduché. To je ideální pro vývojáře, kteří potřebují **generovat ITF-14 čárové kódy** rychle a spolehlivě.

## Požadavky

Před začátkem se ujistěte, že máte:

1. **Aspose.BarCode for .NET** – stáhněte jej z [webu](https://releases.aspose.com/barcode/net/).  
2. Vývojové prostředí .NET (Visual Studio, Rider nebo VS Code).  
3. Základní znalost syntaxe **C#**.  
4. Platná cesta ke složce, kam budou uloženy vygenerované PNG soubory – nahraďte `"Your Directory Path"` v kódu vlastní cestou.

## Importujte jmenné prostory

Nejprve načtěte požadovaný jmenný prostor:

```csharp
using Aspose.BarCode;
```

## Postupný návod

### Krok 1: Vytvořte instanci `BarcodeGenerator` (vygenerujte čárový kód itf-14)

Začneme inicializací generátoru s ITF‑14 symbologií a daty k zakódování:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.ITF14, "12345678901231");
```

### Krok 2: Nastavte X‑Dimension (řídí šířku pruhu)

X‑Dimension určuje šířku každého pruhu čárového kódu. Hodnota 2 pixely funguje dobře pro většinu tiskáren etiket:

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Krok 3: Vygenerujte ITF‑14 čárové kódy s různými typy okrajů

Níže jsou uvedeny pět **příkladů ITF‑14 čárových kódů**, které ukazují **jak změnit okraj**. Každý úryvek používá stejnou instanci `BarcodeGenerator` a pouze mění vlastnost `ItfBorderType`.

#### ITF Border Type: None  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.None;
gen.Save($"{path}ITF14BorderNone.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: Bar  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.Bar;
gen.Save($"{path}ITF14BorderBar.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: BarOut  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.BarOut;
gen.Save($"{path}ITF14BorderBarOut.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: Frame  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.Frame;
gen.Save($"{path}ITF14BorderFrame.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: FrameOut  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.FrameOut;
gen.Save($"{path}ITF14BorderFrameOut.png", BarCodeImageFormat.Png);
```

Každé volání `Save` zapíše PNG obrázek do adresáře, který jste zadali, a poskytne vám vizuální referenci pro každou možnost okraje.

## Časté problémy a tipy

- **Formátování cesty** – Ujistěte se, že proměnná `path` končí zpětným lomítkem (`\`) ve Windows nebo lomítkem (`/`) na Linuxu/macOS.  
- **Výjimka licence** – Pokud spustíte kód bez licence, na vygenerovaných obrázcích se objeví malá vodoznak.  
- **Kompatibilita se skenery** – Některé skenery ignorují vnější okraj; otestujte s vaším hardwarem, abyste zjistili, který typ okraje funguje nejlépe.  
- **Profesionální tip**: Můžete řetězit více změn vlastností (barva, text atd.) před voláním `Save`, abyste vytvořili plně přizpůsobené čárové kódy v jednom kroku.

## Často kladené otázky

### K čemu se používá čárový kód ITF-14?
Čárové kódy ITF-14 se používají především pro balení a označování produktů v maloobchodním průmyslu. Kódují informace jako GTIN (Global Trade Item Number) produktu a jsou běžně umístěny na kartonech a paletách.

### Mohu přizpůsobit vzhled čárových kódů ITF-14 pomocí Aspose.BarCode?
Ano, Aspose.BarCode poskytuje rozsáhlé možnosti přizpůsobení, včetně možnosti změnit typ okraje čárového kódu, barvu a mnoho dalších vizuálních aspektů.

### Je Aspose.BarCode kompatibilní s jinými .NET frameworky?
Ano, Aspose.BarCode pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard, kromě tradičního .NET Framework.

### Kde najdu komplexní dokumentaci k Aspose.BarCode pro .NET?
Kompletní dokumentaci najdete [zde](https://reference.aspose.com/barcode/net/) s podrobnými informacemi a příklady použití Aspose.BarCode.

### Je k dispozici bezplatná zkušební verze Aspose.BarCode?
Ano, bezplatnou zkušební verzi Aspose.BarCode pro .NET můžete získat [zde](https://releases.aspose.com/).

Pokud máte jakékoli otázky nebo narazíte na problémy během implementace, neváhejte kontaktovat komunitu Aspose.BarCode na jejich [fóru podpory](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}