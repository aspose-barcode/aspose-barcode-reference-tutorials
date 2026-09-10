---
date: 2026-06-09
description: Dowiedz się, jak tworzyć kod kreskowy DataMatrix w trybie ASCII przy
  użyciu Aspose.BarCode dla .NET. Ten przewodnik pokazuje, jak szybko generować kod
  kreskowy w C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Tryb kodowania DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Tworzenie kodu kreskowego DataMatrix w trybie ASCII przy użyciu Aspose.BarCode
  dla .NET
url: /pl/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET

## Wprowadzenie

Gotowy, aby **tworzyć obrazy kodów DataMatrix**, które wykorzystują wydajne kodowanie ASCII? W tym samouczku nauczysz się, jak wygenerować kod DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET. Przejdziemy przez każdy krok — od konfiguracji projektu po zapisanie finalnego obrazu — abyś mógł dodać generowanie kodów kreskowych do swoich aplikacji C# w kilka minut.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza dla DataMatrix w .NET?** Aspose.BarCode for .NET  
- **Ile linii kodu jest potrzebnych?** Około 5‑7 linii dla podstawowego kodu ASCII  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; licencja jest wymagana w produkcji  
- **Obsługiwane platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Czy mogę zmienić rozmiar lub kolory?** Tak, Aspose.BarCode udostępnia właściwości do ustawiania wymiarów oraz kolorów pierwszego planu i tła  

## Co to jest kod kreskowy DataMatrix?
DataMatrix to dwuwymiarowy kod kreskowy, który przechowuje tekst i dane binarne w zwartym, kwadratowym wzorze.  
Kod DataMatrix koduje informacje w siatce czarnych i białych modułów, umożliwiając zapisanie do 2 335 znaków alfanumerycznych w jednym symbolu. Jest szeroko stosowany w przemyśle, logistyce i opiece zdrowotnej, ponieważ może być drukowany w bardzo małych rozmiarach przy zachowaniu wysokiej czytelności.

## Jak utworzyć kod kreskowy DataMatrix w trybie ASCII?
Załaduj przestrzeń nazw Aspose.BarCode, utwórz instancję `BarcodeGenerator`, ustaw `EncodeMode` na **EncodeMode.ASCII**, przypisz ciąg danych i wywołaj `Save`, aby zapisać plik obrazu. To podejście generuje w pełni zgodny kod DataMatrix z kodowaniem wyłącznie ASCII w kilku linijkach kodu C#.

## Dlaczego używać kodowania ASCII dla DataMatrix?
Tryb ASCII jest domyślnym i najwydajniejszym kodowaniem dla danych tekstowych, zapewniając najmniejszy możliwy rozmiar symbolu dla ciągów alfanumerycznych. Obsługuje wszystkie 128 znaków ASCII, przetwarza dane szybciej niż tryby rozszerzone i gwarantuje maksymalną kompatybilność ze starszymi skanerami oczekującymi standardowych symboli ASCII.

## Wymagania wstępne

