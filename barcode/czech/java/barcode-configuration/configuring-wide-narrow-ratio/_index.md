---
date: 2026-08-12
description: Zjistěte, jak zlepšit čitelnost čárových kódů úpravou poměru široko‑úzký
  CODE_128 v jazyce Java pomocí Aspose.BarCode a efektivně generovat PNG obrázky.
  Postupujte podle našeho krok‑za‑krokem tutoriálu generování čárových kódů v Javě.
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Konfigurace poměru široko‑úzký
og_description: Zjistěte, jak zlepšit čitelnost čárových kódů úpravou poměru široko‑úzký
  CODE_128 v Javě s Aspose.BarCode. Tento krok‑za‑krokem tutoriál vám ukáže, jak rychle
  generovat PNG čárové kódy.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Zlepšete čitelnost čárových kódů pomocí poměru široko‑úzký CODE_128 (58
  znaků)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Zlepšete čitelnost čárových kódů pomocí poměru široko‑úzký CODE_128
url: /cs/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zlepšení čitelnosti čárových kódů pomocí poměru široko‑úzký CODE_128

## Úvod

Pokud potřebujete **zlepšit čitelnost čárových kódů** pro inventární štítky, přepravní etikety nebo jakoukoli aplikaci používající CODE_128, úprava poměru široko‑úzký je nejúčinnější technikou. V tomto tutoriálu vás provedeme **krok‑za‑krokem procesem tvorby čárového kódu** pomocí Aspose.BarCode pro Java, ukážeme vám, jak nastavit poměr, **vytvořit PNG obrázky čárových kódů** a **uložit obrázek čárového kódu** na disk. Také uvidíte, proč je poměr důležitý pro výkon skeneru a jak jej jemně doladit pro vaše konkrétní tiskové prostředí.

## Rychlé odpovědi
- **Co je poměr široko‑úzký?** Řídí relativní šířku širokých pruhů oproti úzkým pruhům v čárovém kódu.  
- **Která symbologie podporuje úpravu poměru?** Většina 1‑D symbologií, včetně CODE_128, umožňuje nastavit vlastní poměr.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze, ale pro produkční použití je vyžadována komerční licence.  
- **Mohu vygenerovat obrázek čárového kódu ve formátu PNG?** Ano — použijte `generator.save(...)` k vytvoření PNG obrázků čárových kódů.  
- **Je kód kompatibilní s Java 8+?** Naprosto; Aspose.BarCode funguje se všemi moderními verzemi Javy.

## Požadavky

Než se ponoříme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný ve vašem počítači.  
- Knihovnu Aspose.BarCode pro Java. Stáhněte ji z [download link](https://releases.aspose.com/barcode/java/).

## Import balíčků

Na začátek importujte nezbytnou třídu Aspose.BarCode do svého projektu.  
`BarcodeGenerator` je hlavní třída používaná k vytváření obrázků čárových kódů se zadanou symbologií a možnostmi.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Co je poměr široko‑úzký a proč jej upravovat?

Poměr široko‑úzký určuje, kolikrát je „široký“ pruh širší než „úzký“ pruh. Úprava tohoto poměru zlepšuje kompatibilitu se skenery (většina scannerů čte nejlépe při poměrech mezi 2,0 a 3,0), kompenzuje omezení DPI tiskárny a umožňuje sladit vizuální styl značky, aniž by se snížila spolehlivost.

## Jak zlepšit čitelnost čárových kódů vytvořením CODE_128 čárového kódu s poměrem široko‑úzký v Javě

Začněte přidáním knihovny Aspose.BarCode do svého Java projektu, poté vytvořte instanci `BarcodeGenerator` s určením `EncodeTypes.CODE_128`. Nakonfigurujte generátor s požadovaným poměrem široko‑úzký pomocí `setWideNarrowRatio`, případně upravte další vizuální nastavení, a nakonec zavolejte `save` k zápisu čárového kódu jako PNG souboru. Tento stručný postup zajišťuje konzistentní kvalitu čárových kódů a zlepšuje míru čtení scannerů napříč různými zařízeními.

### Krok 1: nastavit adresář dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ujistěte se, že adresář existuje a máte oprávnění k zápisu; zde bude umístěn soubor **uloženého obrázku čárového kódu**.

### Krok 2: vytvořit objekt čárového kódu

Třída `BarcodeGenerator` vytváří obrázky čárových kódů na základě zadané symbologie a možností kódování.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Zde **vytváříme CODE_128 čárový kód** předáním `EncodeTypes.CODE_128` do konstruktoru.

### Krok 3: nastavit poměr široko‑úzký

`setWideNarrowRatio` nastavuje poměr mezi širokými a úzkými pruhy pro generovaný čárový kód.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metoda `setWideNarrowRatio` vám umožní jemně doladit vizuální rozestupy. Hodnota `3.0f` znamená, že široký pruh je třikrát širší než úzký pruh, což spadá do optimálního rozmezí 2,0‑3,0 pro většinu scannerů.

### Krok 4: uložit obrázek na disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Volání `save` **vygeneruje obrázek čárového kódu** a uloží jej jako PNG soubor, čímž dokončí krok **uložit obrázek čárového kódu**.

## Proč upravovat poměr široko‑úzký?

Úprava poměru široko‑úzký zlepšuje kompatibilitu se skenery, protože většina průmyslových scannerů čte nejlépe, když je poměr mezi 2,0 a 3,0. Také zvyšuje kvalitu tisku kompenzací rozlišení tiskárny 150–300 dpi, snižuje zkreslení pruhů. Navíc poměr umožňuje firmám sladit estetiku čárových kódů s brandingovými směrnicemi při zachování spolehlivého výkonu skenování.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Čárový kód vypadá deformovaně | Poměr je pro tiskárnu příliš vysoký/nízký | Upravte hodnotu předávanou do `setWideNarrowRatio` (např. 2.0‑2.5). |
| Soubor nebyl vytvořen | Neplatná cesta `dataDir` nebo nedostatečná oprávnění | Ověřte cestu k adresáři a zajistěte, aby aplikace měla právo zápisu. |
| Scanner nemůže číst čárový kód | Poměr mimo doporučené rozmezí pro symbologii | Použijte standardní poměry (2.0‑3.0) nebo otestujte s cílovým scannerem. |

## Často kladené otázky

**Q: Mohu použít Aspose.BarCode s jinými Java frameworky?**  
A: Ano, Aspose.BarCode funguje bez problémů se Spring, Java EE, Android a dalšími Java prostředími.

**Q: Jak mohu generovat čárové kódy s různými symbologiemi?**  
A: Změňte typ symbologie v konstruktoru `BarcodeGenerator`, například `EncodeTypes.QR` pro QR kódy.

**Q: Je k dispozici zkušební verze pro Aspose.BarCode?**  
A: Ano, můžete získat bezplatnou zkušební verzi na [Aspose.BarCode free trial page](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci pro Aspose.BarCode?**  
A: Odkazujte se na dokumentaci na [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).

**Q: Jak získat podporu pro Aspose.BarCode?**  
A: Navštivte komunitní fórum Aspose.BarCode na [Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13) pro podporu a diskuse komunity.

---

**Poslední aktualizace:** 2026-08-12  
**Testováno s:** Aspose.BarCode for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Generovat čárový kód v Javě – Nastavit rozlišení obrázku s Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Detekovat orientaci čárového kódu v Javě s Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Jak vytvořit obrázky code128 čárových kódů v Javě s Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}