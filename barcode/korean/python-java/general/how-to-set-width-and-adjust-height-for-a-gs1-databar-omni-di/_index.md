---
category: general
date: 2026-09-29
description: C#를 사용하여 GS1 DataBar Omni‑Directional 바코드의 너비를 설정하고 높이를 변경하는 방법. 전체 코드를
  포함한 단계별 가이드를 따라 보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: ko
lastmod: 2026-09-29
og_description: C#에서 GS1 DataBar Omni‑Directional 바코드의 너비를 설정하고 높이를 변경하는 방법. 정확한 API
  호출을 배우고 완전한 실행 가능한 예제를 확인하세요.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: GS1 DataBar 바코드의 너비 설정 방법 – C# 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: C#에서 GS1 DataBar Omni‑Directional 바코드의 너비 설정 및 높이 조정 방법
url: /ko/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 GS1 DataBar Omni‑Directional 바코드의 너비 설정 및 높이 조정 방법

GS1 DataBar Omni‑Directional 바코드의 너비를 설정하는 것은 스캔 장비에 정확한 크기가 필요할 때 자주 수행하는 작업입니다. 이 튜토리얼에서는 **높이 변경 방법**도 배워 바코드가 레이아웃에 완벽히 맞도록 할 수 있습니다. 이 가이드는 프로젝트 설정부터 완전하게 실행 가능한 코드 샘플까지 전체 과정을 단계별로 안내합니다.

다룰 내용:

* 필요한 NuGet 패키지와 .NET 버전
* 바코드 가독성에 중요한 X‑dimension(모듈 너비) 설명
* **너비 설정 방법**과 **높이 변경 방법**에 대한 정확한 API 호출
* 최소 모듈 너비 및 고해상도 렌더링과 같은 엣지 케이스 처리
* 서로 다른 바 높이를 가진 두 개의 PNG 파일을 생성하는 전체 복사‑붙여넣기 예제

## Prerequisites

시작하기 전에 다음을 준비하세요:

