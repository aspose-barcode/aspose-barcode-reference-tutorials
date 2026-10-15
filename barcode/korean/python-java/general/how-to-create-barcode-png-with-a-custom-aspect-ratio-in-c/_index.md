---
category: general
date: 2026-10-05
description: C#에서 바코드 PNG를 생성하고, 스택형 DataBar 전방향 바코드의 종횡비를 15로 설정하는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: ko
lastmod: 2026-10-05
og_description: C#에서 바코드 PNG를 만들고, 몇 단계만으로 스택형 DataBar 전방향 바코드의 종횡비를 15로 설정하는 방법을
  알아보세요.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: C#에서 바코드 PNG 생성 – 가로세로비 15 설정 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: C#에서 사용자 지정 종횡비로 바코드 PNG 만들기
url: /ko/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 사용자 지정 종횡비로 바코드 PNG 만들기

C#에서 **바코드 PNG**를 만들어야 한다면, 이 가이드는 스택형 DataBar 전방향 바코드에 대해 **종횡비 15 설정 방법**을 보여줍니다. 각 API 호출을 단계별로 살펴보고, 종횡비가 중요한 이유를 설명하며, .NET 프로젝트 어디에든 넣어 사용할 수 있는 완전한 실행 예제를 제공합니다.

바코드 이미지를 생성하는 것은 재고 관리 시스템, 운송 라벨, 소매 POS 애플리케이션 등에서 흔히 요구되는 작업입니다. 이 튜토리얼을 마치면 비즈니스 파트너가 요구하는 정확한 시각적 사양을 충족하는 PNG 파일을 얻게 됩니다. 외부 도구 없이, 수동 이미지 편집 없이—오직 코드만으로 가능합니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 이상 (예제는 .NET 6을 사용하지만 .NET 5+에서도 동작)
* Visual Studio 2022 (또는 .NET을 지원하는 IDE)
* **Aspose.BarCode for .NET** NuGet 패키지  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* PNG 파일을 저장하려는 폴더에 대한 쓰기 권한

이 요구 사항은 최소 수준이며, 동일한 코드는 .NET Core, .NET Framework 또는 콘솔 애플리케이션에서도 작동합니다.

## Aspose.BarCode로 바코드 PNG 만들기

첫 번째 단계는 올바른 바코드 유형을 사용하여 `BarcodeGenerator` 클래스를 인스턴스화하는 것입니다. 여기서는 `EncodeTypes.DatabarStackedOmniDirectional`을 사용합니다. 이 유형은 어느 방향에서든 읽을 수 있는 스택형 DataBar를 생성합니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*왜 중요한가:* 생성자는 두 개의 인수를 받습니다—**바코드 심볼**과 **데이터 문자열**. DataBar 형식은 GS1 애플리케이션 식별자를 기대하므로 샘플 데이터가 `(01)`로 시작합니다.

## 스택형 DataBar의 종횡비 설정 방법

DataBar의 시각적 너비는 **aspect ratio** 속성으로 제어됩니다. 비율이 높을수록 바가 넓어져 저해상도 프린터에서도 스캔 신뢰성을 높일 수 있습니다.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension`은 단일 모듈(가장 작은 바 또는 공백)의 크기를 정의합니다. 이를 2 px로 유지하면 대부분의 라벨 프린터에 적합한 선명하고 고밀도 이미지를 얻을 수 있습니다.

## 종횡비 15 설정 – 코드 상세 분석

이제 **종횡비 15 설정** 요구 사항을 적용합니다. 이것이 튜토리얼의 핵심이며, 필요한 정확한 API 호출을 보여줍니다.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*왜 15인가?* 스택형 DataBar의 기본 종횡비는 12입니다. 이를 15로 높이면 각 바의 너비가 25 % 확대되어, 더 넓은 바코드를 요구하는 물류 업체의 사양에 부합하게 됩니다.

## 바코드를 PNG로 저장하기

제너레이터 설정이 완료되면 마지막 단계는 이미지를 디스크에 쓰는 것입니다. `Save` 메서드는 파일 경로와 이미지 포맷 열거형을 인수로 받습니다.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG 포맷은 무손실 품질을 유지하므로, 바코드가 어떤 디스플레이나 프린터에서도 설계대로 정확히 렌더링됩니다.

## 전체 예제 및 기대 출력

아래는 콘솔 앱의 `Main` 메서드에 복사해 넣을 수 있는 전체 프로그램입니다. 앞서 설명한 모든 단계를 포함하며, 작은 검증 메시지도 포함합니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**예상 출력**

프로그램을 실행하면 `DatabarAspectRatio15.png`라는 파일이 생성되고, 선명하고 넓은 스택형 DataBar 바코드가 들어 있습니다. PNG를 열면 가로로 늘어난 바코드가 표시되며, 여전히 GS1 DataBar 사양을 준수합니다.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **종횡비 15인 스택형 DataBar를 보여주는 바코드 PNG 생성**

### 팁 및 일반적인 함정

| 상황 | 권장 사항 |
|-----------|----------------|
| **이미지가 흐릿함** | `XDimension.Pixels`를 3 px 이상으로 늘리되, 전체 이미지 크기를 500 px 이하로 유지하여 파일이 과도하게 커지는 것을 방지합니다. |
| **스캐너가 코드를 읽지 못함** | 데이터 문자열이 GS1 형식(`(01)` 접두사)을 따르는지 확인합니다. 또한 프린터 해상도가 최소 300 dpi인지 확인하세요. |
| **다른 파일 형식이 필요함** | `BarCodeImageFormat.Png`를 `Jpeg`, `Bmp`, `Gif` 등으로 교체하면 API가 지원하는 모든 주요 래스터 포맷을 사용할 수 있습니다. |
| **웹 애플리케이션에서 실행** | `generator.Save(Stream, BarCodeImageFormat.Png)`를 사용해 파일 시스템을 거치지 않고 HTTP 응답에 직접 이미지를 씁니다. |

### 예제 확장하기

* **하나의 이미지에 여러 바코드:** 추가 `BarcodeGenerator` 인스턴스를 생성하고 `Graphics`를 사용해 단일 `Bitmap`에 그립니다.  
* **사람이 읽을 수 있는 텍스트 추가:** `generator.Parameters.Caption.Visible = true`로 설정하고 `generator.Parameters.Caption.Font`를 통해 글꼴을 커스터마이즈합니다.  
* **동적 종횡비:** 구성 파일이나 데이터베이스에서 비율 값을 가져와 실행 시 가변 너비 바코드를 생성합니다.

## 결론

이 튜토리얼을 통해 C#에서 **바코드 PNG**를 만드는 방법과 스택형 DataBar 전방향 바코드에 대해 정확히 **종횡비 15**를 설정하는 방법을 배웠습니다. 완전한 실행 코드는 모든 필수 API 호출을 보여주고, 각 설정이 왜 중요한지 설명하며, 실제 배포 시 유용한 팁을 제공합니다.  

다음 단계로는 다른 바코드 유형(예: QR Code 또는 Code 128)의 **종횡비 설정 방법**을 탐색하거나, 필요 시 바코드 이미지를 반환하는 ASP .NET Core 서비스에 제너레이터를 통합해 볼 수 있습니다. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료는 완전한 코드 예제와 단계별 설명을 포함해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용할 수 있도록 돕습니다.

- [C#와 Aspose.Barcode를 사용하여 databar PNG 이미지 만드는 방법](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [C#와 Aspose.Barcode를 사용하여 databar 스택형 바코드 만드는 방법](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [.NET에서 databar 스택형 전방향 종횡비 맞춤 설정](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}