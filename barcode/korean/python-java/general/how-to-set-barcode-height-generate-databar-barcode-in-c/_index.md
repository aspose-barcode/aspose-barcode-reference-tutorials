---
category: general
date: 2026-10-12
description: Aspose.BarCode를 사용하여 C#에서 바코드 높이를 설정하고 DataBar 바코드를 생성하는 방법. 전체 코드를 포함한
  단계별 가이드를 따라보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: ko
lastmod: 2026-10-12
og_description: C#에서 바코드 높이를 설정하고 Aspose.BarCode로 DataBar 바코드를 생성하는 방법. 전체 코드를 배우고,
  각 단계가 중요한 이유와 바코드 높이를 변경하는 방법을 알아보세요.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: C#에서 바코드 높이를 설정하고 DataBar 바코드를 생성하는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 바코드 높이 설정 및 C#에서 DataBar 바코드 생성 방법
url: /ko/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set barcode height, generate DataBar barcode in C#

바코드 **크기 설정 방법**을 프로그래밍 방식으로 지정해야 할 경우, 이 가이드는 정확한 단계들을 보여줍니다. DataBar Omni‑directional 바코드를 생성하고, 높이를 조정하며, 두 버전을 PNG 파일로 저장하는 방법을 배웁니다.

바코드의 바 높이를 변경하는 것은 영수증, 제품 라벨, 모바일 화면 등에 바코드를 통합할 때 흔히 요구되는 작업입니다. 아래 예제는 GS1 DataBar 심볼 전체를 지원하는 Aspose.BarCode 라이브러리를 사용합니다.

## What you’ll achieve

이 튜토리얼을 마치면 다음을 수행할 수 있습니다:

* DataBar Omni‑directional 바코드의 **바코드 높이 설정 방법**  
* 서로 다른 높이의 두 이미지를 생성하는 **barcode c# 생성 코드**  
* **databar 생성 방법**을 이해하고 바 높이가 중요한 이유 파악  
* **바코드 높이 변경** 로직을 생성기를 다시 만들지 않고 적용  

Aspose.BarCode NuGet 패키지와 .NET 6+ 런타임만 있으면 외부 도구가 필요 없습니다.

## Prerequisites

* .NET 6 SDK 이상 설치  
* Visual Studio 2022 (또는 기타 C# 편집기)  
* Aspose.BarCode for .NET – `dotnet add package Aspose.BarCode` 로 설치  

> **팁:** 상용 키가 없을 경우 Aspose의 무료 체험 라이선스를 사용하세요; API 사용 방식은 동일합니다.

## Step 1: Install the Aspose.BarCode package

프로젝트 폴더에서 터미널을 열고 다음을 실행합니다:

```bash
dotnet add package Aspose.BarCode
```

패키지는 `Aspose.BarCode` 네임스페이스를 추가하고, 여기서 **barcode c# 생성**에 사용할 `BarcodeGenerator` 클래스를 제공합니다.

## Step 2: Create a DataBar barcode generator

**바코드 설정 방법**의 첫 번째 구체적인 단계는 원하는 심볼과 데이터 문자열을 사용해 `BarcodeGenerator`를 인스턴스화하는 것입니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*왜 중요한가:* `EncodeTypes.DatabarOmniDirectional`는 어느 각도에서든 스캔 가능한 컴팩트한 Omni‑directional DataBar를 생성합니다—작은 라벨에 이상적입니다.

## Step 3: Set common barcode parameters (including the initial bar height)

이제 **바코드 X‑dimension 및 바 높이**를 설정하고 첫 번째 이미지를 저장합니다.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension은 각 바의 전체 너비를 제어합니다; 2‑픽셀 설정은 대부분의 화면에서 읽기 쉽고 선명한 이미지를 제공합니다. 이후 **바코드 높이 변경** 단계에서는 동일한 생성기를 재사용해 시간과 메모리를 절약합니다.

## Step 4: Save the first barcode image (30‑pixel height)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

`DatabarHeight30.png` 파일에는 바 높이가 30 픽셀인 DataBar 바코드가 저장됩니다.

## Step 5: Change only the bar height to 60 pixels

**바코드 높이 변경**을 보여주기 위해 `BarHeight` 속성만 60 픽셀로 바꿉니다. 다른 설정은 그대로 유지되며, 이는 단일 생성기로 여러 크기를 만들 때 가장 효율적인 방법입니다.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Step 6: Save the second barcode image (60‑pixel height)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

이제 두 개의 PNG 파일이 생성되었습니다. 각각 바 높이는 다르지만 데이터와 X‑dimension은 동일합니다.

## Full, runnable example

아래는 새 콘솔 애플리케이션(`dotnet new console`)에 복사‑붙여넣기하고 바로 실행할 수 있는 전체 프로그램입니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Expected output

프로그램을 실행하면 실행 파일 작업 디렉터리에 두 파일이 생성됩니다:

* `DatabarHeight30.png` – 바 높이가 30 픽셀인 DataBar 바코드.  
* `DatabarHeight60.png` – 동일한 바코드이지만 바가 두 배 높이(60 픽셀)로 표시됩니다.

두 이미지 모두 이미지 뷰어에서 열 수 있으며 PDF, HTML 페이지, 인쇄 라벨 등에 직접 삽입할 수 있습니다.

## Why adjusting bar height matters

* **스캔 신뢰성:** 저해상도 매체에서 바가 너무 짧으면 스캐너가 인식하기 어려울 수 있습니다; 높이를 늘리면 감지가 개선됩니다.  
* **디자인 제약:** 모바일 앱에서는 컴팩트한 바코드(30 px)가 필요하고, 인쇄 영수증에서는 더 큰 바코드(60 px)가 필요할 수 있습니다.  
* **규제 준수:** 일부 산업에서는 GS1 DataBar 심볼에 최소 바 높이를 요구합니다.

같은 `BarcodeGenerator` 인스턴스를 재사용하면 데이터 문자열을 다시 파싱하는 오버헤드를 피할 수 있어, 고처리량 환경에서 특히 유리합니다.

## Common variations and edge cases

| Situation | Recommended tweak |
|-----------|-------------------|
| 다른 X‑dimension이 필요함 | 첫 `Save` 전에 `XDimension.Pixels`를 변경합니다. |
| 다른 심볼(예: DataBar Stacked) 사용 | `BarcodeGenerator` 생성 시 `EncodeTypes.DatabarStacked`를 사용합니다. |
| 바코드를 PDF에 삽입해야 함 | `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)`를 사용하고 스트림을 PDF 라이브러리에 추가합니다. |
| .NET Framework 4.6에서 실행 | 동일한 코드가 작동합니다; 적절한 Aspose.BarCode 어셈블리를 참조하면 됩니다. |

## Pro tips for reliable barcode generation

* 동일한 데이터를 여러 크기로 생성할 때 **생성기 캐시**를 활용하세요.  
* **


## What Should You Learn Next?

다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하는 관련 주제를 다룹니다. 각 리소스에는 단계별 설명과 완전한 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}