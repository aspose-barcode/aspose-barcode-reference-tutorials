---
date: 2026-10-19
description: Naučte se, jak vytvořit QR kód v Javě a generovat více čárových kódů
  na jediném obrázku pomocí Aspose.BarCode for Java. Obsahuje nastavení, kód a řešení
  problémů.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Generování více čárových kódů na jednom obrázku
og_description: Vytvořte QR kód v Javě a spojte několik typů čárových kódů do jednoho
  obrázku pomocí Aspose.BarCode for Java. Postupujte podle podrobného návodu, prohlédněte
  si ukázky kódu a naučte se tipy na řešení problémů.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Vytvořit QR kód v Javě – generovat více čárových kódů na jednom obrázku
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Vytvořit QR kód v Javě – generovat více čárových kódů na jednom obrázku
url: /cs/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření QR kódu v Javě – generování více čárových kódů na jednom obrázku

## Úvod

V tomto tutoriálu se naučíte **jak vytvořit QR kód v Javě** a sloučit několik různých typů čárových kódů na jediné plátno pomocí **Aspose.BarCode for Java**. Ať už potřebujete kompaktní QR štítek, produktový čárový kód nebo kombinaci 2‑D a lineárních symbolik, tento průvodce vás provede každým krokem – od nastavení projektu až po uložení finálního kombinovaného obrázku – takže můžete okamžitě začlenit generování čárových kódů do svých Java aplikací.

## Rychlé odpovědi
- **Jakou knihovnu bych měl použít?** Aspose.BarCode for Java poskytuje nejúplnější sadu symbolik.  
- **Mohu generovat různé typy čárových kódů dohromady?** Ano, můžete kombinovat CODE_39, QR, AZTEC a další na jednom plátně.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 a novější jsou plně kompatibilní.  
- **Je výstupní formát konfigurovatelný?** Můžete exportovat kombinovaný obrázek jako PNG, JPEG, BMP nebo TIFF.

## Co je create QR code java?

`create QR code java` odkazuje na proces převodu textového řetězce do dvourozměrné matice, kterou lze skenovat pomocí chytrých telefonů nebo čteček čárových kódů. Aspose.BarCode for Java provádí kódování a vykreslování, takže se můžete soustředit na obchodní logiku místo manipulace s obrázkem na úrovni pixelů.

## Proč použít Aspose.BarCode Java pro generování čárových kódů v Javě?

Aspose.BarCode podporuje **více než 50 symbologií čárových kódů** – včetně QR, Data Matrix, Code 128, AZTEC a tradičních lineárních kódů – což z něj činí nejužitečnější Java knihovnu pro čárové kódy. Vykresluje **antialiasované obrázky až do 1200 dpi**, což zaručuje ostré skeny na obrazovce i v tisku. API vyžaduje pouze JVM a poskytuje plynulý konfigurační model pro přizpůsobení velikosti, barvy, okrajů a opravy chyb během několika řádků kódu.

## Předpoklady

- Pevné základy v Javě.  
- Nainstalovaný a v PATH nakonfigurovaný JDK 8 nebo novější.  
- JAR soubor Aspose.BarCode for Java (ke stažení na oficiální stránce stahování Aspose.BarCode for Java).  
- IDE jako IntelliJ IDEA nebo Eclipse pro úpravu a spuštění ukázky.  

## Importování jmenných prostorů

Importovací příkazy přinášejí třídy Aspose.BarCode jako `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat` do rozsahu, což vám umožní odkazovat na ně bez plně kvalifikovaných názvů.  
`BarcodeGenerator` je hlavní třída používaná k nastavení a generování obrázků čárových kódů.  
`EncodeTypes` je výčtová hodnota v Aspose.BarCode, která určuje symbologii čárového kódu k vygenerování.  
`BarCodeImageFormat` definuje výstupní formát obrázku pro vygenerovaný čárový kód.

## Krok 1: nastavení adresáře zdrojů

**Adresář zdrojů** je složka ve vašem souborovém systému, kam budou zapisovány všechny vygenerované obrázky čárových kódů. Jednorázové nastavení udržuje projekt uspořádaný a usnadňuje odstraňování starých souborů.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Krok 2: vytvoření kolekce čárových kódů

`HashMap<String, EncodeTypes>` ukládá řetězec dat každého čárového kódu spolu se symbologií, kterou chcete použít. `HashMap` je kolekce v Javě, která mapuje klíče na hodnoty. Tato kolekce řídí následnou smyčku generování. `EncodeTypes` je výčtová hodnota, která určuje, který typ čárového kódu generovat.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 3: generování obrázků čárových kódů

