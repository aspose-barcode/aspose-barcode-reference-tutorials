---
date: 2026-04-29
description: Naučte se číst čárové kódy v Javě pomocí Aspose.BarCode. Tento tutoriál
  ukazuje příklad čtečky čárových kódů pro načtení a rozpoznání obrázků čárových kódů
  z databáze.
keywords:
- read barcode java
- barcode reader example
- java barcode library
- read barcode image
- recognize barcode image
linktitle: Načítání a rozpoznávání čárového kódu
second_title: Aspose.BarCode Java API
title: Čtení čárových kódů v Javě – Načtěte a rozpoznávejte čárové kódy pomocí Aspose
url: /cs/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení čárových kódů v Javě – Načtení a rozpoznání čárových kódů

## Úvod

Pokud potřebujete rychle **read barcode java** aplikace, Aspose.BarCode for Java nabízí jednoduchý, výkonný způsob, jak načíst obrázky čárových kódů z databáze a rozpoznat je během několika řádků kódu. V tomto tutoriálu projdeme kompletním, reálným příkladem, který ukazuje, jak se připojit k databázi, extrahovat obrázek čárového kódu a použít čtečku čárových kódů Aspose k jeho dekódování. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do jakéhokoli Java projektu.

## Rychlé odpovědi
- **Co knihovna dělá?** It reads barcode images (e.g., Code 39) directly from files or streams.  
- **Jaké primární klíčové slovo je cíleno?** read barcode java  
- **Potřebuji licenci pro testování?** A temporary license is available for evaluation.  
- **Jaký typ databáze je ukázán?** The example uses MySQL, but the code works with any JDBC‑compatible database.  
- **Jak dlouho trvá implementace?** Roughly 10‑15 minutes for a basic integration.

## Co je “read barcode java”?
Čtení čárového kódu v Javě znamená načtení obrázku, který obsahuje vzor čárového kódu, a použití dekódovacího enginu k překladu tohoto vzoru do původního datového řetězce. Aspose.BarCode poskytuje robustní dekodér, který podporuje desítky symbologií, včetně Code 39, QR a DataMatrix.

## Proč použít Java knihovnu čárových kódů od Aspose?
- **Broad symbology support** – over 150 barcode types out of the box. → Široká podpora symbologií – více než 150 typů čárových kódů ihned po instalaci.  
- **No external dependencies** – pure Java, works on any platform with JDK 8+. → Žádné externí závislosti – čistá Java, funguje na jakékoli platformě s JDK 8+.  
- **High accuracy** – optimized algorithms reduce false reads, even on low‑quality images. → Vysoká přesnost – optimalizované algoritmy snižují chybné čtení i u nízkokvalitních obrázků.  
- **Simple API** – a few lines of code turn a raw image into readable text. → Jednoduché API – několik řádků kódu převádí surový obrázek na čitelný text.

## Požadavky
- Základní znalost programování v Javě.  
- Aspose.BarCode for Java knihovna (stáhněte ji **[here](https://releases.aspose.com/barcode/java/)**).  
- Přístup k databázi, která ukládá obrázky čárových kódů jako BLOBy.  
- JDK 8 nebo novější nainstalované na vašem vývojovém počítači.

## Importovat balíčky

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## Krok 1: Navázání připojení k databázi

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

// Open a connection to the database
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## Krok 2: Spuštění SQL dotazu

```java
// Create a statement to execute the SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## Krok 3: Načtení a vytvoření obrázků

```java
while (rs.next()) {
    // Read BLOB field and create an image from it
    String len1 = rs.getString("BarCodeImage");
    int len = len1.length();
    byte[] b = new byte[len];
    InputStream in = rs.getBinaryStream("BarCodeImage");

    int index = in.read(b, 0, len);
    OutputStream outImgBarCode = new FileOutputStream(strBarCodeImage);

    while (index != -1) {
        // Write bytes to file
        outImgBarCode.write(b, 0, index);
        // Read next bytes
        index = in.read(b, 0, len);
    }
    outImgBarCode.close();
```

## Krok 4: Čtení čárového kódu z obrázku

```java
// Read the barcode from the image
BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_STANDARD);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}

nCount++;
}

System.out.println(nCount + " records found.");
con.close();
} catch (Exception ex) {
System.out.println(ex.getMessage());
}
```

## Časté problémy a řešení
- **NullPointerException při čtení BLOBů** – Ensure the column name matches exactly and that the BLOB actually contains data.  
- **Není podporovaný typ čárového kódu** – Verify the `DecodeType` matches the symbology stored in the image; for QR codes use `DecodeType.QR`.  
- **Chyby oprávnění cesty k souboru** – The `strBarCodeImage` path must be writable by the Java process; use a temporary directory if needed.  

## Často kladené otázky

**Q: Je Aspose.BarCode kompatibilní se všemi typy čárových kódů?**  
A: Ano, podporuje širokou škálu symbologií čárových kódů, včetně CODE_39_STANDARD, QR Code, DataMatrix a mnoha dalších. Viz dokumentace produktu pro úplný seznam.

**Q: Mohu použít Aspose.BarCode s různými databázemi?**  
A: Rozhodně. Příklad používá MySQL, ale můžete přejít na PostgreSQL, SQL Server nebo jakoukoli JDBC‑kompatibilní databázi úpravou třídy ovladače a připojovacího řetězce.

**Q: Jak mám zacházet s chybami během rozpoznávání čárových kódů?**  
A: Zabalte logiku čtení do bloku try‑catch (jak je ukázáno) a zaznamenejte zprávu výjimky. Zvažte opakování při přechodných I/O chybách a ověřte, že soubor obrázku existuje před dekódováním.

**Q: Je knihovna vhodná pro rozsáhlé aplikace?**  
A: Ano. Aspose.BarCode je navržena pro scénáře s vysokou propustností; můžete znovu použít jedinou instanci `BarCodeReader` napříč více vlákny, pokud je to potřeba.

**Q: Kde mohu získat dočasnou licenci pro testování?**  
A: Dočasnou licenci můžete získat **[here](https://purchase.aspose.com/temporary-license/)** pro evaluační účely.

---

**Poslední aktualizace:** 2026-04-29  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}