---
category: general
date: 2026-10-12
description: C#를 사용하여 마이크로 PDF417 바코드를 생성하고 바코드를 PNG로 변환하는 방법을 배웁니다. 전체 코드와 팁이 포함된
  단계별 가이드.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: ko
lastmod: 2026-10-12
og_description: C#를 사용하여 마이크로 PDF417 바코드를 생성하고 바코드를 PNG로 변환하세요. 이 완전한 가이드를 따라 표준 버전과
  GS1 버전을 모두 생성하십시오.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 마이크로 PDF417 바코드 생성 및 PNG로 변환 – C# 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: C#에서 마이크로 PDF417 바코드를 생성하고 PNG로 변환하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 마이크로 PDF417 바코드를 생성하고 PNG로 변환하는 방법

.NET 애플리케이션에서 **마이크로 PDF417 바코드 생성**이 필요하다면, 이 튜토리얼이 정확히 어떻게 하는지 보여줍니다. 표준 마이크로 PDF417 바코드와 GS1‑준수 버전을 모두 생성하고, 이후 **바코드를 PNG로 변환**하여 인쇄나 웹 표시와 같은 다운스트림 사용에 활용하는 완전하고 실행 가능한 예제를 확인할 수 있습니다.

바코드를 생성하는 것은 단일 메서드를 호출하는 것보다 더 복잡합니다—올바른 모듈 크기, 열 수, 인코딩 형식을 선택하는 것이 스캔 신뢰성을 결정합니다. 이 가이드를 끝까지 읽으면 각 설정이 왜 중요한지, 그리고 프로젝트에 맞게 어떻게 조정할 수 있는지 이해하게 됩니다.

## 사전 요구 사항

| 요구 사항 | 이유 |
|-------------|--------|
| .NET 6.0 SDK or later | C# 콘솔 앱 실행 환경을 제공합니다. |
| Visual Studio 2022 (or any C# IDE) | 편집 및 디버깅을 쉽게 해줍니다. |
| **Aspose.BarCode for .NET** NuGet package | `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat` 클래스를 제공합니다. |
| Write permission to the output folder | PNG 파일을 생성하는 `Save` 호출에 필요합니다. |

Aspose.BarCode 패키지는 CLI를 통해 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## 단계 1: 최소 콘솔 프로젝트 설정

새 콘솔 프로젝트를 만들고 바코드 라이브러리를 참조합니다. 아래 `Program.cs`에 필요한 모든 코드가 포함되어 있으며, 별도의 외부 파일은 필요하지 않습니다.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### 각 라인이 중요한 이유

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – 첫 번째는 일반 마이크로 PDF417 바코드를 생성하고, 두 번째는 GS1 표준을 따르며 애플리케이션 식별자(AI)를 포함합니다. 다운스트림 시스템이 GS1 데이터를 기대하는지에 따라 선택하세요.
* **`XDimension.Pixels = 2`** – 모듈 폭을 제어합니다. 값이 작을수록 이미지가 조밀해지지만 저해상도 스캐너에서는 읽기 어려울 수 있습니다. 대부분의 라벨 프린터에 안전한 기본값은 2픽셀입니다.
* **`Pdf417.Columns = 4`** – 마이크로 PDF417는 열 수를 제한해 전체 너비를 줄일 수 있습니다. 4열은 짧은 페이로드에 충분한 데이터 용량을 유지하면서 바코드를 컴팩트하게 유지합니다.
* **`BarCodeImageFormat.Png`** – PNG는 무손실 품질을 유지해 바코드 선명도에 필수적입니다. 그래서 우리는 JPEG 대신 **바코드를 PNG로 변환**합니다.

## 단계 2: 프로그램 실행 및 출력 확인

1. 프로젝트 빌드: `dotnet build`.
2. 실행: `dotnet run`.

콘솔에 다음과 유사한 메시지가 표시됩니다:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

생성된 PNG 파일을 이미지 뷰어로 열어보세요. 두 이미지 모두 스캔 준비가 된 선명하고 고대비의 바코드를 보여줍니다.

### 예상 시각적 결과

| 바코드 유형 | 외관 |
|--------------|------------|
| **Micro PDF417** | 4개의 열을 가진 작은 직사각형 패턴으로, 대부분의 2‑D 바코드 스캐너에서 읽을 수 있습니다. |
| **GS1 Micro PDF417** | 크기는 동일하지만 GS1 AI를 인코딩합니다; GS1을 이해하는 스캐너는 GTIN 및 일련 번호를 반환합니다. |

스캐너가 이미지를 읽지 못한다면 `XDimension.Pixels` 값을 **3** 또는 **4**로 늘리거나, 표준 마이크로 PDF417의 열 수를 줄여 보세요.

## 흔히 발생하는 문제와 회피 방법

| 문제 | 원인 | 해결책 |
|-------|-------|-----|
| 인쇄 후 바코드가 흐림 | 프린터 DPI 설정이 낮음 | PNG를 300 dpi 이상으로 내보내거나 프린터 드라이버가 스케일링을 처리하도록 합니다. |
| 스캐너가 “잘못된 데이터” 반환 | GS1 AI 형식이 누락되었거나 잘못됨 | 각 AI가 괄호로 감싸여 있고 GS1 사양을 따르는지 확인합니다(예: GTIN‑14는 `(01)`). |
| 이미지 파일이 생성되지 않음 | 출력 폴더에 쓰기 권한이 없음 | 프로그램을 관리자 권한으로 실행하거나 `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`와 같은 폴더를 선택합니다. |
| 라벨에 바코드가 너무 큼 | 기본 열 수가 너무 많음 | `Pdf417.Columns`를 (예: **3**)으로 줄이거나 `XDimension`을 늘려 전체 크기를 줄입니다. |

## 예제 확장

* **다른 이미지 형식** – 워크플로에 필요하면 `BarCodeImageFormat.Png`를 `Jpeg` 또는 `Bmp`로 교체합니다. PNG는 무손실 품질 면에서 여전히 최선의 선택입니다.
* **동적 데이터** – 사용자 입력이나 데이터베이스 값을 `BarcodeGenerator` 생성자에 전달해 실시간으로 바코드를 생성합니다.
* **배치 생성** – CSV 파일에서 행을 읽어 각 바코드를 고유 파일명으로 저장하도록 로직을 루프로 감쌉니다.

## 결론

이제 C#에서 **마이크로 PDF417 바코드 생성**과 **바코드를 PNG로 변환**하는 방법을 알고, 표준 및 GS1‑준수 시나리오 모두에 적용할 수 있습니다. 완전하고 실행 가능한 코드는 X 차원, 열 수, 인코딩 유형이라는 핵심 설정을 보여주어, 컴팩트하고 고품질 2‑D 바코드가 필요한 모든 .NET 프로젝트에 솔루션을 쉽게 적용할 수 있습니다.

*다음 단계*: Aspose.BarCode가 지원하는 다른 심볼(예: QR, DataMatrix)을 탐색하고, 고해상도 인쇄를 위해 다양한 `XDimension` 값을 실험하거나, 생성된 PNG를 웹 API에 통합해 필요 시 바코드를 제공하도록 합니다.

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하며, 밀접하게 연관된 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움을 줍니다.

- [C#에서 마이크로 pdf417 바코드를 생성하고 PNG로 저장하는 방법](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [C#에서 바코드 PNG 생성 – GS1 마이크로 PDF417 전체 가이드](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [C#에서 마이크로 PDF417 바코드 생성 – 완전 가이드](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}