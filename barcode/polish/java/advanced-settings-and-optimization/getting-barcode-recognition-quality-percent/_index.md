---
date: 2025-11-30
description: Dowiedz się, jak ocenić jakość odczytu kodu kreskowego w Javie przy użyciu
  Aspose.Barcode. Przewodnik krok po kroku, jak uzyskać procentową jakość rozpoznawania.
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – Uzyskiwanie jakości rozpoznawania kodu kreskowego w procentach
url: /pl/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Uzyskiwanie jakości rozpoznawania kodu kreskowego w procentach

## Wprowadzenie

Jeśli potrzebujesz **ocenić jakość odczytu kodu kreskowego** w aplikacji Java, **Aspose.Barcode Java** zapewnia prostą API, która zwraca jakość rozpoznania w procentach. W tym samouczku przeprowadzimy Cię przez dokładne kroki potrzebne do pobrania tego procentu, wyjaśnimy, dlaczego miara jest istotna, i pokażemy, jak zintegrować wywołanie z istniejącą bazą kodu.

## Szybkie odpowiedzi
- **Co oznacza „jakość odczytu”?** To wskaźnik pewności (0‑100 %) przypisywany przez bibliotekę każdemu zdekodowanemu kodowi kreskowemu.  
- **Jaka wersja biblioteki jest wymagana?** Dowolna aktualna wersja Aspose.Barcode Java (przykład używa najnowszej serii 24.x).  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.  
- **Czy mogę odczytać wszystkie typy kodów kreskowych?** Tak – flaga `DecodeType.ALL_SUPPORTED_TYPES` włącza każdy format obsługiwany przez Aspose.Barcode.  
- **Czy wartość jakości jest wiarygodna dla kodów QR?** Absolutnie – ten sam algorytm pewności jest stosowany zarówno dla symbologii 1‑D, jak i 2‑D.

## Czym jest Aspose.Barcode Java i jak ocenić jakość odczytu kodu kreskowego?

**Aspose.Barcode Java** to w pełni zarządzana biblioteka, która pozwala programistom generować, odczytywać i analizować kody kreskowe bez zewnętrznych zależności. Jedną z jej najbardziej przydatnych diagnostyk jest metryka **jakość odczytu**, która informuje, jak pewnie silnik zdekodował symbol. Ta metryka jest niezbędna, gdy trzeba zdecydować, czy zaakceptować skan, poprosić o ponowne przechwycenie lub uruchomić logikę obsługi błędów.

## Dlaczego warto używać Aspose.Barcode Java do oceny jakości odczytu kodu kreskowego?

- **Spójne wyniki pewności** we wszystkich obsługiwanych symbologiach.  
- **Brak natywnych DLL** – czysta Java, więc działa na każdej platformie zgodnej z JVM.  
- **Precyzyjna kontrola**: możesz pobrać jakość dla każdego kodu kreskowego, a nie tylko globalny wynik tak/nie.  
- **Silnik odczytu zoptymalizowany pod kątem wydajności**, skalujący się od komputerów stacjonarnych po usługi w chmurze.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- **Środowisko programistyczne Java** – JDK 8 lub nowszy, z ulubionym IDE (IntelliJ, Eclipse, VS Code itp.).  
- **Biblioteka Aspose.Barcode Java** – pobierz najnowszy JAR z oficjalnej strony: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Przykładowy obraz kodu kreskowego** – w samouczku używany jest `code39Extended.jpg` znajdujący się w folderze `BarcodeReader/advanced_features/`.

Teraz, gdy wszystko jest gotowe, przejdźmy do kodu.

## Importowanie przestrzeni nazw

Poniższe importy dają dostęp do klas czytnika i wyników potrzebnych do wyodrębnienia jakości.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Krok 1: Ustaw ścieżkę katalogu zasobów

Zdefiniuj folder zawierający przykładowy obraz. `Utils.getDataDir` to pomocnicza metoda, która rozwiązuje absolutną ścieżkę dla bieżącego projektu.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Krok 2: Zainicjalizuj obiekt BarCodeReader

Utwórz instancję `BarCodeReader`, wskazując plik obrazu i nakazując jej spróbować **wszystkie obsługiwane typy kodów kreskowych**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Krok 3: Odczytaj kody kreskowe i pobierz procent jakości

Iteruj po każdym wykrytym kodzie kreskowym, wypisz jego tekst, typ oraz procent **jakości odczytu** zwracany przez `getReadingQuality()`.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**Co się tutaj dzieje?**  
- `readBarCodes()` zwraca kolekcję obiektów `BarCodeResult`, po jednym dla każdego znalezionego kodu kreskowego.  
- `getReadingQuality()` zwraca `double` w przedziale od `0` do `100`, reprezentujący poziom pewności.  
- Możesz użyć tej wartości, aby zdecydować, czy skan jest akceptowalny, czy też należy poprosić użytkownika o kolejną próbę.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Jakość zawsze 0** | Obraz ma niską rozdzielczość lub jest mocno rozmyty. | Użyj obrazu o wyższej rozdzielczości lub zastosuj wstępne przetwarzanie obrazu (np. wyostrzanie). |
| **Nie wykryto kodów kreskowych** | Nieprawidłowa flaga `DecodeType`. | Upewnij się, że używasz `DecodeType.ALL_SUPPORTED_TYPES` lub określ dokładny typ, którego oczekujesz. |
| **Wyjątek przy `Utils.getDataDir`** | Struktura projektu różni się od przykładu. | Zastąp wywołanie pomocnicze ścieżką absolutną zakodowaną na stałe lub ścieżką względną pasującą do Twojego układu. |

## Najczęściej zadawane pytania

### Q1: Czy Aspose.Barcode jest kompatybilny ze wszystkimi typami kodów kreskowych?

A1: Aspose.Barcode obsługuje szeroką gamę symbologii kodów kreskowych, w tym 1‑D (Code‑39, Code‑128, UPC) oraz 2‑D (QR, DataMatrix, PDF417).

### Q2: Czy mogę używać Aspose.Barcode do celów komercyjnych?

A2: Tak, możesz używać Aspose.Barcode zarówno w projektach prywatnych, jak i komercyjnych. Szczegóły licencjonowania dostępne są [tutaj](https://purchase.aspose.com/buy).

### Q3: Jak mogę uzyskać tymczasową licencję do celów testowych?

A3: Uzyskaj tymczasową licencję z portalu Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

### Q4: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje społecznościowe?

A4: Odwiedź [forum Aspose.Barcode](https://forum.aspose.com/c/barcode/13), aby uzyskać wsparcie od społeczności i oficjalną pomoc.

### Q5: Czy w dokumentacji dostępne są przykłady kodu?

A5: Tak, obszerne przykłady kodu są dostępne w oficjalnej dokumentacji [tutaj](https://reference.aspose.com/barcode/java/).

## Podsumowanie

Korzystając z **Aspose.Barcode Java**, możesz łatwo pobrać procent **jakości odczytu kodu kreskowego** dla dowolnego zeskanowanego symbolu. Ta metryka umożliwia tworzenie inteligentniejszej logiki walidacji, poprawę doświadczenia użytkownika oraz utrzymanie wysokiej integralności danych w aplikacjach Java.

---

**Ostatnia aktualizacja:** 2025-11-30  
**Testowano z:** Aspose.Barcode Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}