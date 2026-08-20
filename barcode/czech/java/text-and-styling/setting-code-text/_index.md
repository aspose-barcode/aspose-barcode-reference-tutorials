---
date: 2026-06-09
description: Naučte se, jak vytvořit čárový kód Code128 v Javě pomocí Aspose.BarCode.
  Tento podrobný návod ukazuje, jak v Javě generovat čárový kód, nastavit vlastní
  text, upravit šířku čáry a uložit obrázek.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Nastavení textu kódu
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Vytvoření čárového kódu Code128 v Javě – Nastavení textu kódu pomocí Aspose.BarCode
url: /cs/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu Code128 v Javě – Nastavení textu kódu pomocí Aspose.BarCode

V tomto tutoriálu se naučíte, jak **vytvořit čárový kód Code128 v Javě** pomocí knihovny Aspose.BarCode Java. Ať už budujete inventární systém, řešení pro sledování dokumentů nebo jakoukoli aplikaci, která potřebuje čárové kódy, provedeme vás každým krokem – od vytvoření **Code128** čárového kódu po přizpůsobení textu kódu a jemné doladění šířky čáry. Na konci budete mít připravený obrázek, který můžete vložit kamkoli potřebujete.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.BarCode for Java.  
- **Jaký typ čárového kódu je předveden?** CODE_128.  
- **Jak nastavit vlastní text čárového kódu?** Použijte konstruktor `BarcodeGenerator` nebo metodu `setCodeText`.  
- **Mohu změnit šířku čáry?** Ano – upravte `XDimension` (šířka čáry) v milimetrech.  
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována pro nasazení mimo zkušební verzi.

## Jak vytvořit čárový kód Code128 v Javě?

Načtěte `BarcodeGenerator` s symbologií `CODE_128` a požadovaným textem, nastavte šířku čáry pomocí `XDimension` a poté zavolejte `save` pro zápis souboru obrázku. Tento tříkrokový vzor vytvoří vysoce kvalitní čárový kód během několika sekund a funguje na libovolném runtime Java 8+, Windows, Linux nebo macOS.

## Předpoklady pro generování čárového kódu v Javě

- Základní znalost programování v Javě.  
- Vývojové prostředí Java (JDK 8 nebo novější).  
- Aspose.BarCode for Java knihovna – stáhněte ji **[zde](https://releases.aspose.com/barcode/java/)**.  
- Váš preferovaný IDE (IntelliJ IDEA, Eclipse, atd.).

## Import balíčků

Importujte nezbytné Aspose.BarCode jmenné prostory, aby byly třídy k dispozici ve vašem projektu.

## Co je třída BarcodeGenerator?

`BarcodeGenerator` je jádrová třída Aspose.BarCode, která vytváří obrázky čárových kódů v paměti. Poskytuje plynulé API pro nastavení symbologie, textu kódu, rozměrů, barev a dalších možností vykreslování před exportem výsledku do formátů jako PNG, JPEG, SVG nebo PDF. Můžete také přizpůsobit popisky, okraje a úrovně opravy chyb podle potřeby.

## Tutoriál generátoru čárových kódů: Vytvoření čárového kódu Code128

### Krok 1: Vytvoření instance `BarcodeGenerator`

Konstruktor `BarcodeGenerator` přijímá dva argumenty: symbologii čárového kódu (`CODE_128`) a **vlastní text kódu**, který chcete zakódovat, např. `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Krok 2: Úprava šířky čárového kódu pro vlastní text

Nastavte vlastnost `XDimension` (šířka čáry) pro kontrolu, jak široká každá čára bude. V tomto příkladu používáme `0.5` mm, což je velikost, která vyvažuje čitelnost a prostor na štítku pro většinu aplikací.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Krok 3: Uložení obrázku čárového kódu

Zavolejte metodu `save`, určete výstupní cestu a formát obrázku (JPEG, PNG, SVG atd.). Příklad ukládá soubor jako **`setCodeText.jpg`** do složky dokumentů projektu.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Proč používat Aspose.BarCode pro Java?

Aspose.BarCode pro Java nabízí komplexní sadu funkcí, které zjednodušují generování čárových kódů napříč platformami. Podporuje více než šedesát symbologií, poskytuje výstupy ve vysokém rozlišení raster i vektor a nabízí optimalizace výkonu pro hromadné zpracování, což z něj činí ideální řešení pro podnikovou úroveň a bezproblémovou integraci s existujícími Java projekty.

- **Široká podpora symbologi** – Více než **60** typů čárových kódů, včetně Code128, QR, DataMatrix a PDF417.  
- **Vysoké rozlišení** – Vytváří ostré PNG, JPEG, SVG a PDF obrázky až do šířky **2000 mm** bez ztráty kvality.  
- **Zaměřeno na výkon** – Zpracuje dávku 500 stránek čárových kódů za méně než **2 sekundy** na standardním serverovém hardware.  
- **Cross‑platform** – Plně kompatibilní s Windows, Linux a macOS a funguje s jakýmkoli runtime Java 8+.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Čárový kód vypadá rozmazaně** | Zvyšte rozlišení obrázku nebo exportujte do vektorového formátu (SVG, PDF). |
| **Text je oříznutý** | Zvětšete `XDimension` a `BarHeight`, aby symbologie měla dostatek prostoru. |
| **Licence nebyla použita** | Umístěte `Aspose.BarCode.lic` do kořenové složky projektu a načtěte ji pomocí `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Často kladené otázky

**Q:** *Jaký je rozdíl mezi `CODE_128` a ostatními variantami Code128?*  
**A:** `CODE_128` automaticky vybírá nejefektivnější kódování (A, B nebo C) na základě vstupu, což poskytuje optimální hustotu a rychlost.

**Q:** *Mohu změnit výstupní formát na PNG místo JPEG?*  
**A:** Ano – použijte `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Je možné přidat lidsky čitelný popisek pod čárový kód?*  
**A:** Rozhodně. Nastavte `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` a definujte text popisku pomocí `setText`.

**Q:** *Podporuje Aspose.BarCode Unicode znaky?*  
**A:** Ano. Poskytněte text kódovaný v UTF‑8 a ujistěte se, že vybraná symbologie podporuje danou znakovou sadu.

**Q:** *Jak mohu generovat více čárových kódů ve smyčce?*  
**A:** Vytvořte novou instanci `BarcodeGenerator` uvnitř smyčky, přiřaďte jedinečný text pro každou iteraci a zavolejte `save` s odlišným názvem souboru.

---

**Poslední aktualizace:** 2026-06-09  
**Testováno s:** Aspose.BarCode 24.12 for Java  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvoření datového matice a nastavení umístění textu kódu v Javě](/barcode/java/text-and-styling/setting-code-text-location/)
- [Jak nastavit barvu textu čárového kódu v Javě s Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Generování čárového kódu v Javě – nastavení rozlišení obrázku s Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```