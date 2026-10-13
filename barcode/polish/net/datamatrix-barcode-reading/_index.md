---
date: 2026-09-28
description: Dowiedz się, jak odczytywać kody DataMatrix i jak łatwo generować kody
  kreskowe DataMatrix przy użyciu Aspose.BarCode for .NET. Poznaj programowanie czytnika,
  funkcję structured append oraz przewodniki generowania.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Odczytywanie kodów DataMatrix
og_description: Jak odczytywać kody DataMatrix przy użyciu Aspose.BarCode for .NET
  – szybki, wieloplatformowy przewodnik obejmujący odczyt, structured append i generowanie.
  (150‑160 znaków)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Jak odczytywać kody DataMatrix za pomocą Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Jak odczytywać kody DataMatrix za pomocą Aspose.BarCode for .NET
url: /pl/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytywać kody DataMatrix

Jeśli potrzebujesz **how to read datamatrix** efektywnie w środowisku .NET, ten przewodnik zapewnia krok po kroku opis odczytu, konfigurowania structured append oraz generowania kodów DataMatrix przy użyciu Aspose.BarCode for .NET. Zobaczysz, dlaczego biblioteka jest najlepszym wyborem, co musisz przygotować wcześniej oraz gdzie znaleźć najbardziej przydatne fragmenty kodu.

## Szybkie odpowiedzi
- **Czym jest DataMatrix?** Dwu‑wymiarowy kod macierzowy, który przechowuje duże ilości danych w małym rozmiarze.  
- **Która biblioteka pomaga odczytywać DataMatrix w .NET?** Aspose.BarCode for .NET.  
- **Czy potrzebuję licencji?** Dostępna jest darmowa wersja próbna; do produkcji wymagana jest licencja komercyjna.  
- **Czy mogę również generować kody DataMatrix?** Tak — użyj tego samego API do **how to generate datamatrix** kodów z własnymi ustawieniami.  
- **Obsługiwane platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 na Windows, Linux i macOS.

## Co to jest odczyt kodu DataMatrix?
Odczyt kodu DataMatrix wyodrębnia zakodowany tekst lub dane binarne z obrazu, strony PDF lub klatki wideo na żywo. Dekoder Aspose.BarCode działa bezpośrednio z obiektami `System.Drawing.Image`, `Stream` lub `PdfPage`, więc możesz podawać mu pliki, strumienie pamięci lub przechwyty z kamery bez dodatkowych kroków konwersji.

## Dlaczego używać Aspose.BarCode do DataMatrix?
Aspose.BarCode przetwarza do **5 000 kodów na sekundę** na standardowym procesorze 2,5 GHz, obsługuje **ponad 50 formatów wejściowych** i nie wymaga **żadnych zewnętrznych zależności natywnych**. Biblioteka działa na Windows, Linux i macOS, wspiera poziomy korekcji błędów od ECC 000 do ECC 200 oraz oferuje wbudowaną obsługę structured‑append — wszystko przy zużyciu pamięci poniżej 20 MB dla partii 1 000 stron.

## Wymagania wstępne
- .NET Framework 4.5+ lub .NET Core 3.1+ (dowolna aktualna wersja .NET).  
- Zainstalowany pakiet NuGet Aspose.BarCode for .NET.  
- Podstawowa znajomość C# oraz IDE, takiego jak Visual Studio lub Rider.

## Programowanie czytnika DataMatrix: płynna integracja

### Jak odczytać kod DataMatrix w .NET?
`BarcodeReader` to klasa Aspose.BarCode, która dekoduje kody kreskowe z obrazów, strumieni lub stron PDF.  
Załaduj obraz lub stronę PDF, utwórz `BarcodeReader`, włącz flagę `ReadMultipleBarcodes`, jeśli spodziewasz się więcej niż jednego kodu, i wywołaj `Read`. Metoda zwraca kolekcję `BarCodeResult` zawierającą odkodowaną wartość, typ symbolu oraz współczynnik pewności.  
`BarCodeResult` reprezentuje pojedynczy odkodowany kod, w tym jego wartość, typ symbolu i współczynnik pewności.

