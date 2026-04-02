---
date: 2025-12-27
description: Dowiedz się, jak tworzyć kod Data Matrix i jak ustawić położenie tekstu
  kodu kreskowego w Javie przy użyciu Aspose.BarCode. Skorzystaj z naszego przewodnika
  krok po kroku, aby uzyskać pełną personalizację.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Utwórz kod kreskowy Data Matrix i ustaw położenie tekstu kodu w Javie
url: /pl/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie kodu kreskowego Data Matrix i ustawianie położenia tekstu kodu w Javie

## Wprowadzenie

Generowanie kodów kreskowych to rutynowe wymaganie w systemach inwentaryzacji, wysyłki i wielu innych aplikacjach opartych na Javie. Dzięki **Aspose.BarCode for Java** możesz **tworzyć kod kreskowy Data Matrix** szybko oraz kontrolować każdy aspekt wizualny, w tym miejsce, w którym pojawia się tekst czytelny dla człowieka. W tym samouczku przeprowadzimy Cię krok po kroku przez **tworzenie kodu kreskowego Data Matrix** oraz pokażemy **jak ustawić tekst kodu** nad symbolem, aby spełniał Twoje wymagania projektowe.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.BarCode for Java  
- **Jaki typ kodu kreskowego jest demonstrowany?** Data Matrix  
- **Jak pozycjonować tekst kodu?** Używając `CodeLocation.ABOVE`  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna  
- **Czy kod działa na Java 8+?** Oczywiście, obsługuje Java 8 i nowsze wersje  

## Co to jest kod kreskowy Data Matrix?
Kod kreskowy Data Matrix to dwuwymiarowy (2‑D) symbol, który przechowuje duże ilości danych w zwartym, kwadratowym lub prostokątnym wzorze. Jest szeroko stosowany do znakowania małych przedmiotów, elektroniki i wyrobów medycznych, ponieważ może zakodować do 2 335 znaków alfanumerycznych.

## Dlaczego ustawiać położenie tekstu kodu?
Umieszczenie tekstu czytelnego dla człowieka **nad**, **pod** lub **obok** kodu kreskowego pomaga użytkownikom szybko zweryfikować zakodowane dane bez skanowania. Dostosowanie położenia tekstu poprawia spójność interfejsu użytkownika i spełnia wytyczne brandingowe.

## Wymagania wstępne

- Podstawowa znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK).  
- IDE, takie jak Eclipse lub IntelliJ IDEA.  
- Biblioteka Aspose.BarCode for Java (pobierz ją z [tutaj](https://releases.aspose.com/barcode/java/)).  

## Importowanie pakietów

Najpierw zaimportuj niezbędne klasy Aspose.BarCode do swojego projektu:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Te importy dają dostęp do generatora kodów kreskowych oraz wyliczenia kontrolującego położenie tekstu.

## Przewodnik krok po kroku

### Krok 1: Definiowanie ścieżek katalogów
Określ, gdzie chcesz odczytywać/zapisywać pliki. Zamień symbole zastępcze na rzeczywiste ścieżki w swoim systemie.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Krok 2: Utworzenie instancji BarcodeGenerator
Zainicjuj `BarcodeGenerator` z typem **Data Matrix** i podaj tekst kodu, który ma zostać zakodowany.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Krok 3: Jak ustawić położenie tekstu kodu
Użyj wyliczenia `CodeLocation`, aby przenieść tekst czytelny dla człowieka. W tym przykładzie umieszczamy go **nad** kodem kreskowym.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Krok 4: Zapis wygenerowanego obrazu kodu kreskowego
Na koniec zapisz obraz kodu kreskowego na dysku. Plik będzie zawierał symbol Data Matrix z tekstem umieszczonym nad nim.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Typowe problemy i rozwiązania
- **Tekst się nie wyświetla:** Upewnij się, że używasz wersji Aspose.BarCode obsługującej `CodeLocation`.  
- **Błędy ścieżki pliku:** Sprawdź, czy `dataDir` kończy się separatorem plików (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Nieobsługiwane znaki:** Data Matrix może kodować tylko ograniczony zestaw znaków; unikaj specjalnych symboli nieobecnych w standardzie ISO/IEC 16022.

## Najczęściej zadawane pytania (FAQ)

### Q: Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?
A: Tak, Aspose.BarCode oferuje rozbudowane opcje personalizacji, pozwalając kontrolować kolory, marginesy i style czcionek.

### Q: Czy Aspose.BarCode jest kompatybilny z Java 8 i późniejszymi wersjami?
A: Oczywiście, biblioteka działa z Java 8 oraz wszystkimi kolejnymi wydaniami.

### Q: Jak włączyć Aspose.BarCode do istniejącego projektu Java?
A: Dodaj pliki JAR Aspose.BarCode do ścieżki klas projektu, zaimportuj wymagane pakiety i możesz od razu generować kody kreskowe.

### Q: Czy dostępna jest wersja próbna Aspose.BarCode?
A: Tak, możliwości Aspose.BarCode możesz wypróbować, pobierając darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Q: Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.BarCode?
A: Odwiedź [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), aby uzyskać pomoc społeczności oraz oficjalne wsparcie.

## Dodatkowe pytania FAQ

**Q: Czy mogę wygenerować kod kreskowy z tekstem umieszczonym pod symbolem?**  
A: Tak, ustaw `CodeLocation.BELOW` w tej samej metodzie `setLocation`.

**Q: Czy biblioteka obsługuje inne kody 2‑D, takie jak QR Code?**  
A: Oczywiście, wystarczy zamienić `EncodeTypes.DATA_MATRIX` na `EncodeTypes.QR`.

**Q: Jak zmienić rozmiar czcionki tekstu kodu kreskowego?**  
A: Użyj `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Zakończenie

Teraz wiesz, jak **tworzyć kod kreskowy Data Matrix** w Javie i precyzyjnie kontrolować **ustawienie tekstu kodu** przy użyciu Aspose.BarCode. Eksperymentuj z innymi wartościami `CodeLocation` oraz opcjami stylizacji, aby dopasować je do wymagań swojego projektu.

---

**Ostatnia aktualizacja:** 2025-12-27  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}