1. **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE kompatybilne z C#.  
2. **Aspose.BarCode for .NET** – Pobierz najnowszy pakiet z [tutaj](https://releases.aspose.com/barcode/net/).  
   - Dokumentacja: [dokumentacja Aspose.BarCode dla .NET](https://reference.aspose.com/barcode/net/)  
   - Pomoc społeczności: [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  
3. **Podstawowa znajomość C#** – Znajomość struktury projektu .NET ułatwi szybkie podążanie za krokami.  
4. **Inne produkty Aspose** można znaleźć [tutaj](https://releases.aspose.com/).

## Importowanie przestrzeni nazw

Aby rozpocząć, dodaj wymagane dyrektywy `using` na początku pliku C#:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Te przestrzenie nazw dają dostęp do klasy `BarcodeGenerator` oraz typów związanych z obrazem potrzebnych do zapisu wyniku.

## Krok 1: Utwórz katalog

Wybierz folder, w którym będą przechowywane wygenerowane obrazy kodów. Zastąp `"Your Directory Path"` absolutną lub względną ścieżką istniejącą na Twoim komputerze.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Kod zapewnia, że katalog istnieje przed próbą zapisu plików, zapobiegając błędom w czasie wykonywania.

## Krok 2: Kodowanie danych w trybie ASCII

Klasa `BarcodeGenerator` tworzy i konfiguruje obrazy kodów. Wyliczenie `DataMatrixEncodeMode` wybiera algorytm kodowania dla symboli DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Po uruchomieniu kodu znajdziesz plik `datamatrix_ascii.png` w wybranym folderze. Obraz zawiera kod DataMatrix, który koduje ciąg `"1234567890"` przy użyciu zwartego trybu ASCII.

## Typowe problemy i rozwiązania

- **Błędy dostępu do pliku** – Upewnij się, że aplikacja ma uprawnienia do zapisu w docelowym folderze. Uruchomienie Visual Studio jako Administrator może rozwiązać problemy z uprawnieniami w systemie Windows.  
- **Nieprawidłowy rozmiar symbolu** – Jeśli kod jest za duży lub za mały, dostosuj `generator.Parameters.Image.Width` i `Height` lub pozwól Aspose automatycznie obliczyć optymalny rozmiar, pomijając te właściwości.  
- **Nieobsługiwane znaki** – Tryb ASCII akceptuje tylko znaki w zakresie 0‑127. Dla danych Unicode przełącz się na `DataMatrixEncodeMode.Base256` lub inny odpowiedni tryb.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego w aplikacji komercyjnej?**  
A: Tak, wymagana jest ważna licencja Aspose do użytku produkcyjnego; dostępna jest bezpłatna wersja próbna do oceny.

**Q: Czy biblioteka działa z .NET Core?**  
A: Zdecydowanie – Aspose.BarCode w pełni wspiera .NET Core 3.1+, .NET 5, .NET 6 i nowsze wersje.

**Q: Ile znaków mogę zakodować w trybie ASCII?**  
A: Do 2 335 znaków alfanumerycznych mieści się w jednym symbolu DataMatrix przy użyciu kodowania ASCII.

**Q: Czy mogę zmienić kolor pierwszego planu lub tła kodu kreskowego?**  
A: Tak, dostosuj `generator.Parameters.Image.ForeColor` i `BackColor` do dowolnej wartości `System.Drawing.Color`.

**Q: Gdzie mogę znaleźć bardziej zaawansowane przykłady?**  
A: Oficjalna dokumentacja zawiera dziesiątki przykładów obejmujących niestandardowe rozmiary, kolory i poziomy korekcji błędów.

## FAQ

### P1: Czy mogę używać Aspose.BarCode dla .NET w innych językach programowania oprócz C#?

O1: Aspose.BarCode obsługuje wiele języków programowania, ale ten samouczek koncentruje się na C#.

### P2: Jakie są różne tryby kodowania dostępne w kodach DataMatrix?

O2: Kody DataMatrix obsługują różne tryby kodowania, w tym ASCII, C40, Text i Base256. Każdy tryb jest przeznaczony do różnych typów danych.

### P3: Czy mogę dostosować wygląd generowanego kodu kreskowego, taki jak rozmiar i kolor?

O3: Tak, Aspose.BarCode udostępnia szeroki zakres parametrów do dostosowywania wyglądu kodu kreskowego, w tym rozmiar, kolor i inne.

### P4: Czy dostępna jest bezpłatna wersja próbna Aspose.BarCode dla .NET?

O4: Tak, możesz wypróbować Aspose.BarCode dla .NET w wersji próbnej z [tutaj](https://releases.aspose.com/).

### P5: Gdzie mogę kupić licencję na Aspose.BarCode dla .NET?

O5: Licencję możesz kupić na stronie Aspose [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-06-09  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Kodowanie DataMatrix w bajtach przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Odczyt kodu DataMatrix C# – Generowanie trybu DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}