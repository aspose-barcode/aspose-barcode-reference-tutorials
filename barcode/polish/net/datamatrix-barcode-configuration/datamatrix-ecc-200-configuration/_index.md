---
date: 2026-08-02
description: Dowiedz się, jak utworzyć kod kreskowy DataMatrix, wygenerować DataMatrix
  i poznać generowanie kodów kreskowych o wysokiej gęstości przy użyciu Aspose.BarCode
  w projektach .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Konfiguracja DataMatrix ECC 200
og_description: Utwórz kod kreskowy DataMatrix przy użyciu Aspose.BarCode dla .NET.
  Ten samouczek pokazuje generowanie kodów kreskowych o wysokiej gęstości, konfigurację
  tymczasowej licencji Aspose oraz krok po kroku kod w C#.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Tworzenie kodu kreskowego DataMatrix – przewodnik Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Jak utworzyć kod kreskowy DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla
  .NET
url: /pl/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET

## Wprowadzenie

W tym przewodniku **utworzysz kod kreskowy DataMatrix** (ECC 200) przy użyciu Aspose.BarCode dla .NET. Niezależnie od tego, czy tworzysz system śledzenia zapasów, system punktu sprzedaży, czy automatyzujesz przepływy dokumentów, kod kreskowy o wysokiej gęstości może przechowywać dużo danych w małej przestrzeni. Przejdziemy przez każdy krok konfiguracji, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i dostarczymy gotowe fragmenty C#.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza dla DataMatrix w .NET?** Aspose.BarCode for .NET  
- **Jaki poziom ECC zapewnia ECC 200?** Korekcja błędów o wysokiej gęstości dla niezawodnego skanowania.  
- **Czy potrzebuję licencji, aby uruchomić przykład?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy mogę wyeksportować PNG, JPEG lub TIFF?** Tak – metoda `Save` obsługuje wiele formatów obrazu.

## Czym jest DataMatrix ECC 200?

DataMatrix ECC 200 to dwuwymiarowy kod kreskowy o wysokiej gęstości, który może przechowywać do 2 335 znaków alfanumerycznych lub 1 556 bajtów danych binarnych w kompaktowym kwadratowym lub prostokątnym wzorze. Używa korekcji błędów Reed‑Solomon do odzyskiwania utraconych lub uszkodzonych modułów, co czyni go idealnym dla zastosowań takich jak znakowanie części lotniczych, etykietowanie farmaceutyczne i logistyka, gdzie niezawodność jest kluczowa.

## Dlaczego warto używać generowania kodów kreskowych Aspose?

Aspose.BarCode obsługuje **ponad 30 symboli**, może renderować obrazy do 10 000 × 10 000 px bez ładowania całego pliku do pamięci i zapewnia deterministyczny wynik na Windows, Linux i macOS. Jego API pozwala kontrolować każdy parametr renderowania, co czyni go najbardziej elastycznym wyborem dla **generowania kodów kreskowych ASP.NET** scenariuszy.

## Wymagania wstępne

