---
category: general
date: 2026-08-15
description: BarCodeReader를 사용하여 C#에서 이미지의 바코드를 읽습니다. C#에서 여러 바코드를 읽는 방법, PDF417 바코드
  읽기, 그리고 전체 C# BarCodeReader 예제를 확인하세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: ko
lastmod: 2026-08-15
og_description: C#에서 이미지의 바코드를 단계별 가이드와 함께 읽어보세요. C#으로 여러 바코드를 읽는 방법, PDF417 심볼을 디코딩하는
  방법, 그리고 완전한 C# BarCodeReader 예제를 실행하는 방법을 확인하세요.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: C#에서 이미지의 바코드 읽기 – BarCodeReader 튜토리얼
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: C#에서 이미지의 바코드 읽기 – BarCodeReader 튜토리얼
url: /ko/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 이미지에서 바코드 읽기 (C#) – BarCodeReader 튜토리얼

.NET 애플리케이션에서 **이미지에서 바코드 읽기**가 필요하다면, 이 가이드는 `BarCodeReader` 클래스를 사용하여 정확히 수행하는 방법을 보여줍니다. 또한 **C#에서 다중 바코드 읽기**, PDF417 심볼 디코딩, 그리고 프로젝트에 복사할 수 있는 완전한 **C# BarCodeReader 예제**를 확인할 수 있습니다.

이 튜토리얼은 NuGet 패키지 추가부터 확장된 PDF417 필드 출력까지 모든 단계를 다루므로, 실행 가능한 콘솔 프로그램을 완성할 수 있습니다. 외부 문서는 필요 없으며, 모든 코드와 설명이 포함되어 있습니다.

## 필요 사항

시작하기 전에 다음을 확인하십시오:

* .NET 6.0 SDK 또는 그 이후 버전 (코드는 .NET Core 및 .NET Framework에서도 작동합니다)
* Visual Studio 2022 또는 C# 호환 편집기
* `Aspose.BarCode` NuGet 패키지 (또는 `BarCodeReader`를 제공하는 동등한 라이브러리)
* Macro PDF417 바코드가 포함된 이미지 파일 (예: `ExtPDF417Meta.png`)

이러한 사전 요구 사항을 갖추면 추가 설정 없이 샘플을 컴파일할 수 있습니다.

## BarCodeReader를 사용하여 이미지에서 바코드 읽기

첫 번째 단계는 이미지 파일을 가리키고 라이브러리에 검색할 바코드 유형을 알려주는 `BarCodeReader` 인스턴스를 만드는 것입니다.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**왜 작동하나요:**  
`BarCodeReader`는 이미지를 열고 지정된 `DecodeType`을 스캔하여 `BarCodeResult` 객체 컬렉션을 반환합니다. 각 결과는 일반 바코드 데이터(`CodeTypeName`, `CodeText`)와 Macro PDF417의 경우 표준에 정의된 모든 추가 필드를 노출하는 `Extended.Pdf417` 객체를 포함합니다.

## 단일 이미지에서 C#으로 다중 바코드 읽기

이미지에 하나 이상의 바코드가 포함된 경우가 있습니다(예: PDF417 옆에 QR 코드). 이러한 상황을 처리하려면 명시적인 `DecodeType`을 생략하거나 `DecodeType.AllSupported`를 전달하고 결과를 반복하면 됩니다.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**왜 필요한가요:**  
`AllSupported`를 지정하면 엔진이 알고 있는 모든 바코드 형식을 시도하도록 하여 이미지 내 모든 심볼을 포착할 수 있습니다. 바코드 유형을 사전에 예측할 수 없을 때 권장되는 접근 방식입니다.

## C#을 사용하여 PDF417 바코드 읽는 방법

클래식 PDF417(비매크로) 형식만 필요하다면 `DecodeType`을 `Pdf417`로 변경하십시오. 나머지 코드는 동일하지만 확장 필드는 사용할 수 없습니다.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**왜 중요한가요:**  
클래식 PDF417은 매크로 전용 속성을 노출하지 않으므로 `Extended.Pdf417` 블록이 필요 없습니다. 정확한 `DecodeType`을 사용하면 라이브러리가 지원되지 않는 알고리즘을 건너뛰어 스캔 속도가 빨라집니다.

## 복사해서 사용할 수 있는 전체 C# BarCodeReader 예제

아래는 세 가지 시나리오를 하나의 실행하기 쉬운 콘솔 애플리케이션으로 결합한 전체 프로그램입니다. `YOUR_DIRECTORY/ExtPDF417Meta.png`를 이미지의 실제 경로로 교체하십시오.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### 예상 출력

샘플 이미지에 Macro PDF417 바코드가 포함된 경우 콘솔에 다음과 유사한 내용이 출력됩니다:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

이미지에 일반 PDF417만 포함된 경우 “Macro PDF417” 섹션은 비어 있고, “Classic PDF417” 섹션에 디코딩된 텍스트가 표시됩니다.

## 결론

이제 `BarCodeReader`를 사용하여 C#에서 **이미지에서 바코드 읽기**, 단일 파일에서 **C#으로 다중 바코드 읽기**, 그리고 **PDF417 바코드 읽기**(매크로 및 클래식 변형 모두)의 정확한 단계를 알게 되었습니다. 전체 **C# BarCodeReader 예제**는 모든 .NET 프로젝트에 붙여넣을 준비가 되었으며, 다른 형식을 처리하거나 더 큰 이미지 처리 파이프라인에 통합하도록 확장할 수 있습니다.

**다음 단계**

* `reader` 블록 주변에 `try / catch`와 같은 오류 처리 패턴을 탐색하십시오.  
* 감지 속도와 정확성을 조정하기 위해 `ReaderParameters` 객체를 실험해 보십시오.  
* 바코드 읽기를 이미지 전처리 라이브러리와 결합하십시오 (

## 다음에 배워야 할 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 리소스에는 단계별 설명과 함께 완전한 작동 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 자체 프로젝트에서 대체 구현 방법을 탐색하는 데 도움이 됩니다.

- [Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드 읽는 방법](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix 바코드 C# 읽기 – DataMatrix 모드 자동 생성](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [이미지에서 바코드 읽기 – Aspose.BarCode와 함께 Java에서 바코드 영역 추출 마스터하기](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}