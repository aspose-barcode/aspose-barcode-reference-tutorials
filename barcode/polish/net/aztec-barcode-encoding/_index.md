---
date: 2026-05-19
description: Dowiedz się, jak utworzyć kod kreskowy Aztec przy użyciu Aspose.BarCode
  dla .NET, dostosować współczynniki proporcji, kodować bajty lub tekst oraz obsługiwać
  tryby symboli.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Kodowanie kodu kreskowego Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak utworzyć kod kreskowy Aztec przy użyciu Aspose.BarCode dla .NET
url: /pl/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kodowanie kodu kreskowego Aztec

Czy jesteś gotowy, aby zanurzyć się w świat kodowania kodów kreskowych Aztec i dowiedzieć się, jak **tworzyć kod Aztec** przy użyciu Aspose.BarCode dla .NET? Ta biblioteka daje pełną kontrolę nad rozmiarem, korekcją błędów i reprezentacją danych, co czyni ją idealną do wszystkiego, od mobilnego biletowania po śledzenie zapasów.

## Szybkie odpowiedzi
- **Jaka biblioteka obsługuje kody Aztec?** Aspose.BarCode for .NET  
- **Czy mogę zmienić współczynnik proporcji?** Tak, za pomocą właściwości `AspectRatio`  
- **Czy kodowanie na poziomie bajtów jest możliwe?** Zdecydowanie – użyj metody `EncodeBytes`  
- **Jakie poziomy korekcji błędów są dostępne?** Poziomy 0 do 4 (wyższy = większa redundancja)  
- **Czy potrzebuję licencji do produkcji?** Tak, licencja komercyjna usuwa ograniczenia wersji ewaluacyjnej  

## Co to jest kod Aztec?
Kod Aztec to dwuwymiarowy kod macierzowy, który może zakodować do 3 000 znaków numerycznych lub 2 300 znaków alfanumerycznych. Posiada centralny wzorzec odnajdywania, umożliwiając szybkie skanowanie nawet przy niskiej rozdzielczości druku. Ponieważ wzorzec znajduje się w centrum, kod może być odczytany z dowolnego kierunku, co czyni go bardzo niezawodnym w aplikacjach mobilnych i przemysłowych.

## Jak dostosować współczynnik proporcji kodu Aztec?
`BarcodeGenerator` jest główną klasą używaną do tworzenia kodów kreskowych w Aspose.BarCode. Ustaw właściwość `AspectRatio` w obiekcie `BarcodeGenerator` na żądany stosunek szerokości do wysokości, a następnie wygeneruj obraz. Dostosowanie współczynnika proporcji pomaga dopasować kod do ograniczonych przestrzeni UI lub układów etykiet bez utraty niezawodności skanowania, a także umożliwia dopasowanie do wytycznych marki lub konkretnych wymagań drukarki.

### Kroki do dostosowania współczynnika proporcji
1. **Utwórz instancję `BarcodeGenerator`** z `EncodeTypes.Aztec`.  
2. **Przypisz swoje dane** (tekst, bajty lub ciąg numeryczny).  
3. **Ustaw `AspectRatio`** – na przykład `1.5` dla szerszego paska.  
4. **Wygeneruj obraz** używając `Save` lub `GetBarCodeImage`.  

## Jak zakodować surowe bajty w kodzie Aztec?
`EncodeBytes` jest metodą przyjmującą tablicę bajtów i konwertującą ją na macierz Aztec. Przekaż tablicę bajtów do metody `EncodeBytes` klasy `BarcodeGenerator`. API automatycznie konwertuje dane binarne na zwarty macierz Aztec, zachowując każdy bit. Jest to idealne do osadzania zaszyfrowanych ładunków, identyfikatorów binarnych lub skompresowanych plików bezpośrednio w kodzie kreskowym.

