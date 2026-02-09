---
date: 2026-02-09
description: Naučte se, jak generovat čárové kódy na jednom obrázku v Javě pomocí
  Aspose.BarCode, výkonné knihovny pro generování čárových kódů v Javě. Tento průvodce
  pokrývá integraci a generování více čárových kódů.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Jak v Javě generovat čárové kódy na jednom obrázku
url: /cs/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování více čárových kódů na jedné obrázku v Javě s Aspose.BarCode

## Úvod

Pokud hledáte spolehlivý způsob **jak generovat čárové kódy** v Java aplikaci, jste na správném místě. S Aspose.BarCode pro Java můžete umístit několik různých typů čárových kódů na jeden obrázek během několika řádků kódu. Tento tutoriál vás provede celým procesem – od nastavení projektu až po uložení kombinovaného obrázku – takže můžete okamžitě začít používat generování čárových kódů ve svých řešeních.

## Rychlé odpovědi
- **Jakou knihovnu použít?** Aspose.BarCode pro Java poskytuje nejúplnější sadu symbologií.  
- **Mohu generovat různé typy čárových kódů dohromady?** Ano, můžete kombinovat CODE_39, QR, AZTEC a další na jedné plátně.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 a novější jsou plně kompatibilní.  
- **Je výstupní formát konfigurovatelný?** Můžete exportovat kombinovaný obrázek jako PNG, JPEG, BMP atd.

## Co znamená „jak generovat čárové kódy“ v Javě?
Generování čárových kódů znamená převod řetězce dat na vizuální vzor, který dokážou čtečky rozpoznat. Aspose.BarCode automaticky provádí kódování, vykreslování a tvorbu obrázku, takže se můžete soustředit na obchodní logiku místo nízkoúrovňového zpracování obrazu.

## Proč generovat více čárových kódů na jednom obrázku?
- **Úspora místa na štítcích** – kombinujte produktové, šaržové a přepravní identifikátory na jednom štítku.  
- **Pracovní postupy s více skenováním** – vložte QR, Data Matrix a Code 128 pro různé skenovací stanice.  
- **Zjednodušené sledování majetku** – zobrazte SKU, data RFID tagu a sériová čísla společně pro rychlé audity.  

## Požadavky

Předtím, než se pustíte do tutoriálu, ujistěte se, že máte následující:

- Základní znalosti programování v Javě.  
- Nainstalovaný Java Development Kit (JDK).  
- Stáhnutou a nastavenou knihovnu Aspose.BarCode pro Java. Knihovnu můžete stáhnout [zde](https://releases.aspose.com/barcode/java/).  
- Integrované vývojové prostředí (IDE) jako Eclipse nebo IntelliJ IDEA.

## Import Namespaces

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

Definujte cestu k adresáři zdrojů, kam budou generované čárové kódy ukládány. Tento adresář je klíčový pro organizaci a správu vašich obrázků čárových kódů.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Vytvoření kolekce čárových kódů

Inicializujte `HashMap`, která bude uchovávat data čárových kódů. Každý záznam v kolekci představuje čárový kód s příslušným typem kódování.

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

## Jak generovat QR kód v Javě?

Pokud potřebujete příklad **generovat QR kód v Javě**, jednoduše nahraďte položku v kolekci `EncodeTypes.QR`. Stejná smyčka vygeneruje vysoce rozlišený QR kód, který může ukládat URL, kontaktní informace nebo libovolná alfanumerická data.

## Jak generovat čárový kód Code 128 v Javě?

Ukázka výše již demonstruje **generování čárového kódu Code 128** pomocí `EncodeTypes.CODE_128`. Code 128 je ideální pro logistiku, protože podporuje celý ASCII set a nabízí kompaktní kódování.

## Použití Java knihovny pro generování čárových kódů mimo Aspose

Zatímco Aspose.BarCode je plnohodnotná **java knihovna pro generování čárových kódů**, můžete také zkusit open‑source alternativy jako ZXing nebo Barcode4J pro lehčí scénáře. Nicméně Aspose poskytuje vestavěnou podporu pro vysoké rozlišení, více symbologií a snadné skládání obrázků – vše v jednom balíčku.

## Běžné případy použití generování více čárových kódů

- **Obalové štítky** – kombinujte produktové, šaržové a přepravní kódy na jednom štítku.  
- **Vstupenky na akce** – vložte QR, Data Matrix a Code 128 identifikátory pro různé skenovací stanice.  
- **Správa inventáře** – zobrazte SKU, data RFID tagu a sériová čísla společně pro rychlý audit.

## Řešení problémů a tipy

- **Problémy s velikostí obrázku** – upravte proměnnou `offset` pro zvýšení nebo snížení mezery mezi čárovými kódy.  
- **Nesprávná symbologie** – ověřte, že vaše verze Aspose.BarCode podporuje požadovaný typ čárového kódu.  
- **Výkon** – znovu použijte jediný objekt `Graphics`, pokud generujete mnoho obrázků ve smyčce.  
- **Správa paměti** – při práci s velkým počtem čárových kódů zvažte dočasné ukládání každého obrázku na disk, abyste předešli nadměrnému využití haldy.

## Často kladené otázky

### Q1: Mohu přizpůsobit vzhled jednotlivých čárových kódů v generovaném obrázku?

A1: Ano, Aspose.BarCode poskytuje rozsáhlé možnosti přizpůsobení vzhledu čárových kódů, což vám umožní nastavit styl každého kódu podle vašich preferencí.

### Q2: Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?

A2: Rozhodně! Aspose.BarCode podporuje širokou škálu symbologií, včetně CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 a AZTEC, jak je ukázáno v tomto tutoriálu.

### Q3: Jak mohu integrovat Aspose.BarCode do svého Java projektu?

A3: Jednoduše si stáhněte knihovnu Aspose.BarCode pro Java z [zde](https://releases.aspose.com/barcode/java/) a postupujte podle instalačních pokynů uvedených v dokumentaci.

### Q4: Mohu používat Aspose.BarCode pro komerční aplikace?

A4: Ano, licenci můžete získat [zde](https://purchase.aspose.com/buy) a používat Aspose.BarCode pro komerční účely.

### Q5: Existují zkušební možnosti pro Aspose.BarCode?

A5: Samozřejmě! Funkce Aspose.BarCode můžete vyzkoušet získáním bezplatné zkušební licence [zde](https://releases.aspose.com/).

**Další otázky**

**Q: Jak konkrétně v Javě vygenerovat QR kód?**  
A: Použijte `EncodeTypes.QR` při vytváření instance `BarcodeGenerator`, jak je ukázáno v příkladu kolekce.

**Q: Podporuje Aspose.BarCode výstup ve vysokém rozlišení pro tisk?**  
A: Ano, můžete při ukládání obrázku specifikovat DPI tak, aby vyhovovalo požadavkům na tiskovou kvalitu.

---

**Poslední aktualizace:** 2026-02-09  
**Testováno s:** Aspose.BarCode pro Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}