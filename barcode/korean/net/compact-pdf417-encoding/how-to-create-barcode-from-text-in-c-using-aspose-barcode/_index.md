---
category: general
date: 2026-10-28
description: Aspose.BarCode를 사용하여 C#에서 텍스트로 바코드를 생성합니다. PDF417 바코드 이미지를 생성하고, 열 수를
  설정하며, X‑디멘션을 조정하고, 컴팩트 모드를 활성화하는 방법을 배웁니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: ko
lastmod: 2026-10-28
og_description: Aspose.BarCode를 사용하여 C#에서 텍스트로 바코드를 생성합니다. 이 튜토리얼에서는 PDF417 바코드 이미지를
  생성하고, 크기, 열 및 컴팩트 모드를 사용자 지정하는 방법을 보여줍니다.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: C#에서 텍스트로 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: C#에서 Aspose.BarCode를 사용해 텍스트로 바코드 생성하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 Aspose.BarCode를 사용하여 텍스트에서 바코드 생성하는 방법

.NET 애플리케이션에서 **텍스트에서 바코드 생성**이 필요하다면, 이 가이드는 바로 실행할 수 있는 솔루션을 제공합니다. **PDF417 바코드** 이미지를 생성하고, 모듈 너비, 열 개수를 제어하며, IDE를 떠나지 않고 컴팩트 모드를 활성화하는 방법을 확인할 수 있습니다.

이 튜토리얼은 라이브러리 설치부터 최종 PNG 파일 저장까지 **C#에서 바코드 생성**에 필요한 모든 내용을 다룹니다. 끝까지 진행하면 보고서, 티켓, 재고 라벨 등에 고밀도 PDF417 바코드를 삽입할 수 있습니다.

## 사전 요구 사항

* .NET 6.0 SDK 이상이 설치되어 있음  
* Visual Studio 2022 (또는 .NET을 지원하는 기타 편집기)  
* Aspose.BarCode for .NET NuGet 패키지를 다운로드할 수 있는 인터넷 연결  

이 항목들만 있으면 Windows, Linux, macOS에서 예제를 컴파일하고 실행할 수 있습니다.

## 1단계: Aspose.BarCode NuGet 패키지 설치

바코드 생성을 구동하는 라이브러리는 **Aspose.BarCode for .NET**입니다. .NET CLI를 사용하여 설치합니다:

```bash
dotnet add package Aspose.BarCode
```

이 패키지는 `Aspose.BarCode` 네임스페이스를 추가하며, 여기에는 이 튜토리얼 전반에 걸쳐 사용되는 `BarcodeGenerator` 클래스가 포함됩니다.

## 2단계: 콘솔 프로젝트 생성 및 코드 추가

새 콘솔 프로젝트를 만들고 생성된 `Program.cs`를 다음 코드로 교체합니다. 이 프로그램은 **텍스트에서 바코드 생성**하고 이를 **PDF417 바코드 이미지**로 저장하는 방법을 보여줍니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### 각 라인이 중요한 이유

* **`EncodeTypes.Pdf417`**는 PDF417 심볼을 선택합니다. 이는 2차원 형식으로 대량의 데이터를 인코딩하기에 이상적입니다.  
* **`XDimension.Pixels = 2`**는 모듈 너비를 줄여 바코드를 더 촘촘하게 만들며, 제한된 공간에 더 적합합니다.  
* **`Pdf417.Columns = 3`**은 수직 데이터 열 수를 제어합니다. 열 수가 적을수록 바코드는 더 높고 좁아집니다.  
* **`Pdf417.Truncate = true`**는 컴팩트 모드를 활성화하여 오른쪽에 사용되지 않는 열을 잘라냅니다. 이는 일반 PDF417을 **컴팩트 PDF417 바코드 이미지**로 변환하는 핵심 설정입니다.  

## 3단계: 프로젝트 빌드 및 실행

프로젝트 디렉터리에서 다음 명령을 실행합니다:

```bash
dotnet build
dotnet run
```

프로그램이 종료되면 파일 위치를 확인하는 콘솔 메시지가 표시됩니다. `CompactPdf417.png`를 이미지 뷰어로 열어 결과를 확인하십시오.

