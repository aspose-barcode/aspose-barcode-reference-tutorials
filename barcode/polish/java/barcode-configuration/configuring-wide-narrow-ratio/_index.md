---
date: 2026-02-12
description: Dowiedz się, jak tworzyć kod kreskowy code128 z niestandardowym stosunkiem
  szeroko‑wąski w Javie przy użyciu Aspose.BarCode i efektywnie generować obrazy PNG
  kodów kreskowych. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Jak utworzyć kod kreskowy CODE_128 z proporcją szerokość‑wąskość w Javie
url: /pl/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy CODE_128 z proporcją szerokie‑wąskie w Javie

## Wstęp

Jeśli potrzebujesz **utworzyć kod kreskowy code128** z precyzyjnymi proporcjami wizualnymi, kluczem jest regulacja proporcji szerokie‑wąskie. W tym samouczku przeprowadzimy Cię krok po kroku przez **proces tworzenia kodu kreskowego** przy użyciu Aspose.BarCode for Java, pokazując, jak skonfigurować proporcję, **generować obrazy kodu kreskowego PNG** oraz **zapisać obraz kodu kreskowego** na dysku. Niezależnie od tego, czy tworzysz etykiety magazynowe, znaczniki wysyłkowe, czy jakąkolwiek aplikację wymagającą niestandardowo stylizowanego kodu kreskowego CODE_128, znajdziesz tutaj wszystko, czego potrzebujesz.

## Szybkie odpowiedzi
- **Czym jest proporcja szerokie‑wąskie?** Kontroluje względną szerokość szerokich pasków w stosunku do wąskich pasków w kodzie kreskowym.  
- **Które symbole obsługują regulację proporcji?** Większość symboli 1‑D, w tym CODE_128, pozwala ustawić własną proporcję.  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna, ale do użytku produkcyjnego wymagana jest licencja komercyjna.  
- **Czy mogę wygenerować obraz kodu kreskowego w formacie PNG?** Tak — użyj `generator.save(...)`, aby generować obrazy kodu kreskowego PNG.  
- **Czy kod jest kompatybilny z Java 8+?** Absolutnie; Aspose.BarCode działa ze wszystkimi nowoczesnymi wersjami Javy.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz następujące elementy:

- Zainstalowany Java Development Kit (JDK) na swoim komputerze.  
- Bibliotekę Aspose.BarCode for Java. Pobierz ją z [download link](https://releases.aspose.com/barcode/java/).

## Importowanie pakietów

Aby rozpocząć, zaimportuj niezbędną klasę Aspose.BarCode do swojego projektu.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Co to jest proporcja szerokie‑wąskie i dlaczego ją regulować?

Proporcja szerokie‑wąskie określa, jak grube wydają się „szerokie” paski w porównaniu do „wąskich”. Regulacja tej proporcji może poprawić czytelność przez skaner, spełnić określone standardy druku lub po prostu dopasować się do wizualnego stylu marki.

## Jak utworzyć kod kreskowy code128 z proporcją szerokie‑wąskie w Javie

Poniżej znajduje się **przewodnik krok po kroku**, który prowadzi Cię przez każdy etap procesu.

### Krok 1: Ustaw katalog dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Upewnij się, że katalog istnieje i masz uprawnienia do zapisu; to właśnie tam zostanie umieszczony plik **zapisywania obrazu kodu kreskowego**.

### Krok 2: Utwórz obiekt Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Tutaj **tworzymy kod kreskowy code128**, przekazując `EncodeTypes.CODE_128` do konstruktora.

### Krok 3: Ustaw proporcję szerokie‑wąskie

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metoda `setWideNarrowRatio` pozwala precyzyjnie dostroić odstępy wizualne. Wartość `3.0f` oznacza, że szeroki pasek jest trzykrotnie szerszy od wąskiego.

### Krok 4: Zapisz obraz na dysku

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Wywołanie `save` **generuje obraz kodu kreskowego** i zapisuje go jako plik PNG, kończąc etap **zapisywania obrazu kodu kreskowego**.

## Dlaczego regulować proporcję szerokie‑wąskie?

- **Kompatybilność ze skanerami:** Niektóre skanery preferują proporcję w przedziale od 2.0 do 3.0 dla optymalnych wskaźników odczytu.  
- **Jakość druku:** Regulacja proporcji może kompensować ograniczenia DPI drukarki, zapobiegając zniekształceniom pasków.  
- **Spójność marki:** Niektóre firmy chcą, aby kody kreskowe wizualnie pasowały do kolorów korporacyjnych lub wytycznych projektowych.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| Kod kreskowy wygląda na zniekształcony | Zbyt wysoka/niska proporcja dla drukarki | Dostosuj wartość przekazywaną do `setWideNarrowRatio` (np. 2.0‑2.5). |
| Plik nie został utworzony | Nieprawidłowa ścieżka `dataDir` lub brak uprawnień | Zweryfikuj ścieżkę katalogu i upewnij się, że aplikacja ma dostęp do zapisu. |
| Skaner nie odczytuje kodu | Proporcja poza zalecanym zakresem dla symbolu | Użyj standardowych proporcji (2.0‑3.0) lub przetestuj z docelowym skanerem. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.BarCode z innymi frameworkami Javy?**  
O: Tak, Aspose.BarCode jest zaprojektowany tak, aby działał płynnie ze Spring, Java EE, Androidem i innymi środowiskami Javy.

**P: Jak mogę generować kody kreskowe z różnymi symbolami?**  
O: Po prostu zmień typ symbolu w konstruktorze `BarcodeGenerator`, np. `EncodeTypes.QR` dla kodów QR.

**P: Czy dostępna jest wersja próbna Aspose.BarCode?**  
O: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.BarCode?**  
O: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/barcode/java/).

**P: Jak uzyskać wsparcie dla Aspose.BarCode?**  
O: Odwiedź forum Aspose.BarCode [tutaj](https://forum.aspose.com/c/barcode/13) w celu uzyskania pomocy i dyskusji społecznościowych.

---

**Ostatnia aktualizacja:** 2026-02-12  
**Testowano z:** Aspose.BarCode for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}