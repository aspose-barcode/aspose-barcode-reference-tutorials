---
date: 2026-05-04
description: Dowiedz się, jak utworzyć kod Data Matrix przy użyciu biblioteki Java
  do generowania kodów kreskowych i ustawić położenie tekstu kodu powyżej symbolu
  za pomocą Aspose.BarCode. Skorzystaj z naszego krok po kroku przykładu generowania
  kodu kreskowego.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Ustawienie lokalizacji tekstu kodu
second_title: Aspose.BarCode Java API
title: Utwórz kod Data Matrix przy użyciu biblioteki Java Barcode i ustaw położenie
  tekstu kodu
url: /pl/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy Data Matrix przy użyciu biblioteki Java Barcode i ustaw lokalizację tekstu kodu

## Wprowadzenie

Jeśli tworzysz system inwentaryzacji, wysyłki lub śledzenia w Javie, szybko odkryjesz, że niezawodna **java barcode library** jest niezbędna. Dzięki **Aspose.BarCode for Java** możesz wygenerować **kod kreskowy Data Matrix** w zaledwie kilku linijkach kodu i w pełni kontrolować układ wizualny, w tym miejsce, w którym pojawia się tekst czytelny dla człowieka. W tym samouczku przeprowadzimy Cię przez kompletny **przykład generowania kodu kreskowego**, pokażemy, jak **dostosować położenie tekstu kodu kreskowego**, i wyjaśnimy, dlaczego umieszczenie tekstu nad symbolem może poprawić użyteczność.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.BarCode for Java  
- **Jaki typ kodu kreskowego jest pokazany?** Data Matrix  
- **Jak ustawić tekst kodu?** Używając `CodeLocation.ABOVE` (można także użyć `BELOW`)  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna  
- **Czy kod może działać na Java 8+?** Absolutnie, obsługuje Java 8 i nowsze  

## Czym jest biblioteka Java barcode?
**Java barcode library** dostarcza programistom gotowe API do tworzenia, odczytywania i stylizacji kodów kreskowych 1‑D i 2‑D bezpośrednio z aplikacji Java. Abstrahuje skomplikowane zasady kodowania i pozwala skupić się na logice biznesowej zamiast na niskopoziomowym przetwarzaniu obrazu.

## Dlaczego używać biblioteki Java barcode do przykładu generowania kodów kreskowych?
- **Szybkość:** Generuj wysokiej jakości kody kreskowe w milisekundach.  
- **Niezawodność:** Wbudowana zgodność ze standardami ISO/IEC.  
- **Elastyczność:** Pełna kontrola nad rozmiarem, kolorem, marginesami i **tekst kodu kreskowego** rozmieszczeniem.  
- **Wieloplatformowość:** Działa w każdym środowisku opartym na JVM, od aplikacji desktopowych po usługi w chmurze.

## Czym jest kod kreskowy Data Matrix?
Kod kreskowy Data Matrix to dwuwymiarowy (2‑D) symbol, który przechowuje duże ilości danych w zwartym kwadratowym lub prostokątnym wzorze. Jest szeroko stosowany do znakowania małych przedmiotów, elektroniki i wyrobów medycznych, ponieważ może zakodować do 2 335 znaków alfanumerycznych.

## Dlaczego ustawiać lokalizację tekstu kodu kreskowego?
Umieszczenie tekstu czytelnego dla człowieka **nad**, **pod** lub **obok** kodu kreskowego pomaga użytkownikom szybko zweryfikować zakodowane dane bez skanowania. Dostosowanie lokalizacji tekstu poprawia spójność interfejsu, spełnia wytyczne brandingowe i może zmniejszyć liczbę błędów przy ręcznym wprowadzaniu danych.

## Wymagania wstępne

- Podstawowa znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK).  
- IDE, takie jak Eclipse lub IntelliJ IDEA.  
- Biblioteka Aspose.BarCode for Java (pobierz ją z [here](https://releases.aspose.com/barcode/java/)).  

## Importowanie pakietów

Najpierw zaimportuj niezbędne klasy Aspose.BarCode do swojego projektu:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Te importy dają dostęp do generatora kodów kreskowych oraz wyliczenia kontrolującego położenie tekstu.

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj ścieżki katalogów
Określ, gdzie chcesz odczytywać/zapisywać pliki. Zastąp symbole zastępcze rzeczywistymi ścieżkami na swoim komputerze.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Krok 2: Utwórz instancję BarcodeGenerator
Zainicjuj `BarcodeGenerator` z typem **Data Matrix** i podaj tekst kodu, który chcesz zakodować.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Krok 3: Ustaw lokalizację tekstu kodu kreskowego (dostosuj tekst kodu kreskowego)
Użyj wyliczenia `CodeLocation`, aby przenieść tekst czytelny dla człowieka. W tym przykładzie umieszczamy go **nad** kodem kreskowym.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro tip:** Aby umieścić tekst **pod** symbolem, po prostu zmień `CodeLocation.ABOVE` na `CodeLocation.BELOW`.

### Krok 4: Zapisz wygenerowany obraz kodu kreskowego
Na koniec zapisz obraz kodu kreskowego na dysku. Plik będzie zawierał symbol Data Matrix z tekstem umieszczonym nad nim.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Typowe problemy i rozwiązania
- **Tekst się nie wyświetla:** Upewnij się, że używasz wersji Aspose.BarCode obsługującej `CodeLocation`.  
- **Błędy ścieżki pliku:** Sprawdź, czy `dataDir` kończy się separatorem plików (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Nieobsługiwane znaki:** Data Matrix może kodować tylko ograniczony zestaw znaków; unikaj specjalnych symboli nieobecnych w standardzie ISO/IEC 16022.  

## Najczęściej zadawane pytania (FAQ)

### P: Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?
A: Tak, Aspose.BarCode oferuje rozbudowane opcje dostosowywania, pozwalając kontrolować kolory, marginesy i style czcionek.

### P: Czy Aspose.BarCode jest kompatybilny z Java 8 i późniejszymi wersjami?
A: Absolutnie, biblioteka działa z Java 8 i wszystkimi późniejszymi wydaniami.

### P: Jak mogę zintegrować Aspose.BarCode z istniejącym projektem Java?
A: Dodaj pliki JAR Aspose.BarCode do ścieżki klas projektu, zaimportuj wymagane pakiety i możesz od razu generować kody kreskowe.

### P: Czy dostępna jest wersja próbna Aspose.BarCode?
A: Tak, możesz poznać możliwości Aspose.BarCode, uzyskując darmową wersję próbną [here](https://releases.aspose.com/).

### P: Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.BarCode?
A: Odwiedź [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) w celu uzyskania pomocy społeczności i oficjalnego wsparcia.

## Dodatkowe często zadawane pytania

**P: Czy mogę wygenerować kod kreskowy z tekstem umieszczonym pod symbolem?**  
A: Tak, ustaw `CodeLocation.BELOW` w tej samej metodzie `setLocation`.

**P: Czy biblioteka obsługuje inne kody 2‑D, takie jak QR Code?**  
A: Absolutnie, po prostu zmień `EncodeTypes.DATA_MATRIX` na `EncodeTypes.QR`.

**P: Jak zmienić rozmiar czcionki tekstu kodu kreskowego?**  
A: Użyj `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy Data Matrix** w Javie przy użyciu **java barcode library** i precyzyjnie kontrolować **ustawienie tekstu kodu kreskowego** za pomocą Aspose.BarCode. Eksperymentuj z innymi wartościami `CodeLocation`, ustawieniami czcionek i opcjami kolorów, aby dopasować je do wymagań projektu.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}