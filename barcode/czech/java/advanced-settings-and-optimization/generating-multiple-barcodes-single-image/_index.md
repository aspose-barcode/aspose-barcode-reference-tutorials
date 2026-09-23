---
date: 2026-04-03
description: Naučte se, jak vytvořit QR kód v Javě a generovat více čárových kódů
  na jednom obrázku pomocí Aspose.BarCode pro Javu. Obsahuje nastavení, kód a řešení
  problémů.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Generování více čárových kódů na jednom obrázku
second_title: Aspose.BarCode Java API
title: Vytvořte QR kód v Javě – Generujte více čárových kódů na jednom obrázku
url: /cs/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření QR kódu v Javě – Generování více čárových kódů na jednom obrázku

## Úvod

V tomto tutoriálu se naučíte **jak vytvořit QR kód v Javě** a zkombinovat několik různých typů čárových kódů do jednoho obrázku pomocí **Aspose.BarCode for Java**. Ať už potřebujete kompaktní QR štítek, produktový čárový kód nebo kombinaci 2‑D a lineárních symbologií, tento průvodce vás provede každým krokem – od nastavení projektu až po uložení finálního kombinovaného obrázku – takže můžete okamžitě začlenit generování čárových kódů do svých Java aplikací.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.BarCode for Java poskytuje nejúplnější sadu symbologií.  
- **Mohu generovat různé typy čárových kódů dohromady?** Ano, můžete kombinovat CODE_39, QR, AZTEC a další na jedné plátně.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 a novější jsou plně kompatibilní.  
- **Je výstupní formát konfigurovatelný?** Můžete exportovat kombinovaný obrázek jako PNG, JPEG, BMP atd.  

## Co je vytvoření QR kódu v Javě?

Vytvoření QR kódu v Javě znamená převod textového řetězce do dvourozměrné matice, kterou lze skenovat chytrými telefony nebo čtečkami čárových kódů. **Aspose.BarCode for Java** se stará o kódování a vykreslování, takže se můžete soustředit na obchodní logiku místo nízkoúrovňového zpracování obrazu.

## Proč použít Aspose.BarCode Java pro generování čárových kódů v Javě?

- **Široká podpora symbologií** – od klasických lineárních kódů po moderní 2‑D matice.  
- **Vysoce kvalitní vykreslování** – antialiasovaný výstup, který funguje na jakémkoli zařízení.  
- **Jednoduché API** – vytvářejte, přizpůsobujte a kombinujte čárové kódy pomocí několika volání metod.  
- **Žádné externí závislosti** – vše běží na JVM bez nativních knihoven.  

## Předpoklady

- Základní znalost programování v Javě.  
- Nainstalovaný Java Development Kit (JDK) ve vašem systému.  
- Knihovna Aspose.BarCode for Java stažená a nastavená. Můžete ji stáhnout [zde](https://releases.aspose.com/barcode/java/).  
- Integrované vývojové prostředí (IDE) jako Eclipse nebo IntelliJ IDEA.

## Importování jmenných prostorů

Ve vašem Java projektu importujte potřebné jmenné prostory pro přístup k funkcionalitě Aspose.BarCode. Přidejte následující importy na začátek vaší Java třídy:

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

## Krok 1: Nastavení adresáře zdrojů

Definujte cestu k adresáři zdrojů, kam budou generované čárové kódy uloženy. Tento adresář je klíčový pro organizaci a správu vašich obrázků čárových kódů.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Vytvoření kolekce čárových kódů

Inicializujte `HashMap` pro uložení dat čárových kódů. Každý záznam v kolekci představuje čárový kód s příslušným typem kódování.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 3: Generování obrázků čárových kódů

Procházejte kolekci a generujte obrázky čárových kódů pomocí knihovny Aspose.BarCode. Uložte obrázky do `ArrayList` pro další zpracování.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 4: Vytvoření kombinovaného obrázku

Určete maximální šířku a celkovou výšku obrázků čárových kódů. Vytvořte `BufferedImage`, který spojí jednotlivé obrázky čárových kódů do jednoho výstupního obrázku.

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

## Krok 5: Uložení výsledku

Uložte finální kombinovaný obrázek na určené umístění souboru.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Běžné případy použití pro generování více čárových kódů

- **Štítky balení** – kombinujte produktové, šaržové a přepravní kódy na jednom štítku.  
- **Vstupenky na akce** – vložte QR, Data Matrix a Code 128 identifikátory pro různé skenovací stanice.  
- **Správa zásob** – zobrazte SKU, data RFID tagu a sériová čísla společně pro rychlý audit.

## Řešení problémů a tipy

- **Problémy s velikostí obrázku** – upravte proměnnou `offset` pro zvýšení nebo snížení mezery mezi čárovými kódy.  
- **Nepodporovaná symbologie** – ověřte, že vaše verze Aspose.BarCode podporuje požadovaný typ čárového kódu.  
- **Výkon** – znovu použijte jediný objekt `Graphics`, pokud generujete mnoho obrázků ve smyčce.

## Často kladené otázky

**Q1: Mohu přizpůsobit vzhled jednotlivých čárových kódů v generovaném obrázku?**  
A1: Ano, Aspose.BarCode poskytuje rozsáhlé možnosti přizpůsobení vzhledu čárových kódů, což vám umožní upravit styl každého čárového kódu podle vašich preferencí.

**Q2: Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?**  
A2: Rozhodně! Aspose.BarCode podporuje širokou škálu symbologií, včetně CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 a AZTEC, jak je ukázáno v tomto tutoriálu.

**Q3: Jak mohu integrovat Aspose.BarCode do svého Java projektu?**  
A3: Jednoduše stáhněte knihovnu Aspose.BarCode for Java z [zde](https://releases.aspose.com/barcode/java/) a postupujte podle instalačních pokynů uvedených v dokumentaci.

**Q4: Mohu používat Aspose.BarCode pro komerční aplikace?**  
A4: Ano, můžete získat licenci z [zde](https://purchase.aspose.com/buy) pro použití Aspose.BarCode pro komerční účely.

**Q5: Existují nějaké zkušební možnosti pro Aspose.BarCode?**  
A5: Samozřejmě! Můžete prozkoumat funkce Aspose.BarCode získáním bezplatné zkušební licence [zde](https://releases.aspose.com/).

**Q6: Jak vygenerovat vysoce rozlišený QR kód pro tisk?**  
A6: Nastavte požadované DPI na `BarcodeGenerator` před voláním `generateBarCodeImage()`, poté uložte obrázek v bezztrátovém formátu, například PNG.

**Q7: Co mám dělat, pokud se kombinovaný obrázek zobrazuje oříznutý?**  
A7: Ověřte, že výpočty `offset` a velikosti plátna správně zohledňují výšky všech čárových kódů; zvýšení výšky plátna nebo zmenšení velikosti jednotlivých čárových kódů řeší většinu problémů s oříznutím.

---

**Poslední aktualizace:** 2026-04-03  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}