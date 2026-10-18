---
category: general
date: 2026-10-18
description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 만드는 방법을 배웁니다. 이 튜토리얼은 기본, 컴팩트,
  매크로 및 마이크로 PDF417 생성과 전체 코드를 다룹니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: ko
lastmod: 2026-10-18
og_description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 생성하세요. 이 가이드를 따라 기본, 컴팩트, 매크로
  및 마이크로 PDF417 바코드를 단계별로 생성하십시오.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: C#에서 PDF417 바코드 생성 – 완전한 Aspose.BarCode 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드 생성 – 단계별 가이드
url: /ko/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 Aspose.BarCode를 사용하여 PDF417 바코드 생성 – 단계별 가이드

.NET 애플리케이션에서 **PDF417 바코드 생성**이 필요하다면, 이 튜토리얼은 전체 과정을 단계별로 안내합니다. 기본 바코드 생성, 컴팩트 모드 활성화, 매크로 메타데이터 추가, 마이크로 변형 생성 방법을 명확한 설명과 실행 가능한 코드와 함께 확인할 수 있습니다.

PDF417 바코드 생성은 물류, 티켓 발행, 문서 관리 등에서 흔히 사용됩니다. 이 가이드를 마치면 외부 도구 없이도 모든 C# 프로젝트에 바코드 생성을 통합할 수 있게 됩니다.

## Prerequisites

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 이상 (코드는 .NET Framework 4.7+에서도 동작합니다)
* Visual Studio 2022 또는 기타 C# IDE
* **Aspose.BarCode for .NET** NuGet 패키지  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 생성된 PNG 파일이 저장될 폴더에 대한 쓰기 권한

추가 설정은 필요하지 않습니다; 라이브러리가 모든 저수준 인코딩 세부 사항을 처리합니다.

## Step 1: 기본 PDF417 바코드 생성

첫 번째 단계에서는 사용자 지정 크기와 열 수를 가진 일반 PDF417 바코드를 설정합니다.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**이 설정이 중요한 이유**

* `XDimension.Pixels`는 각 바코드 요소의 물리적 크기를 제어합니다. 값이 2이면 대부분의 화면과 프린터에서 선명한 이미지를 제공합니다.
* `Pdf417.Columns`는 바코드가 포함하는 데이터 열 수를 결정합니다. 열 수가 적을수록 폭이 좁아지고, 열 수가 많을수록 데이터 용량이 증가합니다.

코드를 실행하면 `Pdf417Basic.png`가 생성되며, 오른쪽에 전체 메타데이터 열이 있는 일반적인 PDF417 심볼이 표시됩니다.

## Step 2: 컴팩트(축소) 모드 활성화

컴팩트 모드는 오른쪽 메타데이터 열을 제거하여 바코드를 더 좁게 만듭니다. 공간이 제한된 상황에서 남은 행으로 데이터를 복원할 수 있을 때 유용합니다.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**왜 축소하나요?**  
`Truncate`가 `true`이면 생성기가 오류 정정 및 파일 수준 메타데이터를 저장하는 선택적 오른쪽 열을 생략합니다. 결과 바코드는 열 수가 줄어들지만 대부분의 PDF417 리더에서 스캔이 가능합니다.

## Step 3: 파일 수준 메타데이터가 포함된 매크로 PDF417 바코드 생성

매크로 PDF417는 세그먼트 식별자를 추가하여 큰 문서를 여러 바코드로 분할할 수 있게 합니다. 긴 문자열이나 다중 페이지 파일을 인코딩할 때 편리합니다.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**매크로 필드 설명**

| 속성 | 목적 |
|----------|---------|
| `MacroPdf417FileID` | 전체 파일에 대한 고유 식별자; 모든 세그먼트가 이 값을 공유합니다. |
| `MacroPdf417SegmentID` | 현재 세그먼트의 인덱스(1부터 시작). |
| `MacroPdf417SegmentsCount` | 전체 데이터 세트를 구성하는 세그먼트 총 개수. |

매크로 PDF417를 지원하는 스캐너는 모든 세그먼트를 읽고 이러한 식별자를 사용해 원본 데이터를 재조합할 수 있습니다.

## Step 4: 짧은 데이터를 위한 마이크로 PDF417 바코드 생성

마이크로 PDF417는 작은 페이로드(최대 90 문자)를 위해 설계된 압축 버전입니다. 열 범위를 1‑4로 제한하여 아주 작은 라벨이나 디스플레이 영역이 제한된 장치에 적합합니다.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**마이크로 PDF417를 사용해야 할 때**  
데이터 페이로드가 짧고 가능한 가장 작은 바코드가 필요할 때 이 변형을 사용하세요. 재고 태그, 출입 카드, 화면 공간이 매우 제한된 모든 시나리오에 이상적입니다.

## Full working example

아래는 한 번에 네 가지 바코드 유형을 모두 생성하는 독립 실행형 콘솔 애플리케이션 예제입니다. 코드를 새 C# 프로젝트에 복사하고 `YOUR_DIRECTORY`를 기존 폴더 경로로 바꾼 뒤 실행하세요.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**예상 출력**

프로그램을 실행하면 지정된 폴더에 네 개의 PNG 파일이 생성됩니다:

* `Pdf417Basic.png` – 3열을 가진 표준 바코드
* `CompactPdf417.png` – 동일한 데이터이지만 오른쪽 열이 축소된 버전
* `MacroPdf417.png` – 세그먼트 메타데이터가 포함된 매크로 바코드
* `MicroPdf417.png` – 짧은 문자열을 위한 압축 마이크로 바코드

이미지 뷰어로 파일을 열면 서로 다른 PDF417 패턴을 확인할 수 있습니다. 모바일 바코드 리더(e.g., ZXing, Scandit)로 스캔하면 원본 텍스트 문자열이 반환됩니다.

## Common questions and tips

* **바코드가 흐릿하게 보이면 어떻게 하나요?**  
  `XDimension.Pixels` 값을 3 또는 4로 늘리세요. 모듈 크기가 커지면 해상도가 높아지지만 파일 크기도 커집니다.

* **PNG 대신 SVG를 출력할 수 있나요?**  
  예. `Save` 호출에서 `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Svg`로 교체하면 됩니다.

* **오류 정정 레벨을 수동으로 설정해야 하나요?**  
  Aspose.BarCode가 최적의 레벨을 자동으로 선택합니다. 특수한 경우에는 `Pdf417.ErrorCorrectionLevel`을 조정할 수 있습니다.

* **바코드를 PDF 문서에 삽입하려면?**  
  `Aspose.Pdf`를 사용해 생성된 PNG 또는 SVG를 PDF 페이지의 이미지 요소로 추가하면 됩니다.

* **라이브러리가 스레드‑안전한가요?**  
  각 `BarcodeGenerator` 인스턴스는 독립적이므로 공유 상태 없이 여러 스레드에서 생성기를 만들 수 있습니다.

## Conclusion

이제 Aspose.BarCode를 사용해 C#에서 **PDF417 바코드 생성** 방법을 알게 되었으며, 기본, 컴팩트, 매크로, 마이크로 변형을 모두 다룰 수 있습니다.

## What Should You Learn Next?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료에는 단계별 설명과 완전한 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [C#에서 pdf417 바코드 생성 – 단계별 가이드](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [C#에서 컴팩트 모드로 PDF417 바코드 생성](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Aspose.BarCode를 사용해 C#에서 매크로 PDF417 바코드 생성](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}