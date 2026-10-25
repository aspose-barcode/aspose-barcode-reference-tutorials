---
category: general
date: 2026-10-24
description: C#에서 Aspose.BarCode를 사용하여 컴팩트 설정 및 바코드 XDimension 제어와 함께 PDF417 바코드를
  생성하는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: ko
lastmod: 2026-10-24
og_description: C#에서 Aspose.BarCode를 사용해 PDF417 바코드를 생성하세요. 이 완전한 가이드를 따라 컴팩트한 PDF417
  이미지를 만들고, XDimension을 제어하며, 열을 설정할 수 있습니다.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Aspose.BarCode를 사용하여 PDF417 바코드 생성 – C# 단계별
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: C#에서 Aspose.BarCode를 사용하여 PDF417 바코드 생성하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode를 사용하여 C#에서 PDF417 바코드 생성 방법

.NET 애플리케이션에서 **PDF417 바코드 생성**이 필요하다면, 이 가이드는 완전하고 바로 실행 가능한 솔루션을 제공합니다. Aspose.BarCode를 사용하면 **compact PDF417**, **barcode XDimension**, **PDF417 columns**에 대한 세밀한 제어를 손쉽게 할 수 있습니다.

바코드 생성은 재고 관리 시스템, 티켓 발행 플랫폼, 문서 워크플로우 등에서 흔히 요구되는 기능입니다. 이 튜토리얼을 마치면 UI에 삽입하거나 라벨에 인쇄할 수 있는 선명한 PNG 형식 PDF417 바코드 이미지를 생성하는 독립 실행형 C# 프로그램을 만들 수 있습니다.

## 준비 사항

- .NET 6.0 SDK 이상 (코드는 .NET Framework 4.6+에서도 동작)
- Visual Studio 2022 또는 선호하는 C# 편집기
- 유효한 Aspose.BarCode for .NET 라이선스 (무료 체험판으로 개발 가능)
- C# 문법에 대한 기본 지식

> **Pro tip:** Aspose.BarCode를 평가 중이라면 공식 사이트에서 체험판을 다운로드하고 NuGet 패키지 `Aspose.BarCode`를 프로젝트에 추가하세요. 체험판은 생성된 이미지에 작은 워터마크를 삽입하며, 라이선스를 적용하면 사라집니다.

## Step 1: Aspose.BarCode NuGet 패키지 설치

솔루션 폴더에서 터미널을 열고 다음을 실행합니다:

```bash
dotnet add package Aspose.BarCode
```

이 명령은 최신 안정 버전(2026년 10월 기준, 버전 23.12)을 가져옵니다. 패키지를 추가하면 **PDF417 바코드** 이미지를 **생성**하기 위해 사용할 `Aspose.BarCode.Generation` 네임스페이스가 복원됩니다.

## Step 2: 기본 C# 콘솔 프로젝트 만들기

프로젝트가 아직 없다면 다음 명령으로 생성합니다:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

`Program.cs`를 엽니다. 스켈레톤에는 바코드 생성 코드를 넣을 `Main` 메서드가 이미 포함되어 있습니다.

## Step 3: 바코드 생성기 초기화

