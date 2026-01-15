---
date: 2026-01-15
description: Krok po kroku przewodnik po kodach kreskowych, jak odczytać kod DataMatrix
  w C# i wygenerować obraz kodu kreskowego w C# przy użyciu Aspose.BarCode dla .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Odczyt kodu DataMatrix w C# – Tryb generowania DataMatrix (Auto)
url: /pl/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt kodu DataMatrix C# – Generowanie w trybie DataMatrix (Auto)

W dzisiejszym szybko zmieniającym się cyfrowym świecie możliwość **odczytu kodu DataMatrix C#** szybko i niezawodnie jest niezbędna do wszystkiego, od śledzenia zapasów po bezpieczną obsługę dokumentów. Ten samouczek przeprowadzi Cię przez generowanie kodu DataMatrix w trybie *Auto* przy użyciu Aspose.BarCode dla .NET, a następnie pokaże, jak odczytać ten kod ponownie w C#. Niezależnie od tego, czy podążasz za **przewodnikiem po tutorialu kodów kreskowych**, czy po prostu potrzebujesz solidnego przykładu kodu, zakończysz ten przewodnik działającym rozwiązaniem, które możesz wstawić do własnych projektów.

## Szybkie odpowiedzi
- **Co robi tryb „Auto”?** Pozwala Aspose.BarCode automatycznie wybrać najlepszy schemat kodowania dla Twoich danych.  
- **Jakiej biblioteki wymaga?** Aspose.BarCode for .NET (dostępna darmowa wersja próbna).  
- **Czy mogę odczytać kod w tej samej aplikacji?** Tak – użyj `BarCodeReader` z `DecodeType.DataMatrix`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku produkcyjnego.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest odczyt kodu DataMatrix C#?
Odczyt kodu DataMatrix w C# oznacza dekodowanie dwuwymiarowej macierzy czarnych i białych modułów z powrotem do pierwotnego tekstu lub danych. Aspose.BarCode udostępnia prosty interfejs API, który ukrywa niskopoziomowe przetwarzanie obrazu, pozwalając skupić się na logice biznesowej.

## Dlaczego używać Aspose.BarCode do generowania obrazu kodu kreskowego C#?
- **Niezawodność:** Obsługuje wszystkie standardy DataMatrix i automatycznie wybiera optymalne kodowanie.  
- **Elastyczność:** Pełna kontrola nad wymiarami, kodowaniem ECI i formatem obrazu.  
- **Cross‑platform:** Działa z aplikacjami .NET Framework, .NET Core i .NET 5+.

## Wymagania wstępne

1. **Środowisko .NET** – Zainstaluj najnowszy runtime .NET z [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Pobierz bibliotekę ze [website](https://releases.aspose.com/barcode/net/).  

## Importowanie przestrzeni nazw

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Teraz, gdy przestrzenie nazw są zaimportowane, przejdźmy krok po kroku przez kod.

## Krok 1: Ustaw ścieżkę katalogu

```csharp
string path = "Your Directory Path";
```

Zastąp `"Your Directory Path"` folderem, w którym chcesz zapisać wygenerowany plik PNG (lub inny format).

## Krok 2: Utwórz kod DataMatrix w trybie Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Ustawienie `DataMatrixEncodeMode.Auto` pozwala bibliotece wybrać najlepsze kodowanie dla podanego tekstu. Śmiało zamień przykładowy tekst na dowolny ciąg znaków, dla którego chcesz **generować obraz kodu kreskowego C#**.

## Krok 3: Odczytaj kod (odczyt kodu DataMatrix C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Ten fragment dekoduje właśnie wygenerowany obraz i wypisuje pierwotny tekst w konsoli, demonstrując pełny cykl od generacji do odczytu.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Nie wykryto kodu** | Rozdzielczość obrazu zbyt niska | Zwiększ `XDimension.Pixels` (np. do 6) |
| **Zniekształcone znaki** | Nieprawidłowe kodowanie ECI | Ustaw `ECIEncoding` zgodnie z danymi (UTF‑8, ASCII itp.) |
| **Wyjątek przy `ReadBarCodes`** | Obiekt Bitmap został zwolniony przed odczytem | Utrzymaj instancję `Bitmap` przy życiu aż do zakończenia odczytu |

## Najczęściej zadawane pytania

**P: Co to jest tryb kodowania DataMatrix „Auto”?**  
O: Pozwala Aspose.BarCode automatycznie wybrać optymalną metodę kodowania dla podanych danych, upraszczając proces **jak generować kod datamatrix**.

**P: Czy mogę dostosować wymiary wygenerowanego kodu?**  
O: Tak – zmień `generator.Parameters.Barcode.XDimension.Pixels`, aby zmienić rozmiar modułu.

**P: Czy Aspose.BarCode for .NET nadaje się do użytku komercyjnego?**  
O: Zdecydowanie tak. Zakup licencję na [website](https://purchase.aspose.com/buy).

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak, możesz wypróbować Aspose.BarCode w wersji próbnej pod [this link](https://releases.aspose.com/).

**P: Jakie opcje kodowania są dostępne dla kodów DataMatrix?**  
O: Aspose.BarCode obsługuje UTF‑8, ASCII i inne kodowania ECI; ustaw żądaną wartość za pomocą `ECIEncoding`.

## Podsumowanie

Masz teraz kompletny, gotowy do produkcji przykład, który **odczytuje kod DataMatrix C#**, generuje kod w trybie Auto i weryfikuje wynik — wszystko przy użyciu Aspose.BarCode dla .NET. Eksperymentuj z różnymi tekstami, rozmiarami i ustawieniami ECI, aby dopasować je do swojego scenariusza, i odwołaj się do oficjalnej [documentation](https://reference.aspose.com/barcode/net/) w celu głębszej personalizacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.BarCode 24.12 dla .NET  
**Autor:** Aspose