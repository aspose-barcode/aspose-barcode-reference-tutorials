---
category: general
date: 2026-08-03
description: C#에서 바코드 PNG를 생성하고 DataBar 이미지의 종횡비를 변경하는 방법을 배워보세요. 코드와 팁이 포함된 전체 예제를
  따라해 보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: ko
lastmod: 2026-08-03
og_description: C#에서 바코드 PNG를 생성하고 DataBar 바코드의 종횡비를 변경하는 방법을 확인하세요. 이 가이드는 바로 실행할
  수 있는 코드와 실용적인 팁을 제공합니다.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: C#에서 바코드 PNG 만들기 – 종횡비 제어가 포함된 전체 예제
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: C#에서 바코드 PNG 만들기 – 단계별 가이드
url: /ko/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 바코드 PNG 만들기 – 단계별 가이드

C#에서 **바코드 PNG**를 만들어야 한다면, 이 튜토리얼이 정확히 방법을 보여줍니다. 스택형 전방향 DataBar 바코드를 생성하고 PNG 파일로 저장하며, 다양한 스캔 환경에 맞게 **종횡비를 변경하는 방법**을 배웁니다.

이 가이드는 필요한 패키지, 완전한 실행 가능한 프로그램, 각 설정이 중요한 이유에 대한 설명을 모두 포함합니다. 끝까지 따라오면 종횡비가 15인 PNG 파일 하나와 30인 PNG 파일 하나, 총 두 개의 파일을 테스트 또는 프로덕션에 바로 사용할 수 있게 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있어야 합니다:

- .NET 6.0 SDK 또는 그 이후 버전이 설치되어 있어야 합니다
- Visual Studio 2022 (또는 기타 C# IDE)
- **Aspose.BarCode**에 대한 NuGet 참조 (`BarcodeGenerator`를 제공하는 라이브러리)
- PNG 파일이 저장될 디렉터리에 대한 쓰기 권한

다음 명령으로 Aspose.BarCode 패키지를 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## 단계 1: 프로젝트 설정 및 네임스페이스 가져오기

새 콘솔 애플리케이션을 만들고 바코드 생성 및 파일 I/O에 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Why this matters:** `Aspose.BarCode.Generation`을 가져오면 `BarcodeGenerator`에 접근할 수 있습니다. 코드를 `Main` 내부에 두면 예제가 독립적이고 실행하기 쉬워집니다.

## 단계 2: 스택형 전방향 DataBar용 바코드 생성기 만들기

`EncodeTypes.DatabarStackedOmniDirectional` 타입과 샘플 GS1‑128 데이터 문자열을 사용해 `BarcodeGenerator`를 인스턴스화합니다.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Why this matters:** 선택한 인코드 타입은 대부분의 최신 스캐너가 읽을 수 있는 고밀도 DataBar를 생성합니다. 데이터 문자열은 제품 식별에 일반적인 GS1 애플리케이션 식별자 (01) 형식을 따릅니다.

## 단계 3: 픽셀 단위 X‑dimension(모듈 폭) 정의하기

모듈 폭을 설정해 바코드 전체 크기를 조절하지만 가독성에는 영향을 주지 않도록 합니다.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** X‑dimension을 2 픽셀로 설정하면 스캐너에 너무 작지도, 라벨 공간에 너무 크지도 않은 바코드가 됩니다.

## 단계 4: 종횡비 15인 첫 번째 PNG 저장하기

DataBar 종횡비를 조정한 뒤 이미지를 PNG 파일로 저장합니다.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Why this matters:** 종횡비는 스택형 DataBar의 높이‑너비 비율을 제어합니다. 비율 15는 가독성과 라벨 높이 사이의 균형을 맞추는 일반적인 기본값입니다.

## 단계 5: 종횡비를 30으로 변경하고 두 번째 PNG 저장하기

같은 생성기 인스턴스를 수정해 더 큰 종횡비를 사용하고 두 번째 이미지를 저장합니다.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Why this matters:** 종횡비를 높이면 바코드가 수직으로 늘어나 저해상도 장치나 좁은 매체에 인쇄된 라벨에서 스캔 신뢰성을 높일 수 있습니다.

## 예상 출력

프로그램을 실행하면 두 개의 PNG 파일이 생성됩니다:

| 파일                               | 종횡비 | 대략적인 크기 (픽셀) |
|------------------------------------|-------|----------------------|
| `DatabarAspectRatio15.png`         | 15    | 200 × 300 (width × height) |
| `DatabarAspectRatio30.png`         | 30    | 200 × 600 (width × height) |

두 이미지 모두 GS1 식별자 `(01)12345678901231`을 인코딩한 명확하고 스캔 가능한 DataBar 바코드를 포함합니다.

## 일반적인 질문 및 엣지 케이스

### 다른 시각적 속성을 어떻게 변경하나요?

`generator.Parameters.Barcode` 객체를 통해 전경색, 배경색 또는 인간이 읽을 수 있는 텍스트를 조정할 수 있습니다. 예시:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### 다른 이미지 형식이 필요하면 어떻게 하나요?

필요에 따라 `BarCodeImageFormat.Png`를 `Jpeg`, `Bmp`, `Gif` 등으로 교체하면 됩니다. PNG는 무손실 바코드 이미지에 가장 적합한 선택입니다.

### 종횡비가 스캔 속도에 영향을 미치나요?

높은 종횡비는 바코드 높이를 증가시켜 짧은 스택형 심볼을 읽기 어려워하는 장치에서 스캔 신뢰성을 높일 수 있습니다. 하지만 지나치게 높은 바코드는 작은 라벨에 들어가지 않을 수 있으니 목표 하드웨어에서 테스트하세요.

### 루프에서 여러 바코드를 생성할 수 있나요?

예. 각 데이터 문자열마다 새 `BarcodeGenerator` 인스턴스를 만들거나, 동일 인스턴스를 재사용하면서 `CodeText`와 `DataBar.AspectRatio`만 업데이트하면 됩니다. 이렇게 하면 객체 할당 오버헤드를 줄일 수 있습니다.

## 전문가 팁

- **생성기 재사용**: `CodeText` 또는 `AspectRatio`만 변경하면 객체를 다시 인스턴스화할 필요가 없어 배치 처리 속도가 빨라집니다.
- **출력 검증**: 핸드헬드 스캐너나 모바일 앱을 사용해 생성된 PNG가 올바르게 읽히는지 확인한 뒤 프로덕션에 배포하세요.
- **파일 명명**: 파일 이름에 종횡비를 포함시키면(예시와 같이) 테스트 중 다양한 변형을 쉽게 추적할 수 있습니다.

## 결론

이제 C#에서 **바코드 PNG** 파일을 만드는 방법과 스택형 전방향 DataBar 심볼의 **종횡비를 정확히 변경하는 방법**을 알게 되었습니다. 전체 예제는 초기화, X‑dimension 설정, 종횡비 조정, 이미지 저장을 모두 하나의 실행 가능한 프로그램으로 보여줍니다.

앞으로 추가 바코드 유형을 탐색하거나 색상을 실험하고, 생성기를 더 큰 보고서나 재고 시스템에 통합할 수 있습니다. 즐거운 코딩 되세요!

## 다음에 배워야 할 내용

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용할 수 있도록 돕습니다.

- [바코드 PNG 만들기 – DataMatrix 종횡비 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [.NET용 Aspose.BarCode를 사용하여 사용자 정의 종횡비로 Aztec 바코드 생성 방법](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [.NET용 Aspose.BarCode로 Codablock F 종횡비 맞춤 설정 방법](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}