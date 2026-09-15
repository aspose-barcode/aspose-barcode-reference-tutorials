---
date: 2026-06-14
description: Dowiedz się, jak generować kody kreskowe DotCode przy użyciu Aspose.BarCode
  for .NET, obejmując współczynnik proporcji, tryby kodowania, rozszerzony tekst oraz
  inicjalizację czytnika.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Jak generować kody kreskowe DotCode – przewodnik konfiguracji
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak generować kody kreskowe DotCode – przewodnik konfiguracji
url: /pl/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kody kreskowe DotCode – Przewodnik konfiguracji

## Wprowadzenie
**Jak generować** kody kreskowe DotCode szybko i niezawodnie jest powszechnym wymaganiem dla programistów tworzących rozwiązania do inwentaryzacji, śledzenia lub mobilnego skanowania. W tym samouczku przeprowadzimy Cię przez wszystkie opcje konfiguracji, które Aspose.BarCode dla .NET oferuje dla symboli DotCode — regulacje proporcji, tryby kodowania Auto i Bytes, obsługa rozszerzonego tekstu kodu, inicjalizacja czytnika, układ wierszy/kolumn oraz tryb Structured‑Append. Po zakończeniu będziesz w stanie tworzyć idealnie wymiarowane, wysokiej gęstości obrazy DotCode, które spełniają standardy branżowe i integrują się bezproblemowo z dowolną aplikacją .NET.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do tworzenia kodu kreskowego DotCode?** `BarcodeGenerator` z `EncodeTypes.DotCode`.
- **Która właściwość kontroluje proporcje?** `BarCodeImageAspectRatio`.
- **Czy mogę przełączać się między trybami Auto i Bytes?** Tak, za pomocą właściwości `EncodeMode`.
- **Czy potrzebny jest osobny czytnik dla DotCode?** Nie, ten sam `BarcodeGenerator` może dekodować po wywołaniu `ReadBarcode`.
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Jak generować kody kreskowe DotCode przy użyciu Aspose.BarCode dla .NET?
`BarcodeGenerator` jest podstawową klasą w Aspose.BarCode do tworzenia obrazów kodów kreskowych. Załaduj `BarcodeGenerator` z `EncodeTypes.DotCode`, ustaw żądane właściwości (proporcje, tryb kodowania, wiersze/kolumny itp.) i wywołaj `GenerateBarCodeImage()` — biblioteka zwraca gotowy do użycia `System.Drawing.Image` lub tablicę bajtów. Ten jednoczesny proces obsługuje wszystkie szczegóły kodowania niskiego poziomu, wspiera formaty wyjściowe takie jak PNG, JPEG i SVG oraz może renderować obrazy do 10 000 × 10 000 px bez nadmiernego zużycia pamięci.

## Co to jest kod kreskowy DotCode?
Kod kreskowy DotCode to wysokiej gęstości, kwadratowa symbologia 2D, która przechowuje do 1 200 znaków numerycznych lub 800 znaków alfanumerycznych w zwartym macierzy punktów. Jest zoptymalizowany pod kątem etykietowania małych paczek i skanowania mobilnego, oferując szybkie odczyty nawet przy niskiej rozdzielczości kamer.

## Dlaczego warto używać DotCode z Aspose.BarCode?
Aspose.BarCode obsługuje **20+** typów kodów 2D, w tym DotCode, i może przetwarzać pliki większe niż **200 MB** bez ładowania całego obrazu do pamięci. Biblioteka gwarantuje **99,9 %** dokładności skanowania na standardowych smartfonach i zapewnia wbudowane poziomy korekcji błędów, aby zminimalizować niepowodzenia odczytu.

## Wymagania wstępne
- .NET Framework 4.5 lub wyższy, lub .NET Core 3.1 / .NET 5+.
- Aspose.BarCode dla .NET (zalecana najnowsza wersja).
- Tymczasowy lub pełny klucz licencyjny (wersja próbna działa w środowisku deweloperskim).

## Dostosowywanie proporcji DotCode
**Aspect‑ratio** określa, jak rozciągnięta lub ściśnięta jest macierz DotCode. Użyj właściwości `BarCodeImageAspectRatio`, aby ustawić wartość między **0,5** (wyższa) a **2,0** (szersza). Stosunek **1,0** daje idealnie kwadratowy symbol, co jest domyślną wartością i najlepiej sprawdza się w większości skanerów.

