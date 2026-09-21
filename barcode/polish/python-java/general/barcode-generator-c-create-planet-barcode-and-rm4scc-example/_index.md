---
category: general
date: 2026-08-03
description: Samouczek generatora kodów kreskowych w C# pokazujący, jak utworzyć kod
  kreskowy Planet przy użyciu Aspose.BarCode, ustawić wymiar X i zapisać jako obrazy
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: pl
lastmod: 2026-08-03
og_description: Samouczek generatora kodów kreskowych w C# prowadzi Cię przez tworzenie
  kodu kreskowego Planet, regulację wymiaru X oraz zapisywanie jako PNG przy użyciu
  Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Generator kodów kreskowych C# – twórz kod Planet krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator kodów kreskowych C# – tworzenie kodu Planet i przykład RM4SCC
url: /pl/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator kodów kreskowych C# – tworzenie kodu Planet i przykład RM4SCC

Jeśli potrzebujesz **generatora kodów kreskowych C#**, który może generować symbole specyficzne dla poczty, ten przewodnik pokaże Ci dokładnie, jak **tworzyć obrazy kodu Planet** przy użyciu Aspose.BarCode. Zobaczysz, jak skonfigurować wymiar X, wygenerować pasujący kod RM4SCC i zapisać oba jako pliki PNG — wszystko w kilku zwięzłych krokach.

Poradnik obejmuje wszystko, co potrzebne do uruchomienia kodu na .NET 6 lub nowszym, wyjaśnia, dlaczego każde ustawienie ma znaczenie, oraz wskazuje typowe pułapki, takie jak nieprawidłowa szerokość modułu czy brak uprawnień do katalogu. Po zakończeniu będziesz mieć dwa gotowe do druku obrazy kodów kreskowych, które spełniają standardy Planet i RM4SCC.

## Wymagania wstępne

* .NET 6 SDK (lub dowolna wersja .NET obsługiwana przez Aspose.BarCode)
* Visual Studio 2022 lub dowolne IDE C#, które preferujesz
* Odwołanie NuGet do **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Uprawnienie do zapisu w folderze, w którym planujesz przechowywać pliki PNG

Nie są wymagane żadne dodatkowe usługi zewnętrzne; biblioteka obsługuje całe kodowanie lokalnie.

## Krok 1: Inicjalizacja obiektu generatora kodów kreskowych C# 

Pierwszym zadaniem jest utworzenie instancji `BarcodeGenerator`. Konstruktor przyjmuje symbologię kodu kreskowego (`EncodeTypes.Planet`) oraz dane do zakodowania.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Dlaczego ten krok?*  
`BarcodeGenerator` jest punktem wejścia dla każdego generowanego kodu kreskowego. Wybranie `EncodeTypes.Planet` informuje bibliotekę, aby stosowała specyfikację ISO/IEC 24723 używaną przez wiele usług pocztowych.

## Krok 2: Ustawienie wymiaru X (szerokości modułu) dla kodu Planet

Wymiar X definiuje szerokość pojedynczego modułu kodu kreskowego (najmniejszej kreski lub przerwy). Wartość **4 piksele** dobrze sprawdza się w większości drukarek etykiet.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Dlaczego to ważne*  
Jeśli moduł jest zbyt wąski, kod kreskowy może stać się nieczytelny; jeśli jest zbyt szeroki, rozmiar etykiety rośnie niepotrzebnie. Dostosowanie `Pixels` pozwala precyzyjnie dopasować kod kreskowy do rozdzielczości Twojej drukarki.

## Krok 3: Zapisanie kodu Planet jako obrazu PNG

Aspose.BarCode automatycznie oblicza wysokość kodu kreskowego na podstawie wybranej symbologii, więc musisz jedynie podać ścieżkę pliku i format.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Wskazówka*  
Zastąp `YOUR_DIRECTORY` ścieżką absolutną lub względną, która istnieje na Twoim komputerze. Jeśli katalog nie istnieje, metoda `Save` zgłasza `DirectoryNotFoundException`.

**Oczekiwany wynik** – plik PNG, który wygląda podobnie do ilustracji poniżej (rzeczywisty obraz nie jest tutaj wyświetlany, ale zobaczysz klasyczny kod Planet z ładunkiem numerycznym `123456`).

## Krok 4: Inicjalizacja drugiego generatora dla kodu RM4SCC