먼저 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.BarCode.Generation;
```

그 다음 `Main` 내부에서 PDF417 심볼과 인코딩할 데이터를 사용해 `BarcodeGenerator`를 인스턴스화합니다:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

문자열에는 Unicode 문자를 포함시켜 Aspose.BarCode가 비ASCII 입력을 올바르게 처리함을 보여줍니다. ASCII만 필요하면 원하는 일반 문자열로 교체하면 됩니다.

## Step 4: 바코드 XDimension(모듈 크기) 조정

**barcode XDimension**은 가장 작은 바(모듈)의 너비를 결정합니다. 픽셀 단위로 설정하면 최종 이미지 크기를 픽셀 단위로 정확히 제어할 수 있습니다:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 픽셀 값은 스캔 신뢰성을 유지하면서도 컴팩트한 이미지를 제공합니다. 더 큰 바코드가 필요하면 값을 늘리고, 매우 촘촘한 레이아웃이 필요하면 값을 줄이세요.

## Step 5: compact PDF417 옵션 구성

PDF417 전용 설정 두 가지가 시각적 크기에 큰 영향을 줍니다:

| 설정 | 의미 | 컴팩트 출력에 대한 일반 값 |
|------|------|---------------------------|
| `Columns` | 데이터 열 수 | `3` |
| `Truncate` (compact mode) | 오른쪽 정지 구역을 생략하고 행 수를 감소 | `true` |

다음과 같이 적용합니다:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

`Columns`를 `3`으로, `Truncate = true`로 설정하면 표준 라벨에 잘 맞으면서도 대부분의 스캐너가 읽을 수 있는 *compact PDF417* 바코드가 생성됩니다.

## Step 6: 바코드 이미지 저장

마지막으로 바코드를 디스크에 기록합니다. 예제는 PNG로 저장하지만 Aspose.BarCode는 BMP, JPEG, GIF, TIFF, SVG도 지원합니다:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png` 상수는 라이브러리에게 무손실 PNG를 생성하도록 지시합니다. 이는 후속 처리나 인쇄에 이상적입니다.

## 전체 실행 가능한 소스 코드

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

프로그램을 실행하면 프로젝트 루트 폴더에 `CompactPdf417.png`가 생성됩니다. 이미지 뷰어로 열면 문자열 *Åspóse.Barcóde©*를 인코딩한 촘촘한 PDF417 바코드를 확인할 수 있습니다.

![Aspose.BarCode를 사용하여 생성된 PDF417 바코드 스크린샷](placeholder-image.png "Generated PDF417 barcode")

*이미지 대체 텍스트: Aspose.BarCode를 사용하여 생성된 PDF417 바코드 스크린샷* – 이 대체 텍스트는 접근성과 SEO를 위해 주요 키워드를 포함합니다.

## 결과 확인 방법

1. PNG 파일을 엽니다. 바코드는 오른쪽에 여분의 정지 구역 없이 세 개의 수직 데이터 열과 컴팩트 레이아웃으로 구성되어야 합니다.
2. PDF417를 지원하는 스마트폰 바코드 스캐너로 이미지를 스캔합니다. 디코딩된 텍스트가 원본 문자열과 일치해야 합니다.
3. 스캔이 실패하면 `XDimension.Pixels` 값을 `3` 또는 `4`로 늘려 보세요. 모듈이 커질수록 저해상도 장치에서 가독성이 향상됩니다.

## 일반적인 변형 및 예외 상황

### 1. 이미지 형식 변경

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG는 벡터 기반이므로 확대해도 바코드가 선명하게 유지됩니다—웹 페이지에 유용합니다.

### 2. 대용량 데이터 인코딩

PDF417은 최대 약 1.1 KB의 텍스트를 저장할 수 있습니다. 페이로드가 세 열의 용량을 초과하면 라이브러리가 자동으로 행을 추가합니다. 바코드를 컴팩트하게 유지하려면 다음을 고려하세요:

- 데이터 길이를 줄이기(예: 전체 메시지 대신 식별자 사용)
- **PDF417 columns** 수 늘리기(예: `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. 체험판 워터마크 제거를 위한 라이선스 사용

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

실행 파일 옆에 라이선스 파일을 배치합니다. 라이선스를 적용하면 생성된 이미지에 워터마크가 표시되지 않습니다.

### 4. 예외 처리

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

일반적인 실패 원인으로는 쓰기 권한 부족이나 지원되지 않는 이미지 형식이 있습니다.

## 설정이 중요한 이유

- **barcode XDimension** – 각 바의 시각적 두께를 제어합니다. 너무 작으면 바코드가 읽히지 않고, 너무 크면 공간을 낭비합니다.
- **PDF417 columns** – 열 수가 적을수록 바코드가 좁아지지만 행 수가 늘어나게 됩니다.

## 다음에 배워야 할 내용은?


다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하여 관련 주제를 심도 있게 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 제공하므로 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Aspose를 사용한 PDF417 바코드 생성 – 완전 가이드](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [C#에서 컴팩트 설정으로 PDF417 바코드 생성](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [C#에서 Aspose로 바코드 저장 및 PDF417 생성 방법](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}