> **Wskazówka:** Przy drukowaniu na wąskich etykietach stosunek **0,75** często poprawia czytelność bez utraty pojemności danych.

## Tryb kodowania DotCode (Auto)
W trybie **Auto** biblioteka analizuje ciąg wejściowy i automatycznie wybiera najefektywniejsze kodowanie (numeryczne, alfanumeryczne lub bajtowe). Dzięki temu maksymalizuje się gęstość danych i zmniejsza rozmiar symbolu.

> **Bezpośrednia odpowiedź:** Ustaw `EncodeMode = EncodeModes.Auto` w `BarcodeGenerator`, aby Aspose.BarCode wybrał optymalne kodowanie dla Twoich danych, zapewniając najmniejszy możliwy DotCode przy zachowaniu wszystkich znaków.

## Tryb kodowania DotCode (Bytes)
Gdy potrzebujesz przechowywać dane binarne lub wstępnie zakodowane tablice bajtów, wybierz tryb **Bytes**. Wymusza on, aby generator traktował wejście jako surowe bajty, pomijając automatyczne wykrywanie zestawu znaków.

> **Bezpośrednia odpowiedź:** Użyj `EncodeMode = EncodeModes.Bytes` i podaj ładunek `byte[]`, aby osadzić informacje binarne, takie jak zaszyfrowane identyfikatory lub skompresowane pliki, bezpośrednio w symbolu DotCode.

## Konfiguracja rozszerzonego tekstu kodu DotCode
Rozszerzony tekst kodu pozwala dołączyć dodatkowe informacje, które nie są częścią głównego ładunku danych, ale mogą być wyświetlane obok kodu kreskowego w raportach lub interfejsach GUI. Ustaw właściwość `ExtendedCodeText` na dowolny ciąg (do **256** znaków) i wybierz czcionkę za pomocą `ExtendedCodeTextFont`.

> **Pro tip:** Połącz rozszerzony tekst z mniejszym rozmiarem czcionki (np. 8 pt), aby zmniejszyć wizualny ślad, jednocześnie zapewniając czytelny kontekst dla człowieka.

## Inicjalizacja czytnika DotCode
`BarCodeReader` jest klasą używaną do dekodowania kodów kreskowych z obrazów lub strumieni. Odczyt obrazu DotCode jest tak prosty, jak jego generowanie. Utwórz `BarCodeReader` z strumieniem obrazu i określ `EncodeTypes.DotCode`. Wywołaj `ReadBarCode()`, aby uzyskać odczytany ciąg.

> **Bezpośrednia odpowiedź:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – ten jedyny blok dekoduje symbol bez zewnętrznych zależności.

## Konfiguracja wierszy i kolumn DotCode
DotCode umożliwia jawną kontrolę liczby wierszy i kolumn, co wpływa na rozmiar symbolu i pojemność korekcji błędów. Użyj właściwości `Rows` i `Columns`, aby ustawić wartości między **10** a **144**. Większe macierze zwiększają pojemność danych i odporność.

> **Best practice:** Dla etykiet inwentaryzacyjnych, które muszą wytrzymać trudne warunki, skonfiguruj **Rows = 64** i **Columns = 64**, aby dodać dodatkową redundancję.

## Konfiguracja trybu Structured Append dla DotCode
Structured Append umożliwia podzielenie dużego ładunku danych na wiele symboli DotCode, które mogą być odczytywane kolejno. Ustaw `StructuredAppend = true` i określ `StructuredAppendCount` oraz `StructuredAppendIndex` dla każdej części.

> **Bezpośrednia odpowiedź:** Włącz `StructuredAppend` w każdym `BarcodeGenerator`, przypisz unikalny indeks (zaczynając od 1) i ustaw całkowitą liczbę; biblioteka automatycznie osadzi niezbędne informacje łączące.

