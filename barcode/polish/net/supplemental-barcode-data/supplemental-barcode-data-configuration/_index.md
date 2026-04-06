---
date: 2026-03-07
description: Dowiedz się, jak utworzyć kod kreskowy EAN‑13 z danymi uzupełniającymi
  w C# przy użyciu Aspose.BarCode dla .NET – szybko generuj kod kreskowy w formacie
  PNG.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Tworzenie kodu kreskowego EAN‑13 z danymi uzupełniającymi – Aspose.BarCode
url: /pl/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy EAN-13 z danymi uzupełniającymi – Aspose.BarCode dla .NET

W tym praktycznym samouczku **utworzysz kod kreskowy EAN-13** zawierający dodatkowe dane EAN‑2 lub EAN‑5 oraz zobaczysz, jak **generować pliki PNG kodu kreskowego** przy użyciu kilku linii C#. Niezależnie od tego, czy tworzysz system kasowy dla handlu detalicznego, aplikację logistyczną, czy prostą aplikację inwentaryzacyjną, możliwość dodania informacji uzupełniających sprawia, że Twoje kody kreskowe są znacznie bardziej użyteczne.

## Szybkie odpowiedzi
- **Co oznacza „dane uzupełniające”?** Dodatkowe cyfry (EAN‑2/EAN‑5) drukowane obok głównego kodu kreskowego, często używane do oznaczania ceny lub numeru wydania.  
- **Jaki typ kodu kreskowego jest używany?** EAN‑13 jako główny symbol, z opcjonalnymi dodatkami EAN‑2 lub EAN‑5.  
- **Czy mogę wyeksportować obrazy PNG?** Tak – metoda `Save` umożliwia bezpośredni eksport do PNG.  
- **Czy potrzebna jest licencja do rozwoju?** Bezpłatna wersja próbna wystarcza do testów; do produkcji wymagana jest licencja komercyjna.  
- **Czy jest to kompatybilne z .NET Core / .NET 6?** Absolutnie – Aspose.BarCode obsługuje wszystkie nowoczesne środowiska .NET.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz:

- Visual Studio (lub dowolne IDE kompatybilne z .NET).  
- Kopię Aspose.BarCode dla .NET – pobierz ją **[tutaj](https://releases.aspose.com/barcode/net/)**.  
- Podstawową znajomość C#.  
- Zapisywalny folder, w którym zostaną zapisane wygenerowane pliki PNG.

## Importowanie przestrzeni nazw

Najpierw dodaj przestrzeń nazw Aspose.BarCode, aby mieć dostęp do klas generatora:

```csharp
using Aspose.BarCode.Generation;
```

> **Wskazówka:** Jeśli używasz .NET Core, dodaj pakiet NuGet `Aspose.BarCode` do swojego projektu zamiast ręcznie odwoływać się do pliku DLL.

## Co to jest kod kreskowy uzupełniający?

Kod kreskowy uzupełniający to dodatkowy ciąg numeryczny drukowany obok głównego kodu kreskowego.  
- **EAN‑2** – dwucyfrowy dodatek, często używany do numerów wydań w czasopismach.  
- **EAN‑5** – pięciocyfrowy dodatek, powszechnie stosowany do rozszerzeń cenowych na produktach detalicznych.

Dodanie tych dodatków nie zmienia podstawowych danych EAN‑13; po prostu dostarcza dodatkowego kontekstu, który mogą odczytać skanery.

## Dlaczego warto używać Aspose.BarCode do danych uzupełniających?

- **Jednolinijkowe API** – konfiguruje zarówno główny kod kreskowy, jak i jego dodatek w jednym obiekcie.  
- **Pełna kontrola nad wymiarami** – reguluj wymiar X, odstęp dodatku oraz format obrazu.  
- **Cross‑platform** – działa na .NET Framework, .NET Core oraz .NET 5/6+.

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog wyjściowy

Określ, gdzie będą przechowywane pliki PNG. Zastąp symbol zastępczy rzeczywistą ścieżką na swoim komputerze.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Zainicjalizuj generator kodów kreskowych (Barcode Generator C#)

Utwórz instancję `BarcodeGenerator`, określając **EAN‑13** jako główny typ i podając 13‑cyfrową zawartość.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Krok 3: Dostosuj wymiary kodu kreskowego

Dopracuj wizualny rozmiar kodu kreskowego oraz przestrzeń przeznaczoną na dodatek.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Krok 4: Dodaj suplement EAN‑2

Ustaw dane uzupełniające na dwucyfrową wartość (np. „12”). Zostanie ona wyświetlona po prawej stronie głównego kodu kreskowego.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Krok 5: Zapisz kod kreskowy EAN‑2 jako PNG

Wyeksportuj obraz. Argument `BarCodeImageFormat.Png` zapewnia wysokiej jakości plik PNG.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Krok 6: Przełącz na suplement EAN‑5

Zmień `SupplementData` na pięciocyfrowy ciąg dla rozszerzeń cenowych.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Krok 7: Zapisz kod kreskowy EAN‑5 jako PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Dlaczego to działa:** Ta sama instancja `BarcodeGenerator` jest ponownie używana, więc przed każdym wywołaniem `Save` wystarczy zmodyfikować właściwość `SupplementData`. Dzięki temu kod pozostaje zwięzły i unika niepotrzebnego tworzenia obiektów.

## Typowe problemy i wskazówki

- **Nieprawidłowa ścieżka katalogu** – upewnij się, że folder istnieje i aplikacja ma uprawnienia do zapisu.  
- **Nieprawidłowa długość dodatku** – EAN‑2 wymaga dokładnie 2 cyfr, EAN‑5 wymaga 5; w przeciwnym razie zostanie zgłoszony wyjątek.  
- **Obraz niewidoczny** – sprawdź, czy użyto `BarCodeImageFormat.Png`; inne formaty (np. JPEG) mogą wprowadzać artefakty kompresji, które wpływają na czytelność przez skaner.  

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.BarCode dla .NET w moim projekcie .NET Core?
Tak, Aspose.BarCode dla .NET jest w pełni kompatybilny z .NET Core, .NET 5 i .NET 6.

### Czy dostępna jest bezpłatna wersja próbna Aspose.BarCode dla .NET?
Tak, możesz wypróbować go za darmo, odwiedzając **[ten link](https://releases.aspose.com/)**.

### Gdzie mogę uzyskać tymczasową licencję na Aspose.BarCode dla .NET?
Możesz uzyskać tymczasową licencję pod adresem **[ten link](https://purchase.aspose.com/temporary-license/)**.

### Czy Aspose.BarCode obsługuje szeroką gamę typów kodów kreskowych?
Zdecydowanie – obsługuje EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 i wiele innych.

### Czy mogę dostosować wygląd generowanych kodów kreskowych?
Tak, możesz modyfikować kolory, czcionki, marginesy, a nawet dodawać obrazy tła przy użyciu rozbudowanego API `Parameters`.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy EAN-13** z dodatkowymi danymi EAN‑2 lub EAN‑5 oraz **generować pliki PNG kodu kreskowego** przy użyciu Aspose.BarCode dla .NET. To podejście daje pełną kontrolę nad wymiarami kodu, odstępem dodatku i formatem wyjściowym, co czyni je idealnym dla handlu detalicznego, logistyki i wszelkich scenariuszy, w których wymagane są dodatkowe informacje numeryczne.

Aby zgłębić temat, zapoznaj się z pełnym przewodnikiem referencyjnym: **[dokumentacja Aspose.BarCode dla .NET](https://reference.aspose.com/barcode/net/)**.

---

**Ostatnia aktualizacja:** 2026-03-07  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}