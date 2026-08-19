---
category: general
date: 2026-08-19
description: C#와 Aspose.BarCode를 사용하여 데이터바 PNG 파일을 생성합니다. 데이터바 이미지를 생성하고, 데이터바 매개변수를
  구성하며, PNG 출력을 저장하는 방법을 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: ko
lastmod: 2026-08-19
og_description: Aspose.BarCode를 사용하여 C#에서 데이터바 PNG 파일을 생성합니다. 이 튜토리얼에서는 데이터바 이미지를
  생성하고, X‑디멘션 및 종횡비와 같은 데이터바 매개변수를 구성하며, 인쇄 또는 웹 사용을 위한 고품질 PNG 파일을 저장하는 방법을 단계별로
  안내합니다.
og_image_alt: create databar PNG example
og_title: C#에서 데이터바 PNG 이미지 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: C#와 Aspose.BarCode를 사용하여 데이터바 PNG 이미지 만드는 방법
url: /ko/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 Aspose.BarCode를 사용하여 databar PNG 이미지 만들기

.NET 애플리케이션에서 **databar PNG** 파일을 생성해야 한다면, 이 가이드가 정확히 방법을 알려줍니다. 스택형 전방향 DataBar 코드를 생성하고, 주요 매개변수를 설정하며, 서로 다른 종횡비를 가진 두 개의 PNG 파일을 저장하는 완전한 실행 가능한 예제를 확인할 수 있습니다.

DataBar 이미지를 생성하는 것은 단일 메서드를 호출하는 것만으로는 충분하지 않습니다. 인쇄 또는 스캔 사양을 충족하기 위해 X‑dimension(모듈 폭) 및 종횡비와 같은 **databar 매개변수**를 **구성**해야 합니다. 이 튜토리얼을 마치면 실제 시나리오에서 안정적으로 작동하는 **databar 그래픽을 생성하는 방법**을 이해하게 됩니다.

## 사전 요구 사항

- .NET 6.0 이상 (코드는 .NET Framework 4.7+에서도 작동합니다)
- Visual Studio 2022 또는 C# 호환 IDE
- **Aspose.BarCode for .NET**에 대한 유효한 라이선스(무료 평가판으로 테스트 가능)
- C# 구문에 대한 기본적인 이해

> **Pro tip:** 아직 라이선스가 없으시다면 Aspose 포털에서 임시 평가 키를 요청할 수 있습니다. API 동작은 동일하며, 워터마크만 변경됩니다.

## Step 1: Install the Aspose.BarCode NuGet package

Visual Studio에서 프로젝트를 열고 솔루션을 마우스 오른쪽 버튼으로 클릭한 뒤 **Manage NuGet Packages**를 선택합니다. `Aspose.BarCode`를 검색하고 최신 안정 버전을 설치합니다.

```bash
dotnet add package Aspose.BarCode
```

이 명령은 `Aspose.BarCode` 어셈블리를 프로젝트에 추가하고 `BarcodeGenerator` 클래스를 사용할 수 있게 합니다.

## Step 2: Initialize the barcode generator for a stacked omnidirectional DataBar

`BarcodeGenerator` 생성자는 두 개의 인수를 받습니다: 바코드 유형과 원시 데이터 문자열. 스택형 전방향 DataBar의 경우 `EncodeTypes.DatabarStackedOmniDirectional`을 사용합니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` 상수는 라이브러리에게 모든 방향에서 읽을 수 있는 바코드를 생성하도록 지시합니다. 이는 소매 진열 라벨에 이상적입니다.

## Step 3: Configure the X‑dimension (module width) in pixels

X‑dimension은 가장 작은 바 요소의 크기를 제어합니다. 픽셀 단위로 설정하면 최종 이미지 크기를 정밀하게 제어할 수 있습니다.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**2 픽셀** 값은 대부분의 라벨 프린터에서 가독성과 압축성 사이의 좋은 균형을 제공합니다. 더 크거나 작은 모듈이 필요하면 이 값을 조정하세요.

## Step 4: Set the first aspect ratio and save the PNG

종횡비는 스택형 DataBar의 높이에 영향을 줍니다. **15**의 종횡비는 비교적 짧은 바코드를 만들고, **30**은 더 높게 만듭니다.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 메서드는 생성된 바코드를 PNG 파일로 저장합니다. PNG는 무손실 포맷이므로 바코드 스캐너에 필요한 선명한 가장자리를 유지합니다.

## Step 5: Change the aspect ratio and save a second PNG

같은 `BarcodeGenerator` 인스턴스를 재사용하여 종횡비만 변경하면 다양한 변형을 쉽게 만들 수 있습니다.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

이제 두 개의 PNG 파일—`DatabarAspectRatio15.png`와 `DatabarAspectRatio30.png`—이 각각 다른 시각적 밀도를 갖게 됩니다.

## Step 6: Verify the output

생성된 PNG 파일을 이미지 뷰어에서 열어보세요. 깨끗하고 고대비인 DataBar 바코드가 표시되어야 합니다. 스마트폰 바코드 스캐너로 이미지를 스캔하면 두 종횡비 모두 원본 GTIN 값 `12345678901231`을 올바르게 디코딩함을 확인할 수 있습니다.

![databar PNG 예제 만들기](databar_example.png)

*위 이미지는 두 PNG 파일을 나란히 보여줍니다. 왼쪽 이미지는 종횡비 15를 사용하고, 오른쪽은 종횡비 30을 사용했습니다.*

## Common variations and edge cases

| 시나리오 | 변경 내용 | 이유 |
|----------|----------------|--------|
| **다른 데이터** | 문자열 `(01)12345678901231`을 유효한 GS1 애플리케이션 식별자와 데이터로 교체 | 제품 ID, 시리얼 번호 등을 인코딩할 수 있습니다 |
| **고해상도** | `XDimension.Pixels`를 3 또는 4로 증가 | 바코드를 큰 크기로 인쇄하거나 멀리서 스캔할 때 필요합니다 |
| **다른 DataBar 유형** | `EncodeTypes.DatabarStacked` 또는 `EncodeTypes.DatabarExpanded` 사용 | 라벨 레이아웃에 가장 적합한 유형을 선택 |
| **투명 배경** | `BarCodeImageFormat.Png`와 함께 `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` 전달 | 컬러 라벨 위에 바코드를 오버레이할 때 유용 |

> **Watch out for:** X‑dimension을 너무 작게(< 1 픽셀) 설정하면 바코드가 흐릿하게 보일 수 있습니다.

## What Should You Learn Next?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 다양한 구현 방식을 탐색하도록 돕습니다.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}