**예상 출력** – 문자열 `Åspóse.Barcóde©`를 인코딩한 컴팩트 PDF417 바코드를 보여주는 고대비 PNG입니다. 표준 바코드 리더기로 이미지를 스캔하면 원본 텍스트가 반환되어 **pdf417 바코드 생성**이 성공했음을 확인합니다.

## 4단계: 다양한 시나리오에 맞게 바코드 맞춤 설정

예제는 고정된 열 수와 X‑dimension을 사용하지만, 다른 요구 사항에 맞게 생성기를 조정할 수 있습니다:

| 시나리오 | 조정 |
|----------|------------|
| 데이터 양이 많을 경우 | `Pdf417.Columns`를 늘리거나 `Pdf417.Rows`를 수동으로 설정 |
| 스캔 신뢰도 향상 | `XDimension.Pixels`를 3 또는 4로 증가 |
| 다른 이미지 형식 | `BarCodeImageFormat.Png`를 `Jpeg` 또는 `Bmp`로 교체 |
| 투명 배경 | `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` 설정 |

이 옵션들을 사용하면 모바일 앱, 데스크톱 보고서, 웹 서비스에 맞는 **C# 바코드 생성** 솔루션을 만들 수 있습니다.

## 5단계: 엣지 케이스 처리 및 모범 사례

* **Unicode 지원** – 생성기는 Unicode 문자를 자동으로 인코딩하지만, 파일에서 읽어올 경우 소스 문자열이 UTF‑8 인코딩되어 있는지 확인하십시오.  
* **대용량 텍스트** – PDF417은 최대 1,850개의 영숫자 문자를 인코딩할 수 있습니다. 이 한도를 초과하면 라이브러리가 예외를 발생시키므로 데이터를 여러 바코드로 나누거나 용량이 더 큰 심볼로 전환하십시오.  
* **오류 처리** – `try/catch` 블록으로 생성 코드를 감싸 `BarCodeException`을 포착하고 친절한 오류 메시지를 제공하십시오.  
* **성능** – 루프에서 다수의 바코드를 생성할 때는 단일 `BarcodeGenerator` 인스턴스를 재사용하고 반복마다 `CodeText`만 업데이트하면 효율적입니다.  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## 전체 소스 코드

아래는 `Program.cs`에 복사해 넣을 수 있는 완전하고 독립적인 프로그램 전체 코드입니다. 추가 파일은 필요하지 않습니다.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

이 프로그램을 실행하면 아래 그림에 표시된 **pdf417 바코드 이미지**가 생성됩니다.

![C#를 사용하여 텍스트에서 만든 컴팩트 PDF417 바코드](/images/compact-pdf417.png){.img-fluid alt="텍스트에서 바코드 생성 예시, 컴팩트 PDF417 바코드 이미지를 보여줍니다"}

*이미지 설명: 이 PNG 파일은 문자열 “Åspóse.Barcóde©”를 인코딩한 컴팩트 PDF417 바코드를 표시합니다.*  

## 결론

이제 C#에서 **텍스트에서 바코드 생성**하고 사용자 지정 크기와 컴팩트 모드가 적용된 **PDF417 바코드 이미지**를 만드는 방법을 알게 되었습니다. 이 예제는 **C# 바코드 생성**의 필수 단계, Unicode 데이터 처리, 다양한 배포 시나리오에 맞춘 시각적 매개변수 조정 방법을 보여줍니다.

다음으로 **C#에서 QR 코드 생성**, **PDF 문서에 바코드 추가**, **ASP.NET Core API에 바코드 삽입**과 같은 관련 주제를 살펴보세요. 이들 모두는 여기서 다룬 동일한 `BarcodeGenerator` 기본 개념을 기반으로 합니다.

코딩을 즐기시고, .NET 솔루션에 바코드를 통합하는 재미를 느껴 보세요!

## 다음에 배울 내용은?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 관련 주제를 다룹니다. 각 자료에는 단계별 설명과 함께 완전한 코드 예제가 포함되어 있어 추가 API 기능을 마스터하고 프로젝트에서 대체 구현 방식을 탐색하는 데 도움이 됩니다.

- [C#에서 PDF417 바코드 생성 – PDF417 바코드 C# 만들기](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [C#에서 Aspose.BarCode로 PDF417 바코드 생성 방법](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [C#에서 PDF417 바코드 이미지 생성 방법 – 완전 가이드](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}