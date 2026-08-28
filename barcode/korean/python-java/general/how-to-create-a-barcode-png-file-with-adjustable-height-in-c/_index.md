---
category: general
date: 2026-08-19
description: C#에서 바코드 PNG 파일을 생성하고 높이를 조정하는 방법을 배우세요. 바코드 이미지를 생성하고 바코드 높이를 쉽게 변경하는
  방법을 다룹니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: ko
lastmod: 2026-08-19
og_description: C#에서 바코드 PNG 파일을 만들고 바코드 이미지를 생성하는 방법, 바코드 높이를 조정하는 방법, 최적의 스캔을 위한
  바코드 높이 변경 방법을 배워보세요.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: C#에서 바코드 PNG 파일 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: C#에서 높이를 조절할 수 있는 바코드 PNG 파일 만드는 방법
url: /ko/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 높이 조절이 가능한 바코드 PNG 파일 만들기

C#에서 **바코드 PNG 파일**을 생성해야 할 때, 이 가이드는 정확한 방법을 보여줍니다. 바코드 이미지를 **생성하는 방법**과 다양한 사용 사례에 맞게 **바코드 높이를 조절하는 방법**을 포함한 완전한 실행 예제를 확인할 수 있습니다.

바코드 PNG 파일 생성은 재고 시스템, POS 단말기 및 기계 판독 데이터가 필요하거나 표시되는 모든 애플리케이션에서 일반적인 요구 사항입니다. 이 튜토리얼을 마치면 바코드 높이를 변경하고, 여러 PNG 파일을 저장하며, 높이가 스캔 신뢰성에 미치는 영향을 이해할 수 있게 됩니다.

## Prerequisites

시작하기 전에 다음이 설치되어 있는지 확인하세요.

* .NET 6.0 SDK 이상  
* Visual Studio 2022 (또는 .NET을 지원하는 IDE)  
* **Aspose.BarCode for .NET** NuGet 패키지 (코드 샘플이 이 라이브러리를 사용합니다)  

패키지는 명령줄에서 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Aspose.BarCode의 무료 평가판은 개발 및 테스트에 사용할 수 있습니다. 상용 환경에서는 정식 라이선스 키를 구입하세요.

## Install the barcode library

첫 번째 단계는 프로젝트에 라이브러리를 참조하는 것입니다. C# 파일 상단에 다음 `using` 지시문을 추가합니다:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

이 네임스페이스를 통해 `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`에 접근할 수 있습니다.

## Create the barcode PNG file

이제 **바코드 PNG 파일**을 출력할 `BarcodeGenerator` 인스턴스를 생성합니다. 예제는 Databar OmniDirectional 심볼을 사용하지만, `EncodeTypes.DatabarOmniDirectional`을 지원되는 다른 타입으로 교체할 수 있습니다.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

문자열 `"(01)12345678901231"`은 14자리 GTIN에 대한 GS1 애플리케이션 식별자 형식입니다. 자신의 제품 식별자에 맞게 데이터를 조정하세요.

## Set the X‑dimension (optional)

X‑dimension은 단일 바코드 모듈의 너비를 정의합니다. 픽셀 기반 값을 사용하면 이미지 크기를 정밀하게 제어할 수 있습니다.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 픽셀 값은 대부분의 화면 표시에서 잘 작동합니다. 인쇄 시 더 큰 바코드가 필요하면 값을 늘리세요.

## Adjust barcode height and save the barcode PNG file

**BarHeight** 속성은 막대의 수직 크기를 제어합니다. 이 값을 변경하면 인코딩된 데이터에 영향을 주지 않고 **바코드 높이를 조절**할 수 있습니다.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

파일 `DatabarBarHeight30Pixels.png`는 이제 높이가 30 픽셀인 **바코드 PNG 파일**이 됩니다.  

**바코드 높이를 변경**하고 두 번째 이미지를 만들려면 새 값을 할당하고 다시 `Save`를 호출하면 됩니다:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

