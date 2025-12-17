---
date: 2025-12-17
description: Naučte se generovat čárový kód v Javě pomocí Aspose.BarCode, zahrnující
  dynamické generování čárových kódů, vytváření EAN‑13 čárových kódů a ukládání obrázků
  čárových kódů s doplňkovými daty.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Jak vygenerovat čárový kód s doplňkovými údaji v Javě
url: /cs/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód s doplňkovými údaji v Javě

## Úvod

V dnešním rychle se vyvíjejícím digitálním ekosystému je otázka, jak **generovat čárový kód** efektivně, otázkou, kterou čelí mnoho vývojářů Java. Aspose.BarCode pro Java nabízí výkonné, snadno použitelné API, které podporuje **dynamic barcode generation**, včetně vytváření **EAN‑13 barcodes** s doplňkovými údaji. Ať už vytváříte systémy inventarizace, maloobchodní POS aplikace nebo logistické sledovače, tento tutoriál vás provede **java barcode generator example**, který uloží obrázek čárového kódu na disk a umožní vám přizpůsobit část doplňku.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro generování čárových kódů v Javě?** Aspose.BarCode for Java.
- **Která symbologie vytváří 13‑ciferný číselný čárový kód?** EAN‑13.
- **Mohu přidat doplňkové údaje k EAN‑13 čárovému kódu?** Ano, pomocí API `Supplement`.
- **Jak uložit vygenerovaný čárový kód jako obrázek?** Zavolejte `generator.save("path/filename.jpg")`.
- **Je pro produkční použití vyžadována licence?** Ano, je potřeba komerční licence; je k dispozici bezplatná zkušební verze.

## Co je generování čárových kódů v Javě?

Generování čárových kódů znamená převod dat—číslic, písmen nebo jejich kombinace—na vizuální vzor, který skenery mohou číst. S Aspose.BarCode můžete během běhu vytvářet **high‑resolution barcode images**, což je ideální pro scénáře **dynamic barcode generation**, jako je real‑time ticketing nebo plnění objednávek.

## Proč použít Aspose.BarCode pro dynamické generování čárových kódů?

- **Plná kontrola** nad symbologií, velikostí, barvami a doplňkovými údaji.  
- **Žádné externí závislosti** – čistá Java, funguje na jakékoli platformě.  
- **Vestavěná podpora** pro desítky typů čárových kódů, včetně **create ean13 barcode**.  
- **Jednoduché API**, které vám umožní **save barcode image** jedním řádkem kódu.

## Předpoklady

Předtím, než začnete, ujistěte se, že máte:

- **Java Development Kit (JDK)** – jakákoli recentní verze (8 nebo novější).  
- **IDE** – IntelliJ IDEA, Eclipse nebo váš oblíbený editor.  
- **Aspose.BarCode for Java** – stáhněte knihovnu z oficiálního webu **[here](https://releases.aspose.com/barcode/java/)** a přidejte JAR do classpath vašeho projektu.

## Import balíčků

Jakmile je knihovna odkazována, importujte hlavní třídu, která řídí vytváření čárových kódů.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Postupný průvodce

### Krok 1: Definujte adresář dokumentu

Nastavte složku, kde bude uložen vygenerovaný obrázek.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte instanci Barcode Generator

Instancujte `BarcodeGenerator` s požadovaným **codetext** a **symbology**. Zde **create ean13 barcode** pomocí číselného řetězce "123456789123".

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Krok 3: Nastavte doplňková data

Přidejte 5‑ciferný doplňkový řetězec. To je užitečné pro časopisy, periodika nebo jakýkoli případ, kdy po hlavním čárovém kódu následují další informace.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Krok 4: Nastavte mezeru doplňku

Upravte mezeru mezi hlavním čárovým kódem a jeho doplňkem. Hodnota je vyjádřena v bodech.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Krok 5: Uložte obrázek čárového kódu

Nakonec zapište obrázek na disk. Formát je odvozen z přípony souboru (v tomto příkladu JPEG).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Tip:** Můžete změnit příponu souboru na `.png` nebo `.bmp`, abyste získali jiný formát obrázku bez dalšího kódu.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **Image not saved** | `dataDir` ukazuje na neexistující složku | Ujistěte se, že adresář existuje nebo jej vytvořte programově (`new File(dataDir).mkdirs();`). |
| **Invalid supplement length** | Doplňky EAN‑13 musí mít 2 nebo 5 číslic | Zadejte přesně 2 nebo 5 znaků; jinak je vyvolána výjimka. |
| **Unsupported characters** | V codetextu EAN‑13 jsou nečíselné znaky | Používejte pouze číslice 0‑9 pro EAN‑13; pro alfanumerické použij jinou symbologii. |

## Často kladené otázky

### Je Aspose.BarCode kompatibilní se všemi verzemi Javy?

Aspose.BarCode pro Java je navržen tak, aby byl kompatibilní s širokou škálou verzí Javy. Podívejte se na **[documentation](https://reference.aspose.com/barcode/java/)** pro konkrétní podrobnosti.

### Mohu přizpůsobit vzhled vygenerovaných čárových kódů?

Ano, Aspose.BarCode poskytuje různé parametry a nastavení pro přizpůsobení vzhledu čárových kódů. Prozkoumejte dokumentaci pro podrobné informace.

### Je k dispozici zkušební verze?

Ano, můžete získat bezplatnou zkušební verzi **[here](https://releases.aspose.com/)**.

### Jak mohu získat podporu pro Aspose.BarCode?

Navštivte **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** a získejte pomoc od komunity a odborníků.

### Kde mohu zakoupit Aspose.BarCode pro Java?

Aspose.BarCode pro Java můžete zakoupit **[here](https://purchase.aspose.com/buy)**.

**Poslední aktualizace:** 2025-12-17  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}