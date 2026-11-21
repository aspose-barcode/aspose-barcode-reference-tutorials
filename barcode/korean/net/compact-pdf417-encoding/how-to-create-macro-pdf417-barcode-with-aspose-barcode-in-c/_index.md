---
category: general
date: 2026-11-20
description: Aspose.BarCode를 사용하여 C#에서 매크로 PDF417 바코드를 만드는 방법을 배우세요. 이 가이드는 메타데이터,
  매개변수 및 이미지 저장에 대해 다룹니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: ko
lastmod: 2026-11-20
og_description: Aspose.BarCode를 사용하여 C#에서 매크로 PDF417 바코드를 생성합니다. 메타데이터 설정, 매개변수 구성
  및 PNG 내보내기를 위한 전체 튜토리얼을 따라보세요.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: C#에서 매크로 PDF417 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: C#에서 Aspose.BarCode를 사용하여 매크로 PDF417 바코드 생성 방법
url: /ko/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 Aspose.BarCode를 사용하여 매크로 PDF417 바코드 생성 방법

.NET 애플리케이션에서 **매크로 PDF417 바코드**를 생성해야 한다면, 이 튜토리얼이 정확한 단계들을 보여줍니다. 매크로 전용 메타데이터 설정, 시각적 설정 조정, 그리고 결과를 PNG 파일로 저장하는 방법을 확인할 수 있습니다.

매크로 PDF417 바코드를 생성하면 큰 데이터 세트를 여러 심볼에 나누면서 파일 전체 식별자를 유지할 수 있어 유용합니다. 아래 예제에서는 모든 PDF417 기능을 위한 유창한 API를 제공하는 Aspose.BarCode 라이브러리를 사용합니다.

이 가이드를 마치면 전체 매크로 정보를 포함한 바코드 이미지를 생성하는 실행 가능한 콘솔 프로그램을 얻게 됩니다.

## 사전 요구 사항