이제 30 px와 60 px 높이의 두 PNG 파일이 생성되어 **바코드 높이 조절**을 실시간으로 시연합니다.

### Why bar height matters

* **Readability:** 스캐너는 신뢰할 수 있는 판독을 위해 최소 높이를 기대합니다. 높이가 너무 짧으면 특히 저해상도 카메라에서 인식되지 않을 수 있습니다.  
* **Aesthetics:** 바코드 높이를 주변 디자인 요소와 맞추면 UI가 깔끔해집니다.  
* **Print constraints:** 일부 라벨 프린터는 고정된 높이 슬롯을 가지고 있어, 바코드 높이를 조절해야 맞출 수 있습니다.

**Best practice:** X‑dimension의 배수(예: X‑dimension이 2 px일 때 30 px)로 높이를 유지하면 비율이 유지되고 왜곡을 방지할 수 있습니다.

## Complete example

아래는 콘솔 애플리케이션에 바로 붙여넣어 실행할 수 있는 전체 독립 프로그램입니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Expected output**

프로그램을 실행하면 실행 파일 작업 디렉터리에 두 파일이 생성됩니다.

* `DatabarBarHeight30Pixels.png` – 높이 30 픽셀인 바코드 PNG 파일  
* `DatabarBarHeight60Pixels.png` – 높이 60 픽셀인 바코드 PNG 파일  

이미지 뷰어로 열면 스캔 준비가 된 선명한 Databar OmniDirectional 바코드를 확인할 수 있습니다.

## Edge cases and troubleshooting

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| 바코드가 흐릿하게 보임 | 선택한 높이에 비해 X‑dimension이 너무 낮음 | `XDimension.Pixels` 값을 늘리세요 (예: 2 → 3) |
| 스캐너가 낮은 높이 바코드를 인식 못 함 | 높이가 스캐너 최소 요구치 이하 | `BarHeight.Pixels`를 최소 30 px(또는 스캐너 사양)로 설정 |
| PNG 파일이 비어 있거나 손상됨 | 출력 경로가 잘못되었거나 쓰기 권한이 없음 | 절대 경로를 사용하거나 앱에 쓰기 권한을 부여 |
| 다른 심볼로 교체 필요 | 현재 `EncodeTypes`가 목적에 맞지 않음 | `EncodeTypes.DatabarOmniDirectional`을 다른 열거값(예: `EncodeTypes.Code128`)으로 교체 |

## Frequently asked questions

**Q: 다른 이미지 포맷(JPEG, BMP)도 생성할 수 있나요?**  
A: 네. `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` 등으로 교체하면 됩니다.

**Q: PNG를 웹 페이지에 삽입하려면 어떻게 하나요?**  
A: 생성된 PNG를 HTTP 엔드포인트를 통해 제공하거나 Base64 문자열로 변환해 `<img>` 태그의 `src` 속성에 넣으면 됩니다.

**Q: 배경색을 설정할 수 있나요?**  
A: `generator.Parameters.Image.BackgroundColor = Color.White;` (또는 원하는 `System.Drawing.Color`)를 사용하세요.

## Conclusion

이제 C#에서 **바코드 PNG 파일을 생성**하고 스캔 또는 디자인 요구 사항에 맞게 **바코드 높이를 정확히 조절**하는 방법을 알게 되었습니다. `BarHeight.Pixels` 속성을 변경하면 **바코드 높이를 실시간으로 바꾸고** 단일 코드 베이스에서 여러 PNG 자산을 만들 수 있습니다.

다음 단계로 전경색, 여백, 인간이 읽을 수 있는 텍스트 추가와 같은 다른 커스터마이징 옵션을 살펴보세요. 또한 다양한 심볼(`EncodeTypes.Code128`, `EncodeTypes.QR`)을 실험해 인코딩 가능한 데이터 범위를 넓혀 보시기 바랍니다.

행복한 코딩 되세요, 그리고 바코드가 항상 첫 번째 시도에 스캔되길 바랍니다!

## What Should You Learn Next?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하여 밀접하게 연관된 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}