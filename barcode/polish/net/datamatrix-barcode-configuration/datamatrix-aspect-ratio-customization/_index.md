---
date: 2026-05-30
description: Dowiedz się, jak utworzyć plik PNG z kodem kreskowym o niestandardowych
  proporcjach DataMatrix przy użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku
  dotyczący generowania kodów kreskowych i dostosowywania rozmiaru.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Dostosowywanie proporcji DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Utwórz PNG z kodem kreskowym – proporcje DataMatrix – Aspose.BarCode
url: /pl/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz PNG kodu kreskowego – proporcje DataMatrix – Aspose.BarCode

Generowanie **barcode PNG** z niestandardowymi proporcjami DataMatrix jest powszechnym wymaganiem, gdy potrzebujesz **tworzyć barcode PNG** pliki, które pasują do określonych ograniczeń układu. W tym samouczku przeprowadzimy Cię przez dokładne kroki, aby **tworzyć barcode PNG** pliki przy użyciu Aspose.BarCode dla .NET, wyjaśnimy, dlaczego możesz chcieć dostosować proporcje, i pokażemy, jak precyzyjnie dostroić wynik dla Twojej aplikacji.

## Szybkie odpowiedzi
- **Co kontroluje „aspect ratio”?** Określa proporcję szerokość‑do‑wysokość modułów DataMatrix.  
- **Czy mogę wyeksportować PNG, JPEG lub SVG?** Tak – metoda `Save` obsługuje PNG, JPEG, BMP, GIF, TIFF, SVG i PDF.  
- **Czy potrzebuję licencji na tę funkcję?** Darmowa wersja próbna działa w środowisku deweloperskim; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Ile wartości aspect‑ratio jest prawidłowych?** Dowolna dodatnia liczba zmiennoprzecinkowa; typowe wartości to 0,5 – 2,0.

## Czym jest kod kreskowy DataMatrix i dlaczego dostosowywać jego proporcje?
Kod kreskowy DataMatrix to dwuwymiarowy kod macierzowy, który przechowuje duże ilości danych w kompaktowym kwadracie. Dostosowanie **aspect ratio** pozwala rozciągać lub kompresować moduły w poziomie, co jest przydatne, gdy trzeba dopasować kod kreskowy do wąskich kolumn lub szerokich etykiet bez utraty niezawodności skanowania.

## Dlaczego używać Aspose.BarCode do tworzenia barcode PNG?
Aspose.BarCode obsługuje **7 formatów obrazu** — PNG, JPEG, BMP, GIF, TIFF, SVG i PDF — i może przetwarzać **ponad 50 formatów wejściowych i wyjściowych** w pamięci, obsługując dokumenty liczące setki stron bez ładowania całego pliku. Biblioteka oferuje płynne API, które pozwala wygenerować kod DataMatrix w jednej linii kodu, zapewniając renderowanie pikselowo‑idealne oraz pełną kompatybilność z .NET.

## Wymagania wstępne

Zanim zaczniemy dostosowywać proporcje DataMatrix, upewnij się, że masz następujące wymagania:

1. **Visual Studio** – dowolna nowsza wersja będzie odpowiednia.  
2. **Aspose.BarCode for .NET** – pobierz go [tutaj](https://releases.aspose.com/barcode/net/).  
3. Możesz również przeglądać inne wydania produktów Aspose [tutaj](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – Twój projekt musi celować w obsługiwaną wersję.

## Importowanie przestrzeni nazw

Najpierw musisz zaimportować wymaganą przestrzeń nazw w swoim projekcie C#:

`using Aspose.BarCode.Generation;` imports the namespace that contains the barcode generation classes.  

```csharp
using Aspose.BarCode.Generation;
```

> **Wskazówka:** Trzymaj to polecenie `using` na początku pliku, aby klasa `BarcodeGenerator` była zawsze dostępna.

## Jak utworzyć barcode PNG z niestandardowymi proporcjami?

Załaduj `BarcodeGenerator`, ustaw typ DataMatrix, dostosuj właściwość `AspectRatio` i wywołaj `Save`. Ten jednowierszowy wzorzec tworzy barcode PNG, który zachowuje podany stosunek, a biblioteka automatycznie obsługuje skalowanie modułów i strefy ciszy.

`BarcodeGenerator` tworzy obraz kodu kreskowego z określonej symbologii i danych.  

### Krok 1: Przygotuj projekt
Utwórz nowy projekt konsolowy lub Windows Forms w Visual Studio i dodaj odwołanie do biblioteki Aspose.BarCode DLL.

### Krok 2: Zainicjuj generator kodu kreskowego
Utwórz jego instancję z symbologią DataMatrix oraz danymi, które chcesz zakodować:

`BarcodeGenerator` tworzy obraz kodu kreskowego z określonej symbologii i danych.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Ten wiersz tworzy generator gotowy do wygenerowania kodu DataMatrix zawierającego przykładowy tekst.

### Krok 3: Dostosuj proporcje i zapisz pliki PNG
Teraz możesz zmienić **aspect ratio** i zapisać każdą wersję jako obraz PNG:

`AspectRatio` ustawia proporcję szerokość‑do‑wysokość modułów DataMatrix.  
`Save` zapisuje wygenerowany obraz kodu kreskowego do pliku w wybranym formacie.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Pierwsze wywołanie tworzy kod o proporcjach kwadratu (`AspectRatio = 1`).  
- Drugie wywołanie kompresuje kod w poziomie (`AspectRatio = 0.5`), dając szerszy wygląd.

Masz teraz dwa pliki **barcode PNG** o różnych proporcjach, gotowe do użycia w raportach, etykietach lub elementach interfejsu użytkownika.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Wygenerowany obraz jest rozmyty** | Zwiększ parametr `Resolution` przed zapisem (`gen.Parameters.ImageResolution = 300`). |
| **Kod kreskowy nie jest odczytywany** | Upewnij się, że proporcje mieszczą się w przedziale 0,5 – 2,0 i zachowaj wystarczającą strefę ciszy (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Błędy ścieżki pliku** | Użyj `Path.Combine`, aby zbudować ścieżkę wyjściową i sprawdź, czy folder istnieje. |

## Najczęściej zadawane pytania

**Q: Czy mogę dostosować aspect ratio innych typów kodów kreskowych przy użyciu Aspose.BarCode dla .NET?**  
A: Tak, wiele kodów 2‑D (np. QR, PDF417) obsługuje regulację aspect‑ratio poprzez ich specyficzne obiekty parametrów.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.BarCode dla .NET [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę kupić licencję na Aspose.BarCode dla .NET?**  
A: Licencję możesz zakupić na stronie Aspose [tutaj](https://purchase.aspose.com/buy).

**Q: Czy Aspose.BarCode dla .NET jest kompatybilny z różnymi wersjami .NET Framework?**  
A: Tak, działa z .NET Framework 4.x, .NET Core 3.1+ oraz najnowszymi wersjami .NET.

**Q: Czy mogę generować kody kreskowe w różnych formatach przy użyciu Aspose.BarCode dla .NET?**  
A: Oczywiście – PNG, JPEG, BMP, GIF, TIFF, SVG i PDF są obsługiwane od razu.

## Zakończenie

Dostosowywanie **aspect ratio** kodu DataMatrix i **tworzenie barcode PNG** jest proste przy użyciu Aspose.BarCode dla .NET. Postępując zgodnie z powyższymi krokami, możesz generować idealnie dopasowane kody, które spełniają dokładne wymagania układu Twojego projektu. Zbadaj dodatkowe parametry, takie jak `Resolution`, `Margin` i `Color`, aby jeszcze lepiej dopasować wynik, i rozważ możliwości `generate datamatrix barcode` przy budowaniu aplikacji przyjaznych skanowaniu w Visual Studio.

Aby zgłębić temat, zapoznaj się z oficjalną [dokumentacją](https://reference.aspose.com/barcode/net/) lub dołącz do społeczności na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-05-30  
**Testowano z:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Generuj kod DataMatrix – Przewodnik Pro z Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Mistrzowskie kodowanie DataMatrix w ASCII z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}