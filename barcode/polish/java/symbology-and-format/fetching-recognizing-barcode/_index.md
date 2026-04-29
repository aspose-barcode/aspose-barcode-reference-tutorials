---
date: 2026-04-29
description: Dowiedz się, jak odczytywać kody kreskowe w Javie przy użyciu Aspose.BarCode.
  Ten samouczek pokazuje przykład czytnika kodów kreskowych, który pobiera i rozpoznaje
  obrazy kodów kreskowych z bazy danych.
keywords:
- read barcode java
- barcode reader example
- java barcode library
- read barcode image
- recognize barcode image
linktitle: Pobieranie i rozpoznawanie kodu kreskowego
second_title: Aspose.BarCode Java API
title: Odczyt kodów kreskowych w Javie – Pobieranie i rozpoznawanie kodów kreskowych
  przy użyciu Aspose
url: /pl/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczytaj kod kreskowy Java – Pobierz i rozpoznaj kody kreskowe

## Wprowadzenie

Jeśli potrzebujesz szybko **read barcode java** aplikacje, Aspose.BarCode for Java oferuje prosty, wysokowydajny sposób na pobranie obrazów kodów kreskowych z bazy danych i ich rozpoznanie w zaledwie kilku linijkach kodu. W tym samouczku przeprowadzimy Cię przez kompletny, rzeczywisty przykład, który pokazuje, jak połączyć się z bazą danych, wyodrębnić obraz kodu kreskowego i użyć czytnika Aspose do jego dekodowania. Po zakończeniu będziesz mieć fragment kodu, który możesz wstawić do dowolnego projektu Java.

## Szybkie odpowiedzi
- **Co robi biblioteka?** Odczytuje obrazy kodów kreskowych (np. Code 39) bezpośrednio z plików lub strumieni.  
- **Jakie główne słowo kluczowe jest celem?** read barcode java  
- **Czy potrzebuję licencji do testowania?** Dostępna jest tymczasowa licencja do oceny.  
- **Jaki typ bazy danych jest pokazany?** Przykład używa MySQL, ale kod działa z dowolną bazą kompatybilną z JDBC.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowej integracji.

## Co to jest „read barcode java”?
Odczytanie kodu kreskowego w Javie oznacza wczytanie obrazu zawierającego wzór kodu kreskowego i użycie silnika dekodującego do przetłumaczenia tego wzoru na pierwotny ciąg danych. Aspose.BarCode dostarcza solidny dekoder obsługujący dziesiątki symbologii, w tym Code 39, QR i DataMatrix.

## Dlaczego warto używać biblioteki kodów kreskowych Java od Aspose?
- **Szerokie wsparcie symbologii** – ponad 150 typów kodów kreskowych od razu.  
- **Brak zewnętrznych zależności** – czysta Java, działa na każdej platformie z JDK 8+.  
- **Wysoka dokładność** – zoptymalizowane algorytmy zmniejszają liczbę błędnych odczytów, nawet na niskiej jakości obrazach.  
- **Proste API** – kilka linijek kodu zamienia surowy obraz w czytelny tekst.

## Wymagania wstępne
- Podstawowa znajomość programowania w Javie.  
- Biblioteka Aspose.BarCode for Java (pobierz ją **[here](https://releases.aspose.com/barcode/java/)**).  
- Dostęp do bazy danych przechowującej obrazy kodów kreskowych jako BLOBy.  
- Zainstalowany JDK 8 lub nowszy na maszynie deweloperskiej.

## Importowanie pakietów

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## Krok 1: Nawiązanie połączenia z bazą danych

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

// Open a connection to the database
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## Krok 2: Wykonanie zapytania SQL

```java
// Create a statement to execute the SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## Krok 3: Pobranie i utworzenie obrazów

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

## Krok 4: Odczyt kodu kreskowego z obrazu

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

## Typowe problemy i rozwiązania
- **NullPointerException przy odczycie BLOBów** – Upewnij się, że nazwa kolumny jest dokładnie zgodna i że BLOB faktycznie zawiera dane.  
- **Nieobsługiwany typ kodu kreskowego** – Sprawdź, czy `DecodeType` odpowiada symbologii przechowywanej w obrazie; dla kodów QR użyj `DecodeType.QR`.  
- **Błędy uprawnień ścieżki pliku** – Ścieżka `strBarCodeImage` musi być zapisywalna przez proces Java; w razie potrzeby użyj katalogu tymczasowego.  

## Najczęściej zadawane pytania

**P: Czy Aspose.BarCode jest kompatybilny ze wszystkimi typami kodów kreskowych?**  
O: Tak, obsługuje szeroką gamę symbologii kodów kreskowych, w tym CODE_39_STANDARD, QR Code, DataMatrix i wiele innych. Zapoznaj się z dokumentacją produktu, aby zobaczyć pełną listę.

**P: Czy mogę używać Aspose.BarCode z różnymi bazami danych?**  
O: Oczywiście. Przykład używa MySQL, ale możesz przejść na PostgreSQL, SQL Server lub dowolną bazę kompatybilną z JDBC, aktualizując klasę sterownika i ciąg połączenia.

**P: Jak powinienem obsługiwać błędy podczas rozpoznawania kodu kreskowego?**  
O: Owiń logikę odczytu w blok try‑catch (jak pokazano) i zaloguj komunikat wyjątku. Rozważ ponowne próby przy przejściowych błędach I/O oraz sprawdź, czy plik obrazu istnieje przed dekodowaniem.

**P: Czy biblioteka jest odpowiednia dla aplikacji o dużej skali?**  
O: Tak. Aspose.BarCode jest zaprojektowany do scenariuszy o wysokiej przepustowości; możesz ponownie używać jednej instancji `BarCodeReader` w wielu wątkach w razie potrzeby.

**P: Gdzie mogę uzyskać tymczasową licencję do testów?**  
O: Tymczasową licencję możesz uzyskać **[here](https://purchase.aspose.com/temporary-license/)** do celów oceny.

---

**Ostatnia aktualizacja:** 2026-04-29  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}