Wiele systemów pocztowych wymaga zarówno symboli Planet, jak i RM4SCC na tej samej przesyłce. Utwórz nową instancję `BarcodeGenerator` dla symbologii RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Dlaczego osobna instancja?*  
Każda symbologia ma własny zestaw parametrów. Ponowne użycie tego samego generatora może nieumyślnie przenieść ustawienia (takie jak wymiar X), które nie są optymalne dla drugiego kodu kreskowego.

## Krok 5: Konfiguracja wymiaru X dla kodu RM4SCC

RM4SCC również respektuje ustawienie wymiaru X, więc stosujemy tę samą szerokość w pikselach dla spójności wizualnej.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Jeśli potrzebujesz wyższego kodu kreskowego (np. dla większych etykiet), możesz również ustawić `Height.Pixels`. Pozostawienie go nieustawionego pozwala bibliotece automatycznie obliczyć idealną wysokość.

## Krok 6: Zapisanie kodu RM4SCC jako obrazu PNG

Na koniec zapisz kod RM4SCC na dysku.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Masz teraz dwa pliki PNG — `PostalPlanetBarHeightNone.png` i `PostalRM4SCCBarHeightNone.png` — które możesz osadzić w etykietach pocztowych, wydrukować na kopertach lub wysłać do zewnętrznej usługi drukowania.

## Opcjonalnie: Dostosowanie wysokości lub użycie innych formatów obrazu

Jeśli Twój przepływ pracy wymaga określonej wysokości kodu kreskowego lub innego formatu obrazu (np. JPEG lub BMP), możesz zmodyfikować parametry przed wywołaniem `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Przypadek brzegowy** – Gdy ustawiasz niestandardową wysokość, upewnij się, że wartość spełnia minimalną wysokość wymaganą przez standard ISO; w przeciwnym razie kod kreskowy może nie przejść walidacji.

## Typowe pułapki i jak ich unikać

| Pułapka | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| `DirectoryNotFoundException` | Docelowy folder nie istnieje lub jest błędnie zapisany. | Utwórz najpierw folder lub użyj `Path.Combine` z `Environment.CurrentDirectory`. |
| Kod kreskowy nieczytelny na drukarkach o niskiej rozdzielczości | Wymiar X jest zbyt mały w stosunku do DPI drukarki. | Zwiększ `XDimension.Pixels` do 5‑6 dla drukarek 203 dpi lub przetestuj na próbnej etykiecie. |
| Użyto niewłaściwej symbologii | Przekazanie `EncodeTypes.Code128` zamiast `EncodeTypes.Planet`. | Sprawdź ponownie, czy wartość enum `EncodeTypes` odpowiada wymaganemu standardowi pocztowemu. |
| Odwołanie null do `Parameters` | Używanie starszej wersji Aspose.BarCode, w której API się różni. | Uaktualnij do najnowszego pakietu NuGet (v23.12 lub nowszy). |

## Pełny przykład do uruchomienia

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić. Zawiera instrukcje `using`, obsługę błędów oraz komentarze wyjaśniające każdą linię.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Uruchomienie programu tworzy folder `Barcodes` obok pliku wykonywalnego i umieszcza w nim dwa pliki PNG. Otwórz je dowolnym przeglądarką obrazów, aby zweryfikować wynik.

## Podsumowanie

Masz teraz rozwiązanie **generatora kodów kreskowych C#**, które może **tworzyć obrazy kodu Planet**, dostosowywać wymiar X dla optymalnego drukowania oraz generować pasujący kod RM4SCC — wszystko przy użyciu kilku linii kodu. Podejście działa z .NET 6+, wymaga jedynie pakietu NuGet Aspose.BarCode i może być rozszerzone na inne symbologie, takie jak Code128, QR czy DataMatrix, poprzez zamianę wartości `EncodeTypes`.

### Co dalej?

* Eksperymentuj z różnymi wartościami `XDimension.Pixels`, aby dopasować je do DPI Twojej drukarki.  
* Generuj kody kreskowe w innych formatach (PDF, SVG), zmieniając enum `BarCodeImageFormat`.  
* Połącz dwa pliki PNG w jedną etykietę przy użyciu biblioteki graficznej, takiej jak **SkiaSharp**.  
* Zbadaj pełne API Aspose.BarCode pod kątem zaawansowanych funkcji, takich jak walidacja sumy kontrolnej czy własne czcionki.

Śmiało dostosuj kod do przetwarzania wsadowego lub zintegrować go z usługą webową ASP.NET Core, która zwraca obrazy kodów kreskowych na żądanie. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy PNG – Współczynnik proporcji DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Jak zapisać PNG przy użyciu DataMatrix C40 z Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [samouczek generatora kodów kreskowych c# – Dostosuj współczynniki proporcji kodu 16K z Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}