---
date: 2026-01-02
description: Dowiedz się, jak używać generatora kodów kreskowych Aztec z Aspose.BarCode
  dla .NET – krok po kroku przewodnik, jak ustawić tryb symbolu Aztec (Auto, FullRange,
  Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: generator kodów kreskowych aztec – Opanowanie trybu symbolu Aztec z Aspose.BarCode
  dla .NET
url: /pl/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – Opanowanie trybu symboli Aztec w Aspose.BarCode dla .NET

Jeśli chcesz wprowadzić potężne możliwości generowania kodów kreskowych do swoich aplikacji .NET, **barcode generator aztec** z Aspose.BarCode dla .NET jest doskonałym rozwiązaniem. W tym samouczku zagłębimy się w tryb symboli Aztec, pokażemy **jak ustawić opcje aztec** oraz przeprowadzimy Cię przez praktyczne przykłady kodu, które możesz od razu wkleić do swojego projektu.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa?** `BarcodeGenerator` z `Aspose.BarCode.Generation`.
- **Jakie tryby symboli są dostępne?** Auto, FullRange, Compact i Rune.
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.
- **Czy mogę zmienić tekst kodu?** Tak, ustaw `gen.CodeText` przed zapisem.
- **Jakie formaty obrazu są obsługiwane?** PNG, JPEG, BMP, GIF, TIFF i inne.

## Co to jest barcode generator aztec?
barcode generator aztec tworzy dwuwymiarowe kody Aztec, kompaktowy kod macierzowy, który może przechowywać dużą ilość danych w niewielkiej przestrzeni. Jest idealny dla biletów mobilnych, adresów URL oraz danych binarnych, gdzie miejsce jest na wagę złota.

## Dlaczego warto używać Aspose.BarCode dla .NET?
- **Pełne wsparcie .NET** – działa z .NET Framework, .NET Core oraz .NET 5/6.  
- **Bogaty zestaw funkcji** – wiele trybów symboli, korekcja błędów i rozbudowane możliwości dostosowywania.  
- **Brak zewnętrznych zależności** – generuj kody kreskowe w pełni w procesie.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS.

## Wymagania wstępne

- Praktyczna znajomość programowania w .NET.  
- Zainstalowane Visual Studio.  
- Kopia Aspose.BarCode dla .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/net/).

Teraz, gdy jesteś gotowy, przyjrzyjmy się opcjom trybu symboli Aztec.

## Jak ustawić tryb symboli Aztec w barcode generator aztec

### Importowanie przestrzeni nazw

Najpierw dodaj wymaganą przestrzeń nazw na początku pliku C#:

```csharp
using Aspose.BarCode.Generation;
```

Po zaimportowaniu przestrzeni nazw możesz rozpocząć tworzenie kodów Aztec.

### Krok 1: Konfiguracja generatora kodów

Zainicjuj generator z typem kodowania Aztec i podaj tekst, który chcesz zakodować:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Porada:** Użyj łańcucha kompatybilnego z UTF‑8 dla znaków międzynarodowych, jak pokazano powyżej.

### Krok 2: Ustawienie trybu symbolu na Auto

Tryb **Auto** pozwala bibliotece wybrać optymalny rozmiar w zależności od długości danych:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Wygenerowany plik PNG zostanie zapisany w wybranym folderze.

### Krok 3: Ustawienie trybu symbolu na FullRange

Jeśli chcesz, aby biblioteka wykorzystała pełny zakres rozmiarów symboli Aztec, wybierz **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Krok 4: Ustawienie trybu symbolu na Compact

Dla bardziej kompaktowego kodu, który nadal zachowuje dobrą czytelność, użyj **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Krok 5: Ustawienie trybu symbolu na Rune

Tryb **Rune** jest przeznaczony do specjalnych przypadków, gdzie wymagana jest inna stylistyka wizualna:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| Obraz kodu jest pusty | Sprawdź, czy `path` wskazuje istniejący katalog z prawami zapisu. |
| Nieobsługiwane znaki | Używaj wyłącznie znaków wspieranych przez standard Aztec lub przełącz na kodowanie UTF‑8. |
| Nieprawidłowy rozmiar symbolu | Eksperymentuj z `AztecSymbolMode.Auto`, aby biblioteka wybrała najlepszy rozmiar. |

## Najczęściej zadawane pytania

**P: Jaki jest cel trybu Symbol Aztec w generowaniu kodów?**  
O: Pozwala kontrolować gęstość wizualną i poziom korekcji błędów kodu Aztec, dostosowując kod do wymagań dotyczących przestrzeni i czytelności.

**P: Czy mogę zmienić tekst kodu dla kodów Aztec w Aspose.BarCode dla .NET?**  
O: Tak, po prostu przypisz nowy łańcuch do `gen.CodeText` przed wywołaniem `Save`.

**P: Czy istnieje darmowa wersja próbna Aspose.BarCode dla .NET?**  
O: Tak, darmową wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

**P: Gdzie znajdę pełną dokumentację Aspose.BarCode dla .NET?**  
O: Kompletną referencję API znajdziesz [tutaj](https://reference.aspose.com/barcode/net/).

**P: Jak uzyskać tymczasową licencję dla Aspose.BarCode dla .NET?**  
O: Tymczasową licencję można zamówić poprzez [ten link](https://purchase.aspose.com/temporary-license/).

## Podsumowanie

W tym przewodniku omówiliśmy wszystko, co musisz wiedzieć, aby używać **barcode generator aztec** z Aspose.BarCode dla .NET – od konfiguracji generatora po opanowanie każdego trybu symboli (Auto, FullRange, Compact, Rune). Dzięki tym przykładom możesz szybko i niezawodnie osadzać wszechstronne kody Aztec w dowolnej aplikacji .NET.

Jeśli masz dodatkowe pytania, dołącz do społeczności Aspose.BarCode na ich [forum wsparcia](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-02  
**Testowano z:** Aspose.BarCode 24.10 dla .NET  
**Autor:** Aspose