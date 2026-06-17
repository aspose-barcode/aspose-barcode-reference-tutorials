---
date: 2026-02-22
description: Dowiedz się, jak tworzyć obrazy kodów kreskowych w C# przy użyciu Aspose.BarCode
  dla .NET i generować kody GS1 DataMatrix szybko i efektywnie.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Tworzenie obrazu kodu kreskowego w C# – Przykład GS1 DataMatrix
url: /pl/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład GS1 DataMatrix

Jeśli szukasz niezawodnego sposobu na **create barcode image C#** w swoich aplikacjach .NET, Aspose.BarCode for .NET upraszcza ten proces. Ta potężna biblioteka obsługuje szeroką gamę symbologii, w tym GS1 DataMatrix, i zapewnia przejrzyste API, które pozwala skupić się na logice biznesowej zamiast na szczegółach niskopoziomowych kodów kreskowych. W ciągu kilku minut przeprowadzimy Cię przez kompletny, praktyczny przykład, który pokaże, jak wygenerować kod kreskowy GS1 DataMatrix, dostosować jego wygląd i zapisać go jako plik obrazu.

## Szybkie odpowiedzi
- **Co generuje przykład?** Kod kreskowy GS1 DataMatrix zawierający przykładowe dane produktu.  
- **Jakiej biblioteki użyto?** Aspose.BarCode for .NET.  
- **Czy mogę zmienić format wyjściowy?** Tak, możesz zapisać jako PNG, JPEG, BMP itp.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy kod jest kompatybilny z .NET Core?** Zdecydowanie – to samo API działa na .NET Framework oraz .NET Core/5/6.

## Co to jest kod kreskowy GS1 DataMatrix?
GS1 DataMatrix to dwuwymiarowy kod kreskowy, który koduje informacje na poziomie produktu (takie jak GTIN, numer seryjny oraz dodatkowe identyfikatory aplikacji). Jest szeroko stosowany w handlu detalicznym, opiece zdrowotnej i logistyce do kompaktowego, wysokiej gęstości przechowywania danych.

## Dlaczego używać Aspose.BarCode do tworzenia barcode image C#?
- **Full‑featured API** – obsługuje standardy GS1, korekcję błędów i kontrolę rozmiaru.  
- **No external dependencies** – czysta biblioteka .NET, łatwa do integracji.  
- **Cross‑platform** – działa na Windows, Linux i macOS.  
- **Extensive documentation** – zawiera przykłady takie jak ten, aby szybko rozpocząć.

## Wymagania wstępne

Zanim przejdziemy do samouczka, upewnij się, że masz następujące wymagania:

