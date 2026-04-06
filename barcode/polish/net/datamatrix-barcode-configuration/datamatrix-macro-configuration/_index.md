---
date: 2026-01-17
description: Dowiedz się, jak generować kod kreskowy DataMatrix z znakami makro przy
  użyciu Aspose.BarCode dla .NET i odkryj, jak używać DataMatrix w swoich aplikacjach.
linktitle: DataMatrix Macro Configuration
second_title: Aspose.BarCode .NET API
title: Jak wygenerować kod DataMatrix przy użyciu Aspose.BarCode dla .NET
url: /pl/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfiguracja makra DataMatrix z Aspose.BarCode dla .NET

## Wprowadzenie

We współczesnych aplikacjach .NET **generowanie kodów kreskowych DataMatrix** jest niezawodnym sposobem kodowania dużych ilości danych w niewielkim obszarze. Ten samouczek przeprowadzi Cię krok po kroku, jak **generować kod DataMatrix** z znakami makra, wyjaśni *jak efektywnie korzystać z DataMatrix* oraz pokaże, jak zweryfikować wynik przy użyciu Aspose.BarCode dla .NET. Po zakończeniu będziesz w stanie tworzyć, dostosowywać i odczytywać kody DataMatrix z pełnym przekonaniem.

## Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.BarCode dla .NET  
- **Czy mogę wygenerować kod DataMatrix ze znakami makra?** Tak, używając właściwości `MacroCharacters`.  
- **Czy potrzebna jest licencja do produkcji?** Ważna licencja Aspose jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy dostępna jest darmowa wersja próbna?** Oczywiście – pobierz ją z oficjalnej strony Aspose.

## Wymagania wstępne

Zanim przejdziesz do konfiguracji makra, upewnij się, że masz następujące elementy:

1. **Visual Studio** – dowolna aktualna edycja będzie odpowiednia.  
2. **Aspose.BarCode dla .NET** – pobierz ją z [linku do pobrania](https://releases.aspose.com/barcode/net/).  
3. **Podstawowa znajomość .NET** – znajomość C# i ekosystemu .NET.

## Importowanie przestrzeni nazw

Zaczynamy od zaimportowania przestrzeni nazw niezbędnych do generowania i rozpoznawania kodów kreskowych.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Co to jest „generowanie kodu DataMatrix” ze znakami makra?

Kod DataMatrix z włączonym makrem może przenosić dodatkowe informacje (np. odwołanie do innego kodu) przy użyciu specjalnych znaków makra (Macro05, Macro06 itp.). Jest to przydatne w logistyce i produkcji, gdzie pojedynczy symbol może wymagać połączenia z większym zestawem danych.

## Dlaczego warto używać Aspose.BarCode do generowania kodu DataMatrix?

- **Pełna kontrola** nad rozmiarem, korekcją błędów i ustawieniami makra.  
- **Wsparcie wieloplatformowe** dla .NET Framework, .NET Core oraz .NET 5/6.  
- **Wbudowane rozpoznawanie** umożliwia natychmiastową weryfikację kodu po jego utworzeniu.

## Przewodnik krok po kroku

### Krok 1: Konfiguracja projektu

Utwórz nową aplikację konsolową (lub dowolny projekt .NET) w Visual Studio. Dodaj odwołanie do bibliotek Aspose.BarCode DLL, które pobrałeś.

### Krok 2: Konfiguracja makra DataMatrix

Sedno samouczka – tutaj faktycznie **generujemy kod DataMatrix** ze znakiem makra.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Wskazówka:** Zastąp `"ASPOSE"` dowolnym ciągiem, który chcesz zakodować. Znak makra (`Macro05`) informuje skanery, że ten kod jest częścią sekwencji makr.

### Krok 3: Dostosowanie parametrów kodu

Przed zapisaniem możesz dostroić dodatkowe ustawienia:

- **XDimension** – kontroluje rozmiar pojedynczego modułu (piksela).  
- **Margin**, **ErrorCorrection** i **EncodingMode** – wszystkie dostępne poprzez `gen.Parameters.Barcode.DataMatrix`.

### Krok 4: Zapisz kod kreskowy

Powyższy fragment zapisuje obraz jako `DataMatrixMacro.png` w wybranym folderze. PNG jest bezstratny, co czyni go idealnym do dalszego przetwarzania.

### Krok 5: Rozpoznaj kod kreskowy

Używając `BarCodeReader` natychmiast odczytujemy wygenerowany obraz, aby potwierdzić, że znak makra i dane są prawidłowe. Ta weryfikacja w obie strony jest szczególnie przydatna podczas testów automatycznych.

## Jak używać DataMatrix w rzeczywistych scenariuszach?

- **Etykietowanie produktów** – osadzanie numerów seryjnych, identyfikatorów partii lub adresów URL.  
- **Śledzenie dokumentów** – łączenie wydrukowanego formularza z rekordem cyfrowym za pomocą sekwencji makr.  
- **Opieka zdrowotna** – kodowanie informacji o pacjencie na kompaktowych etykietach sprzętu.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Kod nie jest rozpoznawany | Nieprawidłowy `XDimension` lub niska rozdzielczość obrazu | Zwiększ `XDimension.Pixels` do 4‑6 i zapisz jako PNG lub TIFF |
| Znak makra jest ignorowany | Czytnik nie obsługuje trybu makra | Użyj skanera/ czytnika, który explicite wspiera makra DataMatrix (np. nowsze wersje ZXing) |
| Nie znaleziono ścieżki | Nieprawidłowa zmienna `path` | Upewnij się, że katalog istnieje lub użyj `Path.Combine` z `Environment.CurrentDirectory` |

## Najczęściej zadawane pytania

**P: Czym jest Aspose.BarCode dla .NET?**  
O: Aspose.BarCode dla .NET to potężna biblioteka umożliwiająca programistom .NET generowanie i rozpoznawanie kodów kreskowych w różnych formatach, w tym DataMatrix, QR i innych.

**P: Dlaczego warto używać kodów DataMatrix?**  
O: Kody DataMatrix są kompaktowe, bardzo niezawodne i mogą przechowywać duże ilości danych, co czyni je idealnymi dla produkcji, logistyki i opieki zdrowotnej.

**P: Gdzie mogę znaleźć dokumentację Aspose.BarCode dla .NET?**  
O: Dokumentację znajdziesz pod adresem [dokumentacji Aspose.BarCode dla .NET](https://reference.aspose.com/barcode/net/).

**P: Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?**  
O: Tak, darmową wersję próbną można pobrać z [linku do wersji próbnej](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.BarCode dla .NET?**  
O: Jeśli masz pytania lub potrzebujesz pomocy, odwiedź forum Aspose.BarCode dla .NET pod adresem [forum wsparcia](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-01-17  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}