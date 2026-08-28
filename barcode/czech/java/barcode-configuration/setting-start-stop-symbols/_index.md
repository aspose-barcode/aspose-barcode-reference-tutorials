---
date: 2026-08-28
description: Naučte se, jak vytvořit obrázek čárového kódu v Javě pomocí Aspose Barcode
  Java, nastavit start a stop symboly CODABAR a generovat PNG soubory bez vodoznaků.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Nastavení start a stop symbolů
og_description: Vytvořte obrázek čárového kódu v Javě pomocí Aspose Barcode Java.
  Tento průvodce ukazuje, jak nastavit start/stop symboly CODABAR a exportovat PNG
  bez vodoznaků.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Vytvořte obrázek čárového kódu v Javě – průvodce start/stop symboly
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Vytvořte obrázek čárového kódu se start/stop symboly
url: /cs/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Vytvoření obrázku čárového kódu se start/stop symboly

## Úvod

V tomto komplexním tutoriálu **vytvoříte obrázek čárového kódu java** soubory s Aspose Barcode Java a naučíte se **jak nastavit start a stop symboly** pro CODABAR čárové kódy. Ať už budujete terminál pro prodejní místo, systém řízení skladu nebo jakoukoli aplikaci, která potřebuje spolehlivé generování čárových kódů, přizpůsobení těchto symbolů vám umožní splnit starší specifikace a zároveň udržet kód čistý a udržovatelný. Provedeme vás každým krokem, vysvětlíme, proč je každé nastavení důležité, a ukážeme vám, jak vytvořit PNG obrázek bez zkušebního vodoznaku.

## Rychlé odpovědi
- **Jaká knihovna vytváří obrázky čárových kódů v Javě?** Aspose.BarCode for Java.  
- **Mohu přizpůsobit start/stop symboly?** Ano, pomocí `setCodabarStartSymbol` a `setCodabarStopSymbol`.  
- **Jaký typ čárového kódu je v tomto příkladu použit?** CODABAR.  
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována pro ne‑zkušební použití.  
- **Jaký výstupní formát je generován?** PNG obrázek uložený na disk.

## Co je Aspose Barcode Java?

Aspose Barcode Java je **knihovna Java bez závislostí, která generuje více než 70 symbologií čárových kódů**, od klasických 1D kódů jako CODABAR po moderní 2D kódy jako QR a DataMatrix. Zajišťuje veškeré nízkoúrovňové kódování, takže se můžete soustředit na obchodní logiku a zároveň garantovat soulad s průmyslovými standardy.

## Proč používat Aspose Barcode Java pro generování čárových kódů bez vodoznaku?

Načtěte nejprve licenci a knihovna vytváří čisté obrázky – žádný překryv „Aspose Evaluation“. Nabízí také **jemnou kontrolu** (start/stop symboly, barvy, velikosti) a **kompatibilitu napříč platformami** (jakýkoli Java runtime, včetně Androidu). S podporou **50+ výstupních formátů** a možností streamovat obrázky přímo do HTTP odpovědí je to ideální volba pro vysokou propustnost a produkční generování čárových kódů.

## Požadavky

Předtím, než se ponoříme, se ujistěte, že máte:

