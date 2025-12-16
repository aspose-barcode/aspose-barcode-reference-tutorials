---
date: 2025-12-16
description: Naučte se, jak v Javě pomocí Aspose.BarCode vytvořit čárový kód code_128,
  přizpůsobit jeho velikost, nastavit výšku čáry a efektivně vygenerovat obrázek čárového
  kódu.
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: Jak vytvořit čárový kód code_128 a nastavit výšku čáry v Javě
url: /cs/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení výšky čar v Javě

## Úvod

V moderních Java aplikacích často potřebujete **vytvořit čárový kód code_128** tak, aby přesně odpovídal vizuálnímu designu vašich reportů, štítků nebo účtenek. Aspose.BarCode pro Java to usnadňuje – umožňuje **přizpůsobit velikost čárového kódu**, upravit rozměry a vygenerovat obrázek čárového kódu, který Java okamžitě uloží. V tomto tutoriálu si ukážeme, jak nastavit výšku čáry při generování čárového kódu CODE_128, abyste vždy získali perfektně dimenzované čárové kódy.

## Rychlé odpovědi
- **Co dělá hlavní metoda?** Vytvoří čárový kód CODE_128 a umožní nastavit výšku jeho čáry.  
- **Která třída se používá?** `BarcodeGenerator` z knihovny Aspose.BarCode.  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Mohu měnit i jiné rozměry?** Ano, můžete upravit šířku, okraje a další parametry velikosti.  
- **V jakém formátu je výstupní obrázek?** V libovolném formátu podporovaném Aspose.BarCode (např. JPEG, PNG).  

## Co je čárový kód CODE_128 a proč nastavit jeho výšku?
CODE_128 je vysoce hustý lineární čárový kód, který kóduje celý ASCII soubor. Úprava výšky čáry je nezbytná, když musí čárový kód odpovídat fyzickým rozměrům štítku nebo se vejít do UI komponenty. Správná výška zajišťuje čitelnost skenery a zároveň udržuje vizuální rovnováhu rozvržení.

## Proč použít Aspose.BarCode pro Java?
- **Plná kontrola** nad rozměry čárového kódu (výška, šířka, okraje).  
- **Široká podpora formátů** – generujte PNG, JPEG, BMP a další.  
- **Žádné externí závislosti** – čistá Java knihovna, snadno integrovatelná.  
- **Bohaté API** – přizpůsobte barvy, text a korekci chyb bez námahy.

## Předpoklady

Než začnete, ujistěte se, že máte:

- Vývojové prostředí Java (JDK 8 nebo vyšší).  
- Aspose.BarCode pro Java – stáhněte si jej z [odkazu ke stažení](https://releases.aspose.com/barcode/java/).  

## Import balíčků

Ve svém Java projektu importujte hlavní třídu, která poskytuje možnosti generování čárových kódů:

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Jak vytvořit čárový kód code_128 a nastavit jeho výšku

### Krok 1: Inicializace objektu Barcode

Vytvořte instanci `BarcodeGenerator` pro čárový kód CODE_128 s daty, která chcete zakódovat (např. „12345678”).

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Krok 2: Úprava rozměrů čárového kódu – nastavení výšky čáry

Použijte vlastnost `BarHeight` k definování výšky v milimetrech. Toto je hlavní způsob, **jak nastavit výšku čárového kódu**.

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **Tip:** Můžete také upravit `XDimension`, abyste změnili šířku jednotlivých čar, což vám dává plnou kontrolu nad **úpravou rozměrů čárového kódu**.

### Krok 3: Uložení obrázku čárového kódu – generate barcode image java

Nakonec zapíšete čárový kód do souboru. Metoda `save` automaticky určí formát obrázku podle přípony souboru.

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **Poznámka:** Nahraďte `dataDir` skutečnou cestou, kam chcete obrázek uložit.

## Běžné případy použití

- **Tisk štítků** – Zajistěte, aby čárový kód zapadal do předdefinované velikosti štítku.  
- **Generování faktur** – Vložte kompaktní čárový kód, který odpovídá rozvržení vašich PDF faktur.  
- **Mobilní aplikace** – Dynamicky generujte čárové kódy s přesnými rozměry pro skenování na obrazovce.

## Řešení potíží a tipy

| Problém | Řešení |
|---------|--------|
| Čárový kód se zdá příliš tenký nebo příliš tlustý | Upravit `XDimension` pomocí `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)`. |
| Obrázek je rozmazaný | Zvyšte DPI voláním `generator.save(..., BarCodeImageFormat.JPEG, 300)`. |
| Skener kód nečte | Ověřte, že výška čáry splňuje minimální požadavek skeneru (obvykle ≥ 2 mm). |

## Často kladené otázky

**Q: Mohu v Aspose.BarCode pro Java přizpůsobit typ čárového kódu?**  
A: Rozhodně! Knihovna podporuje mnoho symbologií, jako QR, DataMatrix, PDF417 a další – stačí změnit `EncodeTypes` v konstruktoru.

**Q: Je Aspose.BarCode kompatibilní s různými Java IDE?**  
A: Ano, funguje hladce v Eclipse, IntelliJ IDEA, NetBeans i v jakémkoli IDE, které podporuje standardní Java projekty.

**Q: Mohu generovat čárové kódy s číselnými i alfanumerickými hodnotami?**  
A: Ano, CODE_128 dokáže kódovat jak číselná, tak alfanumerická data, což jej činí univerzálním pro většinu aplikací.

**Q: Existuje zkušební verze Aspose.BarCode pro Java?**  
A: Ano, funkce Aspose.BarCode můžete vyzkoušet zdarma prostřednictvím [zkušební verze](https://releases.aspose.com/).

**Q: Kde najdu podporu pro Aspose.BarCode pro Java?**  
A: Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro komunitní podporu a diskuse.

---

**Poslední aktualizace:** 2025-12-16  
**Testováno s:** Aspose.BarCode pro Java 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}