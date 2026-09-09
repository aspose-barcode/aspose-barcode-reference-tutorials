---
date: 2026-06-09
description: Dowiedz się, jak generować kod datamatrix przy użyciu Aspose.BarCode
  dla .NET, dostosowywać współczynniki proporcji, tryby ECC oraz kodowanie datamatrix
  c40, aby efektywnie tworzyć kody kreskowe.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Konfiguracja kodu DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generowanie kodu DataMatrix – Przewodnik profesjonalny z Aspose.BarCode
url: /pl/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generuj kod kreskowy DataMatrix – Przewodnik Pro z Aspose.BarCode

Welcome to our comprehensive tutorial series on **generate datamatrix barcode** using Aspose.BarCode for .NET. Whether you're a seasoned developer fine‑tuning barcode output or a newcomer eager to understand the fundamentals, this guide walks you through every step—from basic configuration to advanced encoding techniques—so you can deliver reliable, scan‑ready barcodes in any .NET application.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Utworzyć i dostosować kody kreskowe DataMatrix programowo.  
- **Która biblioteka jest używana?** Aspose.BarCode for .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana w produkcji.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę dostosować współczynnik proporcji?** Tak – zobacz sekcję „Jak dostosować współczynnik proporcji DataMatrix”.

## Co to jest generate datamatrix barcode?
DataMatrix to dwuwymiarowa macierz czarnych i białych komórek, która może przechowywać do 2 300 znaków alfanumerycznych. Korzystając z Aspose.BarCode, możesz **generate datamatrix barcode** w postaci obrazów, PDF‑ów lub SVG‑ów bezpośrednio z kodu .NET, kontrolując rozmiar, poziom korekcji błędów i tryb kodowania, aby spełnić dowolny standard branżowy.

## Dlaczego warto używać Aspose.BarCode dla DataMatrix?
Aspose.BarCode renderuje symbole DataMatrix z rozdzielczością do **600 dpi** bez pikselizacji, zapewniając wyraźne skany na drukarkach wysokiej rozdzielczości. Obsługuje **wszystkie 50+ trybów ECC i makr** — w tym ECC 000‑140, ECC 200 oraz Macro 05/06 — dzięki czemu możesz wybrać optymalny poziom korekcji błędów dla rozmiaru danych. API oferuje opcje kodowania **ASCII, C40, Text, X12 i Bytes**, co pozwala efektywnie pakować dane. Integracja wymaga tylko jednego pakietu NuGet i nie wymaga zewnętrznych bibliotek natywnych.

## Jak dostosować współczynnik proporcji DataMatrix
Właściwość `AspectRatio` klasy `BarCodeGenerator` kontroluje proporcję szerokości do wysokości generowanego symbolu DataMatrix. `BarCodeGenerator` jest główną klasą w Aspose.BarCode używaną do tworzenia obrazów kodów kreskowych.  

**Bezpośrednia odpowiedź:** Ustaw `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (lub dowolną wartość od 0.5 do 2.0) przed wywołaniem `GenerateBarCodeImage()`. Biblioteka automatycznie przelicza rozmiar modułu, aby zachować niezawodność skanowania przy jednoczesnym respektowaniu żądanej proporcji.

### Krok po kroku
1. **Utwórz** instancję `BarCodeGenerator` z `EncodeTypes.DataMatrix`.  
2. **Dostosuj** `AspectRatio` do pożądanej wartości.  
3. **Wygeneruj** obraz i zweryfikuj go skanerem lub wbudowanym czytnikiem Aspose.

## Jak generować kody DataMatrix ECC 000‑140
ECC 000‑140 jest idealny dla krótkich ciągów danych, gdzie wymagany jest kompaktowy symbol, oferując do 140 kodów korekcji błędów. `DataMatrixEccMode.Ecc000140` wybiera schemat korekcji ECC 000‑140 dla DataMatrix.  

**Bezpośrednia odpowiedź:** Użyj `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` przed renderowaniem. Przełącza to enkoder na algorytm ECC 000‑140, tworząc najmniejszą możliwą macierz dla podanych danych przy jednoczesnym zapewnieniu solidnej korekcji błędów.

### Praktyczna wskazówka
Podczas kodowania danych liczbowych krótszych niż 20 znaków, ECC 000‑140 często daje macierz 10 × 10, co oszczędza cenną przestrzeń etykiety.

## Jak generować kody DataMatrix ECC 200
ECC 200 to najpowszechniej stosowany tryb DataMatrix, obsługujący do 2 335 znaków alfanumerycznych i oferujący doskonałą korekcję błędów. `DataMatrixEccMode.Ecc200` wybiera schemat korekcji ECC 200 dla DataMatrix.  

**Bezpośrednia odpowiedź:** Ustaw `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` i podaj ładunek za pomocą `CodeText`. Biblioteka automatycznie wybierze optymalny rozmiar macierzy.

### Kiedy wybrać ECC 200
Używaj ECC 200 dla dłuższych ciągów, danych mieszanych lub gdy potrzebna jest najwyższa odporność na uszkodzenia — do **30 %** symbolu może zostać przywrócone.

## Jak opanować kodowanie DataMatrix w trybie ASCII
Tryb ASCII koduje znaki przy użyciu jednego bajtu na znak, co czyni go najbardziej efektywnym pod względem miejsca dla zwykłego tekstu. `DataMatrixEncodeMode.Ascii` instruuje generator, aby używał kodowania ASCII dla symbolu DataMatrix.  

**Bezpośrednia odpowiedź:** Przypisz `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` i ustaw `CodeText` na swój ciąg ASCII. Silnik pakuje dane bez dodatkowego narzutu, tworząc najmniejszą możliwą macierz dla czystej treści ASCII.

### Przykładowy scenariusz
SKU magazynowe składające się z wielkich liter i cyfr (np. „AB1234”) idealnie pasuje do trybu ASCII, często skutkując macierzą 12 × 12.

## Jak generować DataMatrix w trybie (Auto)
Tryb Auto pozwala Aspose.BarCode przeanalizować wejście i automatycznie wybrać najefektywniejsze kodowanie (ASCII, C40, Text, X12 lub Bytes). `DataMatrixEncodeMode.Auto` włącza tę funkcję automatycznego wyboru.  

**Bezpośrednia odpowiedź:** Ustaw `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Biblioteka ocenia ładunek, wybiera optymalny tryb i renderuje kod kreskowy w jednym kroku.

