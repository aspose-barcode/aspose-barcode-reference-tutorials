---
category: general
date: 2026-09-29
description: C#에서 GS1 바코드를 생성하고 BarcodeGenerator를 사용하여 바코드 PNG 이미지를 만들세요. 단계별 가이드를
  따라 바코드 이미지를 효율적으로 내보내세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: ko
lastmod: 2026-09-29
og_description: C#에서 GS1 바코드를 생성하고 BarcodeGenerator로 바코드 PNG 파일을 만들세요. 이 완전한 가이드를
  따라 바코드 이미지를 빠르게 내보내세요.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: C#에서 GS1 바코드 만들기 – 몇 분 안에 PNG로 내보내기
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: C#에서 GS1 바코드 생성 및 PNG로 내보내기
url: /ko/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 GS1 바코드 생성 및 PNG로 내보내기

.NET 애플리케이션에서 **GS1 바코드 생성**이 필요하다면, 이 가이드는 정확한 방법을 보여줍니다. Aspose.BarCode `BarcodeGenerator` 클래스를 사용하여 바코드 PNG 이미지를 생성하고 디스크에 내보내는 간결한 솔루션을 확인할 수 있습니다.

GS1 바코드 생성은 재고 관리, 배송 및 POS 시스템에서 흔히 요구되는 작업입니다. 이 튜토리얼을 마치면 GS1‑준수 MicroPDF417 바코드를 만들고 고품질 PNG 파일로 저장하는 작은 C# 프로그램을 작성할 수 있게 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 설치되어 있는지 확인하세요:

* **.NET 6** (또는 이후 버전) 설치
* **Visual Studio 2022** 또는 C#을 지원하는 IDE
* **Aspose.BarCode for .NET** NuGet 패키지 (`Aspose.BarCode`) – 예제에서 사용되는 `BarcodeGenerator` API를 제공합니다.
* C# 문법에 대한 기본적인 이해

> **Pro tip:** 실험할 때는 Aspose.BarCode 무료 커뮤니티 에디션을 사용하세요; 정식 버전은 평가 워터마크를 제거합니다.

## 1단계 – BarcodeGenerator로 GS1 바코드 생성

먼저 *MicroPDF417* 형식에 대해 `BarcodeGenerator`를 인스턴스화하고 GS1 데이터 문자열을 전달해야 합니다. GS1 애플리케이션 식별자(AI)는 괄호로 감싸며, 예를 들어 GTIN‑14는 `(01)`, 시리얼 번호는 `(21)`와 같이 사용합니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**왜 중요한가:**  
`EncodeTypes.MicroPdf417`는 문자열에 유효한 AI가 포함되어 있으면 자동으로 입력을 GS1 데이터로 처리합니다. 이를 통해 별도 설정 없이도 바코드가 GS1 사양을 준수하도록 보장됩니다.

## 2단계 – 최적 크기를 위한 바코드 차원 설정

바코드의 시각적 크기는 **X‑dimension**(단일 모듈의 너비)으로 제어됩니다. `XDimension.Pixels`를 조정하면 가독성을 유지하면서 최종 이미지 크기를 미세 조정할 수 있습니다.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **How to generate barcode PNG** – X‑dimension은 인코딩된 데이터에 영향을 주지 않으며, 생성된 이미지의 물리적 크기만 변경합니다. 고해상도 인쇄를 위해 더 큰 바코드가 필요하면 이 값을 늘리세요(예: `3` 또는 `4`).

## 3단계 – 바코드 PNG 생성 및 바코드 이미지 내보내기

이제 바코드를 렌더링하고 PNG 파일로 저장할 수 있습니다. `Save` 메서드는 대상 경로와 원하는 이미지 형식을 인수로 받습니다.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**내부 동작:**  
`BarcodeGenerator.Save`는 바코드를 비트맵으로 래스터화하고, 앞서 설정한 X‑dimension을 적용한 뒤 비트맵을 PNG 파일로 인코딩합니다. 생성된 파일은 웹 페이지에 직접 사용하거나 라벨에 인쇄하거나 PDF에 삽입할 수 있습니다.

## 전체 소스 코드 예제

아래는 복사·붙여넣기만으로 실행 가능한 완전한 콘솔 애플리케이션 예제입니다. **바코드 PNG 생성**, **바코드 이미지 내보내기**를 보여주며 기본 오류 처리도 포함합니다.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### 예상 출력

프로그램을 실행하면 다음과 같은 결과가 표시됩니다.

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

PNG 파일을 열면 GTIN‑14 `12345678901234`와 시리얼 번호 `ABC123`을 인코딩한 **GS1 MicroPDF417** 바코드가 명확히 보입니다. GS1‑호환 스캐너로 스캔하면 원본 데이터 문자열이 반환됩니다.

## 일반적인 함정 및 모범 사례

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Incorrect AI formatting** | 괄호가 없거나 순서가 잘못되면 바코드가 GS1이 아닙니다. | 각 AI를 반드시 괄호로 감싸세요, 예: `(01)`. |
| **Too small X‑dimension** | 저해상도 장치에서 바코드가 읽히지 않을 수 있습니다. | 대부분의 프린터에서는 `XDimension.Pixels`를 2 이상 유지하고, 고 DPI 출력 시 더 크게 설정하세요. |
| **Output folder does not exist** | `Save`가 `DirectoryNotFoundException`을 발생시킵니다. | `Save` 호출 전에 `Directory.CreateDirectory`로 폴더를 생성하세요. |
| **Using the wrong EncodeType** | 일부 타입(예: `Code128`)은 기본적으로 GS1 데이터를 지원하지 않습니다. | `EncodeTypes.MicroPdf417` 또는 GS1‑호환 타입을 선택하세요. |
| **Missing NuGet reference** | `The type or namespace name 'Aspose' could not be found`와 같은 컴파일 오류가 발생합니다. | NuGet을 통해 `Aspose.BarCode` 패키지를 설치하세요. |

## 예제 확장

* **Different image formats** – 다른 포맷이 필요하면 `BarCodeImageFormat.Png`를 `Jpeg`, `Gif`, `Bmp` 등으로 교체하세요.
* **Higher‑resolution output** – 저장하기 전에 `generator.Parameters.ImageResolution.DpiX`와 `DpiY`를 설정하세요.
* **Embedding in PDF** – `Aspose.Pdf`를 사용해 PNG를 PDF 청구서나 라벨에 삽입할 수 있습니다.

## 결론

이제 Aspose.BarCode `BarcodeGenerator`를 활용해 C#에서 **GS1 바코드 생성**, **바코드 PNG 생성**, 그리고 **바코드 이미지 파일 시스템에 내보내기** 방법을 알게 되었습니다. 가이드에서는 GS1 데이터로 생성기 초기화, X‑dimension 조정, 최종 PNG 저장까지 모든 단계를 다루었으며, 일반적인 오류와 확장 아이디어도 제공했습니다.

다른 GS1 애플리케이션 식별자, 다양한 바코드 심볼, 고해상도 이미지 등을 자유롭게 실험해 보세요. 이 기본기를 마스터하면 재고, 배송, 소매 분야에서 규격에 맞는 바코드 생성이 .NET 툴박스의 일상적인 작업이 됩니다.

## 다음에 배워야 할 내용은?

다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하며, 관련 주제를 깊이 있게 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 제공해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하도록 돕습니다.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}