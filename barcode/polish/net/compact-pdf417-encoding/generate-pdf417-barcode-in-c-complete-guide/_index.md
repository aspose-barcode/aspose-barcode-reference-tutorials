---
category: general
date: 2026-09-18
description: Dowiedz się, jak szybko stworzyć PDF417 barcode image w C# i ustawić
  columns dla compact barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Dowiedz się, jak szybko stworzyć PDF417 barcode image w C# i ustawić
  columns dla compact barcode. Aspose.BarCode ułatwia to.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Utwórz PDF417 barcode image – przewodnik C# krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Jak stworzyć PDF417 barcode image w C# – kompletny przewodnik
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego PDF417 w C# – kompletny przewodnik

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego PDF417** w aplikacji .NET, trafiłeś we właściwe miejsce. Niezależnie od tego, czy drukujesz etykiety boarding‑pass, kodujesz dane inwentaryzacyjne, czy budujesz system mobilnego biletowania, PDF417 zapewnia wysoką pojemność i dwuwymiarowe kody kreskowe. Ten przewodnik pokazuje, jak wygenerować obraz przy użyciu Aspose.BarCode oraz jak ustawić kolumny, aby kod kreskowy był jak najbardziej zwarty.

## Szybkie odpowiedzi
- **Która biblioteka tworzy kody kreskowe PDF417?** Aspose.BarCode for .NET.
- **Ile linii kodu jest potrzebnych?** Około 10 linii w aplikacji konsolowej.
- **Czy mogę kontrolować szerokość kodu kreskowego?** Tak, ustawiając właściwość `Columns`.
- **Jaki format obrazu jest zalecany?** PNG dla jakości bezstratnej.
- **Czy .NET 6 jest obsługiwany?** Tak – biblioteka działa z .NET 6, .NET 7 i nowszymi.

## Co to jest obraz kodu kreskowego PDF417?
Obraz kodu kreskowego PDF417 to dwuwymiarowa macierz, która przechowuje do 1 700 znaków wierszowo, wykorzystując wiersze i kolumny do gęstego pakowania danych. Aspose.BarCode renderuje tę macierz do standardowych formatów obrazu, takich jak PNG, JPEG czy BMP. Może być zapisywany w różnych formatach i nadaje się do drukowania na etykietach, biletach lub ekranach mobilnych.

## Dlaczego ustawiać kolumny dla zwartego obrazu kodu kreskowego PDF417?
Ustawienie kolumn pozwala zmniejszyć szerokość kodu kreskowego, co jest niezbędne przy wąskich etykietach lub elementach interfejsu o ograniczonej przestrzeni. Aspose.BarCode obsługuje od 1 do 30 kolumn, a wybór mniejszej liczby zmniejsza całkowitą szerokość obrazu nawet o 40 %, zachowując integralność danych. Ta regulacja pomaga dopasować kody kreskowe do małych etykiet bez utraty czytelności.

## Jak utworzyć obraz kodu kreskowego PDF417 w C#?
Załaduj bibliotekę `Aspose.BarCode`, skonfiguruj `BarcodeGenerator` z `EncodeTypes.Pdf417`, ustaw `Columns` i `Truncate`, a następnie zapisz wynik jako PNG. Cały proces wymaga dwóch wywołań metod i tworzy gotowy do użycia plik obrazu. Możesz także dostosować wymiary, kolory i dodać tekst czytelny dla człowieka, aby dopasować go do potrzeb aplikacji.

### Wymagania wstępne
- .NET 6+ SDK (lub nowszy)
- Visual Studio 2022 lub dowolny edytor C#
- Pakiet NuGet `Aspose.BarCode`

### Implementacja krok po kroku

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode
`Aspose.BarCode` to biblioteka .NET służąca do generowania i odczytywania różnych symbologii kodów kreskowych.

```bash
dotnet add package Aspose.BarCode
```

