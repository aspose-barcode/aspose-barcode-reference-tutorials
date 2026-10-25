---
date: 2026-10-25
description: Naučte se, jak generovat čárový kód a přidat jej do PDF v Javě pomocí
  Aspose.BarCode. Tento podrobný návod pokrývá generování čárových kódů, nastavení
  velikosti a detekci orientace.
keywords:
- how to generate barcode
- barcode generator tutorial java
- barcode reader tutorial java
- read barcode pdf java
- add barcode existing pdf
lastmod: 2026-10-25
linktitle: Základy čárových kódů
og_description: Naučte se, jak generovat čárový kód a přidat jej do PDF v Javě pomocí
  Aspose.BarCode. Tento podrobný návod pokrývá generování čárových kódů, nastavení
  velikosti a detekci orientace.
og_image_alt: Tutorial showing how to generate barcode and embed it in a PDF using
  Aspose.BarCode for Java
og_title: Jak generovat čárový kód a přidat jej do PDF v Javě
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to generate barcode and add it to PDF in Java using Aspose.BarCode.
    This step‑by‑step guide covers barcode generation, sizing, and orientation detection.
  headline: How to generate barcode and add it to PDF in Java
  type: TechArticle
- description: Learn how to generate barcode and add it to PDF in Java using Aspose.BarCode.
    This step‑by‑step guide covers barcode generation, sizing, and orientation detection.
  name: How to generate barcode and add it to PDF in Java
  steps:
  - name: '**Generate the barcode image** – use `BarcodeGenerator` to create a bitmap
      in memory.'
    text: '**Generate the barcode image** – use `BarcodeGenerator` to create a bitmap
      in memory.'
  - name: '**Create or open a PDF document** – Aspose.PDF lets you work with existing
      PDFs or start from scratch.'
    text: '**Create or open a PDF document** – Aspose.PDF lets you work with existing
      PDFs or start from scratch.'
  - name: '**Place the barcode image on a page** – add the image to a `PdfPage` at
      the desired coordinates and size.'
    text: '**Place the barcode image on a page** – add the image to a `PdfPage` at
      the desired coordinates and size.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library lets me add barcode to PDF in Java?
  - answer: Yes, a commercial license is required; a free trial is available.
    question: Do I need a license for production use?
  - answer: Absolutely – use the `BarcodeGenerator` class to create PNG, JPEG, or
      BMP files.
    question: Can I generate a barcode image without a PDF?
  - answer: Yes, the `BarCodeReader` can automatically detect rotation.
    question: Is barcode orientation detection supported?
  - answer: Java 8 and higher (including Java 11, 17, and later).
    question: Which Java versions are supported?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- generate barcode
- Aspose.Barcode
- Java barcode integration
- PDF barcode
- barcode generation tutorial
title: Jak generovat čárový kód a přidat jej do PDF v Javě
url: /cs/java/barcode-basics/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód a přidat jej do PDF v Javě

## Úvod

Pokud potřebujete **přidat čárový kód do PDF** souborů z Java aplikace, jste na správném místě. **Aspose.BarCode for Java** dělá proces rychlý, spolehlivý a plně přizpůsobitelný. V této sérii projdeme vše od generování obrázku čárového kódu v Javě po jeho vložení do PDF, úpravu jeho velikosti a dokonce i detekci jeho orientace za běhu. Na konci budete schopni vytvořit profesionální čárové kódy, které se bez problémů integrují s vašimi stávajícími Java projekty.

## Rychlé odpovědi
- **Jaká knihovna mi umožní přidat čárový kód do PDF v Javě?** Aspose.BarCode for Java.  
- **Potřebuji licenci pro produkční použití?** Ano, je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Mohu vygenerovat obrázek čárového kódu bez PDF?** Rozhodně – použijte třídu `BarcodeGenerator` k vytvoření souborů PNG, JPEG nebo BMP.  
- **Je podporována detekce orientace čárového kódu?** Ano, `BarCodeReader` může automaticky detekovat otočení.  
- **Které verze Javy jsou podporovány?** Java 8 a vyšší (včetně Java 11, 17 a novějších).

## Co je Aspose Barcode Java?

Aspose Barcode Java je čistě Java knihovna, která vám umožní generovat a číst čárové kódy více než 60 symbologií. Funguje bez externích závislostí, což umožňuje snadnou integraci do webových služeb, desktopových aplikací nebo dávkových zpracovatelských pipeline a podporuje vysoké rozlišení renderování pro obrazovku i tisk.

## Proč používat Aspose Barcode Java?

