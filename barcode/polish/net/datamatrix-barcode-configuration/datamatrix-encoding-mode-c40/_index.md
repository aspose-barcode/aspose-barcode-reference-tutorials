---
date: 2026-06-09
description: Dowiedz się, jak generować kody kreskowe DataMatrix i zapisywać PNG przy
  użyciu kodowania C40 z Aspose.BarCode – pełny przewodnik po generowaniu kodów kreskowych
  w .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Tryb kodowania DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak wygenerować DataMatrix PNG w trybie C40 przy użyciu Aspose.BarCode
url: /pl/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tryb kodowania DataMatrix (C40) w Aspose.BarCode dla .NET

## Wprowadzenie

W tym samouczku nauczysz się **jak generować datamatrix** i zapisywać je jako pliki PNG, używając trybu kodowania C40 w Aspose.BarCode dla .NET. Niezależnie od tego, czy tworzysz system inwentaryzacji, generator etykiet wysyłkowych, czy dowolne rozwiązanie wymagające kompaktowych, wysokogęstościowych symboli, opanowanie C40 zapewnia mniejsze symbole bez utraty czytelności. Przejdziemy przez każdy krok — od konfiguracji środowiska po wygenerowanie ostatecznego pliku PNG — abyś mógł od razu włączyć kod do swojego projektu.

## Szybkie odpowiedzi
- **Co oznacza „jak generować datamatrix”?** Tworzenie obrazu kodu DataMatrix programowo.  
- **Jaki tryb kodowania jest omawiany?** DataMatrix C40, wydajny schemat alfanumeryczny.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę uruchomić to na .NET Core?** Tak, Aspose.BarCode w pełni obsługuje .NET Core, .NET 5, .NET 6 i nowsze.  
- **Jaki format pliku jest tworzony?** PNG — format bezstratny, przyjazny dla sieci.

## Jak generować DataMatrix przy użyciu kodowania C40

Wczytaj dane, skonfiguruj generator i wywołaj `Save` — to pełny przepływ pracy w trzech zwięzłych krokach. Klasa `BarcodeGenerator` obsługuje tworzenie symbolu, a enum `BarCodeImageFormat.Png` informuje Aspose.BarCode, aby zapisał wynik jako plik PNG. `Save` zapisuje wygenerowany obraz kodu kreskowego do określonej ścieżki pliku w wybranym formacie. Ten akapit z bezpośrednią odpowiedzią dostarcza rozwiązanie od początku do końca, zanim przejdziemy do analizy każdego wiersza kodu.

## Co to jest tryb kodowania DataMatrix (C40)?

`DataMatrixEncodeMode` jest wyliczeniem określającym, którego schematu kodowania Aspose.BarCode ma używać dla symboli DataMatrix. Opcja `DataMatrixEncodeMode.C40` wybiera alfanumeryczne kodowanie C40, które pakuje litery, cyfry i ograniczony zestaw znaków interpunkcyjnych w mniejszej liczbie modułów, zmniejszając ogólny rozmiar symbolu przy zachowaniu czytelności typowego tekstu inwentaryzacyjnego. Ten wydajny schemat jest idealny, gdy trzeba zakodować dane alfanumeryczne w kompaktowej formie.

## Dlaczego warto używać Aspose.BarCode dla .NET?

Aspose.BarCode oferuje **ponad 30 konfigurowalnych parametrów** dotyczących wymiarów, poziomów korekcji błędów i trybów kodowania oraz obsługuje **ponad 50 formatów obrazów i kodów kreskowych**. Biblioteka działa na **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, zapewniając generowanie bez zależności, które działa na serwerach, komputerach stacjonarnych i urządzeniach mobilnych.

## Wymagania wstępne