## Typowe problemy i rozwiązania
- **Kod nieczytelny na ekranach o niskiej rozdzielczości:** Zwiększ właściwość `Resolution` przynajmniej do **300 dpi** przed generacją.
- **Ostrzeżenia o obcięciu danych:** Upewnij się, że długość wejścia nie przekracza maksymalnej dla wybranych wierszy/kolumn; dostosuj rozmiar lub przełącz się na tryb Bytes w razie potrzeby.
- **Wygaśnięcie licencji podczas rozwoju:** Użyj tymczasowej licencji uzyskanej z portalu Aspose; zamień ją na stały klucz przed wdrożeniem produkcyjnym.

## Najczęściej zadawane pytania

**P: Czy mogę generować kody DotCode w formacie SVG?**  
O: Tak, ustaw `BarCodeImageFormat = BarCodeImageFormat.Svg` w generatorze, aby otrzymać skalowalny wektorowy wynik.

**P: Czy można osadzić logo wewnątrz symbolu DotCode?**  
O: Aspose.BarCode nie obsługuje bezpośredniego osadzania logo w DotCode, ale możesz nałożyć obraz po wygenerowaniu przy użyciu standardowych bibliotek graficznych.

**P: Jak działa korekcja błędów w DotCode?**  
O: Symbologia zawiera wbudowaną korekcję błędów Reed‑Solomon; zwiększanie liczby wierszy/kolumn automatycznie podnosi poziom korekcji.

**P: Czy potrzebuję osobnej biblioteki do odczytu DotCode z PDF?**  
O: Nie, ten sam `BarCodeReader` może wyodrębniać DotCode z stron PDF, obrazów lub strumieni bez dodatkowych narzędzi.

**P: Jaki jest maksymalny rozmiar danych dla jednego symbolu DotCode?**  
O: Do **1 200** znaków numerycznych lub **800** znaków alfanumerycznych, w zależności od wybranej konfiguracji wierszy/kolumn.

---

**Ostatnia aktualizacja:** 2026-06-14  
**Testowane z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

## Samouczki konfiguracji kodu DotCode
### [Dostosowywanie proporcji DotCode](./dotcode-aspect-ratio-customization/)
Dowiedz się, jak dostosować proporcje kodu kreskowego DotCode przy użyciu Aspose.BarCode dla .NET. Twórz dopasowane kody kreskowe dla swoich aplikacji bez wysiłku.
### [Tryb kodowania DotCode (Auto)](./dotcode-encoding-mode-auto/)
Poznaj tryb kodowania DotCode (Auto) w Aspose.BarCode dla .NET, potężne narzędzie do generowania kodów kreskowych. Naucz się krok po kroku generować kody DotCode. Sprawdź dokumentację, pobierz bibliotekę i uzyskaj tymczasowe licencje.
### [Tryb kodowania DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Poznaj kodowanie DotCode przy użyciu Aspose.BarCode dla .NET: przewodnik krok po kroku do generowania kodów kreskowych.
### [Konfiguracja rozszerzonego tekstu kodu DotCode](./dotcode-extended-code-text-configuration/)
Generuj rozszerzony tekst kodu DotCode z łatwością przy użyciu Aspose.BarCode dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie tworzyć kody kreskowe.
### [Inicjalizacja czytnika DotCode](./dotcode-reader-initialization/)
Dowiedz się, jak zainicjować czytnik DotCode przy użyciu Aspose.BarCode dla .NET. Twórz kody DotCode z łatwością dla różnych zastosowań.
### [Konfiguracja wierszy i kolumn DotCode](./dotcode-rows-columns-configuration/)
Naucz się konfigurować wiersze i kolumny DotCode przy użyciu Aspose.BarCode dla .NET. Generuj precyzyjne i konfigurowalne kody 2D bez problemu.
### [Konfiguracja trybu Structured Append dla DotCode](./dotcode-structured-append-mode-configuration/)
Dowiedz się, jak skonfigurować tryb Structured Append w DotCode przy użyciu Aspose.BarCode dla .NET i tworzyć wydajne kody kreskowe.

## Powiązane samouczki

- [Dostosowywanie proporcji DotCode z Aspose.BarCode dla .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Konfiguracja rozszerzonego tekstu kodu DotCode z Aspose.BarCode dla .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Tryb kodowania DotCode (Auto) w Aspose.BarCode dla .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}