1. **Java Development Kit (JDK)** – Nainstalujte nejnovější JDK z [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Stáhněte jej z [odkaz ke stažení](https://releases.aspose.com/barcode/java/).

Mít tyto komponenty připravené zajišťuje, že můžete **vytvořit obrázek čárového kódu java** bez chybějících součástí.

## Import balíčků

Následující importy vám poskytují přístup k základním třídám potřebným pro generování čárových kódů:

Enum `CodabarSymbol` definuje povolené start/stop znaky pro CODABAR čárové kódy.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Průvodce krok za krokem

### Jak definovat výstupní složku pro obrázek čárového kódu?

Určete složku, kam bude PNG soubor zapsán. Použití `Paths.get` činí kód přenosným napříč Windows, macOS a Linuxem.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Jak vytvořit generátor čárového kódu pro CODABAR?

Třída `BarcodeGenerator` vytváří obrázek čárového kódu pro danou symbologii a data.  

Instancujte `BarcodeGenerator` s CODABAR symbologií a řetězcem dat, který chcete zakódovat.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Jak nastavit startovací symbol CODABAR?

`setCodabarStartSymbol` nastaví znak, který označuje začátek CODABAR čárového kódu.  

Zavolejte `setCodabarStartSymbol` a předávejte jeden z podporovaných znaků (`A`, `B`, `C`, `D`). V tomto příkladu používáme `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Jak nastavit stopovací symbol CODABAR?

`setCodabarStopSymbol` nastaví znak, který označuje konec CODABAR čárového kódu.  

Použijte `setCodabarStopSymbol` s odpovídajícím stop znakem – `D` v tomto případě.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Jak uložit vygenerovaný čárový kód jako PNG soubor?

Enum `SaveFormat` určuje formát souboru pro uložení obrázku čárového kódu.  

Vyvolejte metodu `save`, předáte úplný název souboru a hodnotu `SaveFormat.Png`. Obrázek je zapsán bez vodoznaku po aplikaci platné licence.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Časté úskalí a tipy

Třída `License` načítá soubor licence Aspose a umožňuje plno‑funkční režim.

- **Nesprávná cesta ke složce** – Ujistěte se, že `dataDir` končí správným oddělovačem souborů nebo vytvořte cestu pomocí `Paths.get`.  
- **Nepodporované start/stop znaky** – CODABAR akceptuje pouze `A`, `B`, `C` nebo `D`. Zadání jiné hodnoty vyvolá `IllegalArgumentException`.  
- **Licence není aplikována** – V zkušebním režimu výstup obsahuje vodoznak. Načtěte soubor licence pomocí `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` před vytvořením generátoru, aby se tomu předešlo.  
- **Generování ve velkém měřítku** – Při generování tisíců čárových kódů znovu použijte jedinou instanci `BarcodeGenerator` a měňte pouze text kódu, čímž snížíte režii vytváření objektů.

## Často kladené otázky

### Mohu použít Aspose.BarCode pro Java v komerčním projektu?

Ano. Zakupte komerční licenci [zakoupit komerční licenci](https://purchase.aspose.com/buy) k odstranění evaluačního vodoznaku a získání plné technické podpory.

### Je k dispozici bezplatná zkušební verze?

Samozřejmě. Stáhněte si zkušební verzi [stáhnout zkušební verzi](https://releases.aspose.com/) a vyzkoušejte všechny funkce před zakoupením.

### Jak mohu získat podporu pro Aspose.BarCode pro Java?

Navštivte fórum Aspose.BarCode [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) pro komunitní pomoc nebo otevřete ticket podpory přes váš Aspose účet.

### Jak získat dočasnou licenci pro testování?

Můžete požádat o dočasnou 30‑denní licenci [požádat o dočasnou 30‑denní licenci](https://purchase.aspose.com/temporary-license/). To vám umožní provádět testy podobné produkci bez úplného nákupu.

### Jaké další symbologie čárových kódů Aspose.BarCode podporuje?

Knihovna podporuje **70+ symbologií**, včetně Code128, EAN‑13, QR, DataMatrix, PDF417 a mnoha dalších. Kompletní seznam najdete v oficiální dokumentaci.

## Další otázky a odpovědi (AI‑friendly)

**Q:** Jaké formáty obrázků mohu exportovat kromě PNG?  
**A:** Aspose.BarCode podporuje PNG, JPEG, BMP, GIF a TIFF. Požadovaný formát vyberete změnou hodnoty enumu `SaveFormat` v metodě `save`.

**Q:** Mohu generovat obrázky čárových kódů v paměti bez zápisu na disk?  
**A:** Ano. Zavolejte `generator.save(OutputStream)`, čímž zapíšete přímo do proudu – ideální pro webová API, která vrací obrázek jako HTTP odpověď.

**Q:** Funguje knihovna na Androidu?  
**A:** Verze pro Java běží na Androidu, ale musíte ručně zahrnout požadované závislosti (pro Android není Maven Central). Core API zůstává identické.

## Závěr

Nyní jste se naučili, jak **vytvořit obrázek čárového kódu java** a přesně **nastavit start/stop symboly** pro CODABAR čárový kód pomocí Aspose Barcode Java. Tento přístup vám dává flexibilitu splnit starší specifikace a zároveň udržet kódovou základnu čistou a udržovatelnou. Prozkoumejte další úpravy – například změnu barev, přidání lidsky čitelného textu nebo přechod na jiné symbologie – v oficiální referenci API na [documentation](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-08-28  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose

## Související tutoriály

- [Ověřit kontrolní součet a vytvořit Codabar čárový kód v Javě s Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Vytvořit čárový kód s Aspose – nastavit X a Y rozměry v Javě](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Jak generovat barcode java: Vytvořit přesný obrázek čárového kódu](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}