Przed przejściem do kodu upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne .NET** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
2. **Aspose.BarCode for .NET** – zainstalowane przez NuGet lub oficjalny instalator. Zobacz [dokumentację](https://reference.aspose.com/barcode/net/) po szczegóły.  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z przestrzeniami nazw, klasami i dyrektywami using.  
4. **Folder z prawem zapisu** – katalog na twoim komputerze, w którym zostanie zapisany plik PNG.

## Importowanie niezbędnych przestrzeni nazw

Klasa `BarcodeGenerator` jest punktem wejścia do tworzenia dowolnego kodu kreskowego. Dodaj wymaganą przestrzeń nazw na początku pliku źródłowego C#, aby uzyskać dostęp do API generowania:

```csharp
using Aspose.BarCode.Generation;
```

## Krok po kroku generowanie kodu kreskowego

Poniżej znajduje się **przewodnik krok po kroku** po generowaniu kodu kreskowego. Każdy krok jest wyjaśniony prostym językiem, a oryginalne znaczniki pozostają niezmienione dla wygody kopiowania.

### Krok 1: Zdefiniuj ścieżkę katalogu
Ustaw folder, w którym zostanie zapisany obraz PNG. Zastąp znacznik rzeczywistą ścieżką na swoim komputerze.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Konfiguracja generowania kodu kreskowego
Utwórz instancję `BarcodeGenerator`, określ `EncodeTypes.DataMatrix` i podaj dane, które chcesz zakodować.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Krok 3: Dostosowanie kodu kreskowego
Skonfiguruj wymiar X (szerokość piksela modułów) i przełącz tryb kodowania na C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Krok 4: Zapisz obraz kodu kreskowego
Na koniec zapisz wygenerowany kod kreskowy jako plik PNG. To konkretna odpowiedź na pytanie **jak zapisać png** przy użyciu Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Po uruchomieniu programu znajdziesz plik `DataMatrixEncodeModeC40.png` w określonym folderze, gotowy do użycia w raportach, etykietach lub stronach internetowych.

## Typowe problemy i wskazówki

- **Nieprawidłowa ścieżka** – Upewnij się, że katalog istnieje i masz uprawnienia do zapisu; w przeciwnym razie `gen.Save` zgłosi wyjątek.  
- **Nieprawidłowy tryb kodowania** – Jeśli musisz zakodować znaki spoza zestawu C40, przełącz się na `DataMatrixEncodeMode.Auto` lub inny odpowiedni tryb.  
- **Rozmiar obrazu** – Dostosuj `XDimension.Pixels`, aby zwiększyć lub zmniejszyć ogólny rozmiar kodu kreskowego bez wpływu na czytelność.

## Najczęściej zadawane pytania

**Q: Co to jest tryb kodowania DataMatrix (C40)?**  
A: C40 to kompaktowy schemat kodowania alfanumerycznego dla symboli DataMatrix, idealny dla tekstu zawierającego litery, cyfry i ograniczony zestaw znaków specjalnych.

**Q: Gdzie mogę znaleźć dokumentację Aspose.BarCode dla .NET?**  
A: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/barcode/net/). Zawiera szczegółowe wskazówki dotyczące wszystkich typów kodów kreskowych i opcji kodowania.

**Q: Czy Aspose.BarCode dla .NET jest kompatybilny ze wszystkimi wersjami .NET?**  
A: Tak, biblioteka obsługuje szeroki zakres wersji .NET, od .NET Framework 4.5+ po .NET 6 i nowsze.

**Q: Czy mogę wypróbować Aspose.BarCode dla .NET przed zakupem?**  
A: Tak, możesz wypróbować darmową wersję próbną Aspose.BarCode dla .NET, odwiedzając [ten link](https://releases.aspose.com/). Pozwala to przetestować funkcje i możliwości biblioteki.

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.BarCode dla .NET?**  
A: Społeczność i wsparcie dla Aspose.BarCode dla .NET znajdziesz na [forum Aspose](https://forum.aspose.com/c/barcode/13).

## Podsumowanie

Korzystając z tego **przewodnika krok po kroku**, teraz dokładnie wiesz **jak generować datamatrix** i zapisywać je jako pliki PNG przy użyciu trybu kodowania C40 w Aspose.BarCode dla .NET. To podejście daje pełną kontrolę nad wyglądem, rozmiarem i reprezentacją danych kodu kreskowego, ułatwiając wstawianie wysokiej jakości kodów do dowolnej aplikacji .NET.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Kodowanie DataMatrix w bajtach z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Główny tryb kodowania DataMatrix w ASCII z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Jak generować kody DataMatrix (ECC 200) z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}