| 요구 사항 | 이유 |
|------------|--------|
| .NET 6.0 SDK 이상 | 예제는 최신 C# 기능을 사용하며 Windows, Linux, macOS에서 실행됩니다. |
| Visual Studio 2022(또는 다른 C# IDE) | Aspose.Barcode API에 대한 IntelliSense를 제공합니다. |
| **Aspose.Barcode for .NET** NuGet 패키지 | `BarcodeGenerator`, `EncodeTypes`, 이미지 포맷 지원을 포함합니다. `dotnet add package Aspose.Barcode` 로 설치합니다. |
| PNG 파일이 저장될 폴더에 대한 쓰기 권한 | 생성기가 출력 이미지를 디스크에 기록합니다. |

## How to set width of the barcode

**너비 설정** 단계는 바코드 매개변수의 `XDimension` 속성을 구성하여 수행합니다. `XDimension`은 모듈 너비(가장 작은 바 또는 공백)를 픽셀, 포인트 또는 밀리미터 단위로 나타냅니다. 올바르게 설정하면 바코드가 스캐너 사양을 만족합니다.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Why the X‑dimension matters

* **스캐너 허용 오차** – 대부분의 스캐너는 최소 모듈 너비를 요구합니다; 값이 너무 작으면 판독 오류가 발생할 수 있습니다.
* **인쇄 해상도** – 300 dpi에서 2 px 모듈은 약 0.17 mm에 해당하며, GS1 DataBar에 권장되는 범위 내에 있습니다.
* **이미지 크기** – X‑dimension 값이 클수록 전체 바코드 너비가 증가해 레이아웃 제약에 영향을 줄 수 있습니다.

### Tips for reliable width settings

* **XDimension을 1 px 이하로 설정하지 마세요** – 라이브러리가 값을 강제하지만, 결과 바코드가 읽히지 않을 수 있습니다.
* **대상 DPI에 맞추세요** – 고해상도 포맷(예: 600 dpi TIFF)으로 렌더링할 경우 XDimension을 비례적으로 늘립니다.
* **실제 스캐너로 테스트하세요** – 너비를 변경한 후 바코드를 실제 읽을 장치에서 검증합니다.

## How to change height of the barcode

너비가 정의되면 `BarHeight` 속성을 사용해 수직 크기를 제어할 수 있습니다. 다음 코드는 **높이 변경 방법**을 30 px에서 60 px로 바꾸고 두 개의 별도 이미지를 저장하는 예시를 보여줍니다.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Understanding bar height

* **시각적 균형** – 높은 바는 저대비 배경에서 가독성을 높이지만 이미지의 세로 공간을 늘립니다.
* **규제 제한** – 일부 표준(예: 소매 라벨링)에서는 최대 바 높이를 지정하므로 그에 맞게 조정합니다.
* **종횡비** – 높이를 변경해도 모듈 너비에는 영향을 주지 않으며, 두 값을 독립적으로 미세 조정할 수 있습니다.

### Edge‑case handling for height adjustments

| 상황 | 권장 접근법 |
|-----------|----------------------|
| Height < 10 px | 10 px 이상으로 늘리세요; 매우 짧은 바는 스캐너에서 무시될 수 있습니다. |
| Very tall bars (≥ 100 px) | 출력 매체(종이, 라벨)가 추가 공간을 수용할 수 있는지 확인하세요. |
| Need proportional scaling | `BarHeight = XDimension * desiredRatio` 로 계산하여 시각적 일관성을 유지하세요. |

## Full, runnable example

아래는 **너비 설정**과 **높이 변경** 단계를 결합한 전체 프로그램입니다. 코드를 새 콘솔 프로젝트에 복사하고 Aspose.Barcode NuGet 패키지를 복원한 뒤 실행하세요. 두 개의 PNG 파일이 `bin/Debug/net6.0` 폴더에 생성됩니다.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Expected output**

프로그램을 실행하면 두 개의 PNG 파일이 생성됩니다:

* `DatabarBarHeight30Pixels.png` – 30 px 높이에 2 px 너비 모듈을 가진 바코드.
* `DatabarBarHeight60Pixels.png` – 수직 크기가 두 배가 된 동일 바코드.

어느 이미지든 뷰어로 열면 깨끗한 GS1 DataBar Omni‑Directional 심볼이 스캔 준비된 모습을 확인할 수 있습니다.

## Common questions answered

| 질문 | 답변 |
|----------|--------|
| *픽셀 대신 밀리미터를 사용할 수 있나요?* | Yes. `generator.Parameters.Barcode.XDimension.Millimeters` 와 `BarHeight.Millimeters` 를 설정하면 됩니다. 라이브러리는 이미지 DPI에 따라 장치 픽셀로 변환합니다. |
| *다른 바코드 유형이 필요하면 어떻게 하나요?* | `EncodeTypes.DatabarOmniDirectional` 를 원하는 다른 `EncodeTypes` 값(예: `EncodeTypes.QR`) 으로 교체하면 됩니다. 너비와 높이 속성은 동일하게 동작합니다. |
| *PNG 대신 SVG를 생성할 방법이 있나요?* | `Save` 호출에서 `BarCodeImageFormat.Svg` 를 사용하세요. 너비/높이 설정은 그대로 적용됩니다. |
| *`generator.Dispose()`를 호출해야 하나요?* | `BarcodeGenerator` 는 `IDisposable` 을 구현합니다. 콘솔 앱에서는 `using` 블록으로 감싸면 되지만, 짧은 예제에서는 선택 사항입니다. |

## Conclusion

이제 C#에서 Aspose.Barcode API를 사용해 **GS1 DataBar Omni‑Directional 바코드의 너비 설정**과 **높이 변경** 방법을 알게 되었습니다. 전체 예제는 생성기 생성, `XDimension` 및 `BarHeight` 구성, 그리고 서로 다른 세로 크기의 PNG 파일 저장 과정을 보여줍니다.

다음과 같이 활용해 보세요:

* 다른 `EncodeTypes`(예: QR, Code128) 실험
* 인쇄용 TIFF와 같은 고해상도 포맷으로 렌더링
* 웹 API에 통합해 실시간으로 바코드 반환

즐거운 코딩 되시고, 바코드가 항상 깨끗하게 스캔되길 바랍니다!

## What Should You Learn Next?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움을 줍니다.

- [C#에서 바코드 높이 변경 방법 – 완전 가이드](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [C# 바코드 생성기 예제 – 너비 및 높이 설정](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [C# 바코드 생성기를 사용하여 DataBar Omni‑directional 바코드 생성하는 방법](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}