### Korzyści
Tryb Auto zmniejsza nakład pracy programisty i gwarantuje najmniejszy możliwy symbol dla danych mieszanych, poprawiając szybkość skanowania.

## Jak używać trybu kodowania DataMatrix (Bytes)
Tryb Bytes jest przeznaczony dla danych binarnych, takich jak zaszyfrowane ładunki lub skompresowane pliki. `DataMatrixEncodeMode.Bytes` instruuje generator, aby traktował każdy bajt jako surowe dane.  

**Bezpośrednia odpowiedź:** Użyj `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` i podaj ciąg Base64 jako `CodeText`. Enkoder traktuje każdy bajt jako surowe dane, zachowując dokładną reprezentację binarną.

### Przypadek użycia
Osadzenie 128‑bitowego GUID‑u lub małego zaszyfrowanego tokenu bezpośrednio w symbolu DataMatrix.

## Jak opanować tryb kodowania DataMatrix (C40)
Tryb C40 kompresuje dane alfanumeryczne wielkimi literami, osiągając do **40 %** redukcji rozmiaru w porównaniu z ASCII. `DataMatrixEncodeMode.C40` aktywuje ten algorytm kompresji.  

**Bezpośrednia odpowiedź:** Ustaw `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` i podaj ciąg wielkimi literami (np. „HELLO WORLD”). Silnik pakuje trzy znaki w dwa kodowe słowa, zmniejszając finalną macierz.

### Pro tip
C40 działa najlepiej, gdy ładunek składa się głównie z wielkich liter, cyfr i spacji. Dla mieszanej wielkości liter rozważ tryb Auto.

## Jak skonfigurować tekst kodu DataMatrix
Właściwość `CodeText` definiuje dokładne dane przechowywane w kodzie kreskowym. Może zawierać zwykły tekst, ciągi liczbowe lub nawet ładunki XML. `CodeText` jest główną właściwością typu string klasy `BarCodeGenerator`, która przechowuje ładunek kodu kreskowego.  

**Bezpośrednia odpowiedź:** Przypisz `generator.Parameters.Barcode.CodeText = "YourDataHere"` przed renderowaniem. Właściwość akceptuje dowolny ciąg UTF‑8 o długości do maksymalnego limitu obsługiwanego przez wybrany tryb ECC.

### Zaawansowana wskazówka
Połącz `CodeText` z `ExtendedDataMatrix`, aby osadzić dodatkowe metadane bez zwiększania widocznego rozmiaru macierzy.

## Jak opanować konfigurację makr DataMatrix
Tryby makr (Macro 05 i Macro 06) pozwalają osadzić drugi symbol DataMatrix wewnątrz głównego, przydatny do linkowania do zewnętrznych źródeł danych. `DataMatrixMacroMode.Macro05` i `DataMatrixMacroMode.Macro06` włączają te funkcje makr.  

