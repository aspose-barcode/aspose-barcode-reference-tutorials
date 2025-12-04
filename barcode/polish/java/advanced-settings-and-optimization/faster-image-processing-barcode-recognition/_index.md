---
date: 2025-12-04
description: Dowiedz się, jak ustawić tryb wysokiej wydajności i jak szybko odczytywać
  kody kreskowe za pomocą wysokowydajnego czytnika kodów kreskowych z Aspose.BarCode
  dla Javy.
language: pl
linktitle: Faster Image Processing for Barcode Recognition
second_title: Aspose.BarCode Java API
title: 'Wysokowydajny czytnik kodów kreskowych: szybsze przetwarzanie obrazu dla rozpoznawania
  kodów kreskowych w Javie z Aspose.BarCode'
url: /java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Czytnik kodów kreskowych o wysokiej wydajności: szybsze przetwarzanie obrazu dla rozpoznawania kodów w Javie z Aspose.BarCode

We współczesnych aplikacjach Java, **czytnik kodów kreskowych o wysokiej wydajności** jest niezbędny, aby sprostać wymaganiom skanowania w czasie rzeczywistym. Gdy potrzebujesz **jak odczytać kod kreskowy** szybko i niezawodnie, Aspose.BarCode dla Javy dostarcza narzędzia przyspieszające przetwarzanie obrazu bez utraty dokładności. W tym przewodniku przeprowadzimy Cię krok po kroku przez włączenie trybu wysokiej wydajności, dopasowanie ustawień jakości i osiągnięcie szybszego rozpoznawania kodów.

## Szybkie odpowiedzi
- **Co oznacza „czytnik kodów kreskowych o wysokiej wydajności”?** To konfiguracja maksymalizująca szybkość skanowania poprzez optymalizację algorytmów przetwarzania obrazu.  
- **Jaką symbologię kodu kreskowego użyto w przykładzie?** DataMatrix (typ kodu 2‑D).  
- **Jak włączyć tryb wysokiej wydajności?** Wywołaj `reader.setQualitySettings(QualitySettings.getHighPerformance())`.  
- **Czy potrzebna jest licencja do produkcji?** Tak, komercyjna licencja jest wymagana do użytku nie‑testowego.  
- **Jaką wersję Javy obsługuje?** Java 8 lub nowsza jest w pełni wspierana.

## Co to jest Czytnik kodów kreskowych o wysokiej wydajności?
**Czytnik kodów kreskowych o wysokiej wydajności** to specjalnie dostrojona instancja silnika Aspose.BarCode, która zmniejsza narzut przetwarzania, stosuje agresywny wstępny processing obrazu i przyspiesza pętlę dekodowania. Jest to idealne rozwiązanie dla scenariuszy takich jak stacje skanowania o dużej przepustowości, aplikacje mobilne czy przetwarzanie wsadowe dużych zestawów obrazów.

## Dlaczego warto używać trybu wysokiej wydajności Aspose.BarCode?
- **Szybkość:** Do 2‑3× szybsze dekodowanie w porównaniu z ustawieniami domyślnymi.  
- **Skalowalność:** Obsługuje tysiące obrazów na minutę na skromnym sprzęcie.  
- **Dokładność:** Utrzymuje wysokie wskaźniki rozpoznawania dzięki automatycznemu stosowaniu medianowego wygładzania i innym optymalizacjom.  
- **Elastyczność:** Nadal możesz dostosować poszczególne ustawienia jakości do konkretnych przypadków użycia.

