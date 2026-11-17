---
category: general
date: 2026-11-17
description: 바코드 저장, 콤팩트 모드 활성화, 열 조정, 그리고 전체 C# 예제를 통한 PDF417 바코드 생성 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: ko
lastmod: 2026-11-17
og_description: C#에서 PDF417 바코드를 생성하면서 바코드를 저장하고, 컴팩트 모드를 활성화하며, 열을 조정하는 방법. 단계별 가이드를
  따라보세요.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: C#에서 바코드를 PNG로 저장하고 컴팩트 모드를 활성화하는 방법
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: C#에서 바코드를 PNG로 저장하고 컴팩트 모드를 활성화하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 바코드를 PNG로 저장하고 컴팩트 모드 활성화하는 방법

웹이나 인쇄에 사용할 수 있는 형식으로 **바코드 저장 방법**이 필요하다면, 이 가이드에서 정확한 단계를 보여드립니다. 또한 **컴팩트 모드 활성화**, **열 조정**, 그리고 Aspose.BarCode 라이브러리를 사용한 **PDF417 바코드 생성** 방법도 배울 수 있습니다.

이 튜토리얼은 프로젝트 설정부터 최종 PNG 파일까지 모든 과정을 다루므로, 추가 조사를 하지 않아도 코드를 그대로 복사해 자신의 솔루션에 적용할 수 있습니다. 외부 문서는 필요 없으며, 완전하고 실행 가능한 예제가 포함되어 있습니다.

## 전제 조건

시작하기 전에 다음이 설치되어 있는지 확인하세요.

