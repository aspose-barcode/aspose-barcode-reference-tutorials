---
date: 2025-12-25
description: Dowiedz się, jak wyodrębniać tekst z obrazów kodów kreskowych, w szczególności
  PDF417 z chińskimi znakami, używając Aspose.BarCode dla Javy. Postępuj zgodnie z
  naszym przewodnikiem krok po kroku, aby efektywnie odczytywać dane z kodów kreskowych.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Wyodrębnij tekst z kodu kreskowego: chińskie znaki PDF417 w Javie'
url: /pl/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnianie tekstu z kodu kreskowego: chińskie znaki PDF417 w Javie

## Introduction

Integracja rozpoznawania kodów kreskowych w aplikacjach Java to cenna umiejętność, szczególnie gdy musisz **wyodrębnić tekst z kodu kreskowego** z obrazów zawierających dane wielojęzyczne. W tym samouczku przeprowadzimy Cię przez użycie Aspose.BarCode dla Javy do rozpoznawania kodów PDF417 z chińskimi znakami. Po zakończeniu dokładnie wiesz, jak odczytać dane z kodu kreskowego i zdekodować je do czytelnego tekstu.

## Quick Answers
- **Jaką bibliotekę obsługuje PDF417 z chińskimi znakami?** Aspose.BarCode for Java.  
- **Jaki zestaw znaków jest potrzebny do dekodowania chińskiego?** MS936 (GBK).  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak, wymagana jest licencja komercyjna.  
- **Czy mogę uruchomić to na dowolnej wersji Javy?** Działa z Java 8 i nowszymi.  
- **Czy dostępna jest darmowa wersja próbna?** Oczywiście – pobierz ją ze strony Aspose.

## What is “extract text from barcode”?

Wyodrębnianie tekstu z kodu kreskowego oznacza konwersję zakodowanych danych z powrotem do ich pierwotnej, czytelnej dla człowieka formy. Dla kodów PDF417 przechowujących chińskie znaki, wiąże się to również z wyborem właściwego kodowania znaków, aby bajty mapowały się na odpowiednie glify.

## Why use Aspose.BarCode for Java?

Aspose.BarCode zapewnia solidne wsparcie dla szerokiego zakresu symbologii kodów kreskowych, w tym PDF417, i obsługuje złożone zestawy znaków od razu. Abstrahuje niskopoziomowe przetwarzanie obrazu, pozwalając skupić się na logice biznesowej, a nie na szczegółach dekodowania.

## Prerequisites

1. **Java Development Kit (JDK)** – zalecana jest najnowsza wersja.  
2. **Aspose.BarCode for Java** – pobierz go [tutaj](https://releases.aspose.com/barcode/java/).  
3. **Obraz kodu PDF417** zawierający chińskie znaki (np. `barcode.png`).

## Import Packages

W swoim projekcie Java zaimportuj niezbędne klasy do pracy z Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Step 1: Set the Document Directory

Określ folder, w którym znajduje się obraz kodu kreskowego:

```java
String dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` rzeczywistą ścieżką na swoim komputerze.

## Step 2: Load Barcode Image

Utwórz instancję `BarCodeReader`, która wskazuje na plik PNG i informuje czytnik, aby szukał symbologii PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Step 3: Read Barcode

Iteruj przez wyniki wykrywania, wyciągnij surową tablicę bajtów i zdekoduj ją przy użyciu zestawu znaków GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Ta pętla **wyodrębnia tekst z kodu kreskowego** i wypisuje zdekodowane chińskie znaki w konsoli.

## How to read barcode with PDF417?

Powyższy kod demonstruje **jak odczytać dane z kodu kreskowego** krok po kroku:

1. **Zainicjalizuj** czytnik z właściwym `DecodeType`.  
2. **Iteruj** po każdym zwróconym `BarCodeResult`.  
3. **Konwertuj** surowe bajty przy użyciu odpowiedniego zestawu znaków (`MS936` dla chińskiego).  

Jeśli Twój kod kreskowy zawiera inne języki, po prostu zmień zestaw znaków na odpowiadający Twoim danym.

## Common Issues & Solutions

| Problem | Rozwiązanie |
|-------|----------|
| Zniekształcone znaki po dekodowaniu | Sprawdź, czy używasz właściwego zestawu znaków (`MS936` dla GBK). |
| Nie wykryto kodu kreskowego | Upewnij się, że jakość obrazu jest wysoka i kod nie jest obrócony; w razie potrzeby możesz wstępnie przetworzyć obraz. |
| Zwrócono wiele wyników | PDF417 może przechowywać wiele segmentów; iteruj przez wszystkie wyniki, jak pokazano. |

## Frequently Asked Questions (FAQs)

### Can I use Aspose.BarCode for Java in commercial projects?
Tak, możesz używać Aspose.BarCode dla Javy w projektach komercyjnych. Szczegóły licencjonowania znajdziesz [tutaj](https://purchase.aspose.com/buy).

### Is there a free trial available?
Tak, możesz uzyskać darmową wersję próbną Aspose.BarCode dla Javy [tutaj](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode?
Odwiedź forum Aspose.BarCode [tutaj](https://forum.aspose.com/c/barcode/13), aby uzyskać wsparcie lub zadać pytania.

### Can I obtain a temporary license for testing purposes?
Tak, możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Where can I find the documentation?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/barcode/java/).

**Additional Q&A**

**Q: Co jeśli mój obraz kodu kreskowego jest w formacie JPEG?**  
A: `BarCodeReader` działa z formatami JPEG, PNG, BMP i innymi popularnymi formatami obrazów — wystarczy odpowiednio zmienić rozszerzenie pliku.

**Q: Czy mogę dekodować kody kreskowe ze strumienia zamiast z pliku?**  
A: Tak, możesz przekazać `InputStream` do konstruktora `BarCodeReader` w celu dekodowania w locie.

**Q: Czy Aspose.BarCode obsługuje inne zestawy znaków?**  
A: Oczywiście. Użyj `Charset.forName("<your‑charset>")`, aby dekodować bajty dla UTF‑8, ISO‑8859‑1 itp.

## Conclusion

Teraz wiesz, jak **wyodrębnić tekst z obrazów kodów kreskowych**, konkretnie kodów PDF417 zawierających chińskie znaki, używając Aspose.BarCode dla Javy. Ta możliwość otwiera drzwi do wielojęzycznych systemów inwentaryzacji, automatyzacji dokumentów i nie tylko. Śmiało eksperymentuj z innymi symbologiami i zestawami znaków, aby rozszerzyć zasięg swojej aplikacji.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}