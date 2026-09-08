---
date: 2026-09-08
description: Dowiedz się, jak utworzyć kod kreskowy code 128 i generować kody kreskowe
  GS1 w C# przy użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku, wymagania
  wstępne oraz personalizacja bez kodu.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Przykład GS1 Code 128
og_description: Dowiedz się, jak utworzyć kod kreskowy code 128 i generować kody kreskowe
  GS1 w C# przy użyciu Aspose.BarCode dla .NET. Skorzystaj z przewodnika krok po kroku,
  aby szybko generować i zapisywać obrazy kodów kreskowych.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Jak utworzyć kod kreskowy code 128 z GS1 przy użyciu Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Jak utworzyć kod kreskowy code 128 z GS1 przy użyciu Aspose.BarCode
url: /pl/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy Code 128 z GS1 przy użyciu Aspose.BarCode

W tym samouczku dowiesz się, jak **utworzyć kod kreskowy Code 128**, który spełnia standard GS1, używając biblioteki Aspose.BarCode dla .NET. Niezależnie od tego, czy potrzebujesz kodu kreskowego do inwentaryzacji, wysyłki czy punktu sprzedaży, ten przewodnik przeprowadzi Cię przez każdy krok — od skonfigurowania środowiska programistycznego po zapisanie ostatecznego obrazu — abyś mógł zacząć generować niezawodne kody kreskowe w kilka minut.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do generowania kodu kreskowego?** `BarcodeGenerator` tworzy i konfiguruje obraz kodu kreskowego.  
- **Jakiej symbologii używa GS1 Code 128?** Używa typu `EncodeTypes.Code128` z formatowaniem danych specyficznym dla GS1.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa w celach oceny; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić format obrazu?** Tak — zapisz jako PNG, JPEG, BMP lub TIFF, zmieniając rozszerzenie pliku.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ i .NET 6+.

## Czym jest tworzenie kodu kreskowego Code 128?
`create code 128 barcode` odnosi się do generowania liniowego kodu kreskowego, który koduje dane alfanumeryczne przy użyciu symbologii Code 128, szeroko stosowanej w logistyce, ponieważ obsługuje pełny zestaw ASCII i może zawierać identyfikatory aplikacji GS1. Kod kreskowy może przechowywać identyfikatory produktów, numery seryjne i inne dane niestandardowe, co czyni go odpowiednim dla szerokiego zakresu scenariuszy biznesowych.

## Dlaczego warto używać Aspose.BarCode dla GS1 Code 128?
Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i może renderować obrazy o rozdzielczości do **10 000 × 10 000 px** bez utraty jakości, co czyni go odpowiednim do druku etykiet w wysokiej rozdzielczości. Biblioteka automatycznie waliduje struktury danych GS1, zmniejszając ryzyko nieprawidłowych kodów kreskowych w liniach produkcyjnych. Dodatkowo oferuje rozbudowane opcje dostosowywania rozmiaru, koloru i układu, co pomaga spełnić rygorystyczne normy branżowe.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne .NET** – Visual Studio 2022, Rider lub dowolne IDE obsługujące .NET 6+.  
2. **Aspose.BarCode for .NET** – pobierz go ze **strony pobierania Aspose.BarCode for .NET** pod adresem [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) i dodaj pakiet NuGet `Aspose.BarCode` do swojego projektu.  
3. **Podstawowa znajomość C#** – powinieneś być swobodny w tworzeniu aplikacji konsolowych lub Windows.  
4. **Znajomość GS1 Code 128** – opcjonalna, ale przydatna; GS1 używa identyfikatorów aplikacji (AI) takich jak `(01)` dla GTIN i `(21)` dla numerów seryjnych.

## Jak utworzyć kod kreskowy Code 128 krok po kroku

Załaduj bibliotekę, skonfiguruj typ kodu kreskowego, ustaw dane GS1, dostosuj wymiary i na koniec zapisz obraz. Bezpośrednia odpowiedź na pytanie „jak utworzyć kod kreskowy Code 128?” brzmi: **zainicjuj `BarcodeGenerator` z `EncodeTypes.Code128` i danymi sformatowanymi zgodnie z GS1, w razie potrzeby dostosuj `XDimension`, a następnie wywołaj `Save` z żądaną nazwą pliku i formatem**. Poniższe sekcje rozkładają każdy krok.

