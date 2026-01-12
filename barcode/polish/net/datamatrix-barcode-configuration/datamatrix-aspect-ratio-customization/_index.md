---
date: 2026-01-12
description: Dowiedz się, jak stworzyć plik PNG z kodem kreskowym o niestandardowym
  współczynniku proporcji DataMatrix przy użyciu Aspose.BarCode dla .NET. Przewodnik
  krok po kroku dotyczący generowania kodów kreskowych i dostosowywania rozmiaru.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Utwórz kod kreskowy PNG – proporcje DataMatrix – Aspose.BarCode
url: /pl/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz PNG kodu kreskowego – proporcje DataMatrix – Aspose.BarCode

Generowanie **barcode PNG** z niestandardowymi proporcjami DataMatrix jest powszechnym wymogiem, gdy potrzebujesz, aby kod kreskowy pasował do określonych ograniczeń układu. W tym samouczku przeprowadzimy Cię przez dokładne kroki, aby **utworzyć PNG kodu kreskowego** przy użyciu Aspose.BarCode dla .NET, wyjaśnimy, dlaczego możesz chcieć dostosować proporcje, i pokażemy, jak precyzyjnie dostroić wynik dla Twojej aplikacji.

## Szybkie odpowiedzi
- **Co kontroluje „aspect ratio”?** Definiuje stosunek szerokości do wysokości modułów DataMatrix.  
- **Czy mogę wyeksportować PNG, JPEG lub SVG?** Tak – metoda `Save` obsługuje PNG, JPEG, BMP, GIF i inne.  
- **Czy potrzebuję licencji na tę funkcję?** Darmowa wersja próbna działa w trakcie rozwoju; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Ile wartości proporcji jest prawidłowych?** Dowolna dodatnia liczba zmiennoprzecinkowa; typowe wartości to 0,5 – 2,0.

## Czym jest kod kreskowy DataMatrix i dlaczego dostosować jego proporcje?
DataMatrix to dwuwymiarowy kod macierzowy, który przechowuje duże ilości danych w niewielkiej przestrzeni. Dostosowanie **aspect ratio** pozwala rozciągać lub kompresować moduły w poziomie, co może być przydatne przy dopasowywaniu kodu kreskowego do wąskich kolumn lub szerokich etykiet bez utraty czytelności.

## Wymagania wstępne

Zanim zaczniemy dostosowywać proporcje DataMatrix, upewnij się, że masz następujące wymagania wstępne:

1. **Visual Studio** – dowolna nowsza wersja będzie odpowiednia.  
2. **Aspose.BarCode for .NET** – pobierz go [tutaj](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – Twój projekt musi celować w obsługiwaną wersję.

## Importowanie przestrzeni nazw

First, you need to import the necessary namespace in your C# project:

```csharp
using Aspose.BarCode.Generation;
```

> **Wskazówka:** Trzymaj to polecenie `using` na początku pliku, aby klasa `BarcodeGenerator` była zawsze dostępna.

## Przewodnik krok po kroku

### Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt konsolowy lub Windows Forms w Visual Studio i dodaj odwołanie do biblioteki Aspose.BarCode DLL.

### Krok 2: Zainicjalizuj generator kodów kreskowych
Utwórz instancję `BarcodeGenerator` z typem DataMatrix oraz danymi, które chcesz zakodować:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Ten wiersz tworzy generator gotowy do wygenerowania kodu DataMatrix zawierającego przykładowy tekst.

### Krok 3: Dostosuj proporcje i zapisz pliki PNG
Teraz możesz zmienić **aspect ratio** i zapisać każdą wersję jako obraz PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Pierwsze wywołanie tworzy kod o proporcjach kwadratu (`AspectRatio = 1`).  
- Drugie wywołanie kompresuje kod w poziomie (`AspectRatio = 0.5`), dając szerszy wygląd.

Masz teraz dwa pliki **barcode PNG** o różnych proporcjach, gotowe do użycia w raportach, etykietach lub elementach interfejsu użytkownika.

## Częste problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Wygenerowany obraz jest rozmyty** | Zwiększ parametr `Resolution` przed zapisem (`gen.Parameters.ImageResolution = 300`). |
| **Kod kreskowy nie jest odczytywany** | Upewnij się, że proporcja mieści się w przedziale 0,5 – 2,0 i zachowaj wystarczającą strefę ciszy (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Błędy ścieżki pliku** | Użyj `Path.Combine` do zbudowania ścieżki wyjściowej i sprawdź, czy folder istnieje. |

## Najczęściej zadawane pytania

**P:** Czy mogę dostosować proporcje innych typów kodów kreskowych przy użyciu Aspose.BarCode dla .NET?  
**O:** Tak, wiele kodów 2‑D (np. QR, PDF417) obsługuje regulację proporcji poprzez ich specyficzne obiekty parametrów.

**P:** Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?  
**O:** Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.BarCode dla .NET [tutaj](https://releases.aspose.com/).

**P:** Gdzie mogę kupić licencję na Aspose.BarCode dla .NET?  
**O:** Licencję możesz zakupić na stronie Aspose [tutaj](https://purchase.aspose.com/buy).

**P:** Czy Aspose.BarCode dla .NET jest kompatybilny z różnymi wersjami .NET Framework?  
**O:** Tak, działa z .NET Framework 4.x, .NET Core 3.1+ oraz najnowszymi wydaniami .NET.

**P:** Czy mogę generować kody kreskowe w różnych formatach przy użyciu Aspose.BarCode dla .NET?  
**O:** Oczywiście – PNG, JPEG, BMP, GIF, TIFF, SVG i PDF są obsługiwane od razu.

## Podsumowanie

Dostosowanie **aspect ratio** kodu DataMatrix oraz **tworzenie barcode PNG** jest proste przy użyciu Aspose.BarCode dla .NET. Postępując zgodnie z powyższymi krokami, możesz generować idealnie dopasowane kody kreskowe spełniające dokładne wymagania układu Twojego projektu. Zbadaj inne parametry, takie jak `Resolution`, `Margin` i `Color`, aby jeszcze lepiej dopasować wynik.

Po głębszej eksploracji sprawdź oficjalną [dokumentację](https://reference.aspose.com/barcode/net/) lub dołącz do społeczności na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-01-12  
**Testowano z:** Aspose.BarCode 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}