---
category: general
date: 2026-10-09
description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 생성하는 방법을 배우세요 – 전체 메타데이터 지원이 포함된
  매크로 PDF417를 생성합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Aspose.BarCode를 사용하여 C#에서 PDF417 바코드를 생성하는 방법을 배우세요 – 파일 ID, 세그먼트
  데이터, 타임스탬프 등을 포함한 전체 메타데이터 지원이 있는 매크로 PDF417를 생성합니다.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: C#에서 Aspose.BarCode를 사용하여 PDF417 바코드 생성 방법
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: C#에서 Aspose.BarCode를 사용하여 PDF417 바코드 생성 방법
url: /ko/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 Aspose.BarCode를 사용하여 PDF417 바코드 생성 방법

빠르고 안정적으로 **PDF417 바코드 C# 생성**을 해야 한다면, 이 튜토리얼은 Aspose.BarCode를 사용한 전체 과정을 안내합니다. 기본 치수부터 Macro PDF417 메타데이터 필드 전체까지 필요한 모든 설정을 확인하고, 최종적으로 다운스트림 처리를 위한 PNG 이미지가 생성됩니다.

## 빠른 답변
- **어떤 라이브러리가 PDF417 바코드를 생성합니까?** Aspose.BarCode for .NET.
- **예제는 어떤 형식으로 출력됩니까?** 무손실 PNG 이미지.
- **라이선스가 필요합니까?** 무료 체험판으로도 예제 실행 가능; 상용 라이선스는 프로덕션에 필요합니다.
- **지원되는 .NET 버전은 무엇입니까?** .NET 6.0 또는 이후 버전.
- **바코드에 메타데이터를 추가할 수 있습니까?** 예 – Macro PDF417는 파일 ID, 세그먼트 수, 타임스탬프 등 다양한 메타데이터를 지원합니다.

## PDF417 바코드란?
PDF417 바코드는 스택형 선형 심볼로, 심볼당 약 1 KB까지 데이터를 인코딩할 수 있으며 다중 세그먼트 파일을 위한 선택적 매크로 메타데이터를 지원합니다. 여러 행의 스택형 선형 패턴으로 구성되어 높은 데이터 용량을 제공하면서도 표준 2‑D 스캐너로 읽을 수 있습니다. 또한 오류 정정 레벨을 포함해 신뢰성을 높이며, 선택적 매크로 기능을 통해 큰 파일을 여러 바코드에 나누어 메타데이터와 함께 재조합할 수 있습니다.

## PDF417에 Aspose.BarCode를 사용하는 이유
Aspose.BarCode는 **50가지 이상의 바코드 심볼**을 지원하며, 최대 **2 000 열**까지의 Macro PDF417 바코드를 생성할 수 있어 **10 MB** 이상의 파일도 전체 페이로드를 메모리에 로드하지 않고 처리합니다. 이러한 정량화된 기능은 고처리량 엔터프라이즈 시나리오를 원활하게 실행하도록 보장하며, 풍부한 사용자 정의 옵션을 제공합니다.

## 사전 요구 사항

- .NET 6.0(이상) 설치  
- Visual Studio 2022 또는 C# 호환 IDE  
- 유효한 **Aspose.BarCode for .NET** 라이선스(무료 체험판으로도 예제 실행 가능)  

프로젝트에 Aspose.BarCode NuGet 패키지를 추가합니다:

```bash
dotnet add package Aspose.BarCode
```

## C#에서 PDF417 바코드를 생성하는 방법?

`BarcodeGenerator`는 바코드 이미지를 생성하기 위한 주요 클래스입니다.  
`EncodeTypes.MacroPdf417`는 바코드 생성을 위해 Macro PDF417 심볼을 선택합니다.  
`Save`는 생성된 바코드를 이미지 파일에 기록합니다.

`EncodeTypes.MacroPdf417` 열거형과 대상 텍스트를 사용하여 `BarcodeGenerator`를 로드한 뒤 `Save`를 호출합니다 – 이것이 세 줄로 이루어진 전체 생성 흐름입니다. 생성기는 Unicode를 자동으로 처리하며, `using` 문은 이미지 저장 후 비관리 리소스가 해제되도록 보장합니다.

### 단계 1: 바코드 생성기 C# 인스턴스 만들기

`BarcodeGenerator` 클래스는 바코드 이미지를 생성하고 구성합니다.  

`EncodeTypes.MacroPdf417` 열거형 값과 인코딩하려는 텍스트를 사용해 `BarcodeGenerator`를 인스턴스화합니다. 텍스트에 Unicode 문자가 포함될 수 있으며, 라이브러리가 이를 자동으로 처리합니다.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*왜 중요한가*: `EncodeTypes.MacroPdf417`는 엔진에게 Macro PDF417 심볼을 생성하도록 지시하며, 이는 세그먼트 데이터와 추가 파일‑레벨 메타데이터를 지원합니다. `using` 문은 이미지 저장 후 비관리 리소스가 해제되도록 보장합니다.

### 단계 2: 기본 바코드 외관 정의

`XDimension.Pixels`는 각 바코드 모듈의 픽셀 크기를 설정합니다.

Macro PDF417 바코드는 정사각형 모듈로 구성됩니다. 모듈 크기와 열 수를 제어하면 가독성과 파일 크기에 영향을 줍니다.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*왜 중요한가*: `XDimension.Pixels`는 시각적 밀도를 결정합니다; 2 픽셀 값은 화면 표시에 적합하면서 이미지 크기를 작게 유지합니다. 레이아웃 제약에 맞게 열 수를 조정하면 더 많은 열이 더 넓고 짧은 바코드를 생성합니다.

### 단계 3: Macro PDF417 특정 메타데이터 설정

