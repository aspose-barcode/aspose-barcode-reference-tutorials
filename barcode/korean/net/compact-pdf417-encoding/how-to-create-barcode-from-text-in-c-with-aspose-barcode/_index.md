---
category: general
date: 2026-10-02
description: C#에서 Aspose.BarCode를 사용해 텍스트로부터 바코드를 생성합니다. PDF417 바코드 생성 방법을 배우고, 컴팩트
  모드에서 PDF417 바코드를 생성하는 방법을 확인하세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: ko
lastmod: 2026-10-02
og_description: C#에서 Aspose.BarCode를 사용하여 텍스트로부터 바코드를 생성합니다. 이 가이드는 PDF417 바코드를 생성하는
  방법과 컴팩트 모드에서 PDF417 바코드를 생성하는 방법을 보여줍니다.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: C#에서 텍스트로 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Aspose.BarCode를 사용하여 C#에서 텍스트로 바코드 생성하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 Aspose.BarCode를 사용하여 텍스트에서 바코드 만들기

.NET 애플리케이션에서 **텍스트에서 바코드 만들기**가 필요하다면, 이 가이드는 전체 과정을 단계별로 안내합니다. 실행 가능한 예제를 통해 **PDF417 바코드 생성**과 **컴팩트 레이아웃으로 PDF417 바코드 생성 방법**을 확인할 수 있습니다.

프로그래밍 방식으로 바코드를 생성하면 수동 작업을 없애고 모든 문서에서 일관성을 보장합니다. 이 튜토리얼을 마치면 PDF417 바코드가 포함된 PNG 파일을 얻을 수 있으며, 이를 청구서, 티켓 또는 신분증 등에 삽입할 수 있습니다.

## 준비 사항

- .NET 6.0 SDK 이상 (코드는 .NET Framework 4.7.2+에서도 동작)
- Visual Studio 2022 또는 C#를 지원하는 편집기
- **Aspose.BarCode for .NET**에 대한 NuGet 라이선스 (무료 체험판으로 테스트 가능)

> **프로 팁:** 프로젝트를 깔끔하게 유지하려면 CLI를 통해 NuGet 패키지를 추가하세요:  
> `dotnet add package Aspose.BarCode`

## 1단계: 콘솔 프로젝트 설정

새 콘솔 애플리케이션을 만들고 Aspose.BarCode 라이브러리를 참조합니다.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 명령은 `Program.cs` 파일을 생성합니다. 이 파일을 아래 전체 예제로 교체합니다.

## 2단계: 텍스트에서 바코드 만들기 – 핵심 코드

`Program.cs`를 열고 내용을 다음 코드로 교체합니다. 각 줄마다 왜 필요한지 주석으로 설명했습니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 각 설정이 중요한 이유

| 설정 | 목적 |
|--------|----------|
| `EncodeTypes.Pdf417` | PDF417 심볼을 선택합니다. 이 심볼은 2차원 매트릭스에 대량의 데이터를 저장할 수 있습니다. |
| `XDimension.Pixels = 2` | 각 모듈의 너비를 제어합니다. 2 픽셀 값은 가독성과 파일 크기 사이의 균형을 맞춥니다. |
| `Pdf417.Columns = 3` | 열 수를 줄여 바코드를 더 컴팩트하게 만들면서 데이터 손실은 없습니다. |
| `Pdf417.Truncate = true` | 불필요한 패딩을 제거하고 바코드를 짧게 만드는 컴팩트 모드를 활성화합니다. |
| `BarCodeImageFormat.Png` | PNG는 무손실 품질을 유지하므로 후처리나 인쇄에 이상적입니다. |

## 3단계: PDF417 바코드 생성 – 예제 실행

프로젝트를 빌드하고 실행합니다:

```bash
dotnet run
```

실행이 끝나면 다음과 같은 출력이 표시됩니다:

```
Barcode saved to CompactPdf417.png
```

`CompactPdf417.png` 파일을 열어 결과를 확인하세요. 이미지에는 문자열 **Åspóse.Barcóde©**를 인코딩한 PDF417 바코드가 포함되어 있습니다.

![Create barcode from text example](barcode-example.png)

*Alt text: 텍스트에서 바코드 만들기 – PDF417 바코드가 PNG로 저장됨*

## 4단계: 사용자 정의 오류 보정으로 PDF417 바코드 생성 (선택 사항)

스캔 환경이 잡음이 많다면 오류 보정 레벨을 높일 수 있습니다:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

오류 레벨을 높이면 바코드가 커지지만 손상에 대한 복원력이 향상됩니다.

## 5단계: 흔히 발생하는 문제와 엣지 케이스 처리

1. **잘못된 문자** – PDF417은 유니코드를 지원하지만, 일부 구형 스캐너는 비 ASCII 기호를 거부할 수 있습니다. 대상 하드웨어에서 테스트하세요.  
2. **파일 경로 권한** – 쓰기 권한이 있는 디렉터리에 저장해야 합니다. 그렇지 않으면 `Save`가 `UnauthorizedAccessException`을 발생시킵니다.  
3. **이미지 크기** – `XDimension` 값을 너무 크게 설정하면 PNG 파일이 크게 됩니다. 대부분의 화면 표시 시나리오에서는 픽셀 크기를 1~4 사이로 유지하세요.

## 요약

이제 C#과 Aspose.BarCode를 사용해 **텍스트에서 바코드 만들기**, **컴팩트 레이아웃으로 PDF417 바코드 생성**, 그리고 **사용자 정의 설정으로 PDF417 바코드 생성 방법**을 알게 되었습니다. 위의 전체 실행 가능한 코드를 복사해 어떤 .NET 프로젝트에도 적용하고, 텍스트 입력이나 출력 형식(JPEG, BMP 등)으로 자유롭게 변형할 수 있습니다.

## 다음 단계

- `EncodeTypes`를 변경하여 QR Code나 Code128 같은 다른 심볼을 탐색해 보세요.  
- Aspose.PDF와 연동해 생성된 PNG를 PDF에 삽입해 엔드‑투‑엔드 문서 생성을 구현하세요.  
- `generator.Parameters.Barcode.Pdf417.Rows`를 실험해 수직 밀도를 조절해 보세요.

예제를 자유롭게 수정하고, 바코드를 애플리케이션에 삽입한 뒤 커뮤니티와 결과를 공유하세요. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하며, 완전한 코드 예제와 단계별 설명을 제공해 추가 API 기능을 마스터하고 다양한 구현 방식을 탐색할 수 있도록 돕습니다.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}