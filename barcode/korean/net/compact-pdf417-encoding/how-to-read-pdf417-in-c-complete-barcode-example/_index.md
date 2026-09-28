---
category: general
date: 2026-07-27
description: C#에서 PDF417 바코드를 빠르게 읽는 방법. 여러 바코드를 읽고, 이미지를 디코딩하며, 전체 C# 바코드 예제에서 매크로
  PDF417 메타데이터를 얻는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: ko
lastmod: 2026-07-27
og_description: 이 단계별 가이드를 통해 C#에서 PDF417 바코드를 읽는 방법. 이미지를 디코딩하고, 여러 바코드를 처리하며, 실행
  가능한 예제에서 Macro PDF417 메타데이터를 추출합니다.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: C#에서 PDF417 읽는 방법 – 전체 바코드 예제
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: C#에서 PDF417 읽는 방법 – 완전한 바코드 예제
url: /ko/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 PDF417 읽기 – 완전한 바코드 예제

머리카락을 뽑지 않고 C# 애플리케이션에서 **PDF417을 읽는 방법**을 궁금해 본 적 있나요? 당신만 그런 것이 아닙니다. 물류 스캐너를 만들든, 티켓 검증기를 만들든, 혹은 PDF417로 인코딩된 ID에서 데이터를 추출해야 하든, 처음에는 과정이 다소 신비롭게 느껴질 수 있습니다.  

이 튜토리얼에서는 PDF417 이미지를 읽고, **read multiple barcodes**가 존재하면 처리하며, 필요할 수 있는 모든 유용한 Macro PDF417 메타데이터를 추출하는 **c# barcode example**을 단계별로 살펴보겠습니다.

## 만들게 될 것

이 가이드를 마치면 다음과 같은 작은 콘솔 프로그램을 갖게 됩니다:

1. 디스크에서 바코드 이미지를 로드합니다.  
2. **PDF417**(Macro PDF417 포함) 바코드를 디코딩합니다.  
3. 코드 유형 및 텍스트와 같은 기본 정보를 출력합니다.  
4. Macro PDF417 필드 전체(파일 ID, 세그먼트 ID, 체크섬 등)를 출력합니다.  

외부 서비스 없이, 단일 NuGet 패키지와 몇 줄의 C# 코드만으로 구현됩니다.

## 사전 요구 사항 – 시작하기 전에 필요한 것

- **.NET 6.0** 이상(코드는 .NET Framework 4.6+에서도 작동합니다).  
- 최근 버전의 **Aspose.BarCode for .NET** 라이브러리 – NuGet을 통해 설치합니다(`Install-Package Aspose.BarCode`).  
- PDF417 바코드를 포함한 이미지 파일(데모에서는 `ExtPDF417Meta.png` 사용).  
- C# 콘솔 앱에 대한 기본 이해(“Hello World”를 작성해 본 적이 있으면 충분합니다).

> **Pro tip:** PDF417 샘플이 없으면 Aspose 데모 사이트에서 생성하거나 PDF417 태그를 만들 수 있는 스마트폰 앱을 사용하세요.

## Step 1: 프로젝트 설정 및 라이브러리 설치

먼저, 새 콘솔 프로젝트를 생성합니다:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

이렇게 하면 필요한 **c# barcode example** 의존성이 가져와집니다. `Program.cs`를 열고 기본 코드를 아래 스켈레톤으로 교체합니다:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Step 2: PDF417용 바코드 리더 초기화

솔루션의 핵심은 `BarCodeReader` 클래스입니다. 스캔할 파일과 관심 있는 바코드 유형을 지정합니다—이 경우 `DecodeType.Pdf417` 또는 매크로 변형인 `DecodeType.MacroPdf417`입니다. 매크로 유형을 사용하면 확장 필드를 캡처할 수 있습니다.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

`MacroPdf417`를 일반 `Pdf417` 대신 사용하는 이유는 무엇일까요? Macro PDF417는 파일 ID, 세그먼트 수, 타임스탬프 등 많은 실제 애플리케이션에서 의존하는 추가 메타데이터를 포함합니다—예를 들어 여러 페이지에 걸친 운송 목록을 생각해 보세요.

## Step 3: 이미지에서 발견된 모든 바코드 읽기

하나의 이미지에 **read multiple barcodes**가 포함될 수 있습니다—예를 들어 PDF417 옆에 QR 코드가 있을 수 있습니다. `ReadBarCodes()` 메서드는 `IEnumerable<BarCodeResult>`를 반환하며, 이를 반복해서 사용할 수 있습니다.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

이미지에 PDF417이 하나만 있더라도 루프는 한 번 실행되므로, 향후 동일한 스캔에서 **read multiple barcodes**가 필요할 경우에도 코드를 유연하게 유지할 수 있습니다.

## Step 4: 기본 바코드 정보 표시

매크로 필드로 들어가기 전에 바코드 유형과 디코딩된 텍스트를 표시하는 것이 유용합니다. 이를 통해 리더가 실제로 PDF417을 인식했는지, 다른 심볼리지를 인식했는지 확인할 수 있습니다.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName`은 매크로 플래그가 설정되지 않은 경우 *Pdf417* 대신 *MacroPdf417*를 반환하고, `CodeText`는 바코드에 인코딩된 원시 데이터를 포함합니다.

## Step 5: Macro PDF417 메타데이터 추출

`Extended` 속성은 PDF417 전용 구조에 대한 깊은 정보를 제공합니다. 아래에 출력하는 각 필드는 PDF417 매크로 사양에 직접 대응합니다.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

각 라인은 매크로 페이로드의 서로 다른 조각을 가져옵니다:

- **FileID** – 전체 문서 세트에 대한 고유 식별자.  
- **SegmentID** – 다중 세그먼트 파일 중 현재 보고 있는 부분.  
- **SegmentsCount** – 예상되는 전체 세그먼트 수.  
- **FileName, Checksum, FileSize** – 전송된 파일의 무결성을 검증하는 데 유용.  
- **TimeStamp, Addressee, Sender** – 많은 물류 시스템이 포함하는 선택적 필드.  

소스 바코드에 이러한 필드 중 일부가 없으면 라이브러리는 `null` 또는 `0`을 반환하며, 필요에 따라 처리하면 됩니다.

## Step 6: 전체 예제 실행

모두 합치면, 다음은 완전한 실행 가능한 프로그램입니다:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 예상 출력

유효한 `ExtPDF417Meta.png`에 대해 프로그램을 실행하면 다음과 유사한 결과가 표시됩니다:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

이미지에 하나 이상의 바코드가 포함된 경우,

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료에는 단계별 설명과 함께 완전한 작동 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 자체 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}