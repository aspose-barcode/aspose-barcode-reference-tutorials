---
date: 2026-01-04
description: Dowiedz się, jak generować kod kreskowy Codabar z znakami start i stop
  przy użyciu Aspose.BarCode dla .NET. Szczegółowy, krok po kroku, poradnik generowania
  kodów kreskowych dla programistów.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Generowanie kodu kreskowego Codabar z znakami start/stop w Aspose.BarCode dla
  .NET
url: /pl/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego Codabar ze znakami start/stop w Aspose.BarCode dla .NET

## Wstęp

Witamy w tym przewodniku, jak **generować obrazy kodu kreskowego Codabar** ze znakami start/stop przy użyciu Aspose.BarCode dla .NET. od tego, czy tworzysz system inwentaryzacji detalicznej, ujawniający laboratoriumjnych lub rozwiązanie do rekordów medycznych, Codabar jest niezawodną symbologią numeryczną, która wymaga występowania znaków start i stop dla dokładnego skanowania. W ciągu kilku minut przeprowadziliśmy Cię przez wszystko, co potrzebne — od zastosowania wstępnego po zapisanie plików PNG — ręcznie od razu po utworzeniu kodów kreskowych Codabar.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode dla .NET
- **W jakim formacie mogę zapisać kod kreskowy?** PNG (BarCodeImageFormat.Png)
- **Czy potrzebuję licencji do tworzenia oprogramowania?** Bezpłatna wersja próbna działa do testowania; do produkcji wymagana jest licencja komercyjna.
- **Czy mogę zmienić symbole start/stop?** Tak – użyj CodabarSymbol.A, B, C lub D.
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wymagania wstępne

Zanim zaczniemy, powinniśmy się, że masz wszystko, co potrzebne, aby podążać za tym samouczkiem:

1. **Konfiguracja środowiska** – Upewnij się, że na swoim komputerze masz działające środowisko programistyczne .NET. Jeśli potrzebujesz wskazówek, zapoznaj się z [dokumentacją](https://reference.aspose.com/barcode/net/).
2. **Biblioteka Aspose.BarCode dla .NET** – Pobierz i zainstaluj bibliotekę z oficjalnego [źródła](https://releases.aspose.com/barcode/net/).
3. **Podstawowa wiedza o .NET** – Znajomość C# i Visual Studio (lub dowolnego preferowanego środowiska IDE) ułatwi Ci wykonanie tych kroków.
4. **IDE** – Visual Studio, Rider lub VisualStudioCode są odpowiednie.

Teraz, gdy omówiliśmy wymagania wstępne, przejdźmy do właściwego kodu.

## Importowanie przestrzeni nazw

Aby rozpocząć pracę z Aspose.BarCode dla .NET, upewnij się, że zaimportowałeś niezbędną przestrzeń nazw:

```csharp
using Aspose.BarCode.Generation;
```

## Jak wygenerować kod kreskowy Codabar – Przewodnik krok po kroku

### Krok 1: Zainicjuj generator kodów kreskowych

Utwórz instancję `BarcodeGenerator`, określ **Codabar** jako typ kodowania i podaj ciąg danych, który już zawiera znaki start/stop (np. “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro tip:** Myślnik (`-`) jest jednym z prawidłowych symboli start/stop dla Codabar. Możesz również użyć A, B, C lub D w zależności od wymagań aplikacji.

### Krok 2: Ustaw wymiar X (szerokość elementu kodu kreskowego)

X‑Dimension kontroluje szerokość najwęższego słupka. Dostosuj ją do swojego środowiska skanowania.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why it matters:** Większa X‑Dimension poprawia czytelność na drukarkach o niskiej rozdzielczości, podczas gdy mniejsza wartość oszczędza miejsce na etykietach o wysokiej gęstości.

### Krok 3: Zdefiniuj znaki Start i Stop

Codabar obsługuje cztery symbole start/stop (A, B, C, D). Poniżej znajdują się przykłady dla każdej opcji. Wybierz tę, która odpowiada specyfikacji systemu, z którym się integrujesz.

#### Ustawianie StartA i StopA

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Ustawianie StartB i StopB

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Ustawianie StartC i StopC

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Ustawianie StartD i StopD

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Możesz powtórzyć konfigurację dla każdego potrzebnego symbolu; poniższy przykład zapisuje cztery oddzielne obrazy — po jednym dla każdej pary start/stop.

### Krok 4: Zapisz wygenerowane obrazy kodu kreskowego (PNG)

Na koniec zapisz kod kreskowy do plików PNG. Demonstracja użycia **save barcode png** oraz dostarcza gotowe zasoby do testów.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Każdy plik zawiera teraz **przykład kodu kreskowego Codabar** z odpowiednimi znakami start/stop.

## Typowe problemy i rozwiązywanie problemów

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|-------------------------------|------------|
| Kod kreskowy wygląda zniekształcony | X‑Dimension zbyt niska dla rozdzielczości drukarki | Wzmocnione `XDimension.Pixels` (np. do 3 lub 4) |
| Skaner nie odczytuje start/stop | Nieprawidłowy symbol start/stop dla docelowego systemu | Sprawdź wymagany symbol (A-D) i ustaw go odpowiednio |
| Plik PNG jest pusty lub pusty | Nieprawidłowa ścieżka wyjściowa lub wersja prawna do zapisu | następuje, że `path` plik instalacyjny i aplikacja ma dostęp do zapisu |

## Często zadawane pytania

### P1: Co to jest Codabar i dlaczego znaki początkowe i końcowe są ważne?

Kodabar do numerycznej symboliki kodów kreskowych szeroko rozpowszechnionych w inwentaryzacji, bibliotekach i opiece zdrowotnej. Znaki start i stop definiują granice kodu kreskowego, moduł rozszerzenia, gdzie dane się kończą i kończą.

### P2: Czy mogę dostosować wygląd kodów kreskowych Codabar za pomocą Aspose.BarCode dla .NET?

Tak. Poza tym X-Dimension może zmieniać kolory, marginesy, a nawet osadzać kod kreskowy w formacie PDF lub SVG przy użyciu tego samego API.

### P3: Czy istnieją jakieś ograniczenia dotyczące kodów kreskowych Codabar w zakresie kodowania danych?

Codabar główny obsługuje dane numeryczne (0‑9) oraz kilka znaków specjalnych. Nie jest przeznaczony do pełnych łańcuchów alfanumerycznych.

### P4: Czy Aspose.BarCode dla .NET nadaje się do użytku komercyjnego i jak mogę uzyskać licencję?

Tak, jest gotowe do produkcji. Kupuj na [stronie zakupu Aspose](https://purchase.aspose.com/buy).

### P5: Gdzie mogę szukać pomocy lub omówić problemy związane z Aspose.BarCode dla .NET?

Dołącz do społeczności na [forum wsparcia Aspose.BarCode dla .NET](https://forum.aspose.com/c/barcode/13), aby uzyskać pomoc inżynierów Aspose oraz innych programistów.

---

**Aktualizacja Ostatnia:** 2026-01-04
**Testowano z:** Aspose.BarCode 24.11 dla .NET
**Autor:** Asponuj  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}