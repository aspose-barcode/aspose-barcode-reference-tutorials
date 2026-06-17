---
date: 2026-04-23
description: Naučte se číst čárové kódy PDF417 s tureckými znaky v Javě pomocí Aspose.BarCode.
  Tento průvodce ukazuje rychlé nastavení čtečky PDF417 v Javě pro spolehlivé dekódování.
keywords:
- how to read pdf417
- pdf417 barcode reader java
- Turkish characters barcode
- Aspose.BarCode Java
linktitle: Rozpoznávání PDF417 čárového kódu s tureckými znaky
second_title: Aspose.BarCode Java API
title: Jak číst PDF417 čárové kódy s tureckými znaky v Javě
url: /cs/java/multilingual-support/recognizing-pdf417-turkish-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 čárové kódy s tureckými znaky v Javě

## Úvod

Pokud potřebujete **číst PDF417** čárové kódy, které obsahují turecké znaky, jste na správném místě. V tomto tutoriálu projdeme kompletním příkladem od začátku do konce s využitím Aspose.BarCode pro Java. Uvidíte, jak nastavit projekt **PDF417 barcode reader Java**, načíst obrázek a dekódovat data tak, aby se speciální turecké znaky zobrazily správně.

## Rychlé odpovědi
- **Jaká knihovna je doporučena?** Aspose.BarCode for Java  
- **Která metoda čte PDF417?** `BarCodeReader` with `DecodeType.PDF_417`  
- **Jak jsou turecké znaky zpracovány?** Decode the byte array with the `windows-1254` charset  
- **Potřebuji licenci pro produkci?** Yes – a commercial license is required  
- **Mohu to vyzkoušet zdarma?** A free trial is available from Aspose  

## Co je PDF417 a proč jej používat s tureckými znaky?

PDF417 je vrstvený lineární formát čárového kódu, který může uložit velké množství dat, včetně Unicode textu. Často se používá pro palubní vstupenky, ID karty a logistické štítky. Když zakódovaný text obsahuje turecké znaky (ğ, ş, İ, atd.), musíte dekódovat bajty pomocí správné kódové stránky – jinak se znaky zobrazí poškozeně.

## Předpoklady

Before we dive into the code, make sure you have:

- **Java Development Environment** – JDK 8 nebo vyšší nainstalovaný.  
- **Aspose.BarCode for Java** – Stáhněte knihovnu z oficiálního webu **[here](https://releases.aspose.com/barcode/java/)**.  
- Obrazový soubor (`barcode.png`), který obsahuje PDF417 čárový kód zakódovaný s tureckými znaky.

## Import balíčků

In your Java project, include the necessary packages for working with Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Nastavení projektu PDF417 Barcode Reader Java

### Krok 1: Vytvořte nový Java projekt a přidejte knihovnu

If you haven’t added the Aspose.JAR files yet, download them from **[this link](https://releases.aspose.com/barcode/java/)** and add them to your project’s classpath.

### Krok 2: Načtěte obrázek čárového kódu

Define the path to the folder that holds your barcode image and instantiate the reader:

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

### Krok 3: Přečtěte a dekódujte čárový kód

Iterate through the detected barcodes, convert the raw bytes to a string using the Windows‑1254 charset (the code page for Turkish), and print the result:

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("windows-1254").decode(bytebuf).toString());
}
```

Výše uvedený úryvek čte PDF417 čárový kód a správně zobrazuje turecké znaky jako **ç, ğ, ş, İ**.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Poškozené znaky | Použita špatná znaková sada | Use `windows-1254` for Turkish or `UTF-8` if the barcode was encoded that way |
| Čárový kód nebyl detekován | Nízká kvalita obrázku | Ensure the image is high‑resolution and not blurred |
| `NullPointerException` | Nesprávná cesta k souboru | Verify `dataDir` points to the correct folder |

## Často kladené otázky

### Je Aspose.BarCode kompatibilní s různými typy čárových kódů?

Ano, Aspose.BarCode podporuje širokou škálu typů čárových kódů, včetně PDF417.

### Mohu použít Aspose.BarCode pro komerční projekty?

Rozhodně. Aspose.BarCode nabízí flexibilní licenční model vhodný jak pro osobní, tak pro komerční použití. Navštivte **[here](https://purchase.aspose.com/buy)** a prozkoumejte licenční možnosti.

### Je k dispozici bezplatná zkušební verze?

Ano, můžete získat bezplatnou zkušební verzi **[here](https://releases.aspose.com/)**.

### Jak mohu získat podporu pro Aspose.BarCode?

Navštivte **[Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13)** pro komunitní podporu nebo prozkoumejte dokumentaci **[here](https://reference.aspose.com/barcode/java/)**.

### Mohu během vývoje použít dočasnou licenci?

Ano, můžete získat dočasnou licenci **[here](https://purchase.aspose.com/temporary-license/)**.

### Co když potřebuji dekódovat jiné jazyky?

Zvolte vhodnou znakovou sadu (např. `windows-1252` pro západoevropské jazyky, `UTF-8` pro Unicode) při volání `Charset.forName(...)`.

## Závěr

S Aspose.BarCode pro Java se **jak číst PDF417** čárové kódy obsahující turecké znaky stává jednoduchým úkolem. Nastavením projektu **PDF417 barcode reader Java**, načtením obrázku a dekódováním bajtů pomocí správné znakové sady můžete spolehlivě získat vícejazyčná data pro jakýkoli obchodní proces.

---

**Poslední aktualizace:** 2026-04-23  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}