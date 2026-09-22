---
category: general
date: 2026-07-18
description: Aspose.BarCode for .NET을 사용하여 텍스트가 포함된 바코드를 생성합니다. PDF417 바코드 생성 방법,
  매크로 옵션 설정 및 PNG 이미지 내보내기에 대해 알아보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: ko
lastmod: 2026-07-18
og_description: C#에서 텍스트와 함께 바코드를 빠르게 생성하세요. 이 단계별 튜토리얼에서는 PDF417 바코드 생성, 매크로 설정 구성,
  PNG로 저장하는 방법을 보여줍니다.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: 텍스트와 함께 바코드 생성 – 마스터 PDF417 매크로 생성
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: 텍스트와 함께 바코드 생성 – 전체 PDF417 매크로 가이드
url: /ko/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 텍스트가 포함된 바코드 생성 – 전체 PDF417 매크로 가이드

맞춤 텍스트를 포함하는 **PDF417** 바코드를 생성하는 방법이 궁금하셨나요? 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 **텍스트가 포함된 바코드 생성** 방법을 정확히 보여드리며, 매크로 PDF417 심볼에 필요한 모든 설정을 단계별로 안내합니다. 불필요한 내용 없이 바로 프로젝트에 적용할 수 있는 완전한 실행 예제를 제공합니다.

다음 내용을 다룹니다:

* 필요한 NuGet 패키지와 using 지시문.  
* Unicode 문자를 포함하는 바코드 생성기 만드는 방법.  
* 모듈 크기, 열 개수, 매크로‑전용 ID 설정.  
* 결과를 PNG 파일로 저장하고 출력 확인하기.  

끝까지 진행하면 인보이스, 티켓 또는 기계가 읽을 수 있는 구간이 필요한 모든 문서에 삽입할 수 있는 사용 준비가 된 Macro PDF417 바코드 PNG 이미지를 얻게 됩니다.

---

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