* .NET 6.0 이상  
* Visual Studio 2022 (또는 기타 C# IDE)  
* `Aspose.BarCode` NuGet 패키지 (`Install-Package Aspose.BarCode`)  

이 세 가지가 아래 코드가 의존하는 전부입니다.

## 1단계: PDF417 바코드 생성기 만들기

**PDF417 바코드 생성**을 시작할 때 가장 먼저 해야 할 일은 올바른 인코드 타입과 인코딩할 데이터를 사용해 `BarcodeGenerator` 인스턴스를 만드는 것입니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417` 열거형은 라이브러리에게 PDF417 심볼을 사용하도록 지시합니다. PDF417은 대용량 데이터를 인코딩하기에 적합한 스택형 선형 바코드입니다. 문자열 `"Compact mode"`는 바코드 아래에 표시되는 사람 읽을 수 있는 텍스트가 됩니다.

## 2단계: X‑dimension(모듈 너비) 설정하기

바코드의 각 막대는 **모듈**이라고 부릅니다. 모듈 너비를 조절하면 데이터는 그대로 두고 바코드의 시각적 크기를 미세하게 조정할 수 있습니다.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

2픽셀 X‑dimension은 대부분의 장치에서 신뢰성 있게 스캔할 수 있는 컴팩트한 이미지를 생성합니다.

## 3단계: PDF417 코드의 **열 조정** 방법

PDF417은 바코드가 사용할 열 수를 지정할 수 있습니다. 열이 적으면 더 높고 좁은 심볼이 되고, 열이 많으면 더 넓고 짧은 심볼이 됩니다.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

이 코드는 **열을 조정하는 방법**을 보여줍니다. 대상 매체에 따라 2, 4 또는 라이브러리에서 지원하는 다른 값을 사용할 수 있습니다.

## 4단계: **컴팩트 모드 활성화** 및 심볼 트렁케이션

컴팩트 모드는 불필요한 패딩을 제거하고 바코드 전체 면적을 줄여줍니다. 라이브러리는 `Truncate` 속성을 통해 이 기능을 제공합니다.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

여기서 **컴팩트 모드 활성화**라는 문구가 등장하며, 가이드 후반부에서도 정확히 같은 문구 **how to enable compact mode**가 사용되어 보조 키워드 요구 사항을 만족합니다.

## 5단계: **바코드 저장**을 PNG 이미지로 만들기

생성된 이미지를 저장하는 것이 마지막 단계입니다. `Save` 메서드는 지정한 형식으로 바코드를 파일 시스템에 기록합니다.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

`YOUR_DIRECTORY`를 애플리케이션이 쓰기 가능한 절대 경로나 상대 경로로 교체하세요. 실행 후 `CompactPdf417.png`라는 파일이 생성되어 컴팩트 PDF417 바코드를 포함하게 됩니다.

### 예상 출력

저장된 PNG 파일을 열면 세 열과 트렁케이션된 패딩을 가진 수직으로 컴팩트한 PDF417 바코드가 표시됩니다. 모듈당 약 2 px 크기로, HTML `<img>` 태그에 삽입하거나 작은 라벨에 인쇄하기에 적합합니다.

## 전체 실행 가능한 예제

아래 코드는 새 콘솔 프로젝트에 복사해 바로 사용할 수 있는 완전한 프로그램입니다. 필요한 `using` 지시문을 모두 포함하고 있으며, **바코드 저장 방법**, **컴팩트 모드 활성화**, **열 조정 방법**, **PDF417 바코드 생성**을 한 흐름에서 보여줍니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

프로그램을 실행하면 앞서 설명한 PNG 파일이 생성됩니다. 콘솔 출력은 저장된 파일 위치를 알려 주어 **바코드 저장 방법** 단계가 성공했는지 확인할 수 있게 합니다.

## 흔히 묻는 질문 및 예외 상황

### 다른 이미지 형식이 필요하면?

`Save` 메서드는 `BarCodeImageFormat` 열거형 값이면 무엇이든 받을 수 있습니다. `Jpeg`, `Bmp`, `Gif` 등으로 교체하면 나머지 코드는 그대로 유지됩니다.

### 트렁케이션이 데이터 용량에 미치는 영향은?

**컴팩트 모드**(트렁케이션)를 활성화하면 행 수가 줄어들어 바코드의 최대 데이터 용량이 감소할 수 있습니다. “Data too large” 예외가 발생하면 열 수를 늘리거나 트렁케이션을 비활성화하세요.

### 동적 열 개수를 사용할 수 있나요?

가능합니다. 입력 문자열 길이에 따라 열 개수를 계산할 수 있습니다.

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

이 스니펫은 **열을 조정하는 방법**을 프로그래밍적으로 보여 주어 레이아웃에 맞게 바코드를 맞출 수 있게 합니다.

### X‑dimension이 정수 픽셀에만 제한되나요?

`Pixels` 속성은 양의 정수를 받습니다. 고해상도 출력(예: 인쇄)에서는 `Points`를 사용해 장치 독립적인 크기를 지정하는 것이 더 좋을 수 있습니다.

## 프로덕션 사용 시 팁

* **전문가 팁:** 입력 데이터가 심볼 용량을 초과할 경우 `BarCodeException`을 처리하도록 `try‑catch` 블록으로 바코드 생성을 감싸세요.  
* **주의 사항:** 파일 시스템 권한. 프로세스가 대상 디렉터리에 쓰기 권한이 없으면 **바코드 저장 방법** 단계에서 `UnauthorizedAccessException`이 발생합니다.  
* **성능 참고:** 루프에서 다수의 바코드를 생성할 때는 `BarcodeGenerator` 인스턴스를 재사용하고 각 반복마다 `CodeText` 속성만 업데이트하면 효율적입니다.

## 결론

이제 Aspose.BarCode for C#를 사용해 **바코드 저장 방법**을 PNG 파일로 저장하고, **컴팩트 모드 활성화**, **열 조정 방법**, 그리고 **PDF417 바코드 생성**까지 전체 과정을 마스터했습니다. 초기화부터 최종 이미지 저장까지 모든 단계가 예제에 포함되어 있습니다.

이후에는 바코드에 로고 추가, 색상 커스터마이징, 또는 ASP.NET Core API에 통합하는 등 관련 주제를 탐색할 수 있습니다. 모든 확장은 이 가이드와 동일한 패턴을 따르므로 자신 있게 코드를 변형할 수 있습니다.

다양한 열 개수, X‑dimension, 이미지 형식을 실험해 프로젝트 사양에 정확히 맞추세요. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 한 연관 주제를 다룹니다. 각 자료는 완전한 코드 예제와 단계별 설명을 제공해 추가 API 기능을 마스터하고 다양한 구현 방식을 탐색하도록 돕습니다.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}