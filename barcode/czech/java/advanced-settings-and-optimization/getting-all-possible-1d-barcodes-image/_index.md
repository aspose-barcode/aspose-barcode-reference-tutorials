---
date: 2026-07-18
description: Zjistěte, jak číst 1D čárové kódy v Java pomocí Aspose.BarCode – rychlá
  Java knihovna pro dekódování čárových kódů, která extrahuje čárové kódy z obrázků.
keywords:
- read 1d barcodes java
- java barcode decoding library
- java barcode reader example
lastmod: 2026-07-18
linktitle: číst 1d čárové kódy java
og_description: číst 1d čárové kódy java pomocí Aspose.BarCode, vysoce výkonná Java
  knihovna pro dekódování čárových kódů, která rychle čte více čárových kódů z obrázků.
og_image_alt: 'Developer guide: read 1d barcodes in Java with Aspose.BarCode'
og_title: číst 1d čárové kódy java – Dekódovat čárové kódy pomocí Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to read 1D barcodes in Java with Aspose.BarCode – a fast
    Java barcode decoding library that extracts barcodes from images.
  headline: read 1d barcodes java – Decode barcodes with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. A commercial license removes all evaluation limitations and grants
      you full redistribution rights.
    question: Is Aspose.BarCode for Java suitable for commercial projects?
  - answer: Absolutely. Obtain a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/) for development and testing.
    question: Can I test the library without purchasing a license?
  - answer: The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).
    question: Where can I find the full API reference?
  - answer: Post your question on the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      where the community and Aspose engineers can assist you.
    question: How do I get help if I run into a problem?
  - answer: Yes – you can download a trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a free trial download?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- read 1d barcodes java
- Aspose.BarCode
- Java barcode processing
title: číst 1d čárové kódy java – Dekódovat čárové kódy pomocí Aspose.BarCode
url: /cs/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# číst 1d čárové kódy v Javě s Aspose.BarCode

## Úvod

V tomto praktickém průvodci se dozvíte, jak **číst 1D čárové kódy v Javě** pomocí výkonné knihovny **Aspose.BarCode**. Ať už potřebujete skenovat štítky produktů, inventární značky nebo jakýkoli lineární čárový kód vložený do obrázku, tento tutoriál vás provede každým krokem – od nastavení prostředí až po extrakci všech možných čárových kódů, které obrázek obsahuje. Na konci budete schopni **dekódovat čárové kódy z obrázkových souborů** pomocí několika řádků Java kódu.

## Rychlé odpovědi
- **Co dělá Aspose.BarCode?** Poskytuje plnohodnotnou knihovnu čárových kódů pro Javu, která dokáže generovat i dekódovat 1D/2D čárové kódy.  
- **Mohu přečíst více čárových kódů z jednoho obrázku?** Ano – metoda `BarCodeReader.readBarCodes()` vrací všechny detekované symboly.  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Jaké verze Javy jsou podporovány?** Java 8 + (doporučeno JDK 11).  
- **Je tato knihovna dostatečně rychlá pro skenování v reálném čase?** Rozhodně – je optimalizována pro vysoce výkonné dávkové zpracování.

Metoda `BarCodeReader.readBarCodes()` prohledá poskytnutý obrázek a vrátí kolekci objektů `BarCodeResult`, které představují každý detekovaný čárový kód.

## Co je „read 1d barcodes java“?

Čtení 1D čárových kódů v Javě je proces extrakce dat lineárního čárového kódu z obrázků pomocí Java knihovny. Zahrnuje analýzu obrázku, vyhledání vzorů čárového kódu a vrácení zakódovaného textu spolu s metadaty, jako je typ symbologie a orientace. Aspose.BarCode pro Javu provádí tuto analýzu automaticky, zvládá rotaci, nízký kontrast a širokou škálu symbologií, takže se můžete soustředit na integraci výsledků do vaší aplikace.

## Proč zvolit Aspose.BarCode pro dekódování čárových kódů z obrázku?

Aspose.BarCode nabízí špičkovou přesnost a rychlost: dokáže dekódovat více než 50 + 1D a 2D symbologií v jednom průchodu a zpracovává typické 300 dpi obrázky za méně než 0,2 sekundy na standardním serveru. API vyžaduje jen několik volání metod, eliminuje externí závislosti a funguje s Java 8 + při podpoře dávkového zpracování tisíců obrázků za minutu. Tyto kvantifikovatelné výhody z něj činí preferovanou volbu pro podnikovou skenování čárových kódů.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte následující:

