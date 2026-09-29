---
category: general
date: 2026-09-29
description: Aspose.BarCode를 사용하여 C#에서 전방위 Databar 바코드를 만드는 방법을 배우세요. X‑디멘션을 조정하고,
  종횡비를 설정하며, PNG 이미지로 저장합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: ko
lastmod: 2026-09-29
og_description: Aspose.BarCode를 사용하여 C#에서 전방위 Databar 바코드를 생성합니다. X‑차원을 설정하고, 종횡비를
  조정하며, PNG 파일로 내보내는 방법을 배워보세요.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: C#에서 전방위 Databar 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C#에서 전방위 Databar 바코드 만드는 방법
url: /ko/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 전방향 Databar 바코드 생성 방법

.NET 애플리케이션에서 **전방향 Databar 바코드**를 생성해야 한다면, 이 가이드는 정확한 단계들을 보여줍니다. DataBar stacked omnidirectional 바코드를 초기화하고, X‑dimension을 설정하고, 종횡비를 변경하며, Aspose.BarCode를 사용해 PNG 이미지를 생성하는 방법을 확인할 수 있습니다.

**DataBar stacked omnidirectional 바코드**를 생성하는 것은 소매 스캐너용 제품 식별자를 인코딩해야 할 때 일반적입니다. 이 튜토리얼에서는 **바코드 종횡비 설정**, 모듈 크기 제어, IDE를 떠나지 않고 결과를 내보내는 방법을 배웁니다.

## Prerequisites

시작하기 전에 다음이 설치되어 있는지 확인하세요:

- .NET 6.0 이상이 설치되어 있어야 합니다
- Visual Studio 2022(또는 C# 호환 IDE)
- **Aspose.BarCode for .NET** NuGet 패키지(버전 23.12 이상)

NuGet 패키지 관리자를 통해 패키지를 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## 1단계: 전방향 Databar 바코드 초기화

첫 번째 단계는 **DataBar stacked omnidirectional** 심볼을 대상으로 하는 `BarcodeGenerator` 인스턴스를 만드는 것입니다. 생성자는 인코드 유형과 데이터 문자열을 받습니다.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**왜 중요한가:** `EncodeTypes.DatabarStackedOmniDirectional` 값은 Aspose.BarCode에게 특정 전방향 Databar 형식을 렌더하도록 지시합니다. 이는 양방향 스캔에 필수적입니다.

## 2단계: X‑dimension(모듈 크기) 정의

X‑dimension은 픽셀 단위로 단일 바코드 모듈의 너비를 제어합니다. `2` 픽셀 값은 화면 렌더링 및 대부분의 프린터에 적합합니다.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**왜 중요한가:** 일관된 X‑dimension은 바코드가 소매 스캐너의 최소 크기 사양을 충족하도록 하면서 이미지 파일 크기를 관리 가능하게 유지합니다.

## 3단계: 첫 번째 종횡비 설정 및 이미지 저장

**종횡비**는 DataBar의 높이‑대‑너비 비율을 결정합니다. `15`의 종횡비는 좁은 라벨 공간에 적합한 높고 좁은 바코드를 생성합니다.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**왜 중요한가:** 종횡비를 조정하면 가독성을 손상시키지 않으면서 다양한 라벨 레이아웃에 바코드를 맞출 수 있습니다. 저장된 PNG는 모든 이미지 뷰어에서 확인할 수 있습니다.

## 4단계: 종횡비 변경 및 두 번째 이미지 생성

라벨에 가로 공간이 더 많을 경우 더 넓은 바코드가 필요할 수 있습니다. 비율을 `30`으로 변경하면 더 평평한 모양이 됩니다.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**왜 중요한가:** **set barcode aspect ratio** 속성을 활용하면 단일 코드 베이스에서 여러 바코드 변형을 생성할 수 있어 자동 라벨 생성 파이프라인을 단순화합니다.

## 예상 출력

프로그램을 실행하면 애플리케이션 출력 폴더에 두 개의 PNG 파일이 생성됩니다:

| 파일 이름                | 종횡비 | 시각적 설명 |
|--------------------------|--------|--------------|
| `DatabarAspectRatio15.png` | 15     | 좁은 라벨에 적합한 높고 좁은 바코드 |
| `DatabarAspectRatio30.png` | 30     | 더 많은 가로 공간을 채우는 넓은 바코드 |

이 이미지는 보고서에 삽입하거나 제품 포장에 인쇄하거나 웹 서비스에 전송하여 추가 처리에 사용할 수 있습니다.

![전방향 Databar 바코드 생성 예시](databar-example.png "전방향 Databar 바코드 생성 예시")

*스크린샷은 두 개의 생성된 PNG 파일을 나란히 보여줍니다.*

## 일반적인 질문 및 엣지 케이스

### 다른 X‑dimension이 필요하면 어떻게 하나요?

`XDimension.Pixels`에 원하는 정수 값을 할당하면 됩니다. `1` 이하의 값은 무시되며, `10` 초과값은 프린터 여백을 초과하는 과도한 모듈을 만들 수 있습니다. 각 변경 후 시각적 출력을 테스트하세요.

### 다른 AI 기반 데이터(예: UPC, EAN)를 인코딩하려면 어떻게 하나요?

`BarcodeGenerator` 생성자에서 데이터 문자열을 해당 Application Identifier(AI)와 함께 교체하면 됩니다. UPC‑A 코드는 AI 접두사 없이 `"012345678905"`를 사용합니다.

### PNG 외의 형식으로 내보낼 수 있나요?

예. `Save` 메서드는 `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, `BarCodeImageFormat.Bmp`를 지원합니다. 워크플로에 맞는 형식을 선택하세요.

## 전문가 팁: 배치 처리에 생성기 재사용

다양한 종횡비로 수십 개의 바코드를 생성해야 할 경우, `BarcodeGenerator` 인스턴스를 유지하고 각 `Save` 전에 `DataBar.AspectRatio`만 수정하면 됩니다. 이렇게 하면 이미지마다 생성기를 다시 인스턴스화하는 오버헤드를 피할 수 있습니다.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## 결론

이제 Aspose.BarCode를 사용해 C#에서 **전방향 Databar 바코드**를 생성하는 방법을 알게 되었습니다. `BarcodeGenerator`를 초기화하고, X‑dimension을 설정하고, **set barcode aspect ratio**를 조정한 뒤 PNG 파일을 저장하면 다양한 라벨 요구 사항을 충족하는 바코드 이미지를 만들 수 있습니다.

다음으로 QR 코드용 **generate barcode image**, **DataBar stacked omnidirectional barcode** 검증, 또는 Aspose.PDF와 함께 생성된 PNG를 PDF 청구서에 통합하는 등 관련 주제를 탐색해 보세요. 다양한 종횡비와 모듈 크기를 실험하여 특정 프린팅 하드웨어에 최적의 구성을 찾으세요.

---

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접하게 관련된 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하여 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 대체 구현 방식을 탐색하도록 돕습니다.

- [C# 바코드 생성기를 사용해 DataBar 전방향 바코드 생성 방법](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [C#에서 databar stacked omnidirectional 바코드 – 완전 가이드](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [C#에서 바코드 생성 방법 – DataBar Expanded로 바코드 이미지 생성](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}