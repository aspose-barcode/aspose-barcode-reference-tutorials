---
category: general
date: 2026-09-22
description: C#에서 Aspose.BarCode를 사용하여 매크로 PDF417 바코드를 생성합니다. Aspose로 바코드를 생성하고 메타데이터를
  구성하며 PNG로 저장하는 방법을 단계별로 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: ko
lastmod: 2026-09-22
og_description: C#에서 Aspose.BarCode를 사용하여 매크로 PDF417 바코드를 생성합니다. 이 가이드는 Aspose로 바코드를
  생성하고, 매크로 메타데이터를 설정하며, 이미지를 내보내는 방법을 보여줍니다.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Aspose.BarCode(C#)로 매크로 PDF417 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Aspose.BarCode(C#)로 매크로 PDF417 바코드 생성
url: /ko/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode (C#)로 매크로 PDF417 바코드 만들기

.NET 애플리케이션에서 **매크로 PDF417 바코드**를 생성해야 하는 경우, 이 튜토리얼은 Aspose.BarCode를 사용하여 정확히 어떻게 하는지 보여줍니다. **Aspose로 바코드를 생성**하고, 매크로 전용 필드를 모두 설정한 뒤 PNG 이미지로 저장하는 완전한 실행 예제를 확인할 수 있습니다.

바코드는 재고 관리, 배송, 문서 추적 등에 자주 사용되며, 매크로 PDF417 변형은 바코드 자체에 추가적인 파일 수준 메타데이터를 삽입할 수 있게 해줍니다. 이 가이드를 끝까지 따라 하면 ISO/IEC 15438 표준을 준수하는 완전한 매크로 PDF417 바코드를 생성할 수 있습니다.

## 필요 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 SDK 이상 (코드는 .NET Core 및 .NET Framework에서도 동작)
* Visual Studio 2022 (또는 다른 C# IDE)
* Aspose.BarCode 패키지를 가져올 수 있는 NuGet‑호환 인터넷 연결
* C# 문법에 대한 기본적인 이해

이 전제 조건들은 추가 설정 없이 코드를 컴파일할 수 있도록 보장합니다.

## 1단계: Aspose.BarCode NuGet 패키지 설치

Aspose.BarCode 라이브러리는 이 튜토리얼 전체에서 사용되는 `BarcodeGenerator` 클래스를 제공합니다.

```bash
dotnet add package Aspose.BarCode
```

위 명령을 실행하면 최신 안정 버전이 프로젝트 파일(`*.csproj`)에 추가됩니다. 이 패키지는 PDF417, 매크로 PDF417 및 기타 다양한 심볼을 지원합니다.

## 2단계: 새 콘솔 프로젝트 생성 (선택 사항)

깨끗한 시작을 원한다면 콘솔 앱을 생성하세요:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

생성된 `Program.cs` 파일이 바코드 생성 코드를 담게 됩니다.

## 3단계: 바코드 생성기 초기화

생성기는 `EncodeTypes.MacroPdf417` 열거값과 인코딩할 텍스트를 사용해 만들어집니다. Aspose.BarCode는 유니코드 문자를 자동으로 처리하므로, 억양이 있는 문자나 기호를 그대로 포함할 수 있습니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### 왜 중요한가
`EncodeTypes.MacroPdf417`은 라이브러리에게 매크로 버전 PDF417을 사용하도록 지시합니다. 매크로 버전은 파일 수준 메타데이터(파일 ID, 세그먼트 수 등)를 삽입할 수 있는 기능을 추가합니다. `"Åspóse.Barcóde©"` 텍스트는 생성기가 UTF‑8 문자를 올바르게 인코딩함을 보여줍니다.

## 4단계: 기본 바코드 크기 설정

PDF417은 열 수와 X‑dimension(단일 모듈의 너비)을 제어할 수 있습니다. 이러한 값을 조정하면 바코드의 물리적 크기와 스캔 신뢰도에 영향을 줍니다.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – 값이 작을수록 바코드가 촘촘해지고, 값이 클수록 저해상도 스캐너에 유리합니다.  
* **Columns** – 데이터 열 수를 제어합니다. 일반적인 범위는 1~30입니다.

## 5단계: 매크로 PDF417 메타데이터 구성

매크로 PDF417은 바코드가 나타내는 파일에 대한 추가 필드를 포함합니다. 각 필드는 선택 사항이지만, 설정하면 매크로 형식을 이해하는 스캐너와의 상호 운용성이 향상됩니다.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 각 필드 설명

| Property | Purpose | Typical range |
|----------|---------|---------------|
| **MacroPdf417FileID** | 여러 바코드에 걸쳐 나뉘어 있을 수 있는 논리 파일의 고유 식별자 | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | 현재 세그먼트의 인덱스(0부터 시작) | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | 전체 파일을 구성하는 세그먼트 총 개수 | 1‑99 |
| **MacroPdf417FileName** | 파일의 사람 친화적인 이름 | 최대 255자 |
| **MacroPdf417Checksum** | 오류 검출을 위한 선택적 체크섬 | 0‑65535 |
| **MacroPdf417FileSize** | 원본 파일의 바이트 단위 크기 | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | 파일 생성 또는 수정 시각 | 任意 `DateTime` |
| **MacroPdf417Addressee** | 목적지 식별자(예: 부서 또는 기계) | 자유 형식 문자열 |
| **MacroPdf417Sender** | 발신자 식별자(예: 회사명) | 자유 형식 문자열 |
| **MacroPdf417Terminator** | 이 세그먼트가 마지막인지 여부 | `Set` 또는 `Unset` |

**팁:** 큰 파일을 여러 바코드에 나눠 저장할 경우, 각 세그먼트의 `SegmentID`가 연속적이어야 하며 `SegmentsCount`는 모든 세그먼트에서 동일하게 유지해야 합니다. 스캐너는 이 값을 사용해 원본 파일을 재구성합니다.

## 6단계: 바코드 이미지 저장

Aspose.BarCode는 PNG, JPEG, BMP, SVG 등 다양한 출력 형식을 지원합니다. PNG는 무손실 품질을 제공하므로 테스트 및 문서화에 이상적입니다.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

프로그램을 실행하면 프로젝트 출력 디렉터리(`bin/Debug/net6.0/`)에 `ExtPDF417Meta.png` 파일이 생성됩니다. 이미지 뷰어로 열어 바코드가 올바르게 렌더링되는지 확인하세요.

## 7단계: 생성된 바코드 검증 (선택 사항)

PDF417 스캐너 앱(모바일 또는 데스크톱)이 있다면 저장된 PNG를 스캔해 보세요. 스캐너는 다음을 반환해야 합니다:

* 인코딩된 텍스트 `"Åspóse.Barcóde©"`
* 설정한 모든 매크로 필드(파일 ID, 세그먼트 ID 등)

자동 검증을 위해 Aspose.BarCode는 `BarCodeReader` 클래스를 제공합니다:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

이 스니펫은 매크로 메타데이터를 프로그램matically 읽어와 **Aspose로 바코드 생성**이 엔드‑투‑엔드로 정상 동작함을 확인하는 방법을 보여줍니다.

## 엣지 케이스 및 모범 사례

| 상황 | 권장 처리 방법 |
|-----------|----------------------|
| **Unicode 문자** | 문자열이 UTF‑8인지 확인(.NET 기본값). Aspose.BarCode는 Unicode를 자동 인코딩하지만, 스캐너의 문자 집합을 검증하세요. |
| **대용량 파일** | 매크로 PDF417은 최대 99 세그먼트까지 파일을 분할합니다. 파일이 400 KB를 초과하면 `SegmentsCount`를 늘리고, 순차적인 `SegmentID`를 가진 여러 바코드를 생성하세요. |
| **타임스탬프 정밀도** | 전역 시간을 위해 `DateTime.UtcNow` 사용; 일부 스캐너는 UTC를 기대합니다. |
| **체크섬 검증** | 수신 측에서 무결성을 검증하려면 올바른 체크섬을 제공하세요. |
| **다른 이미지 형식** | 무한히 확대 가능한 바코드가 필요하면 `BarCodeImageFormat.Svg` 사용. |
| **성능** | 다수의 바코드를 생성할 때는 `BarcodeGenerator` 인스턴스를 재사용하고, 반복 사이에 `Parameters`만 변경하세요. |

## 전체 실행 가능한 예제

아래는 NuGet 패키지가 설치되어 있다고 가정하고, 수정 없이 복사·붙여넣기만으로 바로 실행할 수 있는 완전한 프로그램입니다.



## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하는 관련 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하고 있어, 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}