To jedyne polecenie pobiera wszystkie potrzebne typy, w tym `BarcodeGenerator`, `EncodeTypes` oraz wyliczenie `BarCodeImageFormat`.

> **Porada:** Jeśli celujesz w .NET Framework zamiast .NET 6, użyj klasycznego polecenia PowerShell `Install-Package Aspose.BarCode` w konsoli Menedżera Pakietów.

## Krok 2: Utwórz minimalną aplikację konsolową
`BarcodeGenerator` tworzy obrazy kodów kreskowych na podstawie określonych ustawień. `EncodeTypes` wymienia obsługiwane symbologie kodów kreskowych. `BarCodeImageFormat` wymienia formaty obrazów.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Dlaczego to ważne:**  
- `EncodeTypes.Pdf417` informuje bibliotekę, że chcemy kod PDF417, a nie QR ani Code128.  
- `XDimension.Pixels` kontroluje rozdzielczość każdego małego czarnego lub białego modułu.  
- Blok **jak ustawić kolumny** bezpośrednio wpływa na kształt **obrazu kodu kreskowego PDF417**.  
- `Truncate = true` usuwa niepotrzebne puste wiersze, dając „zwarty” wygląd, który wielu skanerów uwielbia.

## Krok 3: Zagłęb się – zrozumienie kolumn i przycinania

### Jak ustawić kolumny
PDF417 układa dane w macierzy *wierszy* × *kolumn*. Biblioteka domyślnie używa 5 kolumn, co działa w większości przypadków. Jednak możesz potrzebować węższego kodu, aby dopasować go do etykiety, lub szerszego, aby zwiększyć niezawodność skanowania. Właściwość:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

przyjmuje wartości od **1** do **30** (dokładny limit zależy od długości danych). Oto szybka karta podpowiedzi:

| Kolumny | Przybliżona szerokość (mm) | Kiedy używać |
|---------|----------------------------|---------------|
| 1‑3     | Bardzo wąska               | Mała etykieta, ograniczona przestrzeń |
| 4‑6     | Standardowa                | Większość paragonów, biletów |
| 7‑10    | Szersza                    | Dane o wysokiej gęstości, lepsza czytelność |

### Truncate (tryb zwarty)
Ustawienie `Truncate = true` instruuje enkoder, aby odciął niepotrzebne puste wiersze na dole. Wynikiem jest **zwarty obraz kodu kreskowego PDF417**, który zajmuje najmniejszą możliwą powierzchnię, zachowując wszystkie dane. Jeśli pojawią się błędy „kod kreskowy za duży dla etykiety”, przełącz tę flagę.

## Krok 4: Uruchom aplikację i zweryfikuj wynik
Skompiluj i uruchom:

```bash
dotnet run
```

Powinieneś zobaczyć komunikat w konsoli potwierdzający lokalizację zapisu. Przejdź do folderu i otwórz `CompactPdf417.png`. Obraz będzie wyglądał mniej więcej tak:

![Wygenerowany obraz kodu kreskowego PDF417](./CompactPdf417.png "Wygenerowany obraz kodu kreskowego PDF417 – zwarty PNG utworzony przez Aspose.BarCode")

[Wygenerowany obraz kodu kreskowego PDF417](./CompactPdf417.png "Wygenerowany obraz kodu kreskowego PDF417 – zwarty PNG utworzony przez Aspose.BarCode")

*Tekst alternatywny obrazu:* **Wygenerowany obraz kodu kreskowego PDF417** – zwarty plik PNG wygenerowany przez kod tutoriala.

Jeśli twój skaner potrafi go odczytać, gratulacje — udało ci się **wygenerować kod kreskowy PDF417** i opanować **jak ustawić kolumny** dla schludnego **obrazu kodu kreskowego PDF417**.

## Krok 5: Częste pułapki i jak je naprawić