### Krok 1: ustaw ścieżkę katalogu
Zdefiniuj folder, w którym będzie przechowywany wygenerowany obraz. Utrzymanie ścieżki konfigurowalnej sprawia, że kod jest wielokrotnego użytku w różnych środowiskach.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Zastąp `"Your Directory Path"` ścieżką absolutną lub względną, do której aplikacja może zapisywać, np. `@"C:\\Barcodes"` lub `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Krok 2: utwórz kod kreskowy GS1 Code 128
Utwórz generator kodu kreskowego, określ symbologię i podaj dane sformatowane zgodnie z GS1. Ciąg danych musi zawierać identyfikatory aplikacji otoczone nawiasami.

```csharp
string path = "Your Directory Path";
```

Przykład używa GTIN `(01)12345678901231`, numeru seryjnego `(21)ASPOSE` oraz dodatkowego niestandardowego AI `(30)9876`. Aspose.BarCode automatycznie wstawia wymagany znak FNC1 dla zgodności z GS1.

### Krok 3: dostosuj parametry kodu kreskowego
Dostosuj parametry wizualne, takie jak `XDimension` (szerokość wąskiej kreski), aby kontrolować gęstość kodu kreskowego. Możesz także zmienić wysokość, kolory i marginesy.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Ustawienie `XDimension = 2` daje kod kreskowy, który jest łatwo odczytywalny przez większość przenośnych czytników, przy jednoczesnym zachowaniu umiarkowanego rozmiaru obrazu.

### Krok 4: zapisz obraz kodu kreskowego
Zachowaj wygenerowany kod kreskowy na dysku. Możesz wybrać PNG dla jakości bezstratnej, JPEG dla mniejszych plików lub TIFF dla procesów drukowania. Metoda `Save` zapisuje plik obrazu w formacie wskazanym przez rozszerzenie pliku.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Zastąp `GS1Code128Example.png` dowolną prawidłową nazwą pliku i rozszerzeniem, które odpowiadają pożądanemu formatowi wyjściowemu.

### Krok 5: zweryfikuj kod kreskowy (opcjonalnie)
Po zapisaniu możesz wczytać obraz z powrotem do aplikacji lub użyć skanera kodów kreskowych, aby potwierdzić, że zakodowane dane odpowiadają oryginalnemu ciągowi. Ten krok jest przydatny podczas rozwoju i testów automatycznych.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Typowe problemy i wskazówki rozwiązywania
- **FNC1 nie wykryty** – Upewnij się, że ciąg danych zaczyna się od otwierającego nawiasu i zawiera prawidłowe GS1 AI; biblioteka automatycznie wstawia FNC1 tylko dla rozpoznanych wzorców.  
- **Obraz nie został zapisany** – Sprawdź, czy docelowy katalog istnieje i aplikacja ma uprawnienia do zapisu. Użyj `Directory.CreateDirectory(path)`, aby utworzyć go w locie.  
- **Kod kreskowy zbyt gęsty** – Zmniejsz `XDimension` lub zwiększ wysokość obrazu, aby dać skanerom więcej miejsca na odczyt wąskich kresek.  
- **Nieobsługiwane znaki** – Code 128 może kodować tylko pełny zestaw ASCII; unikaj znaków Unicode spoza tego zakresu.

## Najczęściej zadawane pytania

**Q: Czy mogę generować kody kreskowe w API webowym bez instalacji pełnego .NET Framework?**  
A: Tak, Aspose.BarCode działa z .NET Core oraz .NET 5/6, więc możesz udostępnić lekkie API REST, które zwraca obrazy kodów kreskowych na żądanie.

**Q: Czy biblioteka obsługuje generowanie wsadowe wielu kodów kreskowych?**  
A: Zdecydowanie tak. Przejdź pętlą po kolekcji ciągów danych, utwórz `BarcodeGenerator` dla każdego i wywołaj `Save` wewnątrz pętli. Biblioteka jest bezpieczna wątkowo dla przetwarzania równoległego.

**Q: Czy istnieje sposób, aby osadzić kod kreskowy bezpośrednio w pliku PDF?**  
A: Użyj Aspose.PDF do stworzenia dokumentu PDF, a następnie wywołaj `PdfPage.AddImage` z strumieniem obrazu kodu kreskowego. To eliminuje konieczność zapisywania plików pośrednich na dysku.

**Q: Jak mogę zapewnić, że kod kreskowy spełnia standardy jakości ISO/GS1?**  
A: Ustaw `BarcodeGenerator.Options.Barcode.XDimension` na co najmniej 0,33 mm i ustaw `BarHeight` zgodnie z rozmiarem etykiety. Aspose.BarCode waliduje format AI i zgłasza wyjątek przy nieprawidłowych danych.

**Q: Jakie opcje licencjonowania są dostępne do użytku produkcyjnego?**  
A: Aspose oferuje modele licencjonowania wieczystego, subskrypcyjnego oraz opartego na chmurze. Licencja próbna działa w celach oceny, ale licencja płatna usuwa znak wodny oceny i odblokowuje wszystkie funkcje.

## Dodatkowe zasoby

- **Dokumentacja** – Uzyskaj pełną referencję API pod adresem [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Pobieranie** – Pobierz najnowszą wersję biblioteki z [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Darmowa wersja próbna** – Rozpocznij 30‑dniowy trial pod adresem [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Zakup** – Kup licencję komercyjną pod adresem [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Wsparcie** – Dołącz do forum społeczności pod adresem [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) w celu uzyskania pomocy przy rozwiązywaniu problemów.

---

**Ostatnia aktualizacja:** 2026-09-08  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć kod kreskowy ITF-14 .NET – Kompleksowe samouczki Aspose.BarCode](/barcode/net/)
- [Generuj jednowymiarowe kody Databar 2D przy użyciu Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}