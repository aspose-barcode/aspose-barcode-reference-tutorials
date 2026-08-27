---
date: 2026-03-07
description: Naučte se, jak vytvořit čárový kód EAN‑13 s doplňkovými daty v C# pomocí
  Aspose.BarCode pro .NET – rychle generujte PNG čárového kódu.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Vytvořte čárový kód EAN‑13 s doplňkovými daty – Aspose.BarCode
url: /cs/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu EAN-13 s doplňkovými údaji – Aspose.BarCode pro .NET

V tomto praktickém tutoriálu **vytvoříte čárový kód EAN-13**, který obsahuje doplňkové údaje EAN‑2 nebo EAN‑5, a uvidíte, jak **generovat PNG soubory čárových kódů** pomocí několika řádků C#. Ať už budujete systém pokladny v maloobchodě, logistickou aplikaci nebo jednoduchý nástroj pro inventuru, možnost přidat doplňkové informace činí vaše čárové kódy mnohem užitečnějšími.

## Rychlé odpovědi
- **Co znamená „doplňkové údaje“?** Extra číslice (EAN‑2/EAN‑5) tištěné vedle hlavního čárového kódu, často používané pro cenu nebo čísla vydání.  
- **Jaký typ čárového kódu se používá?** EAN‑13 jako primární symbol, s volitelnými doplňky EAN‑2 nebo EAN‑5.  
- **Mohu výstupně získat PNG obrázky?** Ano – metoda `Save` umožňuje export přímo do PNG.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Je to kompatibilní s .NET Core / .NET 6?** Naprosto – Aspose.BarCode podporuje všechny moderní .NET runtime.

## Požadavky

- Visual Studio (nebo jakékoli IDE kompatibilní s .NET).  
- Kopie Aspose.BarCode pro .NET – stáhněte ji **[zde](https://releases.aspose.com/barcode/net/)**.  
- Základní znalost C#.  
- Zapisovatelná složka, kam budou ukládány generované PNG soubory.

## Importování jmenných prostorů

Nejprve přidejte jmenný prostor Aspose.BarCode, abyste mohli přistupovat ke třídám generátoru:

```csharp
using Aspose.BarCode.Generation;
```

> **Tip:** Pokud používáte .NET Core, přidejte do projektu NuGet balíček `Aspose.BarCode` místo ručního odkazování na DLL.

## Co je doplňkový čárový kód?

Doplňkový čárový kód je pomocný číselný řetězec tištěný vedle hlavního čárového kódu.  
- **EAN‑2** – dvouciferný doplněk, často používaný pro čísla vydání časopisů.  
- **EAN‑5** – pěticiferný doplněk, běžně používaný pro rozšíření ceny u maloobchodních položek.

Přidání těchto doplňků nemění primární data EAN‑13; jen poskytuje další kontext, který skenery mohou přečíst.

## Proč použít Aspose.BarCode pro doplňkové údaje?

- **Jednořádkové API** – nakonfigurujte hlavní čárový kód i jeho doplněk v jednom objektu.  
- **Plná kontrola nad rozměry** – upravte X‑rozměr, rozestup doplňku a formát obrázku.  
- **Cross‑platform** – funguje na .NET Framework, .NET Core a .NET 5/6+.

## Průvodce krok za krokem

### Krok 1: Nastavení výstupního adresáře

Definujte, kam budou ukládány PNG soubory. Nahraďte zástupný text skutečnou cestou na vašem počítači.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Inicializace generátoru čárových kódů (Barcode Generator C#)

Vytvořte instanci `BarcodeGenerator`, přičemž jako hlavní typ specifikujete **EAN‑13** a poskytnete 13‑ciferný payload.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Krok 3: Úprava rozměrů čárového kódu

Doladěte vizuální velikost čárového kódu a prostor vyhrazený pro doplněk.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Krok 4: Přidání doplňku EAN‑2

Nastavte doplňková data na dvoucifernou hodnotu (např. „12“). Tato se zobrazí napravo od hlavního čárového kódu.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Krok 5: Uložení čárového kódu EAN‑2 jako PNG

Exportujte obrázek. Argument `BarCodeImageFormat.Png` zajišťuje vysoce kvalitní PNG soubor.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Krok 6: Přepnutí na doplněk EAN‑5

Změňte `SupplementData` na pěticiferný řetězec pro rozšíření ceny.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Krok 7: Uložení čárového kódu EAN‑5 jako PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Proč to funguje:** Stejná instance `BarcodeGenerator` se znovu používá, takže před každým voláním `Save` stačí upravit vlastnost `SupplementData`. To udržuje kód stručný a zabraňuje zbytečnému vytváření objektů.

## Časté problémy a tipy

- **Neplatná cesta k adresáři** – ujistěte se, že složka existuje a aplikace má oprávnění k zápisu.  
- **Nesprávná délka doplňku** – EAN‑2 vyžaduje přesně 2 číslice, EAN‑5 vyžaduje 5; jinak je vyvolána výjimka.  
- **Obrázek není viditelný** – ověřte, že je použito `BarCodeImageFormat.Png`; jiné formáty (např. JPEG) mohou způsobit kompresní artefakty, které ovlivní čitelnost skenerem.  

## Často kladené otázky

### Mohu použít Aspose.BarCode pro .NET v mém .NET Core projektu?
Ano, Aspose.BarCode pro .NET je plně kompatibilní s .NET Core, .NET 5 a .NET 6.

### Je k dispozici bezplatná zkušební verze pro Aspose.BarCode pro .NET?
Ano, můžete si ji vyzkoušet zdarma na **[této stránce](https://releases.aspose.com/)**.

### Kde mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?
Dočasnou licenci můžete získat na **[této stránce](https://purchase.aspose.com/temporary-license/)**.

### Podporuje Aspose.BarCode širokou škálu typů čárových kódů?
Rozhodně – podporuje EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 a mnoho dalších.

### Mohu přizpůsobit vzhled generovaných čárových kódů?
Ano, můžete měnit barvy, písma, okraje a dokonce přidávat obrázky pozadí pomocí rozsáhlého API `Parameters`.

## Závěr

Nyní víte, jak **vytvořit čárový kód EAN-13** s doplňkovými údaji EAN‑2 nebo EAN‑5 a **generovat PNG soubory čárových kódů** pomocí Aspose.BarCode pro .NET. Tento přístup vám dává plnou kontrolu nad rozměry čárového kódu, rozestupem doplňku a výstupním formátem, což je ideální pro maloobchod, logistiku a jakýkoli scénář, kde jsou potřeba další číselné informace.

Pro podrobnější průzkum si prohlédněte kompletní referenční příručku: **[dokumentace Aspose.BarCode pro .NET](https://reference.aspose.com/barcode/net/)**.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}