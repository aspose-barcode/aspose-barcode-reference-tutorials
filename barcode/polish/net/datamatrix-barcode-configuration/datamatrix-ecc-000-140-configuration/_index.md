---
date: 2026-08-17
description: Dowiedz się, jak utworzyć datamatrix barcode aspose przy użyciu Aspose.BarCode
  dla .NET – idealne do generowania kodów kreskowych, zarządzania zapasami oraz projektów
  generatora kodów kreskowych w C#.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 Configuration
og_description: Utwórz datamatrix barcode aspose przy użyciu Aspose.BarCode dla .NET
  – szybkie, wysokowydajne rozwiązanie dla zarządzania zapasami i projektów kodów
  kreskowych w C#.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Utwórz datamatrix barcode aspose przy użyciu Aspose.BarCode dla .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Jak utworzyć datamatrix barcode aspose przy użyciu Aspose.BarCode
url: /pl/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy datamatrix aspose przy użyciu Aspose.BarCode

W nowoczesnym oprogramowaniu łańcucha dostaw często trzeba **tworzyć kod kreskowy datamatrix aspose** szybko i niezawodnie. Ten samouczek przeprowadzi Cię przez generowanie symbolu DataMatrix ECC 000‑140 przy użyciu Aspose.BarCode dla .NET, biblioteki, która zajmuje się trudnym kodowaniem, korekcją błędów i renderowaniem obrazu. Po zakończeniu przewodnika będziesz mieć gotowy fragment C#, który można wstawić do dowolnego projektu .NET zarządzania zapasami.

## Szybkie odpowiedzi
- **Jaka jest główna biblioteka?** Aspose.BarCode for .NET  
- **Jaki typ kodu kreskowego jest omawiany?** DataMatrix ECC 000‑140  
- **Jakiego języka użyto?** C# (C Sharp)  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja jest wymagana w produkcji  
- **Typowy czas implementacji?** Około 10‑15 minut dla podstawowego generatora  

## Co to jest DataMatrix ECC 000‑140?
DataMatrix to dwuwymiarowy kod kreskowy, który przechowuje duże ilości danych w kompaktowym kwadracie. Poziom korekcji błędów **ECC 000‑140** może odzyskać do 140 % uszkodzonych kodów znakowych, co czyni go idealnym dla trudnych warunków magazynowych, gdzie etykiety mogą zostać porysowane lub zamazane.

## Dlaczego wybrać Aspose.BarCode dla .NET?
Aspose.BarCode dla .NET oferuje kompleksowe, wysokowydajne API, które upraszcza tworzenie kodów kreskowych w wielu symbologiach, zapewnia wbudowaną korekcję błędów, automatyczne dopasowanie rozmiaru oraz szerokie wsparcie platform, co czyni go idealnym rozwiązaniem dla przedsiębiorstw w zakresie zarządzania zapasami i etykietowaniem.

