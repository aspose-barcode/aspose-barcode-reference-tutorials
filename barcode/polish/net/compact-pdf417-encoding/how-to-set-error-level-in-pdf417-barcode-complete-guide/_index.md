---
category: general
date: 2026-07-18
description: jak ustawić poziom błędu w kodzie kreskowym PDF417 przy użyciu Aspose.BarCode.
  Dowiedz się, jak wygenerować kod PDF417 z własnym tekstem i dostosować korekcję
  błędów w kilka minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: pl
lastmod: 2026-07-18
og_description: Jak szybko ustawić poziom korekcji błędów w kodzie kreskowym PDF417.
  Ten samouczek poprowadzi Cię przez generowanie kodu PDF417 z własnym tekstem i różnymi
  poziomami korekcji błędów.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Jak ustawić poziom korekcji błędów w kodzie kreskowym PDF417 – przewodnik
  krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Jak ustawić poziom korekcji błędów w kodzie kreskowym PDF417 – kompletny przewodnik
url: /pl/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić poziom błędu w kodzie kreskowym PDF417 – Kompletny przewodnik

Zastanawiałeś się kiedyś **jak ustawić błąd** podczas generowania kodu kreskowego PDF417? Nie jesteś sam — większość programistów napotyka ten problem, gdy potrzebują bardziej wytrzymałego kodu do skanowania w trudnych warunkach. Dobra wiadomość? Dostosowanie poziomu korekcji błędów jest proste dzięki Aspose.BarCode, a także dowiesz się **jak generować PDF417** z własnym niestandardowym tekstem.

W tym samouczku przeprowadzimy Cię przez każdy krok, od stworzenia generatora kodów kreskowych z znakami specjalnymi po zapisanie dwóch plików PNG prezentujących różne poziomy korekcji błędów. Po zakończeniu będziesz pewny w **generowaniu kodu kreskowego PDF417**, dostosowywaniu jego wymiaru X, liczby kolumn oraz, co najważniejsze, **ustawianiu poziomów błędu**, które pasują do Twojego przypadku użycia.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework)
- Aspose.BarCode dla .NET zainstalowany (`Install-Package Aspose.BarCode` via NuGet)
- Folder na dysku, w którym można zapisywać obrazy (zamień `YOUR_DIRECTORY/` w przykładzie)
- Podstawowa znajomość C# — jeśli wcześniej używałeś `Console.WriteLine`, jesteś gotowy

> **Wskazówka:** Jeśli tworzysz rozwiązanie do skanowania mobilnego, dąż do wyższego poziomu błędu (Level 5), aby przetrwać brud, zadrapania lub warunki słabego oświetlenia.

## Krok 1: Utwórz generator kodu kreskowego z własnym tekstem

Pierwszą rzeczą, której potrzebujesz, jest instancja `BarcodeGenerator`, która wie, że ma generować **kod kreskowy PDF417** i zawiera dokładny tekst, który chcesz zakodować. Zwróć uwagę na użycie znaków akcentowanych oraz symbolu praw autorskich — to dowodzi, że generator radzi sobie z Unicode od razu.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Dlaczego to ważne:* Flaga `EncodeTypes.Pdf417` informuje Aspose, że pracujesz z dwuwymiarowym, warstwowym kodem kreskowym, a argument typu string staje się ładunkiem danych. Jeśli pominiesz ten krok, otrzymasz domyślny kod Code128 zamiast pożądanego, wysokopojemnościowego PDF417.

## Krok 2: Dostosuj parametry wizualne

Kod kreskowy PDF417 to nie tylko dane; to także wzór wizualny. Dostosowanie **wymiaru X** (szerokości najmniejszego paska) oraz liczby **kolumn** pozwala kontrolować fizyczny rozmiar i czytelność kodu.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Dlaczego to ważne:* Mniejszy wymiar X daje bardziej zwartą grafikę, ale może stać się nieczytelny dla skanerów o niskiej rozdzielczości. Trzy kolumny zapewniają zrównoważony stosunek proporcji dla większości rozmiarów etykiet.

## Krok 3: Ustaw poziom korekcji błędów na 2 i zapisz

