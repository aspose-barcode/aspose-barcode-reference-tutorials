---
date: 2025-12-19
description: Naučte se číst čárové kódy v Javě z dokumentů Word pomocí Aspose.BarCode.
  Tento průvodce zahrnuje generování obrázků čárových kódů, jejich vkládání do Wordu
  a extrahování obrázků pro čtení čárových kódů.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Jak číst čárový kód v Javě z dokumentů Word
url: /cs/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód Java z dokumentů Word

## Úvod

Práce s čárovými kódy v Java aplikacích je častá, zejména když jsou tyto kódy vloženy do souborů Microsoft Word. V tomto tutoriálu se naučíte **jak číst čárový kód Java** z dokumentu Word pomocí Aspose.BarCode for Java. Provedeme vás generováním obrázku čárového kódu, přidáním čárového kódu do souboru Word, extrakcí obrázků z dokumentu Word a nakonec dekódováním čárového kódu pomocí příkladu Java čtečky čárových kódů.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.BarCode for Java (s Aspose.Words pro práci s obrázky)  
- **Mohu přidat čárový kód do Wordu?** Ano – vygenerujte obrázek a vložte jej pomocí Aspose.Words  
- **Jak extrahovat obrázky z Wordu?** Použijte `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Existuje příklad Java čtečky čárových kódů?** Kód ve 3. kroku ukazuje kompletní příklad  
- **Jaké jsou předpoklady?** JDK, Aspose.BarCode for Java, IDE (Eclipse/IntelliJ)

## Co je rozpoznávání čárových kódů v Javě?
Rozpoznávání čárových kódů v Javě označuje proces detekce a dekódování symbolů čárových kódů z obrázků nebo dokumentů pomocí knihovny, jako je Aspose.BarCode. Umožňuje aplikacím automaticky číst produktové kódy, ID zásob nebo jakákoli zakódovaná data bez ručního zadávání.

## Proč číst čárový kód Java z dokumentů Word?
Vkládání čárových kódů přímo do souborů Word je užitečné pro smlouvy, přepravní štítky nebo zprávy, kde je vyžadována vizuální reprezentace kódu. Schopnost **extrahovat obrázky z Wordu** a dekódovat je programově eliminuje potřebu ručního skenování a snižuje chyby.

## Předpoklady

Než začneme, ujistěte se, že máte:

- **Java Development Kit (JDK)** – aktuální JDK nainstalované na vašem počítači.  
- **Aspose.BarCode for Java** – stáhněte knihovnu z oficiálního webu [here](https://releases.aspose.com/barcode/java/).  
- **Integrované vývojové prostředí (IDE)** – např. Eclipse nebo IntelliJ IDEA pro psaní a spouštění kódu.

## Import balíčků

Ve vašem Java projektu importujte potřebné balíčky Aspose.BarCode a Aspose.Words:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Krok 1: Vygenerujte obrázek čárového kódu (generate barcode image java)

Nejprve vytvořte obrázek čárového kódu pomocí Aspose.BarCode. Tento obrázek bude později **added barcode to word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Krok 2: Vložte obrázek čárového kódu do dokumentu Word (insert image into word)

Nyní použijeme Aspose.Words k **insert image into word** a uložíme dokument:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Krok 3: Rozpoznávejte čárové kódy z dokumentu Word (java barcode reader example)

Nakonec extrahujte každý obrázek ze souboru Word a spusťte **java barcode reader example** pro dekódování čárového kódu:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Poznámka:** Smyčka výše demonstruje **extract images from word**, ukládá každý obrázek a poté dekóduje čárový kód pomocí stejné cesty k souboru obrázku. Přizpůsobte cesty (`dataDir`) podle vašeho prostředí.

## Časté problémy a tipy

- **Neshody cest k souborům** – Ujistěte se, že `dataDir` ukazuje na existující složku; jinak čtečka vyhodí `FileNotFoundException`.  
- **Nepodporované typy čárových kódů** – Příklad používá `CODE_39_STANDARD`. Pokud potřebujete QR, DataMatrix atd., změňte jak `EncodeTypes`, tak `DecodeType` odpovídajícím způsobem.  
- **Výkon** – U velkých dokumentů zvažte zpracování obrázků v paralelních streamech pro zrychlení rozpoznávání.

## Často kladené otázky (FAQ)

### Q: Mohu používat Aspose.BarCode for Java v komerčních projektech?
Ano, Aspose.BarCode for Java je k dispozici pro komerční použití. Podrobnosti o licencování najdete [here](https://purchase.aspose.com/buy).

### Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode for Java?
Ano, funkce Aspose.BarCode for Java můžete vyzkoušet stažením bezplatné zkušební verze [here](https://releases.aspose.com/).

### Q: Jak získám podporu pro Aspose.BarCode for Java?
Pro jakoukoli pomoc nebo dotazy navštivte fórum Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q: Existují dočasné licence pro Aspose.BarCode for Java?
Ano, dočasné licence můžete získat [here](https://purchase.aspose.com/temporary-license/).

### Q: Kde najdu dokumentaci k Aspose.BarCode for Java?
Komplexní dokumentaci najdete [here](https://reference.aspose.com/barcode/java/).

## Další FAQ

**Q: Mohu číst i jiné symbologie čárových kódů než Code 39?**  
A: Samozřejmě. Stačí změnit `EncodeTypes` při generování a `DecodeType` při čtení tak, aby odpovídaly požadované symbologii (např. `EncodeTypes.QR`, `DecodeType.QR`).

**Q: Funguje tento přístup také s .docx soubory?**  
A: Ano. Aspose.Words transparentně pracuje s formáty `.doc` i `.docx`; stejný kód funguje pro oba.

**Q: Jak mohu zlepšit přesnost rozpoznávání u nízkokvalitních obrázků?**  
A: Zvyšte DPI při ukládání obrázku čárového kódu (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) nebo použijte formát vyšší kvality, například PNG.

---

**Poslední aktualizace:** 2025-12-19  
**Testováno s:** Aspose.BarCode for Java 24.11 a Aspose.Words for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}