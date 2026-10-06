---
category: general
date: 2026-09-19
description: Poradnik generatora kodów kreskowych w C# pokazuje, jak wygenerować kod
  kreskowy Planet i wyeksportować obraz kodu kreskowego jako PNG w kilku linijkach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: pl
lastmod: 2026-09-19
og_description: Generator kodów kreskowych C# pozwala szybko tworzyć kod kreskowy
  Planet i eksportować obraz jako PNG dla dowolnej aplikacji .NET.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: generator kodów kreskowych C# – twórz kod Planet i eksportuj obraz
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Jak używać generatora kodów kreskowych C# dla kodu Planet
url: /pl/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać generatora kodów kreskowych C# dla kodu Planet

Jeśli potrzebujesz **generatora kodów kreskowych C#**, który potrafi wygenerować kod Planet, ten przewodnik dostarczy Ci kompletne rozwiązanie. Dowiesz się, **jak generować dane kodu kreskowego**, jak dostosować jego wygląd oraz **jak wyeksportować obraz kodu kreskowego** jako plik PNG przy użyciu kilku linijek kodu.

Tworzenie kodów kreskowych to powszechne wymaganie w systemach inwentaryzacji, platformach biletowych i urządzeniach IoT. Po zakończeniu tego tutorialu będziesz posiadać samodzielną aplikację konsolową, która generuje czysty kod Planet, wyłącza wypełnianie pasków i zapisuje wynik na dysku. Nie są potrzebne żadne zewnętrzne narzędzia poza biblioteką kodów kreskowych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Bibliotekę kodów kreskowych kompatybilną z C# (w przykładzie użyto **Aspose.BarCode for .NET**, która obsługuje symbologię Planet)  
* IDE lub edytor, taki jak Visual Studio 2022, VS Code lub Rider  

Bibliotekę można dodać za pomocą NuGet:

```bash
dotnet add package Aspose.BarCode
```

> **Wskazówka:** Używaj najnowszej stabilnej wersji pakietu, aby korzystać z poprawek błędów i ulepszeń wydajności.

## Użycie generatora kodów kreskowych C# do stworzenia kodu Planet

Pierwszym krokiem jest utworzenie generatora z symbologią Planet oraz danymi, które chcesz zakodować.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` jest punktem wejścia dla wszystkich operacji na kodach kreskowych. Konstruktor przyjmuje symbologię (`EncodeTypes.Planet`) oraz surowe dane (`"123456"`). Ten kod **tworzy kod Planet**, który później może zostać wyrenderowany jako obraz.

## Dostosowywanie parametrów kodu kreskowego

Aby kontrolować jakość wizualną, możesz zmienić wymiar X (szerokość modułu) oraz zdecydować, czy paski mają być wypełnione.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Ustawienie `XDimension.Pixels` na **4** daje kod o wyższej rozdzielczości bez drastycznego zwiększania rozmiaru pliku.  
* `FilledBars = false` powoduje styl jedynie z konturami, co jest przydatne, gdy chcesz, aby kod wtopił się w tło lub przy drukowaniu na urządzeniach o niskim zużyciu tuszu.

## Eksport obrazu kodu kreskowego

Po skonfigurowaniu generatora zapisz wynik do pliku PNG. Metoda `Save` przyjmuje pełną ścieżkę oraz żądany format obrazu.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Kod zapisuje **eksportowany obraz kodu kreskowego** `PlanetEmptyBars.png` na pulpicie użytkownika. PNG jest formatem bezstratnym, który zachowuje ostre krawędzie kodu, co czyni go idealnym zarówno do wyświetlania na ekranie, jak i do druku w wysokiej rozdzielczości.

> **Przypadek brzegowy:** Jeśli potrzebujesz innego formatu (JPEG, BMP, GIF), zamień `BarCodeImageFormat.Png` na odpowiednią wartość wyliczeniową. JPEG wprowadza artefakty kompresji, które mogą wpływać na czytelność skanera, więc używaj go tylko wtedy, gdy rozmiar pliku jest krytyczny.

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i od razu uruchomić.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Po uruchomieniu programu powinieneś zobaczyć komunikat podobny do:

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

Otwarcie pliku PNG wyświetli czysty kod Planet z pustymi paskami, dokładnie tak, jak skonfigurowano.

![barcode generator C# example](/images/barcode-generator-csharp.png){alt="przykład generatora kodów kreskowych C#"}

## Częste pytania i rozwiązywanie problemów

| Pytanie | Odpowiedź |
|----------|-----------|
| **Czy mogę generować inne symbologie przy użyciu tego samego kodu?** | Tak. Zamień `EncodeTypes.Planet` na dowolny obsługiwany typ, np. `EncodeTypes.Code128` lub `EncodeTypes.QR`. |
| **Co zrobić, gdy kod nie jest odczytywany?** | Sprawdź, czy długość danych spełnia specyfikację Planet (dokładnie 6 znaków numerycznych). Upewnij się także, że kontrast między kodem a tłem jest wystarczający. |
| **Jak zmienić rozmiar obrazu?** | Dostosuj `generator.Parameters.ImageWidth` i `generator.Parameters.ImageHeight` lub zmodyfikuj `XDimension`, aby proporcjonalnie skalować kod. |
| **Czy można dodać podpis pod kodem?** | Użyj `generator.Parameters.Barcode.CodeTextVisible = true;` i dostosuj `CodeTextParameters` pod kątem czcionki, wyrównania i marginesu. |

## Kolejne kroki

Teraz, gdy opanowałeś **jak generować obrazy kodów kreskowych** przy użyciu **generatora kodów kreskowych C#**, możesz eksplorować:

* Generowanie wsadowych plików kodów kreskowych z listą wartości w formacie CSV.  
* Osadzanie PNG w fakturach PDF przy użyciu Aspose.PDF.  
* Przejście na formaty **eksportowanego obrazu kodu kreskowego** takie jak SVG dla skalowalnej grafiki internetowej.  

Te rozszerzenia pogłębią Twoją wiedzę o automatyzacji kodów kreskowych w .NET i przygotują Cię do rzeczywistych scenariuszy integracji.

---

**Podsumowanie:** Ten tutorial przedstawił kompletny **workflow generatora kodów kreskowych C#** — tworzenie kodu Planet, dostosowywanie jego wyglądu oraz **eksportowanie obrazu kodu kreskowego** jako PNG. Ten sam schemat możesz zastosować do innych symbologii, formatów obrazu i miejsc docelowych. Powodzenia w kodowaniu!


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki zaprezentowane w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generator kodów kreskowych C# – generowanie obrazu kodu](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Tworzenie obrazu kodu Planet w C# – Jak wygenerować kod pocztowy](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}