Korekcja błędów jest sednem **jak ustawić błąd** dla PDF417. Enum `Pdf417ErrorLevel` obejmuje wartości od `Level0` (brak dodatkowych danych) do `Level5` (maksymalna redundancja). Tutaj zaczynamy od **Level 2**, który dodaje umiarkowaną odporność na błędy bez znacznego powiększania obrazu.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Po uruchomieniu tego fragmentu znajdziesz w swoim folderze plik `Pdf417ErrorLevel2.png`. Otwórz go, a zobaczysz czysty kod kreskowy o trzech kolumnach, który nadal zawiera przyzwoitą ilość redundancji.

## Krok 4: Zwiększ korekcję błędów do poziomu 5 i zapisz ponownie

Czasami potrzebny jest kod, który przetrwa bardziej intensywne uszkodzenia — pomyśl o podłodze magazynu, na której etykiety są zarysowane. Przejście na **Level 5** maksymalizuje korekcję błędów kosztem nieco większego obrazu.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Teraz masz dwa pliki PNG obok siebie: jeden z umiarkowaną korekcją błędów, drugi z maksymalną. Porównaj je; wersja Level 5 będzie miała więcej ciemnych modułów, co jest dokładnie tym, co algorytm dodaje, aby chronić dane.

![przykład ustawiania poziomu błędu w kodzie kreskowym PDF417](image.png)

*Opis obrazu (tekst alternatywny): przykład ustawiania poziomu błędu w kodzie kreskowym PDF417 – pokazuje dwa pliki PNG z różnymi poziomami korekcji błędów.*

## Oczekiwany wynik

| Nazwa pliku                   | Poziom błędu | Przybliżone wymiary (px) |
|-------------------------------|--------------|--------------------------|
| `Pdf417ErrorLevel2.png`       | Level 2      | 150 × 80                 |
| `Pdf417ErrorLevel5.png`       | Level 5      | 180 × 95                 |

Oba obrazy kodują ciąg **„Åspóse.Barcóde©”** i mogą być odczytane przez dowolny standardowy czytnik PDF417 (np. ZXing, Scandit). Obraz Level 5 wytrzymuje uszkodzenia do około 30 %, podczas gdy Level 2 radzi sobie z około 15 % uszkodzeń.

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli mój tekst zawiera podziały linii?

PDF417 automatycznie koduje znaki końca linii (`\n`). Po prostu umieść je w ciągu znaków:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Czy mogę użyć innego formatu obrazu?

Oczywiście. Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Svg` w zależności od dalszego przepływu pracy.

### Czy zmiana wymiaru X wpływa na korekcję błędów?

Pośrednio, tak. Większy wymiar X daje większe moduły, co może poprawić niezawodność skanowania, ale **nie** zmienia logicznego poziomu korekcji błędów. Dla najlepszych rezultatów dostosuj oba parametry niezależnie.

### Jak generować kod kreskowy PDF417 w API webowym?

Umieść ten sam kod w kontrolerze ASP.NET Core i strumieniuj PNG jako `FileResult`. Główna logika pozostaje niezmieniona, co oznacza, że **jak generować PDF417** jest spójne zarówno w środowiskach desktopowych, jak i webowych.

## Podsumowanie

Omówiliśmy **jak ustawić błąd** dla kodu kreskowego PDF417, zademonstrowaliśmy **jak generować PDF417** z własnym tekstem Unicode oraz pokazaliśmy, jak dostosować ustawienia wizualne, takie jak wymiar X i liczba kolumn. Zamieniając `Pdf417ErrorLevel.Level2` na `Level5`, możesz kontrolować kompromis między rozmiarem obrazu a odpornością.

## Kolejne kroki

- Eksperymentuj z **kodem kreskowym z własnym tekstem**, który zawiera adresy URL lub identyfikatory produktów.
- Wypróbuj różne liczby kolumn (`generator.Parameters.Barcode.Pdf417.Columns = 5`), aby zobaczyć, jak zmienia się kształt.
- Połącz PDF417 z innymi typami kodów kreskowych w tym samym dokumencie, aby uzyskać rozwiązania skanowania wielomodalnego.
- Zagłęb się w [oficjalną dokumentację](https://docs.aspose.com/barcode/net/) Aspose, aby poznać zaawansowane funkcje, takie jak macro PDF417 czy tryb kompaktowy.

Śmiało zostaw komentarz, jeśli napotkasz problemy, lub podziel się własnymi wynikami skanowania. Miłego tworzenia kodów kreskowych!

## Co warto nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z instrukcjami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak stworzyć kod Aztec z korekcją błędów w .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Jak generować kody DataMatrix (ECC 200) z Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}