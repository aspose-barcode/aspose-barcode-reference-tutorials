---
category: general
date: 2026-09-10
description: Twórz kod kreskowy PDF417 w C# szybko. Dowiedz się, jak włączyć tryb
  kompaktowy, ustawić kolumny i wygenerować PNG za pomocą BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: pl
lastmod: 2026-09-10
og_description: Utwórz kod kreskowy PDF417 w C#, włączając tryb kompaktowy, ustawiając
  kolumny i zapisując jako PNG. Postępuj zgodnie z kompletnym przewodnikiem krok po
  kroku.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Tworzenie kodu kreskowego PDF417 w C# – samouczek trybu kompaktowego
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym
url: /pl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz, jak **włączyć tryb kompaktowy**, ustawić liczbę kolumn i zapisać wynik jako obraz PNG przy użyciu biblioteki BarcodeGenerator C#.

Generowanie kodu kreskowego jest powszechnym wymogiem w śledzeniu zapasów, systemach biletowych i aplikacjach mobilnego skanowania. Po zakończeniu tego samouczka będziesz mieć samodzielny, uruchamialny przykład, który generuje kompaktowy kod PDF417 gotowy do użycia w produkcji.

## Wymagania wstępne

* .NET 6.0 lub nowszy zainstalowany (kod działa również z .NET Framework 4.7+)
* Najnowsza wersja biblioteki **BarcodeGenerator** (np. Aspose.BarCode dla .NET)
* IDE lub edytor, taki jak Visual Studio 2022 lub VS Code
* Uprawnienia do zapisu w folderze, w którym zostanie zapisany plik PNG

Nie są wymagane dodatkowe pakiety NuGet poza samą biblioteką kodów kreskowych.

## Krok 1: Utwórz generator kodu kreskowego PDF417

Pierwszym krokiem jest utworzenie obiektu `BarcodeGenerator` z wyliczeniem `EncodeTypes.Pdf417` oraz tekstem, który chcesz zakodować. Ten obiekt steruje całym procesem generowania.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Dlaczego to ważne*: Wartość `EncodeTypes.Pdf417` informuje bibliotekę, aby użyła symboliki PDF417, a drugi argument dostarcza ładunek. Możesz zamienić `"Compact mode"` na dowolny ciąg alfanumeryczny, który potrzebujesz zakodować.

## Krok 2: Ustaw wymiar X (szerokość modułu)

Wymiar X kontroluje szerokość każdego małego kwadratu (modułu) w kodzie kreskowym. Mniejsze wartości dają bardziej zwartą grafikę, co jest przydatne przy ograniczonej przestrzeni.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Wartość `2` piksele to dobry kompromis między czytelnością a zwartością dla większości skanerów ekranowych.

## Krok 3: Określ liczbę kolumn

PDF417 może układać dane w siatkę wierszy i kolumn. Zmiana liczby kolumn wpływa na proporcje kodu kreskowego.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Ustawienie **jak ustawić kolumny** na `3` daje krótki, szeroki kod, który ładnie mieści się na etykiecie. Możesz eksperymentować z wartościami od `1` do `30` w zależności od ilości danych i docelowego skanera.

## Krok 4: Włącz tryb kompaktowy

Tryb kompaktowy usuwa niepotrzebne wiersze wypełniające, co sprawia, że kod kreskowy jest mniejszy bez utraty integralności danych. To kluczowy krok do **kompaktowego PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Gdy `Truncate` jest ustawione na `true`, biblioteka automatycznie oblicza minimalną liczbę wierszy potrzebnych do przechowania danych, dlatego końcowy obraz wygląda „zwarty”.

## Krok 5: Zapisz wygenerowany kod kreskowy jako obraz PNG

Na koniec zapisz kod kreskowy do pliku. PNG zachowuje ostre krawędzie potrzebne do niezawodnego skanowania.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Zastąp `YOUR_DIRECTORY` ścieżką bezwzględną lub względną, do której Twoja aplikacja ma prawo zapisu. Po wykonaniu znajdziesz plik `CompactPdf417.png` zawierający kod kreskowy.

### Pełny kod źródłowy

