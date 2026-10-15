---
category: general
date: 2026-10-14
description: C#에서 console barcode scanner를 만들어 PDF417 바코드를 읽고, macro PDF417를 처리하며,
  하나의 이미지에서 여러 바코드를 디코딩합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: C#에서 console barcode scanner를 사용해 이미지에서 PDF417 및 macro PDF417 바코드를
  빠르게 읽는 방법을 제공합니다. 이 단계별 가이드는 하나의 사진에서 여러 바코드를 디코딩하는 방법을 보여줍니다.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C#에서 console barcode scanner 만들기 – 완전 가이드
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: C#에서 console barcode scanner 만들기 – PDF417 바코드 읽기 예제
url: /ko/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 콘솔 바코드 스캐너 만들기 C# – PDF417 바코드 읽기 예제

`BarCodeReader`는 이미지에서 바코드를 디코딩하고 자세한 메타데이터를 반환하는 Aspose.BarCode의 핵심 클래스입니다. 이미지에서 PDF417 바코드 데이터를 읽어야 한다면, 이 가이드는 C#에서 **BarCodeReader** 클래스를 사용하여 수행하는 방법을 보여줍니다. 또한 매크로 PDF417를 처리하고 하나의 이미지에서 여러 바코드를 읽을 수 있는 **콘솔 바코드 스캐너 만들기** 예제를 배울 수 있습니다.

바코드 작업은 종종 다양한 이미지 소스, 변화하는 조명 조건, 그리고 때때로 매크로 PDF417 세그먼트와 같은 복합 데이터를 다루는 것을 의미합니다. 이 튜토리얼은 PDF417 바코드를 디코딩하고 확장 필드를 추출하며 동일한 사진에서 여러 바코드를 처리하는 데 필요한 모든 것을 다룹니다. 최종적으로 이미지 파일에서 바코드를 읽고 콘솔에 자세한 정보를 출력하는 실행 가능한 콘솔 프로그램을 얻게 됩니다.

## 빠른 답변
- **예제는 무엇을 하나요?** 사진에서 PDF417 및 매크로 PDF417 바코드를 읽고 모든 디코딩된 필드를 출력하는 콘솔 바코드 스캐너를 생성합니다.  
- **필요한 라이브러리는?** Aspose.BarCode for .NET (NuGet).  
- **한 번에 여러 바코드를 읽을 수 있나요?** 예 – 리더가 이미지에서 발견된 모든 바코드를 순회합니다.  
- **인터넷 연결이 필요합니까?** 아니요, 라이브러리는 완전히 오프라인으로 작동합니다.  
- **지원되는 .NET 버전은?** .NET 6.0 이상.

## 필요 사항

* .NET 6.0 SDK 또는 이후 버전이 설치되어 있어야 합니다  
* `BarCodeReader`와 `DecodeType.MacroPdf417`를 제공하는 최신 **Aspose.BarCode for .NET** NuGet 패키지(또는 호환 라이브러리)  
* PDF417 또는 매크로 PDF417 바코드가 포함된 이미지 파일(예제에서는 `ExtPDF417Meta.png` 사용)  
* Visual Studio 2022와 같은 코드 편집기 또는 IDE  

추가 서비스나 외부 API는 필요하지 않습니다.

## 바코드 읽기를 위한 프로젝트 설정

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   `ExtPDF417Meta.png`(또는 PDF417 바코드가 포함된 이미지)를 프로젝트 폴더에 넣습니다.  
   이 튜토리얼에서는 파일이 `YOUR_DIRECTORY/ExtPDF417Meta.png`에 있다고 가정합니다.

프로젝트가 이제 바코드 리더 예제를 컴파일하고 실행할 준비가 되었습니다.

## C#에서 콘솔 바코드 스캐너를 만드는 방법은?

