---
category: general
date: 2026-09-19
description: C#에서 바코드를 생성하는 방법을 단계별 가이드와 함께 제공합니다. PDF417 바코드 설정을 맞춤화하고 즉시 사용할 수 있는
  바코드 이미지를 만드는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: ko
lastmod: 2026-09-19
og_description: C#에서 바코드를 생성하는 방법을 자세히 안내합니다. PDF417 바코드 매개변수를 맞춤 설정하고 오늘 바로 사용할 수
  있는 C# 프로젝트용 바코드 이미지를 만들세요.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: C#에서 바코드를 생성하고 PDF417 바코드를 맞춤 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: C#에서 바코드를 생성하고 PDF417 바코드를 커스터마이징하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 바코드 생성 및 PDF417 바코드 사용자 정의 방법

.NET 애플리케이션에서 **how to generate barcode**가 필요하다면, 이 튜토리얼은 완전하고 바로 실행할 수 있는 솔루션을 보여줍니다. PDF417 바코드 차원을 사용자 정의하고, 열 수를 선택하며, 마지막으로 **create barcode image C#** 프로젝트에 직접 삽입할 수 있는 방법을 배웁니다.

바코드 생성은 복잡한 빌드 파이프라인을 필요로 하지 않습니다. 이 가이드를 끝까지 따라가면 필요한 정확한 크기와 해상도를 가진 MicroPDF417 바코드가 포함된 PNG 파일을 얻을 수 있습니다.

## 사전 요구 사항