Aspose Barcode Java poskytuje vývojářům úplnou kontrolu nad tvorbou a rozpoznáváním čárových kódů, přičemž nabízí vysoký výkon bez nativních knihoven. Podporuje širokou škálu symbologií, přizpůsobitelné vzhledy a spolehlivou detekci orientace, což z ní činí ideální řešení pro velké dávkové úlohy a aplikace v reálném čase.

- **Plná kontrola** nad symbologií, velikostí, okraji a barvou.  
- **Žádné externí závislosti** – čistá Java, žádné nativní DLL.  
- **Vysoce výkonné renderování** schopné zpracovat až 10 000 čárových kódů za sekundu na typickém serveru.  
- **Robustní čtecí engine** s vestavěnou detekcí orientace a korekcí chyb pro 99,9 % přesnost čtení při standardních skenováních.  
- **Komplexní API** pokrývající jak generování (`BarcodeGenerator`), tak čtení (`BarCodeReader`).

## Požadavky
- Java 8 nebo novější nainstalována.  
- Knihovna Aspose.BarCode for Java (ke stažení z webu Aspose).  
- (Volitelné) Aspose.PDF for Java, pokud plánujete pracovat přímo s PDF soubory.  

## Jak přidat čárový kód do PDF v Javě

Načtěte svůj PDF, vygenerujte obrázek čárového kódu v paměti a umístěte obrázek na stránku – to je kompletní řešení ve třech řádcích kódu. **`BarcodeGenerator` vytváří obrázky čárových kódů z poskytnutých dat.** Nejprve vytvořte instanci `BarcodeGenerator`, poté zapište obrázek do `ByteArrayOutputStream` a nakonec použijte metodu `PdfPage.addImage` z Aspose.PDF k vložení proudu na zvolené souřadnice.

Třída `BarcodeGenerator` vytváří obrázky čárových kódů v paměti, zatímco třída `BarCodeReader` čte čárové kódy z obrázků nebo PDF stránek. Obě třídy jsou vlákny‑bezpečné, což vám umožní generovat nebo číst čárové kódy paralelně bez další synchronizace.

Vložení čárového kódu do PDF je tak jednoduché jako tři kroky:

1. **Vygenerujte obrázek čárového kódu** – použijte `BarcodeGenerator` k vytvoření bitmapy v paměti.  
2. **Vytvořte nebo otevřete PDF dokument** – Aspose.PDF vám umožní pracovat s existujícími PDF nebo začít od nuly.  
3. **Umístěte obrázek čárového kódu na stránku** – přidejte obrázek do `PdfPage` na požadované souřadnice a velikost.  

> *Tip:* Uchovávejte obrázek čárového kódu v `ByteArrayOutputStream`, abyste se vyhnuli zápisu dočasných souborů na disk.

```java
// Generate barcode image
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Code128, "123456789");
ByteArrayOutputStream baos = new ByteArrayOutputStream();
generator.save(baos, BarCodeImageFormat.Png);

// Create PDF and add barcode
Document pdf = new Document();
Page page = pdf.getPages().add();
Image image = Image.fromStream(baos.toByteArray());
page.getParagraphs().add(image);
pdf.save("output.pdf");
```

## Vytvoření a nastavení velikosti celého obrázku s čárovým kódem v Javě

Když potřebujete čárový kód, který zabírá konkrétní oblast dokumentu, můžete definovat přesnou šířku a výšku v pixelech nebo milimetrech. Aspose.BarCode vám umožní nastavit vlastnosti `xDimension` a `BarHeight`, nebo můžete škálovat vygenerovaný obrázek při jeho přidávání do PDF. To zajišťuje, že čárový kód bude ostrý na vysokém rozlišení tisku a perfektně zapadne do vašeho rozvržení.

## Vytvoření obrázku s přesným čárovým kódem v Javě

Pokud je vaším cílem **vygenerovat obrázek čárového kódu v Javě** pro použití mimo PDF (např. webové stránky, mobilní aplikace), třída `BarcodeGenerator` může přímo do proudu vypsat PNG, JPEG, GIF nebo BMP. Můžete také specifikovat DPI pro kontrolu kvality obrázku, což je zvláště užitečné pro tisk.

## Detekce orientace čárového kódu v Javě

Detekce orientace čárového kódu znamená, že knihovna může číst čárový kód i když je otočen (0°, 90°, 180°, 270°). **`BarCodeReader` čte a dekóduje čárové kódy z obrázků nebo PDF stránek.** Tato funkce je klíčová při skenování dokumentů, které mohou být naskenovány vzhůru nohama nebo na bok. `BarCodeReader` z Aspose.BarCode automaticky zpracovává orientaci, takže není nutné předzpracovávat obrázek.