`BarCodeReader`는 Aspose.BarCode에서 제공하는 클래스이며 이미지에서 바코드를 읽고 디코딩된 데이터를 반환합니다.  
이미지를 `BarCodeReader`로 로드하고 디코드 유형을 `MacroPdf417`로 설정한 뒤 결과를 순회하면 콘솔 바코드 스캐너를 만들 수 있습니다. `using` 문 덕분에 리더가 네이티브 리소스를 자동으로 해제하므로 메모리를 수동으로 관리할 필요가 없습니다. 이 접근 방식은 PNG, JPEG, BMP 등 .NET이 지원하는 모든 이미지 형식에 적용됩니다.

### 단계별 안내

솔루션의 핵심은 `using` 블록 안에서 `BarCodeReader` 인스턴스를 생성하고 `DecodeType.MacroPdf417`를 지정한 뒤 감지된 모든 바코드를 순회하는 것입니다. 아래 코드는 `Program.cs`에 그대로 붙여넣을 수 있는 완전한 자체 포함 프로그램입니다.

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

**왜 이렇게 작동하나요**:  

* `DecodeType.MacroPdf417`는 리더에게 PDF417의 매크로 확장을 찾아야 함을 알려주며, 여기에는 파일 ID, 세그먼트 수, 타임스탬프와 같은 추가 메타데이터가 포함됩니다.  
* `using` 문은 파일 핸들 및 네이티브 디코딩 버퍼와 같은 관리되지 않는 리소스를 즉시 해제하도록 보장합니다.  
* `foreach` 루프는 이미지에 포함된 **모든** 바코드를 자동으로 처리하므로 *여러 바코드 읽기* 요구 사항을 충족합니다.  

프로그램을 실행하면(`dotnet run`) 다음과 유사한 출력이 표시됩니다:

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

이미지에 PDF417 바코드가 두 개 이상 포함된 경우, 루프는 각 바코드마다 별도의 블록을 출력하여 하나의 사진에서 **여러 바코드 읽기**를 시연합니다.

## 이미지에서 여러 바코드를 읽는 방법은?