- **Solidne API:** Obsługuje ponad 30 symbologii kodów kreskowych i automatycznie stosuje reguły kodowania.  
- **Cross‑platform:** Działa na Windows, macOS i Linux bez natywnych zależności.  
- **Wysoka wydajność:** Generuje 200 × 200‑pikselowy DataMatrix w mniej niż 50 ms na typowym procesorze 2,5 GHz, umożliwiając szybkie linie etykietowania.  

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Visual Studio** – dowolna niedawna edycja (Community, Professional lub Enterprise).  
2. **Aspose.BarCode for .NET** – pobierz ją z [link do pobrania](https://releases.aspose.com/barcode/net/). Możesz także odwiedzić [ten link](https://releases.aspose.com/) po dodatkowe zasoby.  
3. **Projekt .NET** – gotowy do odwołania się do zestawu Aspose.BarCode.  

## Importowanie przestrzeni nazw
W swoim pliku C# dodaj wymagany dyrektyw using, aby uzyskać dostęp do klas kodów kreskowych.

```csharp
using Aspose.BarCode.Generation;
```

**Klasa `BarcodeGenerator` jest rdzeniowym silnikiem Aspose.BarCode do tworzenia obrazów kodów kreskowych.**  
**Klasa `BarcodeGenerator` jest rdzeniowym silnikiem Aspose.BarCode, który tworzy i konfiguruje obrazy kodów kreskowych.**  
```csharp
using Aspose.BarCode.Generation;
```

## Przypadek użycia generowania kodów kreskowych w zarządzaniu zapasami
Wyobraź sobie, że musisz oznakować tysiące palet w centrum dystrybucji. Generując kody DataMatrix ECC 000‑140, możesz osadzić identyfikatory produktów, numery partii i daty ważności w jednym, odpornym na błędy symbolu, który skanery ręczne odczytują natychmiast, redukując błędy ręcznego wprowadzania danych nawet o 95 %.

## Jak utworzyć kod kreskowy datamatrix aspose w C#
Wczytaj dane, skonfiguruj generator i zapisz obraz – wszystko w trzech zwięzłych krokach. `BarcodeGenerator` automatycznie wybiera optymalny rozmiar modułu i stosuje poziom korekcji ECC 140, więc nie musisz samodzielnie obliczać sum kontrolnych, szybko i efektywnie.

### Krok 1: określ katalog wyjściowy
Wybierz folder, w którym zostanie zapisany plik PNG. Ścieżka musi istnieć przed wywołaniem `Save`.

```csharp
string path = "Your Directory Path";
```

### Krok 2: utwórz generator kodów kreskowych
Zainicjuj `BarcodeGenerator`, ustaw symbologię na DataMatrix, podaj ładunek i wybierz najwyższy poziom korekcji błędów.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

W tym fragmencie:
* Wybierz **DataMatrix** jako typ kodu kreskowego.  
* Podaj przykładową wartość (`"Åspóse.Barcóde©"`).  
* Ustaw **XDimension**, aby kontrolować rozmiar modułu (tutaj 4 piksele).  
* Wybierz najwyższy poziom korekcji błędów (**ECC 140**).  
* Zapisz wynik jako plik PNG.  

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Nieprawidłowa ścieżka** | Upewnij się, że `path` kończy się separatorem katalogów (`\` lub `/`) i folder istnieje. |
| **Nieobsługiwane znaki** | DataMatrix obsługuje UTF‑8; unikaj znaków kontrolnych i używaj właściwego kodowania. |
| **Licencja nie zastosowana** | Klasa `Aspose.BarCode.License` stosuje licencję komercyjną, aby odblokować pełną funkcjonalność. Wywołaj ją przed generowaniem jakiegokolwiek kodu kreskowego. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.BarCode dla .NET na serwerach Linux?**  
A: Tak. Biblioteka jest w pełni cross‑platform i działa na .NET 5+, .NET 6+ oraz .NET Core na Linuxie bez dodatkowych zależności.

**Q: Jak biblioteka radzi sobie z dużymi partiami kodów kreskowych?**  
A: Możesz ponownie używać jednej instancji `BarcodeGenerator` w pętli; każde wywołanie `Save` renderuje obraz w przybliżeniu 40‑60 ms, co czyni ją odpowiednią do generowania tysięcy etykiet na minutę.

**Q: Czy muszę ręcznie kodować dane dla ECC 140?**  
A: Nie. Ustawienie `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` automatycznie stosuje właściwy algorytm korekcji błędów.

**Q: Czy wersja próbna jest wystarczająca do rozwoju?**  
A: Darmowa wersja próbna zapewnia pełny dostęp do funkcji, w tym ECC 140, ale dodaje znak wodny do wygenerowanych obrazów. Zastosuj licencję w produkcji, aby usunąć znak wodny.

**Q: Czy mogę dostosować kolory kodu kreskowego?**  
A: Oczywiście. Użyj `generator.Parameters.Barcode.Color` i `generator.Parameters.Barcode.BackColor`, aby dopasować je do swojej marki.

---

**Ostatnia aktualizacja:** 2026-08-17  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Mistrzowskie kodowanie DataMatrix w ASCII przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Jak odczytywać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}