### Jak włączyć obsługę structured append?
Ustaw właściwość `ReadStructuredAppend` na `true` przed wywołaniem `Read`. Czytnik automatycznie połączy fragmenty należące do tej samej logicznej wiadomości, zwracając pojedynczy połączony wynik.

## Konfiguracja structured append dla DataMatrix: precyzyjne organizowanie danych
Structured Append umożliwia podzielenie jednej logicznej wiadomości na wiele symboli DataMatrix. Po włączeniu tej funkcji Aspose.BarCode składa fragmenty na podstawie numerów sekwencji osadzonych w każdym symbolu. Jest to idealne rozwiązanie do kodowania długich adresów URL, dużych danych binarnych lub dokumentów wielostronicowych.

## Generowanie kodów DataMatrix: uwolnij kreatywność z Aspose.BarCode dla .NET
`BarcodeGenerator` to klasa Aspose.BarCode używana do generowania obrazów kodów kreskowych z konfigurowalnymi parametrami. Ta sama klasa `BarcodeGenerator`, której używasz do odczytu, tworzy również symbole DataMatrix. Możesz kontrolować rozmiar modułu, margines, poziom ECC oraz nawet osadzić obraz logo. Generator wyjściowy może być w formacie PNG, JPEG, SVG lub PDF, zapewniając pełną elastyczność dla scenariuszy web, druku lub mobilnych.

## Samouczki odczytu kodów DataMatrix
### [Programowanie czytnika DataMatrix](./datamatrix-reader-programming/)
Poznaj programowanie czytnika DataMatrix z Aspose.BarCode dla .NET. Dowiedz się, jak generować i odczytywać kody DataMatrix w aplikacjach .NET dzięki temu kompleksowemu przewodnikowi.
### [Konfiguracja Structured Append dla DataMatrix](./datamatrix-structured-append-configuration/)
Dowiedz się, jak tworzyć i odczytywać konfigurację structured append dla DataMatrix w .NET przy użyciu Aspose.BarCode w celu wysokiej wydajności organizacji danych.
### [Generowanie kodów DataMatrix](./datamatrix-versions/)
Dowiedz się, jak generować kody DataMatrix w .NET przy użyciu Aspose.BarCode for .NET. Niestandardowe wymiary, wsparcie ECC i więcej.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.BarCode w projektach komercyjnych?**  
A: Tak. Wymagana jest ważna licencja komercyjna do użytku produkcyjnego, ale dostępna jest darmowa wersja próbna do oceny.

**Q: Czy biblioteka obsługuje odczyt DataMatrix z plików PDF?**  
A: Zdecydowanie tak. Możesz załadować stronę PDF jako strumień obrazu i przekazać ją bezpośrednio do czytnika kodów.

**Q: Jak obsłużyć Structured Append, gdy kod jest podzielony na wiele obrazów?**  
A: API automatycznie składa fragmenty, jeśli włączysz właściwość `ReadStructuredAppend` przed dekodowaniem.

**Q: Jakie poziomy korekcji błędów są dostępne przy generowaniu kodu DataMatrix?**  
A: Możesz wybrać spośród ECC 000, 050, 080, 100, 140 i 200 w zależności od wymaganego zagęszczenia danych i odporności.

**Q: Czy istnieje sposób na poprawę wydajności odczytu przy dużych partiach obrazów?**  
A: Tak — użyj `BarcodeReader` z ustawionym `ReadMultipleBarcodes` na `true` i przetwarzaj obrazy w równoległych wątkach.

---

**Ostatnia aktualizacja:** 2026-09-28  
**Testowano z:** Aspose.BarCode for .NET 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – Przewodnik krok po kroku](/barcode/net/datamatrix-barcode-configuration/)
- [Jak odczytać DataMatrix Append przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Generowanie kodu DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}