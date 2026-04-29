---
date: 2026-01-04
description: Dowiedz się, jak dodać sumę kontrolną przy generowaniu kodu kreskowego
  Codabar za pomocą Aspose.BarCode dla .NET. Przewodnik krok po kroku obejmujący tryby
  sum kontrolnych Mod10 i Mod16.
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: Jak dodać sumę kontrolną do kodów kreskowych Codabar przy użyciu Aspose.BarCode
  dla .NET
url: /pl/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać sumę kontrolną do kodów kreskowych Codabar przy użyciu Aspose.BarCode dla .NET

Codabar jest powszechnie stosowaną symbologią kodów kreskowych liniowych, szczególnie w logistyce, bibliotekach i opiece zdrowotnej. Dodanie sumy kontrolnej do kodu kreskowego Codabar znacząco poprawia integralność danych, wykrywając błędy transkrypcji, zanim staną się problemem. W tym samouczku dowiesz się **jak dodać sumę kontrolną**, generując kod kreskowy Codabar przy użyciu Aspose.BarCode dla .NET, oraz zobaczysz w działaniu tryby sum kontrolnych Mod10 i Mod16.

## Szybkie odpowiedzi
- **Co oznacza „dodanie sumy kontrolnej” w przypadku Codabar?** Umożliwia to cyfry wykrywające błędy, które walidują zakodowane dane.  
- **Jakie tryby sum kontrolnych są obsługiwane?** Mod10 (powszechny) oraz Mod16 (dla scenariuszy wymagających wyższej dokładności).  
- **Czy potrzebna jest licencja, aby używać tej funkcji?** Tak, do użytku produkcyjnego wymagana jest ważna licencja Aspose.BarCode dla .NET.  
- **Z którymi wersjami .NET jest kompatybilna?** Biblioteka działa z .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Gdzie znajdę wygenerowane obrazy?** Zostaną zapisane w folderze określonym w zmiennej `path`.

## Co oznacza „dodanie sumy kontrolnej” w Codabar?
Dodanie sumy kontrolnej polega na skonfigurowaniu generatora kodów kreskowych tak, aby obliczał i dołączał dodatkową cyfrę (lub cyfry) na podstawie podanych danych. Informacja ta jest weryfikowana przez skanery, zmniejszając ryzyko błędnych odczytów.

## Dlaczego generować kod kreskowy Codabar z sumą kontrolną?
- **Zwiększona niezawodność:** Wykrywa błędy pojedynczych znaków oraz większość błędów przestawienia.  
- **Zgodność:** Niektóre branże (np. banki krwi) wymagają kodów kreskowych z włączoną sumą kontrolną.  
- **Elastyczność:** Aspose.BarCode pozwala przełączać się między Mod10 a Mod16 jedną zmianą właściwości.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz następujące elementy:

1. **Aspose.BarCode dla .NET** – pobierz najnowszą wersję z [tutaj](https://releases.aspose.com/barcode/net/).  
2. **Środowisko programistyczne C#** – Visual Studio, VS Code lub dowolne IDE obsługujące rozwój w .NET.

Gdy wszystko jest gotowe, przejdźmy do implementacji.

## Importowanie przestrzeni nazw

Dodaj wymaganą przestrzeń nazw na początku pliku C#, aby uzyskać dostęp do klas generowania kodów kreskowych:

```csharp
using Aspose.BarCode.Generation;
```

## Krok 1: Inicjalizacja generatora kodów kreskowych

Utwórz instancję `BarcodeGenerator`, określ symbologię Codabar i podaj dane, które chcesz zakodować. Pamiętaj, aby zamienić `"Your Directory Path"` na rzeczywistą ścieżkę folderu, w którym mają być zapisywane obrazy.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## Krok 2: Generowanie kodu kreskowego Codabar **bez** sumy kontrolnej

Jeśli potrzebujesz prostego kodu (bez sumy kontrolnej), ustaw opcję sumy kontrolnej na `Default`. Jest to przydatne w starszych systemach, które nie oczekują cyfry kontrolnej.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## Krok 3: Generowanie kodu kreskowego Codabar z sumą kontrolną **Mod10**

Włącz sumę kontrolną i wybierz algorytm Mod10. To najczęściej używany tryb sumy kontrolnej dla Codabar.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## Krok 4: Generowanie kodu kreskowego Codabar z sumą kontrolną **Mod16**

Dla aplikacji wymagających wyższej zdolności wykrywania błędów, przełącz się na Mod16. Zmiana w kodzie jest minimalna — wystarczy zaktualizować `CodabarChecksumMode`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

Dzięki tym czterem prostym krokom nauczyłeś się **jak dodać sumę kontrolną** do kodów kreskowych Codabar oraz jak przełączać się między trybami Mod10 i Mod16 przy użyciu Aspose.BarCode dla .NET.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Wygenerowany obraz jest pusty | `path` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub użyj `Directory.CreateDirectory(path)` przed zapisem |
| Suma kontrolna nie została zastosowana | `IsChecksumEnabled` pozostawiono jako `Default` | Ustaw `IsChecksumEnabled = EnableChecksum.Yes` przed zapisem |
| Nieprawidłowy tryb sumy kontrolnej | Użyto niewłaściwej wartości wyliczenia | Użyj `CodabarChecksumMode.Mod10` lub `CodabarChecksumMode.Mod16` w zależności od potrzeb |

## Zakończenie

W tym przewodniku omówiliśmy **jak dodać sumę kontrolną** przy generowaniu kodu kreskowego Codabar za pomocą Aspose.BarCode dla .NET, przedstawiliśmy oba tryby sum kontrolnych Mod10 i Mod16 oraz podkreśliliśmy, dlaczego kody z włączoną sumą kontrolną są niezbędne dla integralności danych. Zachęcamy do eksperymentowania z różnymi ciągami danych i odkrywania bogatego zestawu opcji personalizacji kodów kreskowych, które oferuje Aspose.

Jeśli napotkasz jakiekolwiek trudności, społeczność Aspose.BarCode jest gotowa pomóc na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Frequently Asked Questions

**Q: Czy mogę używać sumy kontrolnej Mod16 dla kodów książek w bibliotece?**  
A: Zdecydowanie tak. Mod16 zapewnia silniejsze wykrywanie błędów, co jest korzystne w środowiskach o dużym natężeniu, takich jak biblioteki.

**Q: Czy włączenie sumy kontrolnej wpływa na szybkość skanowania?**  
A: Dodatkowa cyfra wprowadza znikomy czas przetwarzania; większość skanerów radzi sobie z nią bez zauważalnego opóźnienia.

**Q: Jak programowo zweryfikować sumę kontrolną?**  
A: Po wygenerowaniu kodu możesz ponownie obliczyć sumę kontrolną przy użyciu tego samego `CodabarChecksumMode` i porównać ją z ostatnim znakiem zakodowanego ciągu.

**Q: Czy można dostosować wygląd cyfry sumy kontrolnej?**  
A: Tak. Użyj ustawień wyglądu `BarcodeGenerator` (np. `BarHeight`, `ForeColor`), aby stylizować cały kod kreskowy, w tym cyfrę sumy kontrolnej.

**Q: Co zrobić, gdy muszę generować wiele kodów w pętli?**  
A: Utwórz jedną instancję `BarcodeGenerator`, w każdej iteracji aktualizuj właściwość `CodeText` i wywołuj `Save` z unikalną nazwą pliku.

---

**Ostatnia aktualizacja:** 2026-01-04  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}