| Objaw | Prawdopodobna przyczyna | Szybka naprawa |
|-------|--------------------------|----------------|
| Kod kreskowy jest rozmyty | `XDimension.Pixels` jest zbyt niski (np. 1) | Zwiększ do 2‑3 pikseli, aby uzyskać wyraźniejszy obraz. |
| Skaner nie może odczytać | Zbyt wiele kolumn dla danych | Zredukuj `Columns` lub włącz `Truncate`. |
| Nieprawidłowy format pliku | Zapisano przypadkowo jako `BarCodeImageFormat.Jpeg` | Użyj `BarCodeImageFormat.Png` dla wyników bezstratnych. |
| Wyjątek `ArgumentOutOfRangeException` | Liczba kolumn przekracza dozwolony zakres | Utrzymuj liczbę kolumn w przedziale 1‑30 i upewnij się, że dane się mieszczą. |

## Krok 6: Idź dalej – dostosowywanie kolorów i dodawanie tekstu

Jeśli chcesz, aby kod kreskowy pasował do palety marki, możesz dostosować kolory pierwszego planu i tła:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Albo dodać tekst czytelny dla człowieka pod kodem kreskowym:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Te dodatki są opcjonalne, ale ilustrują, jak elastyczny może być przepływ pracy **generowania kodu kreskowego PDF417**.

## Zakończenie
Przeszliśmy przez kompletny przykład od początku do końca, który **generuje kod kreskowy PDF417** przy użyciu Aspose.BarCode, wyjaśniliśmy **jak ustawić kolumny**, aby kontrolować wymiary kodu, i zapisaliśmy wynik jako wyraźny **obraz kodu kreskowego PDF417** w formacie PNG. Kod jest samodzielny, działa z .NET 6+ i można go wstawić do dowolnego istniejącego projektu z minimalnym nakładem pracy.

Co dalej? Spróbuj kodować większe ładunki (np. ciągi JSON), eksperymentuj z różnymi formatami obrazów lub zintegrować generator z API webowym, które dostarcza kody kreskowe na żądanie. Nie ma granic, a teraz masz solidne podstawy do dalszego rozwoju.

Miłego kodowania i niech twoje kody kreskowe zawsze będą odczytywane za pierwszym razem!

## Co powinieneś nauczyć się dalej?
Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – zwarty PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak wygenerować obraz kodu kreskowego w Javie z Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generowanie kodu kreskowego Java – ustaw rozdzielczość obrazu z Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Najczęściej zadawane pytania

**P:** Czy mogę użyć wygenerowanego PNG na stronie internetowej bez dodatkowej konwersji?  
**O:** Tak, PNG jest natywnie obsługiwany przez wszystkie nowoczesne przeglądarki, więc możesz osadzić plik bezpośrednio za pomocą znacznika `<img>`.

**P:** Ile znaków może pomieścić kod kreskowy PDF417?  
**O:** Do 1 700 znaków na wiersz i do 30 wierszy, co daje teoretyczny maksymalny limit około 51 000 znaków, choć praktyczne ograniczenia zależą od możliwości skanera.

**P:** Czy Aspose.BarCode wymaga licencji do rozwoju?  
**O:** Dostępna jest darmowa licencja ewaluacyjna do testów; licencja komercyjna jest wymagana przy wdrożeniach produkcyjnych.

**P:** Czy można generować kody kreskowe PDF417 w usłudze w tle?  
**O:** Zdecydowanie tak. Biblioteka jest bezpieczna wątkowo dla operacji tylko do odczytu, więc możesz generować kody w ASP.NET Core lub usługach Windows bez interakcji z UI.

**P:** Jakie formaty obrazu oprócz PNG są obsługiwane?  
**O:** BMP, JPEG, GIF, TIFF i SVG są obsługiwane poprzez wyliczenie `BarCodeImageFormat`.

---

**Ostatnia aktualizacja:** 2026-09-18  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Powiązane samouczki

- [Utwórz kod kreskowy Pdf417 z Aspose – kompletny przewodnik](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Jak wygenerować obraz kodu kreskowego Pdf417 w C# z Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Utwórz kod kreskowy Pdf417 w C# – przewodnik krok po kroku](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}