---
date: 2026-02-17
description: Naučte se, jak používat Aspose Barcode Java k vytváření obrázků čárových
  kódů, nastavení startovacích a koncových symbolů CODABAR a generování PNG souborů
  bez vodoznaků.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – Vytvořit obrázek čárového kódu se start/stop symboly
url: /cs/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Vytvoření obrázku čárového kódu se start/stop symboly

## Úvod

V tomto komplexním tutoriálu **vytvoříte soubory barcode image java** pomocí **Aspose Barcode Java** a naučíte se **jak nastavit symboly** pro čárové kódy Codabar. Ať už budujete pokladní systém, logistickou aplikaci nebo jakékoli řešení, které potřebuje spolehlivé generování čárových kódů, přizpůsobení start a stop symbolů vám dává plnou kontrolu nad formátem kódu. Provedeme vás každým krokem, vysvětlíme, proč je každé nastavení důležité, a ukážeme vám, jak vytvořit připravený PNG obrázek – bez zkušebního vodoznaku.

## Rychlé odpovědi
- **Jaká knihovna vytváří obrázky čárových kódů v Javě?** Aspose.BarCode for Java.  
- **Mohu přizpůsobit start/stop symboly?** Ano, pomocí `setCodabarStartSymbol` a `setCodabarStopSymbol`.  
- **Jaký typ čárového kódu se v tomto příkladu používá?** CODABAR.  
- **Potřebuji licenci pro produkci?** Pro ne‑zkušební použití je vyžadována komerční licence.  
- **Jaký výstupní formát je generován?** PNG obrázek uložený na disk.

## Co je Aspose Barcode Java?

Aspose Barcode Java je výkonná knihovna bez závislostí, která vám umožní programově generovat širokou škálu symbologií čárových kódů. Abstrahuje nízkoúrovňovou logiku kódování, takže se můžete soustředit na obchodní pravidla a zároveň zajistit, že výstup splňuje průmyslové standardy.

## Proč použít Aspose Barcode Java pro generování čárových kódů bez vodoznaku?

- **Žádný vodoznak v produkci** – po aplikaci platné licence jsou obrázky čisté.  
- **Rozsáhlá podpora symbologií** – od klasických 1D kódů jako CODABAR po 2D kódy jako QR a DataMatrix.  
- **Detailní kontrola** – můžete nastavit start/stop symboly, barvy, velikosti a dokonce generovat obrázky přímo do streamů pro webové aplikace.  
- **Cross‑platform** – funguje na jakémkoli Java runtime, včetně Androidu (s ruční správou závislostí).

## Požadavky

Předtím, než začneme, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – Nainstalujte nejnovější JDK z [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java knihovna** – Stáhněte ji z [download link](https://releases.aspose.com/barcode/java/).

Mít tyto připravené zajišťuje, že můžete **generovat obrázek čárového kódu v Javě** bez chybějících komponent.

## Import balíčků

Ve svém Java projektu importujte potřebné třídy pro práci s Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Průvodce krok za krokem

### Krok 1: Definujte adresář dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou, kam chcete uložit obrázek čárového kódu. Nezapomeňte ukončit cestu vhodným oddělovačem souborů (`/` nebo `\`) nebo použijte `Paths.get` pro platformově nezávislé zpracování.

### Krok 2: Vytvořte instanci Barcode Generator

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Zde říkáme Aspose.BarCode, aby použil symbologii **CODABAR** a datový řetězec `"12345678"`.

### Krok 3: Nastavte start symbol pro Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

Metoda `setCodabarStartSymbol` vám umožňuje **nastavit symboly čárového kódu** pro úvodní znak. V tomto případě volíme `A`.

### Krok 4: Nastavte stop symbol pro Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

Podobně `setCodabarStopSymbol` definuje koncový znak. Použití `D` dokončuje formát CODABAR požadovaný mnoha staršími systémy.

### Krok 5: Uložte vygenerovaný obrázek

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

Volání `save` zapíše čárový kód do PNG souboru pojmenovaného **startAndStopSymbols.png** v adresáři, který jste uvedli dříve.

## Časté problémy a tipy

- **Nesprávná cesta ke složce** – ujistěte se, že `dataDir` končí souborovým oddělovačem (`/` nebo `\`) nebo spojte pomocí `Paths.get`.  
- **Není podporován start/stop symbol** – CODABAR podporuje pouze `A`, `B`, `C`, `D` jako start/stop symboly. Použití jiné hodnoty vyvolá výjimku.  
- **Licence nebyla použita** – v režimu zkušební verze může generovaný obrázek obsahovat vodoznak. Použijte licenci před nasazením do produkce, abyste dosáhli **generování čárových kódů bez vodoznaku**.

## Často kladené otázky

### Mohu použít Aspose.BarCode pro Java v komerčním projektu?
Ano, můžete. Pro komerční využití zvažte zakoupení licence [zde](https://purchase.aspose.com/buy).

### Je k dispozici bezplatná zkušební verze?
Ano, můžete si vyzkoušet bezplatnou verzi [zde](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.BarCode pro Java?
Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro jakoukoli podporu nebo dotazy.

### Jak získám dočasnou licenci?
V případě potřeby můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Existují další symbologie čárových kódů podporované Aspose.BarCode pro Java?
Ano, Aspose.BarCode podporuje širokou škálu symbologií čárových kódů. Podívejte se do dokumentace pro kompletní seznam.

## Další Q&A (AI‑Friendly)

**Q:** Jaké formáty obrázků mohu exportovat kromě PNG?  
**A:** Aspose.BarCode podporuje PNG, JPEG, BMP, GIF a TIFF. Použijte vhodnou příponu souboru v metodě `save`.

**Q:** Mohu generovat obrázky čárových kódů v paměti bez zápisu na disk?  
**A:** Ano, zavolejte `generator.save(OutputStream)`, čímž zapíšete přímo do streamu – ideální pro webové odpovědi.

**Q:** Funguje knihovna na Androidu?  
**A:** Java verze je kompatibilní s Androidem, ale musíte ručně zahrnout požadované závislosti.

## Závěr

Nyní jste se naučili, jak **vytvořit soubory barcode image java** a přesně **nastavit symboly čárového kódu** pro Codabar pomocí **Aspose Barcode Java**. Tato technika vám poskytuje flexibilitu pro splnění specifických průmyslových požadavků na čárové kódy a zároveň udržuje váš kód čistý a udržovatelný. Prozkoumejte další možnosti přizpůsobení – například změnu barev, přidání lidsky čitelného textu nebo přepnutí na jiné symbologie – v oficiální API dokumentaci na [documentation](https://reference.aspose.com/barcode/java/).

---

**Poslední aktualizace:** 2026-02-17  
**Testováno s:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}