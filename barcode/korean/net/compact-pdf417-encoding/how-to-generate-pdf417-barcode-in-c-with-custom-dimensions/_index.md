---
category: general
date: 2026-09-07
description: C#에서 PDF417 바코드를 생성하고 바코드 크기를 정확하게 제어하는 방법을 배워보세요. 단계별 가이드를 따라 PNG 이미지를
  만들세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: ko
lastmod: 2026-09-07
og_description: C#에서 PDF417 바코드를 생성하고 바코드 크기 설정 방법을 배워보세요. 이 튜토리얼은 완전한 실행 가능한 예제를
  보여줍니다.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: C#에서 PDF417 바코드 생성 – 차원 포함 전체 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: C#에서 사용자 지정 크기로 PDF417 바코드 생성하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 사용자 정의 크기로 PDF417 바코드 생성 방법

.NET 애플리케이션에서 **PDF417 바코드 생성**이 필요하다면, 이 가이드는 정확히 어떻게 하는지 보여줍니다. 바코드 크기를 제어하면서 PNG 이미지를 생성하는 완전한 실행 가능한 예제를 확인할 수 있습니다.

PDF417 바코드 생성은 재고 시스템, 탑승권, 보안 문서 등에서 흔히 요구됩니다. 이 튜토리얼에서는 **바코드 크기 설정** 방법도 배워서 출력이 레이아웃 요구에 맞도록 할 수 있습니다.

## 사전 요구 사항