**Bezpośrednia odpowiedź:** Włącz tryb makra za pomocą `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (lub `Macro06`) i ustaw właściwości `MacroPdf417` dla drugorzędnego ładunku. Generator tworzy złożony symbol, który skanery mogą interpretować jako dwa powiązane kody.

### Przykład z życia
Osadzenie URL‑a w części makra przy jednoczesnym zachowaniu identyfikatorów produktu w głównej macierzy, umożliwiając płynne połączenie web‑to‑barcode.

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## Tutoriale konfiguracji kodów DataMatrix
### [Dostosowywanie proporcji DataMatrix](./datamatrix-aspect-ratio-customization/)
Dowiedz się, jak dostosować proporcje kodu DataMatrix przy użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku po generowaniu kodów kreskowych.
### [Generowanie kodów DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Twórz kody DataMatrix ECC 000-140 z łatwością przy użyciu Aspose.BarCode dla .NET. Zwiększ efektywność w zarządzaniu zapasami i nie tylko.
### [Generowanie kodów DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Naucz się generować kody DataMatrix ECC 200 w .NET przy użyciu Aspose.BarCode. Usprawnij operacje dzięki efektywnemu tworzeniu kodów kreskowych.
### [Opanowanie kodowania DataMatrix w trybie ASCII](./datamatrix-encoding-mode-ascii/)
Naucz się tworzyć kody DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku dla programistów.
### [Generowanie DataMatrix w trybie (Auto)](./datamatrix-encoding-mode-auto/)
Dowiedz się, jak generować DataMatrix w trybie (Auto) z Aspose.BarCode dla .NET. Ten przewodnik krok po kroku obejmuje wszystko od wymagań wstępnych po odczyt kodów.
### [Tryb kodowania DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Naucz się kodować dane w formacie DataMatrix przy użyciu trybu Bytes z Aspose.BarCode dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku po generowanie i rozpoznawanie kodów.
### [Opanowanie trybu kodowania DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Poznaj tryb kodowania DataMatrix (C40) z Aspose.BarCode dla .NET. Twórz niestandardowe kody kreskowe efektywnie. Odkryj przewodnik krok po kroku.
### [Konfiguracja rozszerzonego tekstu kodu DataMatrix](./datamatrix-extended-code-text-configuration/)
Naucz się konfigurować rozszerzony tekst kodu DataMatrix przy użyciu Aspose.BarCode dla .NET. Generuj, rozpoznawaj i integruj kody kreskowe w swoich aplikacjach .NET.
### [Opanowanie konfiguracji makr DataMatrix](./datamatrix-macro-configuration/)
Dowiedz się, jak konfigurować makra DataMatrix przy użyciu Aspose.BarCode dla .NET. Generuj, dostosowuj i rozpoznawaj kody DataMatrix w swoich aplikacjach .NET.

## Najczęściej zadawane pytania

**P: Jak zdecydować, którego trybu ECC użyć?**  
O: Wybierz ECC 000‑140 dla małych zestawów danych z ograniczoną korekcją błędów lub ECC 200 dla większych danych i wyższej niezawodności. Tryb makra dodaje dodatkową warstwę danych do linkowania.

**P: Czy mogę osadzić własny tekst w kodzie DataMatrix?**  
O: Tak, ustaw właściwość `CodeText` na własny ciąg, a następnie wybierz odpowiedni tryb kodowania (ASCII, C40 itp.), aby kontrolować rozmiar.

**P: Czy istnieje sposób na automatyczny wybór najlepszego trybu kodowania?**  
O: Ustaw `EncodeMode` na `Auto`; Aspose.BarCode oceni ładunek i automatycznie wybierze najbardziej oszczędny pod względem miejsca tryb.

**P: Jakie są kwestie wydajności przy generowaniu dużych partii kodów?**  
O: Ponownie używaj jednej instancji `BarCodeGenerator`, włącz wielowątkowość i generuj obrazy PNG dla jakości bezstratnej lub JPEG dla mniejszego rozmiaru pliku. Generowanie 10 000 symboli zazwyczaj zajmuje poniżej 30 sekund na standardowym serwerze 8‑rdzeniowym.

**P: Czy Aspose.BarCode obsługuje .NET Core i .NET 5/6?**  
O: Absolutnie – biblioteka jest w pełni kompatybilna z .NET Framework, .NET Core i najnowszymi wydaniami .NET, oferując ten sam zestaw funkcji na wszystkich platformach.

**Ostatnia aktualizacja:** 2026-06-09  
**Testowano z:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Powiązane tutoriale

- [Jak generować kody DataMatrix (ECC 200) z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Opanowanie kodowania DataMatrix w ASCII z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Utwórz PNG kodu kreskowego – proporcje DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}