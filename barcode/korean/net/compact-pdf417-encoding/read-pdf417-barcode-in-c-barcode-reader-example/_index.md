---
category: general
date: 2026-08-03
description: C# BarCodeReader를 사용하여 이미지에서 PDF417 바코드를 읽기 – 다중 바코드 읽는 방법도 보여주는 완전한
  바코드 리더 예제.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: ko
lastmod: 2026-08-03
og_description: C# BarCodeReader 예제로 PDF417 바코드를 빠르게 읽어보세요. 이 단계별 가이드를 따라 매크로 PDF417를
  디코딩하고 이미지에서 여러 바코드를 읽어보세요.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C#에서 PDF417 바코드 읽기 – 완전한 바코드 리더 예제
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: C#에서 PDF417 바코드 읽기 – 바코드 리더 예제
url: /ko/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 PDF417 바코드 읽기 – 바코드 리더 예제

이미지에서 PDF417 바코드 데이터를 읽어야 한다면, 이 가이드는 **BarCodeReader** 클래스를 사용하여 C#에서 수행하는 방법을 보여줍니다. 매크로 PDF417를 처리하고 하나의 이미지에서 여러 바코드를 읽을 수 있는 바코드 리더 예제를 배울 수 있습니다.

바코드를 다룰 때는 다양한 이미지 소스, 조명 조건, 때로는 매크로 PDF417 세그먼트와 같은 복합 데이터와 마주하게 됩니다. 이 튜토리얼에서는 PDF417 바코드를 디코딩하고, 확장 필드를 추출하며, 동일한 사진에서 여러 바코드를 처리하는 데 필요한 모든 것을 다룹니다. 최종적으로 이미지 파일에서 바코드를 읽고 콘솔에 상세 정보를 출력하는 실행 가능한 콘솔 프로그램을 만들 수 있게 됩니다.

## 필요 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 SDK 이상이 설치되어 있음  
* `BarCodeReader`와 `DecodeType.MacroPdf417`를 제공하는 **Aspose.BarCode for .NET** NuGet 패키지 최신 버전(또는 호환 라이브러리)  
* PDF417 또는 매크로 PDF417 바코드가 포함된 이미지 파일(예시에서는 `ExtPDF417Meta.png` 사용)  
* Visual Studio 2022와 같은 코드 편집기 또는 IDE  

추가 서비스나 외부 API는 필요하지 않습니다.

## 바코드 읽기를 위한 프로젝트 설정

1. **새 콘솔 프로젝트 생성**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **바코드 라이브러리 추가**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **바코드 이미지 복사**  

   `ExtPDF417Meta.png`(또는 PDF417 바코드가 포함된 이미지)를 프로젝트 폴더에 넣습니다.  
   이 튜토리얼에서는 파일이 `YOUR_DIRECTORY/ExtPDF417Meta.png`에 있다고 가정합니다.

프로젝트가 이제 바코드 리더 예제를 컴파일하고 실행할 준비가 되었습니다.

## BarCodeReader로 PDF417 바코드 읽는 방법

솔루션의 핵심은 `using` 블록 안에서 `BarCodeReader` 인스턴스를 생성하고, `DecodeType.MacroPdf417`를 지정한 뒤, 감지된 모든 바코드를 순회하는 것입니다. 아래 코드는 `Program.cs`에 붙여넣을 수 있는 완전하고 독립적인 프로그램입니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**동작 원리**:  

* `DecodeType.MacroPdf417`는 리더에게 PDF417의 매크로 확장을 찾아서 파일 ID, 세그먼트 수, 타임스탬프와 같은 추가 메타데이터를 가져오도록 지시합니다.  
* `using` 문은 관리되지 않는 리소스(파일 핸들, 네이티브 디코딩 버퍼 등)가 즉시 해제되도록 보장합니다.  
* `foreach` 루프는 이미지에 포함된 **모든** 바코드를 자동으로 처리하여 *여러 바코드 읽기* 요구사항을 충족합니다.  

프로그램을 실행(`dotnet run`)하면 다음과 유사한 출력이 표시됩니다:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

이미지에 PDF417 바코드가 두 개 이상 포함되어 있으면, 루프는 각 바코드마다 별도의 블록을 출력하여 하나의 사진에서 **여러 바코드 읽기**를 시연합니다.

## 이미지에서 여러 바코드 읽기

동일한 `BarCodeReader` 인스턴스로 여러 종류의 바코드를 동시에 디코딩할 수 있습니다. 매크로 PDF417만이 아니라 일반 PDF417(또는 QR, Code128 등)까지 범위를 넓히려면 `DecodeType` 플래그를 조정하세요:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`*은 비트마스크이므로 지원되는 형식을 원하는 만큼 조합할 수 있습니다. 이 유연성 덕분에 스니펫은 제품 라벨, 티켓, 신분증 등 다양한 사용 사례에 적용 가능한 **바코드 리더 예제**가 됩니다.

## 매크로 PDF417 필드 안전하게 접근하기

매크로 PDF417는 풍부한 확장 속성을 제공하지만, 모든 바코드가 모든 필드를 포함하는 것은 아닙니다. 존재하지 않는 속성에 접근하면 `NullReferenceException`이 발생할 수 있습니다. 가장 안전한 방법은 각 속성을 출력하기 전에 확인하는 것입니다:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*중요 이유*: 실제 배포 환경에서는 매크로 데이터가 없는 일반 PDF417 바코드를 받을 수 있습니다. 방어적인 검사는 애플리케이션이 충돌 없이 계속 실행되도록 보장합니다.

## 흔히 겪는 문제와 모범 사례

| Issue | Why it happens | Recommended fix |
|-------|----------------|-----------------|
| 이미지 경로가 잘못됨 | `BarCodeReader`가 파일을 찾지 못해 디코딩 전에 파일‑없음 예외가 발생 | `Path.Combine`을 사용하고 `File.Exists`로 파일 존재 여부 확인 |
| 저해상도 이미지 | 디코더가 바코드 경계를 찾지 못해 감지가 0개가 됨 | 신뢰할 수 있는 결과를 위해 최소 300 dpi 해상도 제공 |
| 바코드가 45° 이상 회전 | 많은 라이브러리가 수직 방향을 전제로 함 | `reader.RecognitionOptions.RotateImage = true`를 활성화 |

## 다음에 배워야 할 내용은?


다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}