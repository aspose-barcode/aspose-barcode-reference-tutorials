---
category: general
date: 2026-08-22
description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 생성하고, 바코드 크기를 설정하며, 열을 조정하고, 컴팩트
  모드를 활성화하는 방법을 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: ko
lastmod: 2026-08-22
og_description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 생성합니다. 이 가이드는 바코드 크기 설정, 열 제어
  및 작은 이미지를 위한 컴팩트 모드 활성화 방법을 보여줍니다.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: C#에서 PDF417 바코드 생성 – 크기, 열 및 컴팩트 모드 설정
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: C#에서 PDF417 바코드를 생성하고 바코드 크기 설정하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 PDF417 바코드를 생성하고 바코드 크기 설정하기

.NET 애플리케이션에서 **PDF417 바코드 생성**이 필요하다면, 이 가이드는 전체 과정을 단계별로 안내합니다. Aspose.BarCode를 사용해 **PDF417을 생성**하고, **바코드 크기 설정**을 조정하며, 보고서나 모바일 앱에 삽입할 수 있는 컴팩트한 PNG를 만드는 방법을 정확히 확인할 수 있습니다.

바코드 생성에 별도의 그래픽 편집기가 필요하지 않습니다. 이 튜토리얼을 마치면 원하는 정확한 크기의 PDF417 이미지를 생성하는 완전한 C# 메서드를 얻게 되며, 이후 처리에 바로 사용할 수 있습니다.

## 배울 내용

* Aspose.BarCode 라이브러리 설치 및 참조
* PDF417 바코드 생성기 생성 및 인코딩 텍스트 지정
* X‑dimension 및 컬럼 수를 설정하여 **바코드 크기 설정**
* 심볼을 축소하는 컴팩트(축소) 모드 활성화
* 결과를 PNG 파일로 저장
* 읽을 수 없는 코드, 과도하게 큰 이미지 등 일반적인 문제 해결

### 사전 요구 사항

* .NET 6.0 이상 (.NET Framework 4.6+에서도 동작)
* C# 및 Visual Studio(또는 기타 C# IDE)에 대한 기본 지식
* 유효한 Aspose.BarCode 라이선스(무료 평가판으로 테스트 가능)

> **Pro tip:** 많은 바코드를 루프에서 생성해야 한다면 `BarcodeGenerator` 인스턴스를 하나만 재사용하고 `CodeText` 속성만 변경하세요. 메모리 할당을 크게 줄일 수 있습니다.

## Aspose.BarCode로 PDF417 바코드 생성

첫 번째 단계는 PDF417 심볼리지를 위한 `BarcodeGenerator`를 인스턴스화하는 것입니다. 이 객체가 모든 바코드 작업의 진입점이 됩니다.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*왜 중요한가*: `EncodeTypes.Pdf417`은 라이브러리에게 PDF417 표준을 사용하도록 지시합니다. 이 표준은 대용량 데이터와 오류 정정을 지원합니다. 생성자에 인코딩할 데이터를 바로 전달하면 나중에 별도로 `CodeText`를 지정할 필요가 없습니다.

## 바코드 크기 및 컬럼 수 설정

PDF417 심볼은 작은 직사각형 모듈의 행과 열로 구성됩니다. 모듈 너비(X‑dimension)와 컬럼 수를 제어하면 전체 치수를 미세 조정할 수 있습니다.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*설명*:  
* **X‑dimension** (`Pixels`)은 각 모듈의 너비를 결정합니다. 값이 작을수록 바코드가 촘촘해지고, 값이 클수록 저해상도 스캐너에서 가독성이 높아집니다.  
* **Columns**는 가로 레이아웃을 제어합니다. 컬럼 수가 적으면 바코드가 더 높아지고, 컬럼 수가 많으면 더 넓어집니다. 이 두 설정을 함께 조정해 **바코드 크기 설정**을 정확히 맞추세요.

## 더 작은 바코드를 위한 컴팩트 모드 활성화