## Wymagania wstępne
- **Środowisko programistyczne Java:** JDK 8 lub nowszy, ulubione IDE (IntelliJ, Eclipse itp.).  
- **Aspose.BarCode dla Javy:** Pobierz najnowszy plik JAR ze [strony pobierania Aspose.BarCode](https://releases.aspose.com/barcode/java/).  

## Importowanie przestrzeni nazw

Zanim rozpoczniesz, zaimportuj potrzebne klasy:

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.QualitySettings;
```

## Krok 1: Ustaw katalog zasobów

Zdefiniuj folder zawierający przykładowe obrazy.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(FasterImageProcessingForBarcodeRecognition.class) + "BarcodeReader/advanced_features/";
```

## Krok 2: Wybierz obraz zawierający kod kreskowy

Wskaż czytnikowi obraz, który ma zostać zdekodowany. W tym przykładzie używamy obrazu DataMatrix.

```java
// Read code39 barcode from image
String imageFilePath = dataDir + "datamatrix.bmp";
```

## Krok 3: Utwórz instancję BarCodeReader

Zainicjuj `BarCodeReader` podając ścieżkę do obrazu oraz oczekiwaną symbologię.

```java
// Create an instance of BarCodeReader and set image and symbology type to recognize
BarCodeReader reader = new BarCodeReader(imageFilePath, DecodeType.DATA_MATRIX);
```

## Krok 4: Włącz tryb wysokiej wydajności

Aktywuj wbudowaną konfigurację wysokiej wydajności. To jest sedno konfiguracji **czytnika kodów kreskowych o wysokiej wydajności**.

```java
// Set high performance mode
reader.setQualitySettings(QualitySettings.getHighPerformance());
```

## Krok 5: Dostosuj poszczególne opcje (opcjonalnie)

Nadal możesz regulować indywidualne ustawienia jakości, aby dopasować je do charakterystyki obrazu. Włączenie medianowego wygładzania często poprawia wyniki na szumnych obrazach.

```java
// Set separate options
reader.getQualitySettings().setAllowMedianSmoothing(true);
reader.getQualitySettings().setMedianSmoothingWindowSize(4);
```

## Krok 6: Rozpoznaj kod kreskowy z obrazu

Uruchom czytnik i wypisz zdekodowaną informację. To ostatni element procesu **jak odczytać kod kreskowy**.

```java
// Try to recognize the barcode from the image
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("BarCode CodeText: " + result.getCodeText());
    System.out.println("BarCode CodeType: " + result.getCodeTypeName());
}
```

Postępując zgodnie z tymi krokami, uzyskasz **czytnik kodów kreskowych o wysokiej wydajności**, który potrafi szybko i niezawodnie przetwarzać obrazy.

## Typowe problemy i rozwiązania
- **Nie wykryto kodu kreskowego:** Sprawdź, czy ścieżka do obrazu jest prawidłowa i czy kod nie jest obrócony o więcej niż 45°. Rozważ zwiększenie `MedianSmoothingWindowSize`.  
- **Niska wydajność mimo trybu wysokiej wydajności:** Upewnij się, że używasz najnowszego pliku JAR Aspose.BarCode; starsze wersje mogą nie zawierać poprawek wydajnościowych.  
- **Nieobsługiwana symbologia:** Zweryfikuj, czy `DecodeType`, który przekazujesz, odpowiada kodowi w obrazie.

## Najczęściej zadawane pytania

**P: Czy Aspose.BarCode jest kompatybilny z różnymi symbologiami kodów kreskowych?**  
O: Tak, obsługuje szeroką gamę symbologii 1‑D i 2‑D, w tym Code128, QR Code, DataMatrix i wiele innych.

**P: Czy mogę używać Aspose.BarCode zarówno do generowania, jak i rozpoznawania kodów?**  
O: Oczywiście. Biblioteka oferuje pełnoprawne API do tworzenia i odczytywania kodów w aplikacjach Java.

**P: Czy dostępne są różne opcje licencjonowania Aspose.BarCode?**  
O: Tak, różne plany licencyjne można przeglądać na [stronie zakupu Aspose.BarCode](https://purchase.aspose.com/buy).

**P: Czy istnieje darmowa wersja próbna Aspose.BarCode dla Javy?**  
O: Tak, w pełni funkcjonalną wersję próbną można pobrać ze [strony wydań Aspose](https://releases.aspose.com/).

**P: Jak mogę uzyskać wsparcie lub dołączyć do społeczności?**  
O: Odwiedź oficjalne [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), gdzie znajdziesz pomoc, przykłady i dyskusje społeczności.

---

**Ostatnia aktualizacja:** 2025-12-04  
**Testowano z:** Aspose.BarCode 24.12 dla Javy  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