1. **Środowisko programistyczne** – Visual Studio z odpowiednio zainstalowanym frameworkiem .NET.  
2. **Aspose.BarCode for .NET** – Pobierz i zainstaluj ze strony internetowej, [tutaj](https://releases.aspose.com/barcode/net/).  
3. **Licencja** – Uzyskaj tymczasową licencję do testów z [tutaj](https://purchase.aspose.com/temporary-license/).  
4. **Podstawy C#** – Znajomość składni C# i struktury projektu.

Teraz, gdy podstawy zostały omówione, przejdźmy do konfigurowania DataMatrix ECC 200.

## Importowanie przestrzeni nazw

Przestrzeń nazw `Aspose.BarCode.Generation` zawiera wszystkie klasy potrzebne do tworzenia kodów kreskowych. Zaimportuj ją na początku pliku:

```csharp
using Aspose.BarCode.Generation;
```

## Jak utworzyć kod kreskowy DataMatrix (ECC 200) krok po kroku

Aby wygenerować kod kreskowy DataMatrix ECC 200, po prostu wczytaj dane, które chcesz zakodować, skonfiguruj kilka kluczowych parametrów w obiekcie `BarcodeGenerator`, a następnie wywołaj `Save`, aby zapisać plik obrazu. Ten trzyetapowy proces obsługuje kodowanie, korekcję błędów i wybór formatu wyjściowego, umożliwiając integrację tworzenia kodów kreskowych w dowolnej aplikacji .NET przy minimalnej ilości kodu.

### Krok 1: Inicjalizacja generatora kodów kreskowych

`BarcodeGenerator` jest podstawową klasą Aspose.BarCode, która tworzy i renderuje kody kreskowe. Przyjmuje typ symbolu i tekst do zakodowania.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Zastąp `"Your Directory Path"` folderem, w którym chcesz zapisać obraz.

### Krok 2: Ustaw XDimension i typ ECC

`XDimension` definiuje rozmiar w pikselach każdego modułu DataMatrix, natomiast `DataMatrixEcc` wybiera poziom korekcji błędów. ECC 200 zapewnia najwyższą zdolność korekcji dla tego symbolu.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Dostosuj wartość w pikselach, jeśli potrzebujesz większych lub mniejszych modułów; typowe wartości to 4‑6 px dla wyświetlania na ekranie i 8‑10 px dla drukowanych etykiet.

### Krok 3: Generowanie i zapisywanie obrazu kodu kreskowego

Metoda `Save` zapisuje kod kreskowy do pliku. Możesz wybrać PNG, JPEG lub TIFF, przekazując odpowiednią wartość wyliczenia `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Tiff`, jeśli Twój przepływ pracy wymaga innego formatu.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Kod kreskowy jest rozmyty | XDimension jest za niskie | Zwiększ `XDimension.Pixels` do 6‑8 |
| Skanowanie nie powodzi się na telefonie | Nieprawidłowy poziom ECC | Upewnij się, że `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Plik nie został utworzony | Nieprawidłowy ciąg ścieżki | Użyj ścieżki bezwzględnej lub upewnij się, że folder istnieje |

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego kodu w aplikacji konsolowej .NET Core?**  
A: Tak, to samo API działa w .NET Core, .NET 5 i .NET 6.

**Q: Jak zmienić format wyjściowy na JPEG?**  
A: Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` w wywołaniu `Save`.

**Q: Czy można osadzić kod kreskowy bezpośrednio w pliku PDF?**  
A: Tak – najpierw wygeneruj obraz, a następnie dodaj go do PDF przy użyciu Aspose.PDF lub dowolnej biblioteki PDF.

**Q: Co zrobić, jeśli muszę zakodować znaki Unicode?**  
A: DataMatrix obsługuje UTF‑8; po prostu przekaż ciąg Unicode do generatora, jak pokazano.

**Q: Czy biblioteka obsługuje generowanie wsadowe wielu kodów kreskowych?**  
A: Oczywiście – umieść kod generujący w pętli i zmieniaj dane/wartość dla każdej iteracji.

## Podsumowanie

Omówiliśmy wszystko, co potrzebne do **utworzenia kodu kreskowego DataMatrix** (ECC 200) przy użyciu Aspose.BarCode dla .NET: od wymagań wstępnych i importu przestrzeni nazw, po konfigurowanie X‑dimension, wybór poziomu ECC i zapisywanie obrazu w wybranym formacie. Eksperymentuj z wieloma dodatkowymi właściwościami — takimi jak margines, kolor tła i obrót — aby precyzyjnie dostosować wynik do swojego konkretnego przypadku użycia.

Jeśli napotkasz jakiekolwiek problemy, społeczność jest gotowa pomóc na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Szczęśliwego kodowania!

---

**Ostatnia aktualizacja:** 2026-08-02  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak generować kody kreskowe DataMatrix ECC 000-140 przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Jak odczytywać kody kreskowe DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-reading/)
- [Utwórz kod kreskowy PNG – proporcje DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}