PDF417에는 불필요한 패딩을 제거하고 전체 면적을 줄이는 “컴팩트”(또는 축소) 모드가 있습니다. 화면 공간이 제한된 경우 특히 유용합니다.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*왜 축소 모드를 사용하나요?*  
`Truncate`가 `true`이면 생성기가 정지 패턴과 대부분의 스캔 시나리오에 필요하지 않은 일부 오류 정정 코드워드를 생략합니다. 결과 이미지가 약 15‑20 % 정도 작아지면서 일반적인 사용에서는 데이터 무결성을 유지합니다.

## 바코드를 PNG 이미지로 저장

크기와 모드를 설정한 뒤 바코드를 디스크에 기록합니다. PNG는 무손실 포맷이므로 모듈 가장자리가 선명하게 유지됩니다.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

`CompactPdf417.png` 파일에는 이전 단계에서 지정한 치수와 일치하는 선명한 PDF417 심볼이 포함됩니다.

### 예상 출력

저장된 PNG를 열면 세 개의 컬럼으로 구성된 수직 방향 PDF417 바코드가 표시됩니다. 각 모듈은 2 px 너비이며 전체 크기는 대략 **120 × 240 px**(가로 × 세로)입니다. 표준 PDF417 리더로 이미지를 스캔하면 원본 텍스트 “Sample text for PDF417”가 반환됩니다.

## 흔히 겪는 문제와 해결 방법

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| 바코드가 읽히지 않음 | 스캐너에 비해 X‑dimension이 너무 작음 | `XDimension.Pixels`를 3 또는 4로 증가 |
| 이미지가 UI에 비해 너무 넓음 | 컬럼 수가 과다 설정 | `Pdf417.Columns`를 줄이거나 `Truncate` 활성화 |
| `ArgumentOutOfRangeException` 예외 | 컬럼 수가 음수이거나 0 | `Columns`를 양의 정수(최소 1)로 설정 |
| PNG 파일이 비어 있음 | 출력 경로가 존재하지 않거나 쓰기 권한 부족 | 디렉터리 존재 여부와 앱의 쓰기 권한 확인 |

> **Pro tip:** `Save()` 호출 전에 `barcodeGenerator.ValidateParameters()`를 사용해 구성 오류를 미리 감지하세요.

## 전체 실행 가능한 예제

아래는 앞서 설명한 모든 단계를 포함한 독립 실행형 콘솔 프로그램입니다. 새 C# 프로젝트에 복사하고 Aspose.BarCode NuGet 패키지를 복원한 뒤 실행하면 결과를 확인할 수 있습니다.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**프로그램 실행** 시 실행 파일 작업 디렉터리에 `CompactPdf417.png`가 생성됩니다. 모바일 앱(예: “Barcode Scanner”)으로 이미지를 스캔해 인코딩된 텍스트가 원본 문자열과 일치하는지 확인하세요.

## 다음 단계 및 관련 주제

* **오류 정정 수준 높이기** – 환경이 스캔 노이즈가 많을 경우 `Pdf417.ErrorLevel`을 조정  
* **방향 변경** – 가로 레이아웃이 필요하면 `Pdf417.Rotate`를 `RotationAngle.Rotate90`으로 설정  
* **PDF에 바코드 삽입** – Aspose.PDF와 Aspose.BarCode를 결합해 이미지를 문서에 직접 배치  
* **다른 2‑D 바코드 생성** – 동일 `BarcodeGenerator` 클래스로 DataMatrix, QR, Aztec 코드도 지원; `EncodeTypes.Pdf417`을 원하는 심볼리티로 교체하면 됨

**PDF417 바코드 생성** 기술을 마스터하면 티켓 발행, 재고 라벨링, 보안 데이터 전송 등을 다양한 .NET 애플리케이션에서 자동화할 수 있습니다.

## 결론

이제 C#에서 **PDF417 바코드 생성** 방법, 정확한 **바코드 크기 설정**, 컬럼 조정, 컴팩트 모드 활성화, PNG 저장까지 전체 과정을 알게 되었습니다. 이러한 설정을 활용해 UI 제약이나 스캔 요구 사항에 맞게 바코드를 최적화하고, 필요에 따라 다른 바코드 형식에도 적용해 보세요. 즐거운 코딩 되세요!

## 다음에 배워야 할 내용

다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하며, 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}