| 요구 사항 | 이유 |
|-------------|--------|
| **.NET 6.0** 이상 | Aspose.BarCode는 .NET Standard 2.0+을 지원하므로 .NET 6은 최신 런타임을 제공합니다. |
| **Visual Studio 2022** (또는 기타 C# IDE) | 편리한 편집 및 디버깅을 위해. |
| **Aspose.BarCode for .NET** NuGet 패키지 | 바코드를 실제로 생성하는 라이브러리입니다. `dotnet add package Aspose.BarCode` 명령으로 설치하세요. |
| 출력 폴더에 대한 **쓰기 권한** | `Save` 메서드가 PNG 파일을 쓰기 위해 필요합니다. |

이 중 익숙하지 않은 것이 있다면 잠시 멈춰서 준비하세요—그렇지 않으면 코드가 명백한 예외를 발생시킵니다.

---

## 단계 1 – 라이브러리 설치 및 가져오기

먼저, 프로젝트에 NuGet 패키지를 추가합니다:

```bash
dotnet add package Aspose.BarCode
```

그 다음, 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **팁:** Visual Studio를 사용 중이라면 프로젝트를 마우스 오른쪽 버튼으로 클릭 → *Manage NuGet Packages* → *Aspose.BarCode*를 검색하고 최신 안정 버전을 설치하세요.

---

## 단계 2 – 사용자 지정 텍스트로 바코드 생성기 만들기

*주요* 작업은 “Å”, “©”와 같은 특수 문자를 포함한 **텍스트가 포함된 바코드 생성**입니다. 생성자의 인수는 인코드 타입과 원시 데이터 문자열입니다:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

왜 중요한가: `EncodeTypes.MacroPdf417`는 매크로 버전을 원한다는 것을 Aspose에 알려주며, 이를 통해 큰 메시지를 여러 심볼에 나눌 수 있습니다. 텍스트 문자열은 任意의 UTF‑8 시퀀스가 될 수 있으며, Aspose가 내부적으로 변환을 처리합니다.

---

## 단계 3 – 기본 외관 조정 (모듈 크기)

바코드의 “모듈”은 가장 작은 검은색·흰색 사각형입니다. 픽셀 크기를 설정하면 데이터 밀도는 그대로 두고 전체 이미지 크기를 제어합니다:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

인쇄용으로 더 큰 이미지가 필요하면 값을 4 또는 6으로 올리세요. 단, 모듈이 커지면 최종 PNG 파일 크기도 증가한다는 점을 기억하세요.

---

## 단계 4 – Macro PDF417 전용 옵션 설정

Macro PDF417는 스캐너가 여러 심볼을 이어 붙일 수 있도록 두 개의 식별자를 추가합니다. 일반적으로 다음을 설정합니다:

| 속성 | 설명 |
|----------|--------------|
| `Columns` | 심볼당 데이터 열 수 (폭에 영향). |
| `MacroPdf417FileID` | 전체 매크로 파일에 대한 고유 ID (≤ 2³¹‑1이어야 함). |
| `MacroPdf417SegmentID` | 현재 세그먼트의 인덱스 (0‑254). |

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Edge‑case note:** `MacroPdf417FileID`는 동일 논리 파일의 모든 세그먼트에서 동일해야 합니다. 여러 세그먼트를 생성한다면 동일한 ID를 재사용하지 않으면 결합할 수 없는 별개의 심볼이 생성됩니다.

---

## 단계 5 – 바코드를 PNG 이미지로 저장

이제 모든 설정이 완료되었으니 이미지를 디스크에 기록합니다:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save` 메서드는 DPI와 색상 깊이를 자동으로 처리해 PNG를 생성합니다. 실행 후 파일을 열면 다음과 같은 화면을 확인할 수 있습니다:

![텍스트가 포함된 바코드 생성 예시](/images/barcode-example.png){.center alt="텍스트가 포함된 바코드 생성 예시"}

바코드가 보이지 않으면 폴더가 존재하는지, 애플리케이션에 쓰기 권한이 있는지 다시 확인하세요.

---

## 전체 실행 가능한 예제

아래 전체 코드를 새 콘솔 앱(`dotnet new console`)에 복사하고 실행하세요. `C:\Barcodes` 폴더에 PNG가 생성됩니다(먼저 폴더를 만들고 실행).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**예상 출력** (콘솔):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

그리고 PNG에는 “Åspóse.Barcóde©” 텍스트가 포함된 컴팩트한 Macro PDF417 심볼이 표시됩니다.

---

## 일반적인 질문 및 함정

| 질문 | 답변 |
|----------|--------|
| *다른 이미지 형식을 사용할 수 있나요?* | 물론입니다—`BarCodeImageFormat.Png`를 `Jpeg`, `Bmp`, `Gif` 중 하나로 교체하면 됩니다. PNG는 무손실이므로 기본값으로 사용합니다. |
| *여러 개의 세그먼트가 필요하면 어떻게 하나요?* | `BarcodeGenerator`를 세그먼트마다 새로 만들고, `MacroPdf417FileID`는 동일하게 유지하며, `MacroPdf417SegmentID`를 (0‑254) 범위에서 증가시킵니다. |
| *텍스트에 이모지가 포함되어 있는데 작동하나요?* | Aspose.BarCode는 UTF‑8을 지원하므로 대부분의 이모지는 정상적으로 처리됩니다. 다만 대상 스캐너가 이를 디코딩할 수 있는지 확인하세요; 많은 산업용 스캐너는 알파벳·숫자 데이터만 처리합니다. |
| *라벨에 비해 바코드가 너무 넓어요.* | `Columns`를 줄이거나 모듈 크기를 늘리세요. 열 수를 줄이면 더 좁은 심볼이 되지만, 더 높은 DPI 프린터가 필요할 수 있습니다. |
| *라이선스가 필요합니까?* | 무료 평가 라이선스로 테스트는 가능하지만 작은 워터마크가 추가됩니다. 상용 환경에서는 워터마크 제거와 전체 기능 사용을 위해 라이선스를 구매하세요. |

---

## 다음 단계

이제 **PDF417** 바코드를 사용자 지정 텍스트와 함께 생성하는 방법을 알았으니 다음을 시도해 볼 수 있습니다:

* **Decode**: Aspose.BarCode의 `BarCodeReader`를 사용해 모바일 앱에서 바코드 디코딩.  
* **Combine**: 여러 매크로 세그먼트를 하나의 PDF 문서로 결합해 일괄 인쇄.  
* **Explore other symbologies** (QR, DataMatrix): 유사한 파라미터 패턴으로 다른 심볼 탐색.  
* **Adjust error correction level**: `Pdf417.ErrorCorrectionLevel`를 사용해 가혹한 환경에 맞게 오류 정정 수준 조정.  

이러한 주제들은 방금 배운 핵심 개념을 기반으로 하므로 전환이 자연스럽습니다.

---

## 결론

우리는 Aspose.BarCode for .NET을 사용해 **텍스트가 포함된 바코드 생성**과 특히 **PDF417 매크로 심볼 생성**을 위한 완전한 엔드‑투‑엔드 솔루션을 단계별로 살펴보았습니다. X‑dimension, 열 개수, 매크로 ID를 설정하면 크기, 레이아웃, 다중 세그먼트 처리에 대한 완전한 제어가 가능합니다. 생성된 PNG는 인쇄하거나 PDF에 삽입하거나 스캐너에 바로 전달할 수 있습니다.

한 번 시도해 보고 매개변수를 조정해 보세요. 비즈니스에 맞는 바코드 활용이 가능해집니다. 문제가 발생하면 Aspose 문서와 커뮤니티 포럼이 훌륭한 추가 자료가 됩니다. 즐거운 코딩 되세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하여 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 대체 구현 방법을 탐색하도록 돕습니다.

- [PDF417 바코드 생성 방법 – Compact PDF417 인코딩](/barcode/english/net/compact-pdf417-encoding/)
- [Aspose.BarCode for .NET를 사용한 DataMatrix 바코드 생성 방법](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [바코드 생성 방법 - 일차원 바코드 유형](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}