* .NET 6.0 SDK 또는 그 이후 버전 (코드는 .NET Framework 4.6+에서도 작동합니다)
* Visual Studio 2022 (또는 선호하는 C# 편집기)
* Aspose.BarCode for .NET NuGet 패키지 – 다음 명령으로 설치  
  `dotnet add package Aspose.BarCode`

추가 외부 도구는 필요하지 않습니다.

## Step 1: 프로젝트 설정 및 네임스페이스 가져오기

새 콘솔 프로젝트를 생성하고 Aspose.BarCode 참조를 추가합니다.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`Program.cs`를 열고 필요한 `using` 지시문을 추가합니다:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

이 네임스페이스는 **how to generate barcode**를 수행하고 PDF417‑특정 옵션을 제어할 수 있는 클래스를 제공합니다.

## Step 2: 원하는 텍스트로 MicroPDF417 생성기 초기화

첫 번째 줄은 MicroPDF417 심볼로지를 사용하도록 구성된 `BarcodeGenerator` 인스턴스를 생성합니다. 생성자는 인코딩 유형과 인코딩하려는 데이터 문자열을 매개변수로 받습니다.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**왜 중요한가:** MicroPDF417는 전체 PDF417 표준의 컴팩트 버전으로, 작은 라벨이나 모바일 화면에 적합합니다. 올바른 `EncodeTypes`로 생성기를 초기화하면 라이브러리가 적절한 인코딩 알고리즘을 사용합니다.

## Step 3: 더 높은 해상도를 위한 X‑dimension(모듈 폭) 사용자 정의

X‑dimension은 단일 바코드 모듈(가장 작은 검은색 또는 흰색 막대)의 폭을 제어합니다. 낮은 픽셀 값으로 설정하면 더 높은 해상도의 이미지가 생성됩니다.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**왜 중요한가:** X‑dimension이 크면 저해상도 스캐너가 바코드를 읽기 쉬워지고, 값이 작으면 제한된 공간에 더 많은 데이터를 담을 수 있습니다. 스캔 환경에 따라 이 값을 조정하세요.

## Step 4: 바코드 크기 제어를 위한 열 수 정의

MicroPDF417는 1‑4개의 열을 허용합니다. 열 수가 많을수록 짧고 넓은 바코드가, 적을수록 높고 좁은 바코드가 생성됩니다.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**왜 중요한가:** 적절한 열 수를 선택하면 수동 스케일링 없이 특정 UI 요소나 인쇄 라벨에 바코드를 맞출 수 있습니다.

## Step 5: 바코드를 PNG 이미지로 저장

마지막으로, 생성된 바코드를 디스크에 저장합니다. PNG는 무손실 품질을 유지하므로 선명한 스캔에 중요합니다.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

대상 디렉터리가 존재하지 않으면 `Save` 메서드가 `ArgumentException`을 발생시킵니다. 간단한 검사로 이를 방지할 수 있습니다:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### 전체 소스 코드

각 부분을 합치면 다음과 같은 완전하고 실행 가능한 프로그램이 됩니다:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

이 프로그램을 실행하면 아래 스크린샷과 같은 **MicroPdf417.png** 파일이 생성됩니다(이미지는 생략). 바코드는 텍스트 *Sample*을 인코딩하고 정의한 X‑dimension 및 열 설정을 반영합니다.

## 기타 PDF417 옵션 사용자 정의

이 가이드는 크기에 영향을 주는 **customize pdf417 barcode** 매개변수에 초점을 맞추지만, Aspose.BarCode는 필요할 수 있는 다양한 추가 설정을 제공합니다:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | 행 수(높이)를 제어 | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | 오류 정정 수준 설정(높을수록 내성 증가) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | 중단 패턴 없이 축소된 바코드 생성 | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | 숫자, 텍스트 또는 바이트 압축 선택 | `CompactionModes.Numeric`, 등. |

**Pro tip:** 고정 너비에 맞는 바코드가 필요할 때는 먼저 `Columns`를 늘리고 `XDimension`을 줄여 보세요. 스캐너가 기호 누락을 보고하면 `ErrorLevel`을 높여冗余성을 개선합니다.

## 에지 케이스 처리

* **MicroPDF417에 텍스트가 너무 김:** Micro 변형은 최대 1 KB 데이터를 지원합니다. 문자열이 이 한도를 초과하면 `EncodeTypes.MicroPdf417`를 `EncodeTypes.Pdf417`로 변경하여 전체 `Pdf417` 심볼로 전환하십시오.
* **지원되지 않는 이미지 형식:** `BarCodeImageFormat`은 `Jpeg`, `Bmp`, `Gif`도 지원합니다. 다운스트림 처리 파이프라인에 맞는 형식을 선택하세요.
* **크로스‑플랫폼 경로:** Linux나 macOS를 대상으로 할 때는 하드코딩된 역슬래시 대신 `Path.Combine`을 사용하세요.

## 바코드 검증

표준 바코드 스캐너 앱(모바일 또는 데스크톱)으로 생성된 이미지를 검증할 수 있습니다. 스캐너는 원본 텍스트 **Sample**을 반환해야 합니다. 실패할 경우:

1. X‑dimension이 1 픽셀 이하로 설정되지 않았는지 확인하세요(일부 스캐너는 서브픽셀 모듈을 해석하지 못함).
2. 출력 파일이 손상되지 않았는지 확인—프로그램을 다시 실행하고 파일 크기를 비교하세요.
3. `ErrorLevel`을 높여 내성을 개선하세요.

## 결론

이제 Aspose.BarCode를 사용하여 C#에서 **how to generate barcode**하는 방법, **customize pdf417 barcode** 차원 및 열 수를 조정하는 방법, 그리고 프로젝트에 직접 삽입할 수 있는 **create barcode image C#** 방법을 알게 되었습니다. 전체 예제는 프로젝트 설정부터 최종 PNG 출력까지의 실용적인 워크플로를 보여줍니다.

다음으로 `EncodeTypes` 열거형 값을 교체하여 QR, Code128, DataMatrix와 같은 다른 심볼로지를 탐색해 보세요. `Resolution`이나 `Margin`과 같은 추가 매개변수를 조정하면 특정 애플리케이션에 맞게 모든 바코드를 미세 조정할 수 있습니다.

코딩을 즐기세요, 그리고 바코드가 다음 자동화 프로젝트를 강화하도록 하세요!

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색하도록 돕습니다.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}