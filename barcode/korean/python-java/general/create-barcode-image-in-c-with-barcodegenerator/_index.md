---
category: general
date: 2026-08-12
description: BarCodeGenerator를 사용하여 C#에서 바코드 이미지를 생성합니다. DataBar를 생성하는 방법, 바코드 이미지
  크기를 제어하는 방법, 그리고 여러 바코드를 효율적으로 만드는 방법을 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: ko
lastmod: 2026-08-12
og_description: BarCodeGenerator를 사용하여 C#에서 바코드 이미지를 생성합니다. 이 튜토리얼에서는 DataBar 코드를
  생성하고, 바코드 이미지 크기를 조정하며, 여러 개의 바코드를 만드는 방법을 단계별로 보여줍니다.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: C#에서 바코드 이미지 만들기 – 완전한 BarCodeGenerator 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: BarCodeGenerator를 사용해 C#에서 바코드 이미지 만들기
url: /ko/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 BarCodeGenerator를 사용하여 바코드 이미지 만들기

.NET 애플리케이션에서 **바코드 이미지 생성**이 필요하다면, 이 가이드는 `BarCodeGenerator` 클래스를 사용하여 정확히 수행하는 방법을 보여줍니다. 소매 POS 시스템이나 재고 추적 도구를 구축하든, DataBar 심볼을 생성하고, 바코드 이미지 크기를 제어하며, 한 번에 여러 바코드를 생성하는 방법을 배울 수 있습니다.

또한 **barcode generator c#** API를 사용해 차원 조정, 출력 형식 전환, 잘못된 데이터 문자열과 같은 예외 상황을 처리하는 방법을 알게 됩니다. 튜토리얼이 끝날 때쯤에는 반복 코드를 작성하지 않고도 자신 있게 **여러 바코드 생성**을 할 수 있습니다.

## 사전 요구 사항

- .NET 6.0 이상이 설치되어 있어야 합니다
- 개발 환경 (Visual Studio, Rider, 또는 VS Code)
- Aspose.BarCode for .NET NuGet 패키지(또는 `BarCodeGenerator`를 제공하는 호환 라이브러리)

You can add the package with:

```bash
dotnet add package Aspose.BarCode
```

## 이 튜토리얼에서 다루는 내용

1. DataBar Omni‑directional 인코딩을 위한 **barcode generator c#** 인스턴스 설정.
2. X‑dimension 및 bar height를 변경하여 **barcode image size** 조정.
3. 루프를 사용해 서로 다른 높이의 **multiple barcodes** 생성.
4. 이미지를 PNG 파일로 저장하고 출력 결과를 검증.

모든 코드 스니펫은 완전하며 새 콘솔 프로젝트에 복사‑붙여넣기 할 준비가 되어 있습니다.

![바코드 이미지 생성 예시](barcode-example.png){alt="바코드 이미지 생성 예시"}

## 1단계: 생성기 초기화 – 바코드 이미지 기본 설정

첫 번째 단계는 원하는 심볼을 사용하여 `BarCodeGenerator`를 인스턴스화하는 것입니다. DataBar Omni‑directional 심볼의 경우 `EncodeTypes.DatabarOmniDirectional`를 사용합니다.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**왜 중요한가:** 생성기를 인스턴스화하면 인코딩 규칙과 데이터 페이로드가 정의됩니다. 올바른 `EncodeTypes` 값을 생략하면 라이브러리가 지원되지 않는 바코드를 생성하거나 예외를 발생시킵니다.

## 2단계: X‑dimension 및 bar height 구성 – 바코드 이미지 크기 제어

바코드의 시각적 크기는 두 가지 매개변수에 의해 결정됩니다:

| 매개변수 | 제어하는 내용 | 일반 범위 |
|-----------|------------------|---------------|
| `x_dimension.pixels` | 가장 작은 모듈(‘점’)의 너비 | 1 – 4 px |
| `bar_height.pixels`  | 수직 바의 높이 | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**팁:** X‑dimension이 작을수록 고해상도 이미지가 되지만 저품질 프린터에서는 스캔이 어려울 수 있습니다. 목표 스캔 장비에 따라 값을 조정하세요.