- **Java Development Kit (JDK)** – verze 8 nebo novější. Stáhněte jej z oficiální [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – stáhněte nejnovější JAR ze [Aspose release page](https://releases.aspose.com/barcode/java/).  

Nyní, když je vaše prostředí připravené, pojďme začít programovat.

## Import Namespaces

Přidejte potřebné `import` příkazy, aby kompilátor mohl najít třídy Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Krok 1: Inicializace objektu BarCodeReader

Třída `BarCodeReader` je jádrem Aspose.BarCode pro skenování obrázků a extrakci informací o čárových kódech. Vytvořte instanci `BarCodeReader`, která ukazuje na váš soubor s obrázkem. Parametr `DecodeType` říká enginu, jaké symbologie má hledat; použití `CODE_128` jako příkladu funguje pro mnoho běžných 1D kódů.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Tip:** Pokud chcete skenovat *všechny* podporované 1D typy, použijte `DecodeType.ALL_1D` místo jedné konkrétní symbologie.

## Krok 2: Přečtěte všechny možné čárové kódy

Objekt `BarCodeResult` představuje jeden detekovaný čárový kód a poskytuje vlastnosti jako dekódovaný text, název symbologie, úhel rotace a souřadnice čtyř rohů oblasti čárového kódu. Procházejte kolekci vrácenou metodou `readBarCodes()`. Pro každý výsledek vypíšeme dekódovaný text, název symbologie, úhel detekce a souřadnice čtyř rohů oblasti čárového kódu.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

Smyčka automaticky zpracuje každý nalezený čárový kód, takže není potřeba čtečku volat opakovaně. Po skončení smyčky proměnná `iCount` obsahuje celkový počet detekovaných čárových kódů.

## Časté problémy a jejich řešení

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Žádné čárové kódy nebyly vráceny | Obrázek je příliš rozmazaný nebo má nízký kontrast | Předzpracujte obrázek (zvyšte kontrast, binarizujte) před předáním čtečce. |
| Nesprávná symbologie hlášena | Použita nesprávná `DecodeType` | Použijte `DecodeType.ALL_1D`, aby engine automaticky detekoval jakýkoli 1D typ. |
| Úhly jsou nesprávné | Obrázek je otočen | API již vrací úhel rotace; v případě potřeby můžete obrázek otočit zpět. |

## Často kladené otázky

**Q: Je Aspose.BarCode pro Javu vhodný pro komerční projekty?**  
A: Ano. Komerční licence odstraňuje všechna omezení hodnocení a poskytuje plná práva k redistribuci.

**Q: Mohu knihovnu testovat bez zakoupení licence?**  
A: Rozhodně. Získejte dočasnou licenci na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) pro vývoj a testování.

**Q: Kde najdu kompletní referenci API?**  
A: Rozsáhlá dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

**Q: Jak získám pomoc, pokud narazím na problém?**  
A: Položte svůj dotaz na [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13), kde vám pomohou komunita i inženýři Aspose.

**Q: Existuje bezplatná zkušební verze ke stažení?**  
A: Ano – zkušební verzi můžete stáhnout ze [Aspose releases page](https://releases.aspose.com/).

## Závěr

Nyní jste se naučili, jak **číst 1D čárové kódy v Javě** pomocí Aspose.BarCode, robustní **knihovny čárových kódů pro Javu**, která usnadňuje dekódování čárových kódů z obrázkových souborů. Začleňte tento úryvek do vlastních aplikací a automatizujte skenování zásob, ověřování vstupenek nebo jakýkoli scénář, kde se v obrázcích objevují lineární čárové kódy.

---

**Poslední aktualizace:** 2026-07-18  
**Testováno s:** Aspose.BarCode 24.11 pro Java  
**Autor:** Aspose

## Související tutoriály

- [Read Barcode Java: High Performance Barcode Reader for Faster Image Processing](/barcode/java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/extracting-barcode-region-information/)
- [Aspose.Barcode Java – Getting Barcode Recognition Quality in Percent](/barcode/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}