단일 `BarCodeReader` 인스턴스를 사용하고 `DecodeType` 플래그에 감지하고자 하는 모든 형식을 포함하도록 설정합니다. 비트 OR 연산자를 사용해 플래그를 결합하면 한 번의 패스로 PDF417, QR, Code‑128 등 다양한 심볼을 탐지하도록 라이브러리에 지시할 수 있어 별도의 리더를 만들 필요가 없으며 처리 시간이 단축됩니다.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`*은 비트마스크이므로 지원되는 형식은 원하는 만큼 조합할 수 있습니다. Aspose.BarCode는 QR, DataMatrix, Code‑128, UPC‑A 등을 포함한 **30개 이상의 바코드 심볼**을 지원하므로 제품 라벨링, 티켓 검증, 신원 확인 등 다양한 사용 사례를 단일 스캐너로 처리할 수 있습니다.

## 매크로 PDF417이 무엇이며 해당 필드를 안전하게 접근하는 방법은?

매크로 PDF417은 대용량 데이터를 여러 바코드 심볼에 걸쳐 분할할 수 있게 해주는 PDF417 확장입니다.  
매크로 PDF417은 풍부한 확장 속성을 추가하지만, 모든 바코드에 모든 필드가 포함되는 것은 아닙니다. 누락된 속성에 접근하면 `NullReferenceException`이 발생할 수 있습니다. 가장 안전한 방법은 각 속성을 출력하기 전에 존재 여부를 확인하여 매크로 데이터가 없을 때도 애플리케이션이 안정적으로 동작하도록 하는 것입니다.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*왜 이것이 중요한가*: 실제 배포 환경에서는 매크로 데이터가 없는 일반 PDF417 바코드를 받을 수 있습니다. 방어적 검사는 애플리케이션이 충돌 없이 계속 실행되도록 보장합니다.

## 일반적인 함정 및 모범 사례

| 문제 | 발생 원인 | 권장 해결책 |
|-------|----------------|-----------------|
| 이미지 경로가 올바르지 않음 | `BarCodeReader`가 디코딩 전에 파일‑존재‑안함 예외를 발생시킴 | `Path.Combine`을 사용하고 `File.Exists`로 파일 존재 여부를 확인 |
| 저해상도 이미지 | 디코더가 바코드 가장자리를 찾지 못해 탐지 결과가 0개가 됨 | 신뢰할 수 있는 결과를 위해 최소 300 dpi 해상도 제공 |
| 바코드가 45° 이상 회전됨 | 많은 라이브러리가 수직 방향을 전제로 함 | 이미지가 회전될 가능성이 있으면 `reader.RecognitionOptions.RotateImage = true` 활성화 |
| 매크로 필드 누락 | null 속성을 읽으려 하면 충돌 발생 | 매크로 속성에 접근하기 전에 항상 `null` 여부 확인 |
| 대량 배치 처리 | 각 파일마다 리더를 새로 생성하면 오버헤드 증가 | 많은 이미지를 처리할 때는 스트림을 교체하면서 단일 `BarCodeReader` 인스턴스 재사용 |

## 콘솔 바코드 스캐너에 Aspose.BarCode를 사용하는 이유

Aspose.BarCode는 **30개 이상의 바코드 유형**을 디코딩할 수 있으며, 전체 파일을 메모리에 로드하지 않고도 **200 MP**까지의 이미지를 처리하여 일반적인 3.2 GHz CPU에서 **초당 150프레임**의 처리량을 달성합니다. 이러한 정량화된 성능은 지연 시간과 정확성이 중요한 고볼륨 온프레미스 스캔 솔루션에 신뢰할 수 있는 선택이 됩니다.

## 다음에 배워야 할 내용은?

다음 튜토리얼은 이 가이드에서 소개한 기술을 기반으로 하며, 단계별 설명과 완전한 코드 예제를 포함하여 추가 API 기능을 마스터하고 자체 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [Aspose.BarCode for .NET으로 DataMatrix 바코드 읽는 방법](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix 바코드 읽기 C# – DataMatrix 모드 자동 생성](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [이미지에서 바코드 읽기 – Aspose.BarCode와 함께 Java에서 바코드 영역 추출 마스터](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## 자주 묻는 질문

**Q: 이 스캐너를 실제 운영 환경에서 사용할 수 있나요?**  
A: 예. 평가용 워터마크를 제거하고 전체 지원을 받으려면 상용 Aspose.BarCode 라이선스를 구매하십시오.

**Q: 라이브러리가 Linux와 macOS에서도 작동하나요?**  
A: 물론입니다. Aspose.BarCode for .NET은 크로스‑플랫폼이며 Windows, Linux, macOS에서 .NET 6+로 실행됩니다.

**Q: 매우 큰 이미지를 메모리 부족 없이 처리하려면 어떻게 해야 하나요?**  
A: `LoadOptions` 생성자를 사용해 스트리밍 모드를 활성화하면 이미지를 전체를 RAM에 로드하지 않고 청크 단위로 처리할 수 있습니다.

**Q: 암호화되거나 비밀번호로 보호된 이미지를 디코드할 수 있나요?**  
A: 리더는 표준 PNG/JPEG 비밀번호 스키마로 암호화된 이미지를 처리할 수 있으며, `reader.ImagePassword`에 비밀번호를 제공하면 됩니다.

**Q: 바코드가 일부 손상된 경우는 어떻게 해야 하나요?**  
A: `reader.RecognitionOptions.CorrectErrors = true`와 같은 오류 정정 옵션을 활성화하면 손상이나 노이즈에 대한 복원력이 향상됩니다.

**마지막 업데이트:** 2026-10-14  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [C에서 Pdf417 읽기 – 완전한 바코드 리더 예제](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Pdf417와 함께 C에서 다중 바코드 읽기 – 완전 가이드](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [이미지에서 바코드 디코드 – C 바코드 리더 예제](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}