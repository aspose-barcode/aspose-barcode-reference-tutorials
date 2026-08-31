---
date: 2026-04-08
description: Naučte se, jak číst čárový kód z PDF v Javě pomocí Aspose.BarCode. Tento
  průvodce také ukazuje, jak generovat obrázek čárového kódu v Javě a jak extrahovat
  obrázky z PDF v Javě.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Rozpoznávání čárových kódů z PDF
second_title: Aspose.BarCode Java API
title: Jak načíst čárový kód z PDF v Javě pomocí Aspose.BarCode
url: /cs/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# číst čárový kód z PDF v Javě

## Úvod

Vítejte v našem podrobném průvodci **jak číst čárový kód z PDF v Javě** pomocí Aspose.BarCode. Čárové kódy jsou nezbytné pro automatizaci zachytávání dat a s Aspose.BarCode můžete snadno detekovat je uvnitř PDF dokumentů. V tomto tutoriálu vás provedeme vším, co potřebujete – od nastavení licencí po generování obrázku čárového kódu Java, jeho přidání do PDF, extrahování obrázků z PDF Java a nakonec zpětné čtení čárového kódu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode for Java (plus Aspose.PDF pro práci s PDF).  
- **Mohu v Javě vygenerovat obrázek čárového kódu?** Ano – třída `BarcodeGenerator` umožňuje vytvořit PNG/JPEG obrázky.  
- **Jak se extrahují obrázky z PDF?** Použijte `PdfExtractor` z Aspose.PDF.  
- **Jaký typ čárového kódu je demonstrován?** CODE‑39 (standardní).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována platná licence Aspose.BarCode a Aspose.PDF.

## Proč používat Aspose.BarCode pro Javu?
- **Vysoká přesnost** – podporuje desítky symbologií a funguje i na nízkokvalitních obrázcích.  
- **Žádné externí závislosti** – čistá Java, žádné nativní knihovny.  
- **Plná integrace s PDF** – kombinujte s Aspose.PDF pro čtení nebo vkládání čárových kódů přímo do PDF souborů.

## Předpoklady

Předtím, než se pustíte do kódu, ujistěte se, že máte:

1. **Aspose.BarCode for Java License** – získáte ji na [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Aspose.PDF License** – vyžadována pro manipulaci s PDF; licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).  
3. **Aspose.BarCode library** – stáhněte nejnovější JAR z [zde](https://releases.aspose.com/barcode/java/).  

Nyní, když máte potřebné předpoklady, importujte požadované balíčky a začněte programovat.

## Import balíčků

Ve vašem Java projektu přidejte importy Aspose.BarCode a Aspose.PDF. Tento blok zůstává nezměněn oproti originálnímu tutoriálu:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Krok 1: Vytvořit obrázek čárového kódu Java

Nejprve vytvoříme obrázek čárového kódu, který později vložíme do PDF. Toto demonstruje schopnost **vytvořit obrázek čárového kódu v Javě**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Krok 2: Vytvořit PDF a přidat obrázek čárového kódu

Dále vytvoříme nový PDF dokument a vložíme do něj právě vygenerovaný obrázek čárového kódu.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Krok 3: Extrahovat obrázky z PDF Java

S připraveným PDF musíme získat vložený obrázek zpět, aby mohl být čárový kód přečten. K tomu použijeme **extrahovat obrázky z PDF v Javě**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Krok 4: Rozpoznat čárový kód z extrahovaných obrázků

Nakonec předáme každý extrahovaný obrázek do `BarCodeReader`, abychom získali zakódovaný text.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Opakujte tyto kroky podle potřeby a upravte názvy souborů a cesty tak, aby odpovídaly struktuře vašeho projektu.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Žádný čárový kód nebyl detekován** | Kvalita obrazu je příliš nízká nebo je čárový kód příliš malý. | Zvyšte rozlišení obrazu při ukládání (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` vyvolá výjimku** | Soubor PDF nebyl nalezen nebo je cesta nesprávná. | Ověřte, že `strPdfDoc` ukazuje na existující soubor a že aplikace má oprávnění ke čtení. |
| **Licence nebyla použita** | Komponenty Aspose běží v režimu zkušební verze, což omezuje výstup. | Na začátku programu načtěte licenční soubory: `new License().setLicense("Aspose.BarCode.lic");` a obdobně pro Aspose.PDF. |

## Často kladené otázky (FAQ)

### Q: Mohu používat Aspose.BarCode pro Javu bez licence?
I když je možné Aspose.BarCode používat bez licence, doporučujeme získat licenci pro plnou funkčnost a dodržení licenčních podmínek.

### Q: Jak získám dočasnou licenci pro Aspose.BarCode pro Javu?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q: Existují nějaká omezení typů čárových kódů podporovaných Aspose.BarCode?
Aspose.BarCode podporuje širokou škálu typů čárových kódů. Kompletní seznam najdete v dokumentaci.

### Q: Je k dispozici zkušební verze Aspose.BarCode pro Javu?
Ano, zkušební verzi si můžete stáhnout [zde](https://releases.aspose.com/).

### Q: Kde mohu získat podporu nebo klást otázky ohledně Aspose.BarCode pro Javu?
Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro podporu a diskuze.

## Závěr

Gratulujeme! Naučili jste se **číst čárový kód z PDF v Javě** pomocí Aspose.BarCode, **vytvářet obrázek čárového kódu v Javě** a **extrahovat obrázky z PDF v Javě** pro další zpracování. Neváhejte prozkoumat další funkce, jako je hromadné zpracování, práce s různými symbologiemi čárových kódů nebo integrace s dalšími produkty Aspose. Pro podrobnější informace si prostudujte oficiální [dokumentaci](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}