- .NET 6.0 SDK 또는 그 이후 버전 설치  
- Visual Studio 2022 (또는 C# 호환 IDE)  
- **Aspose.BarCode for .NET** NuGet 패키지 (또는 PDF417을 지원하는 호환 라이브러리)  

다음 명령으로 패키지를 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## 단계 1: PDF417 바코드 생성기 만들기

첫 번째 단계는 `EncodeTypes.Pdf417` 유형과 인코딩하려는 텍스트를 사용하여 `BarcodeGenerator`를 인스턴스화하는 것입니다. 생성기 객체는 바코드에 대한 모든 설정을 보유합니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**왜 중요한가:** `EncodeTypes.Pdf417` 열거형은 라이브러리에게 PDF417 심볼을 사용하도록 알려주며, 이는 대용량 데이터와 오류 정정을 지원합니다. 텍스트 문자열은 유니코드 문자를 포함할 수 있어 추가 작업 없이 국제 기호를 인코딩할 수 있습니다.

## 단계 2: 바코드 크기 설정 방법

각 모듈(가장 작은 검은색/흰색 사각형)의 크기를 제어하면 전체 이미지 해상도가 결정됩니다. `XDimension.Pixels` 속성은 하나의 모듈에 대한 픽셀 너비를 설정합니다.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**왜 중요한가:** 더 큰 `XDimension`은 고해상도 이미지를 제공하여 인쇄하거나 멀리서 스캔할 때 유용합니다. 반대로 작은 값은 웹 사용을 위한 파일 크기를 줄입니다.

## 단계 3: PDF417 레이아웃 정의 (열 및 행)

PDF417은 열과 행 수를 지정하여 매트릭스 형태에 영향을 줄 수 있게 합니다. 이는 가독성과 바코드의 물리적 크기에 영향을 미칠 수 있습니다.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**왜 중요한가:** 열과 행을 조정하면 바코드를 특정 공간에 맞추거나 스캐너의 종횡비 요구 사항을 충족시킬 수 있습니다. 데이터가 매트릭스를 완전히 채우지 않을 경우 라이브러리가 자동으로 패딩을 추가합니다.

## 단계 4: 바코드를 PNG 이미지로 저장

마지막으로, 생성된 바코드를 파일에 기록합니다. PNG는 무손실 품질을 유지하므로 추가 처리에 이상적입니다.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

프로그램을 실행하면 `Pdf417Layout.png` 파일이 프로젝트 출력 폴더에 생성됩니다. 이미지 예시는 다음과 같습니다:

![사용자 정의 크기의 생성된 PDF417 바코드 이미지](og_image_placeholder.png)

*이미지 대체 텍스트: 사용자 정의 크기의 생성된 PDF417 바코드 이미지*  

**왜 중요한가:** PNG로 저장하면 설정한 정확한 모듈 크기가 유지되어 후속 스캔 애플리케이션에 필수적입니다.

## 하나의 블록에 포함된 전체 예제

아래는 복사·붙여넣기만 하면 수정 없이 실행할 수 있는 전체 프로그램입니다(출력 경로를 원하는 대로 변경할 수 있음).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### 예상 출력

- **파일:** `Pdf417Layout.png` (PNG, 무손실)  
- **크기:** `XDimension` (2 px) × (columns × rows) 매트릭스로 결정  
- **내용:** 유니코드 문자열 `Åspóse.Barcóde©`를 인코딩한 스캔 가능한 PDF417 바코드  

## 일반적인 질문 및 예외 상황

### 인쇄용으로 더 큰 이미지가 필요하면 어떻게 하나요?

`XDimension.Pixels`를 4 또는 5로 늘립니다. 큰 값은 고해상도 바코드를 생성하지만 파일 크기도 증가합니다.

### 예제 문자열보다 더 많은 데이터를 인코딩할 수 있나요?

예. PDF417은 최대 1,850자를 저장할 수 있습니다. `BarcodeGenerator` 생성자의 텍스트 인수를 교체하면 됩니다. 데이터가 매트릭스 용량을 초과하면 라이브러리가 자동으로 추가 행을 삽입합니다.

### 오류 정정은 어떻게 작동하나요?

PDF417은 내장 오류 정정을 포함합니다. 다음과 같이 수준을 조정할 수 있습니다:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

높은 수준은 바코드가 커지는 대가로 내구성을 높입니다.

### 화면에서 바코드가 흐릿하게 보이면 어떻게 하나요?

출력 이미지의 DPI가 표시 환경과 일치하는지 확인하십시오. 저장 시 DPI를 설정할 수 있습니다:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## 전문가 팁

- **전문가 팁:** 사용하려는 실제 스캐너로 생성된 바코드를 항상 테스트하십시오. 장치마다 모듈 크기와 여백(quiet zone)에 대한 허용 오차가 다릅니다.  
- **주의:** 매우 작은 `XDimension` 값(< 1 px)은 고 DPI 화면에서 보이지 않는 선으로 표시될 수 있습니다.  
- **웹 앱 팁:** `Cache-Control: public, max-age=86400` 헤더와 함께 PNG를 제공하여 반복 생성 오버헤드를 줄이세요.

## 결론

이제 C#에서 **PDF417 바코드 생성**과 **바코드 크기 정확히 설정** 방법을 알게 되었으며, 모든 요구에 맞출 수 있습니다. 완전하고 실행 가능한 예제는 사용자 정의 열/행 레이아웃과 모듈 크기로 PNG 이미지를 생성하는 방법을 보여주며, 인쇄 또는 디지털 배포에 바로 사용할 수 있습니다.

### 다음 단계

- **다양한 이미지 형식(JPEG, BMP)으로 PDF417 바코드 생성** 방법을 탐색하세요.  
- **사용자 입력 또는 장치 DPI에 따라 바코드 크기 동적으로 설정** 방법을 배우세요.  
- 바코드 생성을 ASP.NET Core API에 통합하여 필요 시 바코드를 제공하세요.

오류 정정, 여백, 색상 등 다른 PDF417 설정을 자유롭게 실험해 보세요. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료에는 단계별 설명과 함께 완전한 작동 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [PDF417 바코드 오류 수준 설정 방법 – 완전 가이드](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [C#에서 바코드 저장 방법 – PDF417 바코드 생성](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [C#에서 PDF417 바코드 생성 – 완전 가이드](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}