---
date: 2025-12-21
description: Naučte se, jak číst obrázek čárového kódu pomocí knihovny Aspose.BarCode
  pro Javu, včetně generování čárových kódů PDF417 v Javě a rozpoznávání Unicode čárových
  kódů.
linktitle: Recognizing Unicode Barcodes
second_title: Aspose.BarCode Java API
title: Jak číst obrázek čárového kódu s Unicode čárovými kódy v Javě
url: /cs/java/document-barcode-recognition/recognizing-unicode-barcodes/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozpoznávání Unicode čárových kódů v Javě

## Úvod

If you need to **how to read barcode image** in a Java application, especially when the barcode contains Unicode characters, you’ve come to the right place. In this tutorial we’ll walk through every step required to recognize Unicode barcodes—like Arabic, Chinese, or Cyrillic text—using the powerful Aspose.BarCode library. By the end, you’ll be able to generate and read these barcodes confidently, expanding the reach of your software to global audiences.

## Rychlé odpovědi
- **Která knihovna je nejlepší pro čtení čárových kódů v Javě?** Aspose.BarCode for Java.
- **Mohu generovat PDF417 čárové kódy s Unicode textem?** Yes, using the `BarcodeGenerator` class.
- **Potřebuji licenci pro produkční použití?** A valid Aspose.BarCode license is required.
- **Jaká verze Javy je podporována?** Java 8 and above.
- **Je k dispozici bezplatná zkušební verze?** Yes, you can download a trial from Aspose’s website.

## Co je “how to read barcode image” v Javě?

Reading a barcode image means decoding the visual pattern into the original data string. When the data contains Unicode characters, the library must correctly handle character encoding and decoding, which Aspose.BarCode does automatically once you convert the text to the proper code format.

## Proč použít Aspose.BarCode pro pdf417 generování čárových kódů v Javě?

Aspose.BarCode provides a straightforward API for **pdf417 barcode generation java**, supports a wide range of symbologies, and handles Unicode encoding out‑of‑the‑box. This makes it ideal for enterprise‑level applications that need reliable, high‑performance barcode processing.

## Požadavky

Before diving in, make sure you have:

- A working knowledge of Java programming.
- Aspose.BarCode for Java library installed. You can download it [here](https://releases.aspose.com/barcode/java/).
- A valid license for Aspose.BarCode. You can obtain one [here](https://purchase.aspose.com/buy).

## Import balíčků

To get started, import the necessary packages into your Java project. The Aspose.BarCode library provides a comprehensive set of functionalities for barcode generation and recognition.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
```

## Krok 1: Nastavte adresář zdrojů

Define the path to your resource directory.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Nastavte licenci Aspose.BarCode

Load your Aspose.BarCode license to unlock the library's full potential.

```java
try {
    License lic = new License();
    lic.setLicense("aspose.barcode.lic");
} catch (Exception ex) {
    System.out.println(ex.getMessage());
}
```

## Krok 3: Vygenerujte Unicode čárový kód

Create a Unicode barcode using the provided text.

```java
String file = dataDir + "pdf417_un.png";
String scodeText = "منحة";
System.out.println("codetext: " + scodeText);
String codeText = getCodeTextFromUnicode(scodeText);
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, codeText);
generator.save(file);
```

## Krok 4: Přečtěte Unicode čárový kód

Read the generated Unicode barcode.

```java
BarCodeReader reader = new BarCodeReader(file, DecodeType.PDF_417);
for (BarCodeResult result : reader.readBarCodes()) {
    String rc = result.getCodeText();
    try {
        String s = getUnicodeFromCodeText(rc);
        System.out.println(s);
    } catch (UnsupportedEncodingException e) {
        e.printStackTrace();
    }
}
```

## Krok 5: Převod Unicode na kódový text

Implement the method to convert Unicode to code text.

```java
private static String getCodeTextFromUnicode(String s) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Krok 6: Převod kódového textu na Unicode

Implement the method to convert code text to Unicode.

```java
private static String getUnicodeFromCodeText(String cs) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Garbled output after reading | Wrong character encoding | Ensure `getUnicodeFromCodeText` uses the same charset (`UTF‑8`) as `getCodeTextFromUnicode`. |
| Reader returns `null` | Incorrect `DecodeType` | Use `DecodeType.PDF_417` for PDF417 barcodes. |
| License not applied | License file path incorrect | Place `aspose.barcode.lic` in the project root or provide absolute path. |

## Často kladené otázky

**Otázka: Mohu tento kód použít s jinými symboly čárových kódů?**
Odpověď: Rozhodně. Změňte `EncodeTypes.PDF_417` na jakýkoli podporovaný typ, například `EncodeTypes.CODE_128`, a podle toho upravte `DecodeType`.

**Otázka: Co se stane, když vstupní text obsahuje emoji?**
Odpověď: Emoji jsou znaky Unicode; budou kódovány správně, pokud metody převodu zpracovávají UTF-8.

**Otázka: Existuje způsob, jak číst čárové kódy ze streamu místo ze souboru?**
Odpověď: Ano, `BarCodeReader` také přijímá `InputStream` jako první argument.

**Otázka: Jak mohu zlepšit rychlost rozpoznávání pro velké dávky?**
Odpověď: Znovu použijte jednu instanci `BarCodeReader` a zpracujte obrázky ve smyčce, přičemž každý výsledek ihned zlikvidujte.

**Otázka: Podporuje Aspose.BarCode vícestránkové PDF soubory pro extrakci čárových kódů?**
Odpověď: Podporuje. Použijte `BarCodeReader` s cestou k souboru PDF; knihovna automaticky projde všemi stránkami.

## Závěr

Gratuluji! Nyní jste zvládli **číst obrázek čárového kódu** v Javě pomocí Aspose.BarCode, od generování čárového kódu Unicode PDF417 až po jeho dekódování zpět do původního textu. Tato schopnost otevírá dveře k internacionalizovaným aplikacím, vícejazyčným inventárním systémům a jakýmkoli scénářům, kde jsou vyžadovány globální znakové sady.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}