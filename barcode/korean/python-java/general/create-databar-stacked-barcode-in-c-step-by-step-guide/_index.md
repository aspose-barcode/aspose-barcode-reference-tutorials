---
category: general
date: 2026-08-06
description: C#에서 데이터바 스택드 바코드를 빠르게 생성하세요. X 차원을 설정하고, 종횡비를 조정하며, DataBar Stacked
  Omnidirectional 생성기를 사용해 PNG 파일을 내보내는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: ko
lastmod: 2026-08-06
og_description: Aspose.BarCode를 사용하여 C#에서 데이터바 스택형 바코드를 생성합니다. 이 튜토리얼에서는 X 차원을 설정하고,
  종횡비를 변경하며, PNG 이미지를 저장하는 방법을 보여줍니다.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: C#에서 데이터바 스택형 바코드 만들기 – 완전 프로그래밍 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#에서 데이터바 스택형 바코드 만들기 – 단계별 가이드
url: /ko/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 databar stacked barcode 생성 – 단계별 가이드

C#에서 **create databar stacked barcode** 이미지를 생성해야 한다면, 이 가이드는 Aspose.BarCode 라이브러리를 사용하여 정확히 어떻게 하는지 보여줍니다. X 차원 설정, 바코드 종횡비 변경, 결과를 PNG 파일로 저장하는 방법을 몇 단계에 걸쳐 배울 수 있습니다.

DataBar Stacked 바코드를 생성하는 것은 소매 스캔이나 물류 추적을 위해 GS1‑128 데이터를 인코딩해야 할 때 일반적입니다. 이어지는 섹션에서는 프로젝트 설정부터 출력 검증까지 모든 내용을 다루므로, .NET 애플리케이션에 솔루션을 놓치지 않고 통합할 수 있습니다.

## 전제 조건

* **.NET 6.0**(또는 이후 버전)이 설치되어 있어야 합니다 – 코드는 최신 SDK를 대상으로 합니다.
* **licensed** 복사본의 **Aspose.BarCode for .NET**이 필요합니다. 무료 평가판은 테스트에 사용할 수 있지만 워터마크가 추가됩니다.
* **Visual Studio 2022** 또는 **VS Code**와 같은 IDE에 C# 확장이 설치되어 있어야 합니다.
* **C#** 구문 및 GS1 Application Identifiers 개념에 대한 기본적인 이해가 필요합니다.

> **Pro tip:** NuGet 패키지 관리자를 사용할 경우 `dotnet add package Aspose.BarCode` 명령이 모든 종속성을 자동으로 해결합니다.

## 1단계: 새 콘솔 프로젝트 만들기

터미널이나 패키지 관리자 콘솔을 열고 다음을 실행합니다:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 명령은 최소한의 **Program.cs** 파일을 생성합니다. **Aspose.BarCode** 패키지를 추가하면 `BarcodeGenerator` 클래스를 사용할 수 있게 됩니다.

## 2단계: DataBar Stacked Omnidirectional 생성기 초기화

