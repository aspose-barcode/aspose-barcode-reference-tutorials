---
category: general
date: 2026-09-22
description: C#에서 PDF417 바코드를 만드는 방법, 바코드 크기를 설정하는 방법, 그리고 명확한 단계별 코드 예제로 바코드 이미지
  파일을 생성하는 방법을 배우세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: ko
lastmod: 2026-09-22
og_description: C#에서 PDF417 바코드를 빠르게 생성하세요. 이 튜토리얼에서는 바코드 크기 설정, 컴팩트 모드 활성화, 그리고 모든
  .NET 프로젝트에서 PNG 이미지 출력 방법을 보여줍니다.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C#에서 PDF417 바코드 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: C#에서 PDF417 바코드를 생성하고 크기를 설정하는 방법
url: /ko/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 PDF417 바코드를 생성하고 크기를 설정하는 방법

C#에서 **PDF417 바코드**를 **생성**해야 할 때, 이 가이드는 바코드를 생성하고, 크기를 제어하며, 결과를 이미지 파일로 저장하는 방법을 보여줍니다. 티켓 발행 시스템, 물류 라벨, 보안 자격 증명 등 어떤 용도이든 PDF417 형식을 마스터하면 대용량 데이터를 컴팩트한 시각 형태로 인코딩할 수 있습니다.

이 튜토리얼을 통해 배울 내용:

* **Aspose.BarCode**(또는 호환 라이브러리)를 사용해 **PDF417 바코드 생성**하기.  
* X‑dimension 및 열 개수를 조정해 **바코드 크기 설정**하기.  
* PNG, JPEG, BMP 등으로 **C#에서 바코드 이미지 생성**하기.  

예제는 Aspose.BarCode for .NET 무료 커뮤니티 에디션을 사용하지만, 동일한 개념은 유사한 속성을 제공하는 다른 라이브러리에도 적용됩니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 SDK 이상이 설치되어 있음.  
* C# IDE(Visual Studio, Visual Studio Code, Rider 등).  
* `Aspose.BarCode` NuGet 패키지(`dotnet add package Aspose.BarCode`).  

추가 설정은 필요하지 않으며, 라이브러리는 Windows, Linux, macOS에서 모두 동작합니다.

## 1단계: 기본 PDF417 바코드를 생성하고 크기 지정하기

먼저 `EncodeTypes.Pdf417` 열거형을 사용해 `BarcodeGenerator`를 인스턴스화하고 인코딩할 텍스트를 전달합니다. 그런 다음 **X‑dimension**(모듈 폭)과 **열 개수**를 조정해 전체 크기를 제어합니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**이 설정이 중요한 이유**

* `XDimension.Pixels`은 가장 좁은 바의 폭을 결정합니다. 값이 작을수록 바코드가 촘촘해지고, 값이 클수록 저해상도 스캐너에서 가독성이 높아집니다.  
* `Pdf417.Columns`는 바코드의 가로·세로 비율에 영향을 줍니다. 열이 적으면 바코드가 높아지고, 열이 많으면 평평해집니다. 열 개수를 조정하는 것이 **바코드 크기 설정**의 주요 방법이며, 인코딩 데이터는 변경되지 않습니다.

코드를 실행하면 지정한 폴더에 `Pdf417Basic.png` 파일이 생성됩니다. 이미지 예시는 아래 스크린샷과 유사합니다.

<img src="images/pdf417-basic.png" alt="기본 바코드 레이아웃을 보여주는 PDF417 바코드 생성 예시">

## 2단계: 동일한 크기로 압축 PDF417 바코드(트렁케이트 모드) 만들기

공간이 제한된 경우 짧은 바코드가 필요할 수 있습니다. PDF417은 **트렁케이트(압축) 모드**를 제공하여 정지 패턴을 제거하고 전체 높이를 줄입니다. `Truncate` 속성을 `true`로 설정하면 됩니다.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true`가 적용되면 어떻게 바뀔까?**

* 바코드 높이가 대략 15‑20 % 정도 짧아져 라벨이나 모바일 화면에 적합합니다.  
* 데이터는 완전히 복구 가능하며, 대부분 최신 스캐너가 트렁케이트 모드를 자동으로 인식합니다.

결과물인 `CompactPdf417.png`는 기본 바코드보다 슬림한 형태로 나타납니다.

## 3단계: 마이크로 PDF417 바코드 생성, 열 개수 조정 및 저장하기

마이크로 PDF417은 매우 작은 공간(예: 신분증)용으로 설계된 고밀도 변형입니다. 열은 1‑4개만 지원되며, 라이브러리는 동일한 `XDimension` 속성을 통해 크기를 제어합니다.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**마이크로 PDF417 핵심 포인트**

* `EncodeTypes.MicroPdf417` 열거형이 자동으로 마이크로 변형을 선택합니다.  
* 심볼이 밀집돼 있기 때문에 300 dpi 이상 프린터가 필요할 수 있습니다.  
* 열 개수 조정이 유일한 크기 조절 수단이며, `XDimension`도 그대로 적용됩니다.

## 다양한 출력 포맷에 대한 바코드 크기 설정 방법

위 예제는 PNG를 사용했지만, 동일한 `Save` 메서드로 JPEG, BMP, TIFF 등도 저장할 수 있습니다. 특정 이미지 크기(예: 300 × 150 px)가 필요하면 `XDimension`과 `ResolutionX`/`ResolutionY`를 함께 사용합니다.

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

`ImageResolution`을 높이고 `XDimension`을 스케일링하면 고해상도 인쇄 시 시각 품질을 유지할 수 있습니다.

## 흔히 겪는 문제와 전문가 팁

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| 바코드가 화면에서 흐릿하게 보임 | 낮은 DPI와 작은 `XDimension` 조합 | `ImageResolution` 및/또는 `XDimension.Pixels` 증가 |
| 스캐너가 트렁케이트 모드를 읽지 못함 | 오래된 스캐너 펌웨어가 지원 안 함 | 레거시 하드웨어에는 전체(비트렁케이트) 모드 사용 |
| 마이크로 PDF417이 읽히지 않음 | 300 dpi 미만 인쇄 또는 대비 부족 | 300 dpi 이상 매트 용지에 인쇄하고 어두운 전경 유지 |
| 출력 파일이 손상됨 | 대상 폴더에 쓰기 권한 없음 | `YOUR_DIRECTORY`가 존재하고 쓰기 가능한지 확인 |

**전문가 팁:** 추가 처리(예: PDF 삽입)가 필요할 경우 손실 없는 PNG 형식으로 바코드를 생성하세요. PNG는 정확한 픽셀 값을 유지하지만 JPEG은 압축 아티팩트를 발생시켜 바코드 가독성을 저하시킬 수 있습니다.

## 전체 실행 가능한 예제

아래는 세 가지 바코드 유형을 한 번에 시연하는 콘솔 애플리케이션 전체 코드입니다. 새 .NET 콘솔 프로젝트에 복사하고 실행해 보세요.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**예상 출력**

프로그램을 실행하면 `Barcodes` 폴더에 세 개의 PNG 파일이 생성됩니다:

* `Pdf417Basic.png` – 3열을 가진 표준 PDF417 바코드.  
* `CompactPdf417.png` – 동일 데이터를 트렁케이트(압축) 모드로 저장, 약간 짧음.  
* `MicroPdf417.png` – 4열을 가진 고밀도 마이크로 PDF417 변형.

이미지 뷰어로 열어 보면 특징적인 스택 형태를 확인할 수 있습니다.


## 다음에 배워야 할 내용은?


다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하는 연관 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 제공해 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하도록 돕습니다.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}