## 3단계: 첫 번째 바코드 저장 – 30 px 높이의 바코드 이미지 생성

이제 이미지를 생성하고 디스크에 저장할 수 있습니다. `Save` 메서드는 파일 경로와 이미지 형식 열거형을 받습니다.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**예상 결과:** `C:\Barcodes`에 `Databar30.png`라는 PNG 파일이 생성됩니다. 파일을 열면 선명하고 고대비 패턴의 DataBar Omni‑directional 심볼이 표시됩니다.

## 4단계: 높이 변경 및 추가 이미지 생성 – 여러 바코드 만들기

다른 차원의 **multiple barcodes**를 만들려면 `BarHeight` 속성을 수정하고 `Save`를 다시 호출하기만 하면 됩니다. 이렇게 하면 생성기를 다시 인스턴스화할 필요가 없어 메모리와 CPU 시간을 절약할 수 있습니다.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**왜 작동하는가:** `BarCodeGenerator` 객체는 모든 구성 상태를 보유합니다. 단일 속성을 변경하면 다음 `Save` 호출을 위한 렌더링 엔진이 업데이트되어 **multiple barcodes**를 효율적으로 생성할 수 있습니다.

## 5단계: 고급 – 사용자 정의 데이터로 DataBar 생성 방법

위 예제는 정적 GS1 페이로드를 사용합니다. 실제 상황에서는 가변적인 제품 식별자를 삽입해야 할 경우가 많습니다. 라이브러리는 DataBar 사양에 맞는 문자열이면 어떤 것이든 허용합니다.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**핵심 포인트:** `generator.CodeText`를 설정하면 객체를 다시 생성하지 않고도 인코딩된 데이터가 업데이트됩니다. 대량 데이터 세트를 처리할 때 권장되는 **how to generate databar** 패턴입니다.

## 6단계: 검증 및 문제 해결 – 올바른 바코드 이미지 크기 보장

이미지를 생성한 후, 차원이 기대와 일치하는지 프로그램matically 확인하고 싶을 수 있습니다. `System.Drawing`의 `Image` 클래스를 사용하면 파일을 읽고 크기를 보고할 수 있습니다.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

If the height does not reflect the value you set, check:

- **X‑dimension**: 매우 작은 값은 렌더러가 높이를 반올림하게 만들 수 있습니다.
- **Image format**: 일부 형식(예: JPEG)은 저장 시 압축을 적용하여 픽셀 차원을 변경할 수 있습니다. PNG는 정확한 차원을 유지합니다.

## 7단계: 바코드 이미지 크기 및 성능을 위한 모범 사례

| 권장 사항 | 이유 |
|----------------|--------|
| 대부분의 스캐너에 대해 `x_dimension.pixels`를 2 – 3 px 사이로 유지합니다. | 가독성과 파일 크기의 균형을 맞춥니다. |
| 이미지를 인쇄할 경우 무손실 출력을 위해 PNG를 사용합니다. | 정확한 차원과 선명한 가장자리를 보장합니다. |
| 다수의 바코드를 생성할 때 단일 `BarCodeGenerator` 인스턴스를 재사용합니다. | 객체 할당 오버헤드를 감소시킵니다. |
| `CodeText`에 할당하기 전에 입력 문자열을 GS1 표준에 맞게 검증합니다. | 런타임 예외와 잘못된 스캔을 방지합니다. |
| 생성된 이미지를 전용 폴더에 명확한 명명 규칙(예: `Databar_{GTIN}.png`)으로 저장합니다. | 후속 처리와 감사 추적을 단순화합니다. |

## 전체 작동 예제

아래는 초기화부터 검증까지 모든 단계를 포함한 완전한 프로그램입니다. 코드를 새 콘솔 프로젝트에 복사하고 실행하세요.



## 다음에 배워야 할 내용

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 작동 코드 예제를 제공하여 추가 API 기능을 마스터하고 자체 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [바코드 이미지 생성 – GS1 쿠폰 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode 바코드 이미지 생성 – 행 및 열 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Aspose.BarCode for .NET을 사용하여 ITF-14 바코드 Quiet Zone 생성 방법](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}