## Běžné případy použití
- **Generování faktur** – vložte UPC/EAN kódy do každého PDF faktury.  
- **Štítky pro dopravu** – vytvořte Code128 nebo QR kódy, které kódují sledovací čísla.  
- **Katalogy produktů** – generujte obrázky čárových kódů ve vysokém rozlišení pro tištěné katalogy.  
- **Skenování dokumentů** – detekujte a čtěte čárové kódy ze skenovaných PDF pro automatizaci zadávání dat.

## Běžné problémy a řešení

| Problém | Proč se to děje | Jak opravit |
|-------|----------------|------------|
| Čárový kód je rozmazaný | DPI obrázku je příliš nízké | Nastavte vyšší DPI při volání `generator.save(stream, BarCodeImageFormat.Png, 300)` |
| Čtečka selže u otočených čárových kódů | Otočení nebylo detekováno | Ujistěte se, že používáte `BarCodeReadType.Rotate` nebo povolíte `AutoRotate` v `BarCodeReader` |
| Velikost čárového kódu nepasuje na stránku | Nesprávný škálovací faktor | Použijte `PdfPage.addImage(image, x, y, width, height)` k nastavení přesných rozměrů |
| Spotřeba paměti stoupá při velkých dávkách | Všechny obrázky jsou drženy v paměti | Zapište každý čárový kód do dočasného proudu, přidejte jej do PDF a poté uvolněte proud |

## Základní tutoriály o čárových kódech
### [Přidání čárového kódu do PDF dokumentu v Javě](./adding-barcode-to-pdf-document/)
Vylepšete své Java aplikace pomocí Aspose.BarCode. Průvodce krok za krokem pro přidávání čárových kódů do PDF dokumentů.

### [Vytvoření a nastavení velikosti celého obrázku s čárovým kódem v Javě](./creating-setting-size-whole-picture-barcode/)
Prozkoumejte vytváření a nastavení velikosti celého obrázku v Javě s Aspose.BarCode. Jednoduše přizpůsobte velikost, kódování a vzhled.

### [Vytvoření obrázku s přesným čárovým kódem v Javě](./creating-image-exact-barcode/)
Vytváření obrázku s přesnou generací čárového kódu v Javě pomocí Aspose.BarCode. Snadno vytvořte vlastní čárové kódy. Prozkoumejte dokumentaci, stáhněte a získejte podporu.

### [Detekce orientace čárového kódu v Javě](./detecting-barcode-orientation/)
Vylepšete své Java aplikace rozpoznáváním čárových kódů pomocí Aspose.BarCode pro Java. Postupujte podle našeho průvodce krok za krokem a snadno detekujte orientaci čárových kódů.

## Často kladené otázky

**Q:** Jak mohu vygenerovat čárový kód pro konkrétní symbologii, např. QR Code?  
**A:** Použijte `BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "Your data");` a poté zavolejte `generator.save("output.png");`.

**Q:** Mohu v Javě vygenerovat obrázek čárového kódu bez zápisu na disk?  
**A:** Ano, zavolejte `generator.generateBarCodeImage()`, který vrací `java.awt.Image`, nebo zapište do `ByteArrayOutputStream` pro zpracování v paměti.

**Q:** Funguje detekce orientace čárového kódu na nízkých rozlišeních skenů?  
**A:** Funguje nejlépe na obrázcích s alespoň 150 dpi; nižší rozlišení může snížit přesnost detekce, takže zvyšte DPI, pokud je to možné.

**Q:** Je možné přidat více čárových kódů na jednu PDF stránku?  
**A:** Rozhodně – jednoduše vygenerujte každý obrázek čárového kódu a umístěte jej na různé souřadnice na stránce pomocí `PdfPage.addImage`.

**Q:** Jaké licenční možnosti jsou k dispozici pro Aspose.BarCode pro Java?  
**A:** Existují licence pro vývojáře, pro místo a pro podniky. Pro hodnocení je k dispozici bezplatná dočasná licence.

---

**Poslední aktualizace:** 2026-10-25  
**Testováno s:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak číst čárový kód z PDF v Javě pomocí Aspose.BarCode](/barcode/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Generování čárového kódu v Javě pomocí Aspose.BarCode – Specifikace symbologie](/barcode/java/symbology-and-format/specifying-symbology-barcode/)
- [Jak vygenerovat čárový kód v Javě: Vytvoření a nastavení velikosti celého obrázku](/barcode/java/barcode-basics/creating-setting-size-whole-picture-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}