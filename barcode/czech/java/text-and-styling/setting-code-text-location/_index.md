---
date: 2026-05-04
description: Naučte se, jak vytvořit Data Matrix čárový kód pomocí Java knihovny pro
  čárové kódy a nastavit umístění textu čárového kódu nad symbolem s Aspose.BarCode.
  Sledujte náš krok‑za‑krokem příklad generování čárových kódů.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Nastavení umístění textu kódu
second_title: Aspose.BarCode Java API
title: Vytvořte Data Matrix čárový kód pomocí Java knihovny pro čárové kódy a nastavte
  umístění textu kódu
url: /cs/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte Data Matrix čárový kód pomocí Java knihovny pro čárové kódy a nastavte umístění textu kódu

## Úvod

Pokud budujete inventární, přepravní nebo sledovací systém v Javě, rychle zjistíte, že spolehlivá **java barcode library** je nezbytná. S **Aspose.BarCode for Java** můžete v několika řádcích kódu vygenerovat **Data Matrix barcode** a plně ovládat vizuální rozvržení, včetně toho, kde se zobrazí lidsky čitelný text. V tomto tutoriálu projdeme kompletním **barcode generation example**, ukážeme vám, jak **customize barcode text** umístit, a vysvětlíme, proč umístění textu nad symbolem může zlepšit použitelnost.

## Rychlé odpovědi
- **Jaká knihovna je použita?** Aspose.BarCode for Java  
- **Jaký typ čárového kódu je předveden?** Data Matrix  
- **Jak umístíte text kódu?** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **Potřebujete licenci pro produkci?** Yes, a commercial license is required  
- **Může kód běžet na Java 8+?** Absolutely, it supports Java 8 and later  

## Co je Java barcode library?
**Java barcode library** poskytuje vývojářům připravená API pro vytváření, čtení a stylování 1‑D a 2‑D čárových kódů přímo z Java aplikací. Abstrahuje složitá pravidla kódování a umožňuje soustředit se na obchodní logiku místo nízko‑úrovňového zpracování obrazu.

## Proč použít Java barcode library pro příklad generování čárových kódů?
- **Rychlost:** Generate high‑quality barcodes in milliseconds.  
- **Spolehlivost:** Built‑in compliance with ISO/IEC standards.  
- **Flexibilita:** Full control over size, color, margins, and **barcode text** placement.  
- **Cross‑platform:** Works on any JVM‑based environment, from desktop apps to cloud services.

## Co je Data Matrix čárový kód?
Data Matrix čárový kód je dvourozměrný (2‑D) symbol, který ukládá velké množství dat v kompaktním čtvercovém nebo obdélníkovém vzoru. Je široce používán pro označování malých položek, elektroniky a zdravotnických zařízení, protože může kódovat až 2 335 alfanumerických znaků.

## Proč nastavit umístění textu čárového kódu?
Umístění lidsky čitelného textu **nad**, **pod** nebo **vedle** čárového kódu pomáhá uživatelům rychle ověřit zakódovaná data bez skenování. Úprava umístění textu zlepšuje konzistenci UI, splňuje brandingové směrnice a může snížit chyby při ručním zadávání dat.

## Požadavky

- Základní znalost programování v Javě.  
- Nainstalovaný Java Development Kit (JDK).  
- IDE jako Eclipse nebo IntelliJ IDEA.  
- Aspose.BarCode for Java knihovna (stáhněte ji z [zde](https://releases.aspose.com/barcode/java/)).  

## Import balíčků

Nejprve importujte nezbytné třídy Aspose.BarCode do svého projektu:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Tyto importy vám poskytují přístup k generátoru čárových kódů a výčtu, který řídí umístění textu.

## Průvodce krok za krokem

### Krok 1: Definujte cesty adresářů
Určete, kde chcete číst/zapisovat soubory. Nahraďte zástupné symboly skutečnými cestami na vašem počítači.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte instanci BarcodeGenerator
Instancujte `BarcodeGenerator` s typem **Data Matrix** a poskytněte text kódu, který chcete zakódovat.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Krok 3: Nastavte umístění textu čárového kódu (přizpůsobení textu čárového kódu)
Použijte výčet `CodeLocation` k přesunu lidsky čitelného textu. V tomto příkladu jej umístíme **nad** čárový kód.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Tip:** Chcete-li umístit text **pod** symbolem, jednoduše změňte `CodeLocation.ABOVE` na `CodeLocation.BELOW`.

### Krok 4: Uložte vygenerovaný obrázek čárového kódu
Nakonec zapište obrázek čárového kódu na disk. Soubor bude obsahovat Data Matrix symbol s textem umístěným nad ním.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Časté problémy a řešení
- **Text se nezobrazuje:** Ujistěte se, že používáte verzi Aspose.BarCode, která podporuje `CodeLocation`.  
- **Chyby cesty souboru:** Ověřte, že `dataDir` končí oddělovačem souborů (`/` nebo `\\`) vhodným pro váš OS.  
- **Nepodporované znaky:** Data Matrix může kódovat jen omezenou sadu znaků; vyhněte se speciálním symbolům, které nejsou ve standardu ISO/IEC 16022.  

## Často kladené otázky (FAQ)

### Q: Mohu přizpůsobit vzhled vygenerovaného čárového kódu?
A: Yes, Aspose.BarCode provides extensive customization options, allowing you to control colors, margins, and font styles.

### Q: Je Aspose.BarCode kompatibilní s Java 8 a novějšími verzemi?
A: Absolutely, the library works with Java 8 and all subsequent releases.

### Q: Jak mohu integrovat Aspose.BarCode do svého existujícího Java projektu?
A: Add the Aspose.BarCode JAR files to your project’s classpath, import the required packages, and you’re ready to generate barcodes.

### Q: Je k dispozici zkušební verze Aspose.BarCode?
A: Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [zde](https://releases.aspose.com/).

### Q: Kde mohu získat pomoc nebo podporu pro Aspose.BarCode?
A: Visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) for community assistance and official support.

## Další často kladené otázky

**Q: Mohu vygenerovat čárový kód s textem umístěným pod symbolem?**  
A: Yes, set `CodeLocation.BELOW` in the same `setLocation` method.

**Q: Podporuje knihovna i jiné 2‑D čárové kódy jako QR Code?**  
A: Absolutely, simply change `EncodeTypes.DATA_MATRIX` to `EncodeTypes.QR`.

**Q: Jak změním velikost písma textu čárového kódu?**  
A: Use `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Závěr

Nyní jste se naučili, jak **vytvořit Data Matrix čárový kód** v Javě pomocí **java barcode library** a přesně řídit **jak nastavit umístění textu čárového kódu** s Aspose.BarCode. Experimentujte s dalšími hodnotami `CodeLocation`, nastavením písma a možnostmi barev, aby vyhovovaly požadavkům designu vaší aplikace.

---

**Poslední aktualizace:** 2026-05-04  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}