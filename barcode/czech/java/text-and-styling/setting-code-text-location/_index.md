---
date: 2025-12-27
description: Naučte se, jak vytvořit datovou matici čárový kód a jak nastavit umístění
  textu čárového kódu v Javě pomocí Aspose.BarCode. Postupujte podle našeho krok‑za‑krokem
  průvodce pro úplné přizpůsobení.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Vytvořte Data Matrix čárový kód a nastavte umístění textu kódu v Javě
url: /cs/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření Data Matrix čárového kódu a nastavení umístění textu kódu v Javě

## Úvod

Generování čárových kódů je běžnou potřebou pro inventář, přepravu a mnoho dalších aplikací postavených na Javě. S **Aspose.BarCode for Java** můžete **rychle vytvořit Data Matrix čárový kód** a ovládat každý vizuální aspekt, včetně toho, kde se zobrazí lidsky čitelný text. V tomto tutoriálu projdeme přesné kroky k **vytvoření Data Matrix čárového kódu** a ukážeme **jak nastavit text čárového kódu** nad symbolem, aby odpovídal vašim návrhovým specifikacím.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.BarCode for Java  
- **Jaký typ čárového kódu je předveden?** Data Matrix  
- **Jak se pozicuje text kódu?** Pomocí `CodeLocation.ABOVE`  
- **Je potřeba licence pro produkční nasazení?** Ano, je vyžadována komerční licence  
- **Může kód běžet na Java 8+?** Rozhodně, podporuje Java 8 a novější verze  

## Co je Data Matrix čárový kód?
Data Matrix čárový kód je dvourozměrný (2‑D) symbol, který ukládá velké množství dat v kompaktním čtvercovém nebo obdélníkovém vzoru. Je široce používán pro označování malých předmětů, elektroniky a zdravotnických zařízení, protože může kódovat až 2 335 alfanumerických znaků.

## Proč nastavit umístění textu čárového kódu?
Umístění lidsky čitelného textu **nad**, **pod** nebo **vedle** čárového kódu pomáhá uživatelům rychle ověřit zakódovaná data bez skenování. Úprava umístění textu zlepšuje konzistenci uživatelského rozhraní a splňuje brandingové směrnice.

## Předpoklady

- Základní znalost programování v Javě.  
- Nainstalovaný Java Development Kit (JDK).  
- IDE, například Eclipse nebo IntelliJ IDEA.  
- Knihovna Aspose.BarCode for Java (stáhněte ji z [zde](https://releases.aspose.com/barcode/java/)).  

## Import balíčků

Nejprve importujte nezbytné třídy Aspose.BarCode do svého projektu:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Tyto importy vám umožní přístup k generátoru čárových kódů a výčtu, který řídí umístění textu.

## Průvodce krok za krokem

### Krok 1: Definování cest ke složkám
Určete, kde chcete číst/zapisovat soubory. Nahraďte zástupné symboly skutečnými cestami na vašem počítači.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Krok 2: Vytvoření instance BarcodeGenerator
Instancujte `BarcodeGenerator` s typem **Data Matrix** a zadejte text kódu, který chcete zakódovat.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Krok 3: Jak nastavit umístění textu čárového kódu
Použijte výčet `CodeLocation` k přesunu lidsky čitelného textu. V tomto příkladu jej umístíme **nad** čárový kód.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Krok 4: Uložení vygenerovaného obrázku čárového kódu
Nakonec zapište obrázek čárového kódu na disk. Soubor bude obsahovat Data Matrix symbol s textem umístěným nad ním.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Časté problémy a řešení
- **Text se nezobrazuje:** Ujistěte se, že používáte verzi Aspose.BarCode, která podporuje `CodeLocation`.  
- **Chyby v cestě k souboru:** Ověřte, že `dataDir` končí oddělovačem souborů (`/` nebo `\\`) odpovídajícím vašemu OS.  
- **Ne podpořené znaky:** Data Matrix může kódovat jen omezenou sadu znaků; vyhněte se speciálním symbolům, které nejsou ve standardu ISO/IEC 16022.

## Často kladené otázky (FAQ)

### Q: Mohu přizpůsobit vzhled vygenerovaného čárového kódu?
A: Ano, Aspose.BarCode poskytuje rozsáhlé možnosti přizpůsobení, které vám umožní řídit barvy, okraje i styly fontů.

### Q: Je Aspose.BarCode kompatibilní s Java 8 a novějšími verzemi?
A: Rozhodně, knihovna funguje s Java 8 i se všemi následnými vydáními.

### Q: Jak mohu integrovat Aspose.BarCode do svého existujícího Java projektu?
A: Přidejte soubory JAR Aspose.BarCode do classpath projektu, importujte požadované balíčky a můžete začít generovat čárové kódy.

### Q: Existuje k dispozici zkušební verze Aspose.BarCode?
A: Ano, schopnosti Aspose.BarCode můžete vyzkoušet získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Q: Kde mohu získat pomoc nebo podporu pro Aspose.BarCode?
A: Navštivte [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pro komunitní asistenci a oficiální podporu.

## Další často kladené otázky

**Q: Mohu vygenerovat čárový kód s textem umístěným pod symbolem?**  
A: Ano, nastavte `CodeLocation.BELOW` ve stejné metodě `setLocation`.

**Q: Podporuje knihovna i jiné 2‑D čárové kódy, jako QR Code?**  
A: Rozhodně, stačí změnit `EncodeTypes.DATA_MATRIX` na `EncodeTypes.QR`.

**Q: Jak změním velikost písma textu čárového kódu?**  
A: Použijte `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Závěr

Nyní jste se naučili, jak **vytvořit Data Matrix čárový kód** v Javě a přesně ovládat **nastavení umístění textu čárového kódu** pomocí Aspose.BarCode. Experimentujte s dalšími hodnotami `CodeLocation` a možnostmi stylování, aby vyhovovaly požadavkům vašeho designu.

---

**Poslední aktualizace:** 2025-12-27  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}