Połączenie wszystkich kroków daje pojedynczy, gotowy do uruchomienia program:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Uruchomienie tego programu tworzy `CompactPdf417.png` w tym samym folderze co plik wykonywalny. Otwórz obraz w dowolnym przeglądarce; powinieneś zobaczyć gęsty, wysokokontrastowy kod PDF417 gotowy do skanowania.

## Jak włączyć tryb kompaktowy w innych scenariuszach

* **Generowanie wsadowe** – Podczas tworzenia wielu kodów, ustaw `Truncate` raz na generatorze i używaj go ponownie dla każdego nowego ładunku.
* **Różne formaty obrazu** – Ta sama metoda `Save` działa z `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp`, jeśli potrzebujesz innego typu pliku.
* **Dynamiczna liczba kolumn** – Jeśli długość zakodowanego ciągu się zmienia, oblicz optymalną liczbę kolumn w oparciu o długość ciągu i rozdzielczość skanera.

## Jak ustawić kolumny dla konkretnych przypadków użycia

* **Drukowanie etykiet** – Użyj niskiej liczby kolumn (np. `2`‑`5`), aby kod był wystarczająco krótki, by zmieścić się na wąskich etykietach.
* **Skanowanie mobilne** – Wyższe liczby kolumn (`10`‑`15`) dają wyższe kody, które są łatwiejsze do ustawienia ostrości przez kamery telefonów.
* **Kompromis korekcji błędów** – Więcej kolumn zmniejsza liczbę wierszy, co może wpływać na wbudowaną korekcję błędów kodu. Przetestuj z docelowym skanerem, aby znaleźć optymalne ustawienie.

## Częste pułapki i wskazówki profesjonalistów

| Problem | Dlaczego się dzieje | Rozwiązanie |
|---------|----------------------|-------------|
| Kod kreskowy nieczytelny | Zbyt mały wymiar X (np. `1` piksel) | Zwiększ `XDimension.Pixels` przynajmniej do `2` |
| Obraz jest za duży | Ustawiono zbyt wiele kolumn dla krótkiego ładunku | Zredukuj `Pdf417.Columns` lub włącz `Truncate` |
| Plik PNG jest pusty | Folder wyjściowy nie istnieje lub brak uprawnień do zapisu | Upewnij się, że katalog istnieje i proces ma prawa zapisu |
| Skaner zgłasza „uszkodzone dane” | Wyłączony Truncate przy użyciu wielu kolumn | Włącz `Truncate` lub zmniejsz liczbę kolumn |

## Weryfikacja wyniku

Możesz zweryfikować kod kreskowy przy pomocy dowolnej aplikacji skanującej PDF417 (istnieje wiele darmowych aplikacji na Android/iOS). Otwórz `CompactPdf417.png` w aplikacji i potwierdź, że odkodowany tekst odpowiada pierwotnemu ładunkowi („Compact mode”). Jeśli tekst się różni, sprawdź ponownie flagę `Truncate` oraz ustawienia kolumn.

## Kolejne kroki

* **Integracja z ASP.NET Core** – Zwróć PNG bezpośrednio z akcji kontrolera zamiast zapisywać na dysk.
* **Dodaj tekst czytelny dla człowieka** – Użyj `barcodeGenerator.Parameters.Barcode.CodeTextParameters`, aby wyświetlić zakodowany ciąg pod kodem kreskowym.
* **Poznaj inne symbologie** – Ta sama klasa `BarcodeGenerator` obsługuje QR, Code128, DataMatrix i inne. Zmień `EncodeTypes`, aby je wypróbować.

---

### Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy PDF417** w C#, **włączając tryb kompaktowy**, kontrolując **jak ustawić kolumny** oraz korzystając z API **barcode generator C#**, aby **wygenerować kod kreskowy** spełniający rzeczywiste ograniczenia rozmiaru. Zastosuj te kroki w każdym projekcie .NET, który potrzebuje kompaktowych, wysokiej gęstości kodów kreskowych, i rozszerz wzorzec na inne formaty kodów w razie potrzeby. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy PDF417 w C# – Kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Jak ustawić poziom błędu w kodzie PDF417 – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Jak zapisać kod kreskowy w C# – Generowanie kodów PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}