**Program.cs**를 열고 기본 내용을 다음 코드로 교체합니다. 첫 번째 줄은 **DataBar Stacked Omnidirectional** 심볼로지를 사용하도록 구성된 **BarcodeGenerator**를 생성하고 GS1‑128 페이로드를 제공합니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` 열거형 값은 라이브러리에게 **databar stacked barcode**를 생성하도록 지시합니다. 이는 omnidirectional DataBar 계열의 스택형 변형이며, 최대 14개의 숫자 문자를 저장할 수 있어 GTIN‑14 코드에 적합합니다.

## 3단계: X 차원 설정 (모듈 폭)

X 차원은 가장 작은 바(모듈)의 폭을 제어합니다. 값이 너무 작으면 저해상도 프린터에서 품질이 떨어질 수 있고, 너무 크면 라벨 공간을 초과할 수 있습니다.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** `Pixels` 속성은 화면 기반 테스트에 편리합니다. 인쇄 중심 시나리오에서는 대신 `generator.Parameters.Barcode.XDimension.Millimeters`를 사용하세요.

## 4단계: 종횡비 조정 및 첫 번째 이미지 저장

**aspect ratio**는 스택형 바코드의 높이와 너비 비율에 영향을 줍니다. DataBar Stacked Omnidirectional 유형은 10에서 30 사이의 비율을 지원합니다. 시각적 차이를 보여주기 위해 두 개의 이미지를 생성합니다.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`generator.Save` 호출은 현재 작업 디렉터리에 **PNG** 파일을 기록합니다. `BarCodeImageFormat.Png` 열거형은 무손실 압축을 보장하므로 추가 처리나 PDF에 삽입하기에 이상적입니다.

## 5단계: 종횡비를 30으로 변경하고 두 번째 이미지 저장

이제 종횡비를 **30**으로 변경하여 스택 바의 높이를 높입니다. 이렇게 하면 X 차원을 변경하지 않고 바코드가 더 높아집니다.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

프로그램을 실행하면 두 개의 PNG 파일이 생성됩니다:

* **DatabarAspectRatio15.png** – 작은 라벨에 적합한 컴팩트 바코드.
* **DatabarAspectRatio30.png** – 저대비 표면에서 스캔 신뢰성을 높이는 더 높은 바코드.

이미지를 아무 뷰어에서 열어 바가 올바르게 스택되어 있는지, 인코딩된 데이터가 원본 GS1 문자열과 일치하는지 확인할 수 있습니다.

## 6단계: 인코딩된 값 확인 (선택 사항)

바코드가 입력 문자열을 정확히 나타내는지 확인하려면 동일한 라이브러리로 디코딩할 수 있습니다:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

디코더는 `(01)12345678901231`을 출력해야 하며, 이는 **create databar stacked barcode** 과정이 데이터를 보존했음을 증명합니다.

## 흔히 발생하는 문제와 해결 방법

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| 바코드가 흐릿하게 보임 | 출력 해상도에 비해 X 차원이 너무 낮게 설정됨 | `XDimension.Pixels`를 늘리거나 인쇄용으로 `Millimeters`를 사용 |
| 스캐너가 “symbol not found” 보고 | 지원되는 10‑30 범위를 벗어난 종횡비 | 비율을 10~30 사이로 유지; 15와 30이 안전한 기본값 |
| PNG에 워터마크가 포함됨 | Aspose.BarCode 무료 평가 라이선스 사용 | 전체 라이선스를 구매하거나 테스트용으로 체험판을 사용 |
| 두 번째 이미지 디코딩 실패 | 디코더가 잘못된 심볼로지로 설정됨 | 스택 바코드를 읽을 때 `DecodeType.DatabarStackedOmniDirectional` 사용 |

## 다음 단계

이제 **create databar stacked barcode** 이미지를 만들 수 있으니, 다음과 같은 작업을 고려할 수 있습니다:

* **Embed the PNGs into PDF invoices**를 **Aspose.PDF**와 같은 PDF 라이브러리를 사용하여 수행합니다.
* **Generate barcodes on the fly in a web API** – ASP.NET Core 컨트롤러에서 PNG 바이트를 직접 반환합니다.
* **Experiment with other DataBar variants** (예: `DatabarExpanded`, `DatabarLimited`)를 `EncodeTypes` 열거형을 변경하여 시도합니다.
* **Adjust colors**를 위해 브랜드별 디자인에 맞게 `generator.Parameters.Barcode.ForeColor`와 `BackColor`를 설정합니다.

이러한 주제들은 모두 여기서 다룬 핵심 개념, 즉 `BarcodeGenerator` 초기화, 시각 매개변수 구성, `BarCodeImageFormat`으로 결과 저장을 기반으로 합니다.

---

### 결론

이 튜토리얼에서는 Aspose.BarCode를 사용하여 C#에서 **create databar stacked barcode** 이미지를 만드는 방법을 보여주었습니다. **X dimension** 설정, **barcode aspect ratio** 수정, `BarcodeGenerator`를 이용한 **PNG** 파일 내보내기를 배웠습니다. 선택적인 디코딩 단계로 인코딩된 GS1 데이터가 정확한지 확인할 수도 있습니다. 이러한 패턴을 재고, 배송, POS 애플리케이션에 적용하고, 라이브러리가 제공하는 다양한 커스터마이징 옵션을 탐색해 보세요. 즐거운 코딩 되세요!

## 다음에 배워야 할 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 숙달하고 자체 프로젝트에서 대체 구현 방식을 탐색하도록 돕습니다.

- [일차원 Databar 바코드 높이 조정](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [바코드 이미지 생성 – GS1 쿠폰 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}