1. **Aspose.BarCode for .NET** – Musisz mieć zainstalowany Aspose.BarCode for .NET. Jeśli jeszcze tego nie zrobiłeś, możesz [pobrać go tutaj](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – Powinieneś mieć skonfigurowane środowisko programistyczne .NET na swoim komputerze (Visual Studio, VS Code lub dowolne IDE, które preferujesz).

Teraz, gdy masz już wymagania, rozpocznijmy generowanie kodów GS1 DataMatrix.

## Importowanie przestrzeni nazw

Najpierw zaimportuj niezbędne przestrzenie nazw, aby pracować z Aspose.BarCode for .NET. Te przestrzenie nazw zapewniają dostęp do funkcji generowania kodów kreskowych.

```csharp
using Aspose.BarCode;
using System;
```

## Jak stworzyć barcode image C# – Przewodnik krok po kroku

### Krok 1: Konfiguracja generatora kodów kreskowych

Aby rozpocząć, utwórz instancję `BarcodeGenerator` i określ symbologię **GS1 DataMatrix** oraz dane, które chcesz zakodować. W tym przykładzie kodujemy ciąg **"(01)12345678901231(21)ASPOSE(30)9876"**, który jest zgodny z formatem identyfikatorów aplikacji GS1.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro tip:* Zastąp przykładowe dane własnymi identyfikatorami GS1, aby dopasować je do katalogu produktów.

### Krok 2: Dostosowanie właściwości kodu kreskowego

Możesz dostosować wygląd kodu kreskowego przy użyciu obiektu `Parameters`. Tutaj ustawiamy wymiar X (rozmiar najmniejszego modułu) na 8 pikseli oraz definiujemy rozmiar macierzy 36 kolumn na 12 wierszy. Dostosuj te wartości, aby spełnić wymagania skanowania.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Why adjust X‑dimension?* Większy wymiar X ułatwia skanowanie na urządzeniach o niskiej rozdzielczości, natomiast mniejsza wartość zmniejsza rozmiar obrazu.

### Krok 3: Zapisz obraz kodu kreskowego

Na koniec zapisz wygenerowany kod kreskowy na dysku. Przykład używa formatu PNG, ale możesz wybrać JPEG, GIF, BMP i inne formaty obsługiwane przez Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Po uruchomieniu kodu znajdziesz plik **Gs1DataMatrixExample.png** w określonym folderze, gotowy do użycia na etykietach, opakowaniach lub w aplikacjach cyfrowych.

## Typowe przypadki użycia

- **Retail product labeling** – Etykietowanie produktów detalicznych – kodowanie GTIN, numerów partii i dat ważności.  
- **Pharmaceutical tracking** – Śledzenie farmaceutyczne – spełnianie wymogów regulacyjnych dzięki danym zgodnym z GS1.  
- **Warehouse logistics** – Logistyka magazynowa – kompaktowe przechowywanie informacji o lokalizacji i stanie zapasów.  

## Rozwiązywanie problemów i wskazówki

- **Incorrect data format** – Nieprawidłowy format danych – Upewnij się, że ciąg spełnia składnię identyfikatorów aplikacji GS1; w przeciwnym razie kod kreskowy może nie być możliwy do zeskanowania.  
- **Image size issues** – Problemy z rozmiarem obrazu – Jeśli wygenerowany obraz jest rozmyty, zwiększ wartość `XDimension.Pixels`.  
- **License errors** – Błędy licencji – Licencja próbna działa w ocenie, ale pełna licencja jest wymagana w środowiskach produkcyjnych.

## Najczęściej zadawane pytania

### Co to jest GS1 DataMatrix?
GS1 DataMatrix to dwuwymiarowa symbologia kodu kreskowego używana do kodowania danych związanych z produktami i ich identyfikacją, szczególnie w branży detalicznej i opieki zdrowotnej.

### Czy Aspose.BarCode for .NET jest odpowiedni dla innych typów kodów kreskowych?
Tak, Aspose.BarCode for .NET obsługuje szeroką gamę typów kodów kreskowych, co czyni go wszechstronnym dla różnych zastosowań.

### Czy mogę generować kody kreskowe w innych formatach obrazu oprócz PNG?
Tak, Aspose.BarCode for .NET pozwala zapisywać wygenerowane kody kreskowe w różnych formatach obrazu, takich jak JPEG, GIF i BMP, oprócz PNG.

### Czy potrzebuję licencji, aby używać Aspose.BarCode for .NET?
Tak, wymagana jest ważna licencja do komercyjnego używania Aspose.BarCode for .NET. Licencję możesz uzyskać na [stronie Aspose](https://purchase.aspose.com/buy).

### Gdzie mogę uzyskać wsparcie dla Aspose.BarCode for .NET?
Odpowiedzi na pytania i wsparcie znajdziesz na [forum Aspose.BarCode for .NET](https://forum.aspose.com/c/barcode/13).

## Dodatkowe FAQ (optymalizowane AI)

**Q: Jak wygenerować kod DataMatrix w C# bez formatowania GS1?**  
A: Użyj `EncodeTypes.DataMatrix` zamiast `EncodeTypes.GS1DataMatrix` i podaj zwykły ciąg danych do `BarcodeGenerator`.

**Q: Czy mogę zmienić kolory kodu kreskowego programowo?**  
A: Tak, ustaw `gen.Parameters.Barcode.ForeColor` i `gen.Parameters.Barcode.BackColor`, aby dostosować kolory pierwszego planu i tła.

**Q: Czy można osadzić wygenerowany kod kreskowy bezpośrednio w pliku PDF?**  
A: Oczywiście – pobierz kod kreskowy jako `System.Drawing.Image` i dodaj go do PDF przy użyciu Aspose.PDF lub dowolnej innej biblioteki PDF.

**Q: Jakie wersje .NET są obsługiwane?**  
A: Aspose.BarCode for .NET obsługuje .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 i nowsze.

**Q: Jak mogę poprawić niezawodność skanowania małych etykiet?**  
A: Zwiększ wymiar X, dodaj strefy ciszy (`gen.Parameters.Barcode.Margin`) i zapewnij odpowiedni kontrast między kodem kreskowym a tłem.

## Podsumowanie

W tym samouczku omówiliśmy, jak **create barcode image C#** przy użyciu Aspose.BarCode for .NET do generowania kodu GS1 DataMatrix. Dzięki kilku linijkom kodu możesz osadzić wysokiej jakości kody kreskowe w swoich aplikacjach, niezależnie od tego, czy tworzysz rozwiązania detaliczne, systemy opieki zdrowotnej czy platformy logistyczne. Zbadaj bibliotekę dalej, aby odkryć dodatkowe symbologie, zaawansowane opcje renderowania i scenariusze integracji.

Aby uzyskać więcej informacji i szczegółową dokumentację, zapoznaj się z [dokumentacją Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-22  
**Testowano z:** Aspose.BarCode for .NET (latest version)  
**Autor:** Aspose