### Kroki do kodowania bajtów
1. **Przygotuj tablicę bajtów** (np. `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Zainicjuj `BarcodeGenerator`** z `EncodeTypes.Aztec`.  
3. **Wywołaj `EncodeBytes(data)`**, aby załadować zawartość binarną.  
4. **Wygeneruj kod** przy użyciu `Save` lub `GetBarCodeImage`.  

## Jak zakodować tekst w kodzie Aztec?
`CodeText` jest właściwością przechowującą dane w postaci zwykłego tekstu do zakodowania. Użyj właściwości `CodeText` klasy `BarcodeGenerator`, aby dostarczyć dane tekstowe. Biblioteka automatycznie wybiera optymalny tryb kodowania (numeryczny, alfanumeryczny lub bajtowy) i stosuje odpowiedni poziom korekcji błędów. Ułatwia to osadzanie adresów URL, identyfikatorów produktów lub dowolnych czytelnych ciągów.

### Kroki do kodowania tekstu
1. **Utwórz generator** z `EncodeTypes.Aztec`.  
2. **Ustaw `CodeText`** na ciąg, który chcesz zakodować.  
3. **Opcjonalnie dostosuj `ErrorLevel`** dla większej odporności.  
4. **Wygeneruj obraz** używając `Save` lub `GetBarCodeImage`.  

## Jak generować kody Aztec z różnymi poziomami korekcji błędów?
`ErrorLevel` jest właściwością kontrolującą ilość danych redundantnych dodawanych do kodu. Dostosuj właściwość `ErrorLevel` (0‑4) przed renderowaniem. Wyższe poziomy zwiększają ilość danych redundantnych, umożliwiając odczyt kodu nawet przy uszkodzeniu do 30 % symbolu. Jest to kluczowe w trudnych warunkach, takich jak etykietowanie przemysłowe czy oznakowanie zewnętrzne.

### Kroki do ustawienia korekcji błędów
1. **Zainicjuj `BarcodeGenerator`** dla Aztec.  
2. **Przypisz swoje dane** (tekst lub bajty).  
3. **Ustaw `ErrorLevel`** – np. `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Wygeneruj kod** w preferowanym formacie wyjściowym.  

## Jakie są różne tryby symboli Aztec i jak ich używać?
`SymbolMode` jest ustawieniem określającym rozmiar macierzy i pojemność danych generowanego kodu Aztec. Biblioteka oferuje cztery tryby: **Auto**, **FullRange**, **Compact** i **Rune**.

- **Auto** – generator wybiera najmniejszy możliwy rozmiar.  
- **FullRange** – umożliwia maksymalny rozmiar macierzy dla bardzo dużych zestawów danych.  
- **Compact** – tworzy mniejszy, bardziej zwartą symbol, idealny przy ograniczonej przestrzeni.  
- **Rune** – specjalny tryb do kodowania znaków Unicode (run).  

Wybierz tryb za pomocą `Generator.Parameters.Barcode.Aztec.SymbolMode`. Każdy tryb równoważy rozmiar, czytelność i pojemność danych, pozwalając dostosować kod do wymagań aplikacji.

## Samouczki kodowania kodu Aztec
Poniżej znajdują się dedykowane przewodniki krok po kroku, które zagłębiają się w każdy z powyższych tematów. Kliknij dowolny link, aby zobaczyć pełne przykłady kodu, wymagania wstępne i wskazówki najlepszych praktyk.

### [Dostosuj współczynnik proporcji kodu Aztec](./aztec-aspect-ratio-customization/)
Dowiedz się, jak dostosować współczynniki proporcji kodów Aztec przy użyciu Aspose.BarCode dla .NET. Twórz unikalne, elastyczne kody dla swoich aplikacji .NET.

### [Kodowanie bajtów Aztec](./aztec-bytes-encoding/)
Dowiedz się, jak wykonać kodowanie bajtów Aztec przy użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku, wymagania wstępne i przykłady kodu w zestawie.

### [Kodowanie tekstu Aztec](./aztec-code-text-encoding/)
Odkryj możliwości kodowania tekstu Aztec przy użyciu Aspose.BarCode dla .NET. Dowiedz się, jak tworzyć i rozpoznawać kody Aztec w swoich aplikacjach .NET.

### [Generowanie kodów Aztec z poziomami korekcji błędów](./aztec-error-level-example/)
Dowiedz się, jak generować kody Aztec z różnymi poziomami korekcji błędów przy użyciu Aspose.BarCode dla .NET. Kompletny przewodnik tworzenia kodów kreskowych.

### [Opanowanie trybu Symbolu Aztec](./aztec-symbol-mode-example/)
Poznaj tryb Symbolu Aztec w Aspose.BarCode dla .NET i dowiedz się, jak łatwo generować wszechstronne kody kreskowe. Praktyczne ćwiczenia z trybami Auto, FullRange, Compact i Rune w tym kompleksowym samouczku.

## Najczęściej zadawane pytania

**Q: Które wersje .NET są obsługiwane przez Aspose.BarCode dla kodowania Aztec?**  
A: Biblioteka działa z .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 i nowszymi.

**Q: Czy mogę stworzyć wysokiej rozdzielczości kod Aztec do druku?**  
A: Tak — ustaw właściwość `Resolution` (np. 300 dpi) przed zapisaniem obrazu, aby uzyskać jakość gotową do druku.

**Q: Jak duży ładunek danych może pomieścić kod Aztec?**  
A: Do 3 000 znaków numerycznych lub 2 300 znaków alfanumerycznych, lub około 1 800 bajtów surowych danych w trybie Compact.

**Q: Czy można odczytać kod Aztec, który został obrócony?**  
A: Zdecydowanie — dekoder Aspose.BarCode automatycznie wykrywa orientację i koryguje ją podczas odczytu.

**Q: Czy potrzebuję licencji do rozwoju i testowania?**  
A: Dostępna jest darmowa licencja ewaluacyjna do testów; licencja komercyjna jest wymagana przy wdrożeniach produkcyjnych.

---

**Ostatnia aktualizacja:** 2026-05-19  
**Testowano z:** Aspose.BarCode 24.12 dla .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Kodowanie bajtów Aztec przy użyciu generatora kodów .NET](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Jak stworzyć kod Aztec z korekcją błędów w .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}