* .NET 6.0 SDK 또는 그 이후 버전이 설치되어 있어야 합니다.
* Visual Studio 2022 (또는 C#를 지원하는 IDE)
* **Aspose.BarCode for .NET** NuGet 패키지 (`Aspose.BarCode`).

다음 명령으로 패키지를 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## 단계 1: 매크로 PDF417용 바코드 생성기 초기화

첫 번째 단계는 `EncodeTypes.MacroPdf417` 열거값을 사용해 `BarcodeGenerator`를 인스턴스화하는 것입니다. 이렇게 하면 라이브러리에게 바코드를 매크로 PDF417 심볼로 처리하도록 지시합니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*왜 중요한가*: `MacroPdf417`를 선택하면 `Pdf417` 매개변수 객체의 모든 매크로 관련 속성이 활성화됩니다.

## 단계 2: 기본 시각적 외관 설정

읽기 쉬운 바코드는 적절한 모듈 크기와 열 개수에서 시작합니다. `XDimension.Pixels` 속성은 단일 모듈의 너비를 제어하고, `Pdf417.Columns`는 각 행이 포함하는 데이터 열 수를 정의합니다.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

이 값들을 조정하면 스캐너 신뢰도와 이미지 크기에 모두 영향을 줍니다.

## 단계 3: 매크로 파일 식별 세부 정보 정의

매크로 PDF417는 파일 식별자, 세그먼트 식별자, 그리고 전체 세그먼트 수가 필요합니다. 이 세 필드는 스캐너가 원본 데이터 세트를 재조합할 수 있게 해줍니다.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

이 **매크로 PDF417 매개변수**가 매크로 기능의 핵심입니다. 이들이 없으면 스캐너가 심볼들을 연결할 수 없습니다.

## 단계 4: 선택적 매크로 메타데이터 추가

필수 식별자 외에도 매크로 형식은 체크섬, 파일 크기, 타임스탬프, 수신자, 발신자, 종료 플래그와 같은 추가 필드를 지원합니다. 이러한 데이터를 제공하면 오류 감지가 향상되고 하위 시스템에 대한 컨텍스트를 제공합니다.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*전문가 팁*: 워크플로우에서 특정 필드가 필요하지 않다면 기본값 그대로 두면 됩니다. 라이브러리는 해당 데이터 요소를 바코드에서 제외합니다.

## 단계 5: 바코드 이미지 저장

모든 매개변수를 설정한 후 `Save`를 호출하여 바코드를 내보냅니다. 예제에서는 PNG 파일을 사용자가 지정한 디렉터리에 저장합니다.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

프로그램이 끝나면 `ExtPDF417Meta.png`에 텍스트 `"Åspóse.Barcóde©"`와 모든 매크로 메타데이터를 인코딩한 매크로 PDF417 바코드가 포함됩니다.

## 전체 소스 코드

아래는 완전하고 독립적인 프로그램 전체 코드입니다. Aspose.BarCode NuGet 패키지를 설치한 후 새 콘솔 프로젝트에 복사하고 실행하세요.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### 예상 출력

프로그램을 실행하면 다음과 유사한 확인 메시지가 출력됩니다:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

PNG 파일을 열면 촘촘하고 고대비의 바코드가 보입니다. PDF417 호환 스캐너로 스캔하면 원본 텍스트와 모든 매크로 필드가 반환됩니다.

## 일반적인 질문 및 엣지 케이스

### 세그먼트가 20개 이상 필요하면 어떻게 하나요?

`MacroPdf417SegmentsCount` 속성은 최대 `255`까지 설정할 수 있습니다. 수신 시스템이 더 많은 세그먼트를 처리할 수 있는지 확인하고, 데이터를 관리 가능한 수의 심볼로 나누는 것을 고려하세요.

### 체크섬이 스캔에 어떤 영향을 미치나요?

CCITT‑16 체크섬(`MacroPdf417Checksum`)은 추가 오류 검사 레이어를 제공합니다. 스캐너가 불일치를 감지하면 바코드를 거부합니다. 워크플로우에 필요하지 않다면 체크섬을 생략할 수 있습니다.

### Aspose 없이 PDF417 매크로 바코드를 생성할 수 있나요?

예, 다른 라이브러리(e.g., ZXing.Net, Dynamsoft)도 PDF417을 지원하지만 매크로 전용 필드는 종종 누락됩니다. Aspose.BarCode는 매크로 메타데이터에 대한 가장 완전한 구현을 제공합니다.

### 저장을 지원하는 이미지 포맷은 무엇인가요?

`Save` 메서드는 `BarCodeImageFormat`에 정의된 모든 포맷을 지원하며, `Png`, `Jpeg`, `Gif`, `Bmp`, `Tiff` 등이 있습니다. 하위 처리 파이프라인에 맞는 포맷을 선택하세요.

## 결론

이제 Aspose.BarCode를 사용해 C#에서 **매크로 PDF417 바코드**를 생성하는 방법을 알게 되었습니다. 튜토리얼에서는 생성기 초기화, 시각적 설정, 매크로 파일 식별자, 선택적 메타데이터, 이미지 내보내기를 다루었습니다. 이 기반을 바탕으로 매크로 PDF를 재고 시스템, 문서 추적 또는 세분화된 데이터 전송이 필요한 모든 시나리오에 삽입할 수 있습니다.

다음 단계로는 더 높은 해상도를 위한 다양한 `XDimension` 값 실험, 오류 정정 레벨 조정 추가, 또는 PNG 스트림을 직접 반환하는 웹 API에 바코드를 통합하는 것을 시도해 보세요. 관련 주제로는 **바코드 생성기 예제**, **PDF417 매크로 매개변수**, **매크로 PDF417 메타데이터** 처리에 관한 튜토리얼을 참고하십시오.

코딩 즐겁게!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료는 단계별 설명과 함께 완전한 코드 예제를 제공하여 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색할 수 있도록 돕습니다.

- [C#에서 매크로 PDF417 옵션으로 PDF417 바코드 이미지 생성 방법](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [이미지에서 바코드 읽기 C# – 매크로 PDF417 포함 완전 가이드](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Aspose로 PDF417 바코드 생성 – 단계별 완전 가이드](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}