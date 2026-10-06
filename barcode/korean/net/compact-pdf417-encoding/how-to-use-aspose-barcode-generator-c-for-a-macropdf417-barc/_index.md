---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C#를 사용하면 매크로 데이터를 추가하고 PDF417 바코드를 손쉽게 생성할 수
  있습니다. 매크로 메타데이터를 추가하고 PDF417 이미지를 만드는 방법을 단계별로 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: ko
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C#는 매크로 메타데이터를 추가하고 몇 줄의 코드로 PDF417 바코드를
  생성하는 방법을 보여줍니다.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose 바코드 생성기 C# – 매크로 추가 및 PDF417 바코드 생성
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Aspose Barcode Generator C#를 사용하여 MacroPdf417 바코드 만드는 방법
url: /ko/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Generator C#를 사용하여 MacroPdf417 바코드 사용하는 방법

C#에서 MacroPdf417 바코드를 생성해야 한다면, **Aspose Barcode Generator C#**는 바코드 이미지와 필요한 매크로 메타데이터를 모두 처리하는 간결한 API를 제공합니다. 이 튜토리얼에서는 매크로 정보를 추가하고 몇 단계만으로 PDF417 바코드 이미지를 생성하는 방법을 정확히 보여줍니다.

시각적 매개변수를 구성하고, 파일 ID와 타임스탬프와 같은 매크로 필드를 삽입하며, 결과를 PNG로 저장하는 방법을 배웁니다. 외부 도구는 필요 없으며, Aspose.BarCode 라이브러리와 .NET 개발 환경만 있으면 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 설치되어 있는지 확인하세요:

* .NET 6.0 이상 설치  
* Visual Studio 2022 (또는 기타 C# IDE)  
* **Aspose.BarCode for .NET** 라이선스 또는 평가판  

라이브러리가 플랫폼에 구애받지 않기 때문에 코드는 Windows, Linux, macOS 모두에서 작동합니다.

## 단계 1: Aspose.BarCode NuGet 패키지 설치

Visual Studio에서 프로젝트를 연 다음 **Package Manager Console**에서 다음 명령을 실행합니다:

```powershell
Install-Package Aspose.BarCode
```

이 명령은 `Aspose.BarCode` 어셈블리와 해당 종속성을 프로젝트에 추가합니다.

## 단계 2: 바코드 생성기 인스턴스 만들기

첫 번째 줄은 **MacroPdf417** 심볼을 사용하고 인코딩할 텍스트를 지정하는 `BarcodeGenerator` 객체를 생성합니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*왜 중요한가*: `EncodeTypes.MacroPdf417` 값은 라이브러리에게 매크로 관련 필드가 필요함을 알려 주며, 다음 단계에서 해당 필드를 설정하게 됩니다.

## 단계 3: 시각적 모양 정의

각 모듈(가장 작은 검은색 또는 흰색 사각형)의 크기와 PDF417 매트릭스의 열 수를 제어할 수 있습니다. `XDimension`을 조정하면 전체 이미지 해상도에 영향을 줍니다.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

`Columns` 값을 늘리면 바코드 높이가 감소하고, `XDimension` 값을 크게 하면 고 DPI 화면에서 이미지가 더 선명해집니다.

## 단계 4: 매크로 메타데이터 추가 (매크로 추가 방법)

MacroPdf417은 원본 파일과 세그먼테이션을 설명하는 여러 추가 필드가 필요합니다. 다음 속성들은 PDF417 매크로 사양에 직접 매핑됩니다:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*왜 이러한 필드인가*:  
* `MacroPdf417FileID`는 모든 세그먼트를 연결하여 스캐너가 원본 문서를 재조합할 수 있게 합니다.  
* `MacroPdf417SegmentID`와 `MacroPdf417SegmentsCount`는 디코더에게 순서와 전체 파트 수를 알려 줍니다.  
* `MacroPdf417FileSize`와 `MacroPdf417Checksum`은 무결성 검사를 제공하며, 대용량 데이터 전송에 유용합니다.

## 단계 5: 바코드 이미지 저장 (pdf417 생성 방법)

마지막으로 바코드를 디스크에 저장합니다. `Save` 메서드는 파일 경로와 이미지 형식을 받으며, PNG는 압축 아티팩트 없이 바코드의 선명한 가장자리를 유지합니다.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

프로그램이 실행되면 출력 폴더에 **ExtPDF417Meta.png** 파일이 생성됩니다. 이미지를 열면 인쇄하거나 PDF에 삽입할 준비가 된 깨끗한 MacroPdf417 바코드를 확인할 수 있습니다.

### 예상 출력

| 파일 이름          | 포맷 | 크기(대략) |
|--------------------|------|------------|
| ExtPDF417Meta.png  | PNG  | 300 × 150 px (`XDimension`에 따라 다름) |

PDF417 호환 리더(e.g., ZXing, Aspose.BarCode for .NET)로 이미지를 스캔하면 원본 텍스트 **“Åspóse.Barcóde©”**와 함께 모든 매크로 필드가 반환됩니다.

## 일반적인 함정 및 회피 방법

| 문제 | 발생 원인 | 해결 방법 |
|------|----------|-----------|
| **잘못된 `EncodeTypes`** | `EncodeTypes.Pdf417`을 사용하면 매크로 필드가 비활성화됩니다. | 항상 `EncodeTypes.MacroPdf417`으로 생성자를 호출하세요. |
| **매크로 필드 누락** | 필수 매크로 필드가 없으면 일부 스캐너가 바코드를 무시합니다. | 최소 `FileID`, `SegmentID`, `SegmentsCount`, `Terminator`를 채우세요. |
| **`XDimension`이 너무 작음** | 1픽셀 미만 값은 저해상도 화면에서 읽을 수 없는 바코드를 만들 수 있습니다. | 대부분의 화면 및 인쇄 상황에서 `XDimension`을 2픽셀 이상으로 유지하세요. |
| **파일 경로 오류** | 존재하지 않는 상대 경로를 제공하면 예외가 발생합니다. | `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` 또는 절대 경로를 사용하세요. |

## 전체 소스 코드

아래는 새 콘솔 프로젝트에 복사해 사용할 수 있는 완전하고 실행 가능한 예제입니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

프로그램을 실행(`dotnet run`)하면 콘솔에 성공 메시지가 출력되고 PNG 파일이 프로젝트 출력 폴더에 생성됩니다.

## 다음 단계

* **대용량 데이터 인코딩** – 더 많은 문자를 담기 위해 `Columns`를 늘리거나 `Pdf417.Rows`(via `Pdf417.Rows`)를 조정하세요.  
* **PDF에 삽입** – Aspose.PDF를 사용해 생성된 PNG를 문서에 배치합니다.  
* **스캔 검증** – `Aspose.BarCode.Reader`를 활용해 바코드를 디코딩하고 매크로 필드를 프로그래밍 방식으로 확인합니다.  

이러한 주제를 탐구하면 **PDF417 바코드 생성** 방법을 깊이 이해하고, 배치 문서 처리나 보안 데이터 교환과 같은 실제 시나리오에 대비할 수 있습니다.

---

*코딩을 즐기세요! 이 가이드가 도움이 되었다면 팀원과 공유하거나 GitHub에서 Aspose.BarCode 저장소에 ⭐를 눌러 주세요.*

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [C#에서 Aspose.BarCode를 사용해 매크로 PDF417 바코드 만들기](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Barcode Generator를 사용해 C#에서 PDF417 바코드 생성하기](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode 예제: C#에서 매크로 PDF417 생성](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}