`MacroPdf417FileID`는 모든 바코드 세그먼트가 속한 파일을 식별합니다.

Macro PDF417는 표준 PDF417 형식에 필드를 추가해 여러 바코드 세그먼트에서 큰 파일을 재구성할 수 있게 합니다. 각 필드는 선택 사항이지만, 설정하면 API의 전체 기능을 보여줍니다.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*왜 중요한가*:  
- `MacroPdf417FileID`는 동일 논리 파일에 속하는 모든 세그먼트를 연결합니다.  
- `MacroPdf417SegmentID`와 `MacroPdf417SegmentsCount`는 디코더가 조각을 올바르게 재정렬하도록 합니다.  
- `MacroPdf417Checksum`은 전체 페이로드를 디코딩하지 않고도 빠른 무결성 검사를 제공합니다.  
- `MacroPdf417FileSize`와 `MacroPdf417TimeStamp`는 다운스트림 시스템이 재구성된 파일이 원본과 일치하는지 확인할 수 있게 합니다.  
- `MacroPdf417Addressee` / `MacroPdf417Sender`는 물류 또는 문서 교환 시나리오에서 유용합니다.  
- `MacroPdf417Terminator`를 `Set`으로 설정하면 이 바코드가 마지막 세그먼트임을 표시하여 재구성 알고리즘을 단순화합니다.

### 단계 4: 생성된 바코드 이미지 저장

`Save`는 바코드 이미지를 지정된 파일 경로에 기록합니다.

마지막으로 바코드를 PNG 파일로 저장합니다. 지원되는 형식(`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`) 중 원하는 것을 선택할 수 있습니다.

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*왜 중요한가*: PNG는 무손실 픽셀 데이터를 보존하여 스캐너가 구성한 정확한 모듈 패턴을 읽을 수 있게 합니다. 형식을 변경하면 시각적 품질 및 파일 크기에 영향을 줄 수 있습니다.

#### 예상 출력

전체 프로그램을 실행하면 **ExtPDF417Meta.png** 파일이 생성됩니다. 이미지를 열면 “Åspóse.Barcóde©” 텍스트가 인코딩된 직사각형 Macro PDF417 바코드가 표시되며, 시각적 밀도는 설정한 2‑픽셀 XDimension과 일치합니다. PDF417‑호환 리더로 이미지를 스캔하면 단계 3에서 정의한 모든 메타데이터 필드를 반환합니다.

## 전체 작업 예제

아래 코드를 새 콘솔 프로젝트(`dotnet new console`)에 복사하고 `YOUR_DIRECTORY`를 머신에 존재하는 절대 경로나 상대 경로로 교체하십시오.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

프로그램을 실행합니다(`dotnet run`). 실행 후 지정한 위치에 PNG 파일이 생성되었는지 확인하십시오. Macro PDF417를 지원하는 바코드‑읽기 앱을 사용해 메타데이터가 올바르게 삽입되었는지 확인합니다.

## 일반적인 변형 및 엣지 케이스

- **다른 이미지 형식**: 다운스트림 시스템이 다른 형식을 선호한다면 `BarCodeImageFormat.Png`를 `Jpeg`, `Bmp`, `Tiff` 등으로 교체하십시오.  
- **모듈 크기 변경**: 더 큰 `XDimension.Pixels` 값은 저해상도 스캐너에서 스캔 신뢰성을 향상시키지만 이미지 크기가 증가합니다.  
- **다중 세그먼트**: 다중 세그먼트 파일을 만들려면 일련의 바코드를 생성하고 각 바코드마다 `MacroPdf417SegmentID`를 증가시키며 `MacroPdf417FileID`는 동일하게 유지합니다. 마지막 세그먼트에만 `MacroPdf417Terminator`를 설정하십시오.  
- **Unicode 지원**: 생성기는 Unicode 문자를 자동으로 인코딩합니다; 외부 파일에서 읽는 경우 소스 문자열이 UTF-8 인코딩인지 확인하십시오.  
- **오류 처리**: `using` 블록을 try‑catch로 감싸서 잘못된 매개변수(예: 열 개수 범위 초과)에 대한 `BarCodeException`을 포착하십시오.

## 전문가 팁

- **성능**: 동일한 설정으로 다수의 바코드를 생성할 때 단일 `BarcodeGenerator` 인스턴스를 재사용하고, 저장 간에 `CodeText` 속성만 변경하십시오.  
- **파일 크기 추정**: `MacroPdf417FileSize` 필드는 원본 페이로드의 바이트 수와 일치해야 하며, 불일치 시 다운스트림 검증 실패를 일으킬 수 있습니다.  
- **테스트**: 생성된 바코드를 Aspose의 내장 디코더(`BarCodeReader`)와 타사 스캐너 모두로 검증하여 상호 운용성을 보장하십시오.

## 결론

이 **Aspose.BarCode** 예제는 전체 Macro 메타데이터 지원과 함께 **PDF417 바코드 C# 생성** 방법을 보여주며, 견고한 바코드 기반 데이터 교환 파이프라인을 구축하기 위한 탄탄한 기반을 제공합니다.

## 다음에 배워야 할 내용

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 리소스에는 단계별 설명과 함께 완전한 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 자체 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [Aspose.BarCode를 사용한 Compact PDF417 바코드 생성 방법](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET를 사용한 Code 16K 바코드 조용 영역 생성 방법](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Aspose.BarCode for .NET를 사용한 ITF-14 바코드 조용 영역 생성 방법](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**마지막 업데이트:** 2026-10-09  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose를 사용한 C에서 Pdf417 바코드 이미지 생성 방법](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Aspose.BarCode를 사용한 Compact PDF417 바코드 생성 방법](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [바코드 생성기 튜토리얼: Pdf417 바코드 생성 방법](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}