Generační smyčka prochází `HashMap`, pro každý záznam vytvoří `BarcodeGenerator` a zavolá `generateBarCodeImage()`, aby získala `BufferedImage`. `generateBarCodeImage()` vytvoří `BufferedImage` obsahující vykreslený čárový kód. `BufferedImage` je třída v Javě představující obrázek v paměti. Všechny obrázky jsou přidány do `ArrayList<BufferedImage>` pro pozdější skládání. `ArrayList` je v Javě implementace dynamického seznamu.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 4: vytvoření kombinovaného obrázku

Nejprve algoritmus spočítá **maximální šířku** mezi všemi obrázky čárových kódů a **celkovou výšku** potřebnou k jejich vertikálnímu uspořádání s volitelným odstupem. Poté vytvoří `BufferedImage` této velikosti a vykreslí každý čárový kód na plátno pomocí objektu `Graphics2D`. `Graphics2D` je třída v Javě, která poskytuje 2D vykreslovací schopnosti pro kreslení tvarů a obrázků.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 5: uložení výsledku

Nakonec je kombinovaný obrázek zapsán na disk pomocí `ImageIO.write`, s použitím formátu, který jste určili (PNG, JPEG, BMP nebo TIFF). `ImageIO.write` zapíše `BufferedImage` do souboru ve zvoleném formátu. Cesta k souboru je relativní k dříve definovanému adresáři zdrojů.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Běžné případy použití pro generování více čárových kódů

- **Štítky balení** – kombinujte produktové, šaržové a přepravní kódy na jednom štítku pro snížení nákladů na tisk.  
- **Vstupenky na akce** – vložte QR, Data Matrix a identifikátory Code 128 pro různé skenovací stanice na místě.  
- **Správa zásob** – zobrazte SKU, data RFID tagu a sériová čísla společně pro rychlý audit a sledovatelnost.

## Řešení problémů a tipy

- **Problémy s velikostí obrázku** – upravte proměnnou `offset` pro zvýšení nebo snížení mezery mezi čárovými kódy.  
- **Nesprávná symbologie** – ověřte, že vaše verze Aspose.BarCode podporuje požadovaný typ čárového kódu; novější verze přidávají další 2‑D kódy.  
- **Výkon** – při generování mnoha obrázků ve smyčce znovu použijte jediný objekt `Graphics2D`, aby se minimalizovalo zatížení alokací objektů.  

## Často kladené otázky

**Q: Mohu přizpůsobit vzhled jednotlivých čárových kódů v generovaném obrázku?**  
A: Ano. Použijte vlastnosti `BarcodeGenerator`, jako jsou `setBarColor`, `setBackgroundColor` a `setXDimension`, k individuálnímu stylování každého čárového kódu před jeho přidáním na plátno.

**Q: Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?**  
A: Rozhodně. Knihovna podporuje více než 50 symbologií, včetně CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 a AZTEC, jak je ukázáno v tomto tutoriálu.

**Q: Jak integrovat Aspose.BarCode do mého Java projektu?**  
A: Stáhněte JAR ze stránky stahování knihovny Aspose.BarCode for Java, přidejte jej do classpath vašeho projektu a importujte požadované jmenné prostory, jak je ukázáno v sekci „Importování jmenných prostorů“.

**Q: Mohu používat Aspose.BarCode pro komerční aplikace?**  
A: Ano. Zakupte licenci na stránce nákupu licence Aspose.BarCode, abyste odstranili omezení zkušební verze a získali plnou podporu pro produkci.

**Q: Existují zkušební možnosti pro Aspose.BarCode?**  
A: Samozřejmě. Bezplatná zkušební licence je k dispozici na stránce stahování bezplatné zkušební verze Aspose.BarCode, která vám poskytne plný přístup k API pro vyhodnocení.

**Q: Jak vygenerovat vysoce rozlišený QR kód pro tisk?**  
A: Nastavte vlastnost `setResolutionDpi` na `BarcodeGenerator` před voláním `generateBarCodeImage()`, poté uložte výsledek v bezztrátovém formátu, například PNG.

**Q: Co mám dělat, pokud se kombinovaný obrázek zdá být oříznutý?**  
A: Ověřte, že výpočty `offset` a velikosti plátna správně zohledňují výšky všech čárových kódů; zvýšení výšky plátna nebo zmenšení velikosti jednotlivých čárových kódů řeší většinu problémů s oříznutím.

---

**Poslední aktualizace:** 2026-10-19  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Související tutoriály

- [Jak vytvořit obrázek čárového kódu v Javě – Přidat rámeček pomocí Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Jak generovat čárový kód v Javě: Uložit do streamů s Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Jak generovat čárový kód v Javě a tisknout čárový kód s Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}