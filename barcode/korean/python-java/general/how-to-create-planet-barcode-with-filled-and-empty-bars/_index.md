---
category: general
date: 2026-09-29
description: C#에서 채워진 바와 비어 있는 바가 모두 포함된 플래닛 바코드 만들기 – Aspose.Barcode를 사용한 단계별 가이드
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: ko
lastmod: 2026-09-29
og_description: C#에서 빠르게 플래닛 바코드를 생성하세요. 채워진 바를 렌더링하고, 빈 바로 전환하며, Aspose.Barcode로
  X‑차원을 조정하는 방법을 배워보세요.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: 채워진 바와 빈 바를 이용한 행성 바코드 만들기 – C# 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 채워진 바와 빈 바가 있는 행성 바코드 만드는 방법
url: /ko/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 채워진 바와 빈 바가 있는 플래닛 바코드 생성 방법

C#에서 **플래닛 바코드** 이미지를 생성해야 할 경우, 이 가이드는 채워진 바와 빈 바 버전을 모두 만드는 방법을 정확히 보여줍니다. 바 너비(X‑Dimension)를 설정하고, `FilledBars` 속성을 토글하며, Aspose.Barcode 라이브러리를 사용해 PNG 파일로 저장하는 과정을 확인할 수 있습니다.

우편 바코드 생성은 배송 시스템, 메일링 리스트 애플리케이션, 물류 대시보드에서 흔히 요구되는 기능입니다. 이 튜토리얼을 마치면 보고서, 이메일 또는 인쇄물에 삽입할 수 있는 두 개의 PNG 파일을 바로 사용할 수 있게 됩니다.

## 사전 요구 사항

시작하기 전에 다음을 준비하세요:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 이상 | C# 예제 실행을 위한 런타임을 제공합니다. |
| Visual Studio 2022(또는 기타 C# IDE) | 코드를 컴파일하고 실행할 수 있게 해줍니다. |
| **Aspose.Barcode for .NET** NuGet 패키지 | `BarcodeGenerator` 클래스와 `EncodeTypes.Planet`을 제공합니다. `dotnet add package Aspose.Barcode` 명령으로 설치합니다. |
| 디스크에 폴더에 대한 쓰기 권한 | `Save` 메서드가 지정한 경로에 PNG 파일을 기록합니다. |

## 1단계: 프로젝트 설정 및 네임스페이스 가져오기

새 콘솔 프로젝트를 만들거나 기존 프로젝트에 코드를 추가하고 Aspose.Barcode 네임스페이스를 참조합니다.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

위 `using` 지시문을 통해 튜토리얼에 필요한 `BarcodeGenerator`, `EncodeTypes`, 이미지 포맷 열거형에 접근할 수 있습니다.

## 2단계: 기본(채워진) 바를 사용해 플래닛 바코드 만들기

첫 번째 바코드는 라이브러리의 기본 렌더링을 사용하며, 바가 채워진 형태로 생성됩니다.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**동작 원리:**  
`EncodeTypes.Planet`은 Aspose.Barcode에 미국 우편 서비스에서 사용하는 **Planet** 심볼을 사용하도록 지시합니다. `XDimension` 속성은 각 바의 너비를 제어하며, 4 픽셀로 설정하면 일반 라벨 프린터에서 인쇄 품질이 좋습니다. 기본값으로 `FilledBars`가 `true`이므로 바가 실선으로 표시됩니다.

## 3단계: 빈 바를 사용해 플래닛 바코드 만들기

같은 데이터를 *빈* 바 형태로 생성하려면 `FilledBars` 플래그만 반전시키고 다른 설정은 그대로 유지하면 됩니다.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**중요 이유:**  
일부 메일링 시스템은 어두운 배경에 인쇄하거나 대비 색상 스키마를 사용할 때 가독성을 높이기 위해 **빈‑바** 스타일을 요구합니다. `FilledBars = false`로 설정하면 바의 외곽선만 그려지고 내부는 투명하게 남아 배경이 보이게 됩니다.

## 예상 출력

프로그램을 실행하면 `C:\Barcodes`(또는 지정한 경로) 폴더에 두 개의 PNG 파일이 생성됩니다:

| File | Visual description |
|------|---------------------|
| `PlanetFilledBars.png` | 흰 배경에 검은색 실선 사각형 바가 표시됩니다. |
| `PlanetEmptyBars.png`  | 검은색 외곽선만 표시되고 각 바 내부는 투명(배경이 보임)합니다. |

두 이미지 모두 동일한 숫자 문자열 `"123456"`을 인코딩하고, 바 너비 4 픽셀을 공유하므로 채우기 스타일을 제외하고는 동일하게 보입니다.

## 일반적인 변형 및 예외 상황

### 바 너비 변경하기

라벨 프린터가 다른 바 너비를 요구한다면 `XDimension.Pixels` 값을 조정하세요. 고해상도 프린터에서는 **2** 또는 **3** 픽셀이, 저해상도 프린터에서는 **5** 또는 **6** 픽셀이 스캔 신뢰성을 높일 수 있습니다.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### 다른 이미지 포맷 사용하기

Aspose.Barcode은 PNG, JPEG, BMP, GIF, TIFF를 지원합니다. `BarCodeImageFormat.Png`를 다른 열거형 값으로 교체해 워크플로에 맞게 선택하세요.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### 루프에서 여러 바코드 생성하기

메일링 리스트 등에서 다수의 플래닛 바코드가 필요할 경우, 생성 로직을 `foreach` 루프로 감싸고 각 반복마다 데이터 문자열을 변경하면 됩니다.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### 잘못된 입력 처리하기

플래닛 심볼은 **5‑8** 자리 숫자 문자열만 허용합니다. 유효하지 않은 값을 전달하면 `ArgumentException`이 발생합니다. 간단한 검증 메서드로 이를 방지하세요.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## 전문가 팁: 스캐너 에뮬레이터로 바코드 검증하기

Aspose.Barcode에는 생성된 이미지가 원본 데이터로 올바르게 디코딩되는지 확인할 수 있는 `BarcodeReader` 클래스가 포함되어 있습니다.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

두 파일 모두 `"123456"`을 출력한다면 바코드가 정상적으로 생성된 것입니다.

## 결론

이제 C#에서 **플래닛 바코드** 이미지를 채워진 바와 빈 바 스타일 모두로 생성하고, **Planet 바코드 XDimension**을 제어하며, **Aspose.Barcode** 라이브러리를 사용해 PNG 형식으로 저장하는 방법을 알게 되었습니다. 바 너비를 조정하거나 이미지 포맷을 바꾸고, 값 컬렉션을 순회하면서 어떤 우편 코드 워크플로에도 적용할 수 있습니다.

다음 단계로 살펴볼 내용:

* 바코드 아래에 **사람이 읽을 수 있는 텍스트** 추가하기(`barcodeGenerator.Parameters.Caption.Show = true`).
* Aspose.PDF를 사용해 **PDF 문서에 바코드 삽입**하기.
* **USPS POSTNET** 또는 **Intelligent Mail**과 같은 다른 우편 심볼 생성하기.

파라미터를 자유롭게 실험하고 코드를 배송 또는 메일링 시스템에 통합해 보세요. 즐거운 코딩 되세요!

## 다음에 배워야 할 내용

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하며, 단계별 설명과 완전한 코드 예제를 제공합니다.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}