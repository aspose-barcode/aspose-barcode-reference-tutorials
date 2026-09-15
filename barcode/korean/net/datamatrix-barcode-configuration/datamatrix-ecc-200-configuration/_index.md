---
date: 2026-08-02
description: Aspose.BarCode for .NET 프로젝트에서 DataMatrix 바코드를 생성하고, 고밀도 바코드 생성을 탐색하는
  방법을 배웁니다.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: DataMatrix ECC 200 구성
og_description: Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드를 생성합니다. 이 튜토리얼에서는 고밀도
  바코드 생성, 임시 Aspose 라이선스 설정, 단계별 C# 코드를 보여줍니다.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: DataMatrix 바코드 만들기 – Aspose.BarCode .NET 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드(ECC 200) 만드는 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드 (ECC 200) 생성 방법

## 소개

이 가이드에서는 Aspose.BarCode for .NET을 사용하여 **DataMatrix 바코드** (ECC 200)를 **생성**합니다. 재고 추적기, POS 시스템, 또는 문서 워크플로 자동화 등 어떤 애플리케이션을 구축하든, 고밀도 바코드는 작은 공간에 많은 데이터를 저장할 수 있습니다. 모든 설정 단계를 차례대로 안내하고, 각 설정이 왜 중요한지 설명하며, 바로 실행 가능한 C# 코드 조각을 제공합니다.

## 빠른 답변
- **.NET에서 DataMatrix에 가장 적합한 라이브러리는?** Aspose.BarCode for .NET  
- **ECC 200이 제공하는 ECC 수준은?** 견고한 스캔을 위한 고밀도 오류 정정.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 평가용 임시 라이선스로 동작하지만, 실제 운영에는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5 이상, .NET Core 3.1 이상, .NET 5/6 이상.  
- **PNG, JPEG, TIFF 형식으로 출력할 수 있나요?** 예 – `Save` 메서드가 여러 이미지 형식을 지원합니다.

## DataMatrix ECC 200이란?

DataMatrix ECC 200은 고밀도 2차원 바코드로, 최대 2,335개의 영숫자 문자 또는 1,556바이트의 바이너리 데이터를 컴팩트한 정사각형 또는 직사각형 패턴에 저장할 수 있습니다. Reed‑Solomon 오류 정정을 사용해 손상되거나 손실된 모듈을 복구하므로, 항공우주 부품 표시, 제약 라벨링, 물류 등 신뢰성이 중요한 애플리케이션에 적합합니다.

## Aspose 바코드 생성 사용 이유

Aspose.BarCode는 **30개 이상의 심볼**을 지원하고, 전체 파일을 메모리에 로드하지 않고도 최대 10,000 × 10,000 px 이미지를 렌더링할 수 있으며, Windows, Linux, macOS 전반에 걸쳐 결정적인 출력을 제공합니다. API를 통해 모든 렌더링 매개변수를 제어할 수 있어 **ASP.NET 바코드 생성** 시나리오에 가장 유연한 선택입니다.

## 전제 조건

1. **개발 환경** – 적절한 .NET 프레임워크가 설치된 Visual Studio.  
2. **Aspose.BarCode for .NET** – 웹사이트에서 다운로드하고 설치합니다, [here](https://releases.aspose.com/barcode/net/).  
3. **라이선스** – 테스트용 임시 라이선스를 [here](https://purchase.aspose.com/temporary-license/)에서 받습니다.  
4. **C# 기본** – C# 문법 및 프로젝트 구조에 익숙함.

이제 기본 사항을 다했으니, DataMatrix ECC 200 구성으로 넘어가겠습니다.

## 네임스페이스 가져오기

`Aspose.BarCode.Generation` 네임스페이스에는 바코드 생성을 위해 필요한 모든 클래스가 포함되어 있습니다. 파일 상단에 다음과 같이 가져오세요:

```csharp
using Aspose.BarCode.Generation;
```

## DataMatrix 바코드 (ECC 200) 단계별 생성 방법

DataMatrix ECC 200 바코드를 생성하려면 인코딩할 데이터를 로드하고, `BarcodeGenerator`에 몇 가지 핵심 매개변수를 설정한 뒤 `Save`를 호출해 이미지 파일을 저장하면 됩니다. 이 3단계 흐름은 인코딩, 오류 정정, 출력 형식 선택을 처리하므로 최소한의 코드로 모든 .NET 애플리케이션에 바코드 생성을 통합할 수 있습니다.

### 단계 1: Barcode Generator 초기화

`BarcodeGenerator`는 바코드를 생성하고 렌더링하는 Aspose.BarCode의 핵심 클래스입니다. 심볼 유형과 인코딩할 텍스트를 받아들입니다.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

`"Your Directory Path"`를 이미지 저장을 원하는 폴더 경로로 교체하세요.

### 단계 2: XDimension 및 ECC 유형 설정

`XDimension`은 각 DataMatrix 모듈의 픽셀 크기를 정의하고, `DataMatrixEcc`는 오류 정정 수준을 선택합니다. ECC 200은 이 심볼에 대해 가장 높은 정정 능력을 제공합니다.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

모듈 크기를 크게 혹은 작게 조정하려면 픽셀 값을 변경하세요; 일반적인 값은 화면 표시용 4‑6 px, 인쇄 라벨용 8‑10 px입니다.

### 단계 3: 바코드 이미지 생성 및 저장

`Save` 메서드는 바코드를 파일에 기록합니다. 해당 `BarCodeImageFormat` 열거형 값을 전달하여 PNG, JPEG, TIFF 중 하나를 선택할 수 있습니다.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

워크플로우에서 다른 형식이 필요하면 `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Jpeg` 또는 `BarCodeImageFormat.Tiff`로 변경하세요.

## 일반적인 문제 및 해결 방법

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 바코드가 흐릿하게 보임 | XDimension 값이 너무 낮음 | `XDimension.Pixels`를 6‑8로 증가시킵니다 |
| 모바일에서 스캔 실패 | 잘못된 ECC 수준 | `DataMatrixEcc = DataMatrixEccType.Ecc200`인지 확인합니다 |
| 파일이 생성되지 않음 | 잘못된 경로 문자열 | 절대 경로를 사용하거나 폴더가 존재하는지 확인합니다 |

## 자주 묻는 질문

**Q: 이 코드를 .NET Core 콘솔 애플리케이션에서 사용할 수 있나요?**  
A: 예, 동일한 API가 .NET Core, .NET 5, .NET 6 프로젝트에서 작동합니다.

**Q: 출력 형식을 JPEG로 변경하려면 어떻게 해야 하나요?**  
A: `Save` 호출에서 `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Jpeg`로 교체합니다.

**Q: 바코드를 PDF에 직접 삽입할 수 있나요?**  
A: 예 – 먼저 이미지를 생성한 뒤 Aspose.PDF 또는 다른 PDF 라이브러리를 사용해 PDF에 추가합니다.

**Q: 유니코드 문자를 인코딩해야 하면 어떻게 하나요?**  
A: DataMatrix는 UTF‑8을 지원하므로, 예시와 같이 유니코드 문자열을 생성기에 전달하면 됩니다.

**Q: 라이브러리가 여러 바코드의 배치 생성을 지원하나요?**  
A: 물론입니다 – 생성 코드를 루프 안에 넣고 각 반복마다 데이터/값을 변경하면 됩니다.

## 결론

우리는 Aspose.BarCode for .NET을 사용하여 **DataMatrix 바코드** (ECC 200)를 **생성**하는 데 필요한 모든 내용을 다루었습니다: 전제 조건 및 네임스페이스 가져오기부터 X‑dimension 설정, ECC 수준 선택, 원하는 형식으로 이미지 저장까지. 여백, 배경색, 회전 등 다양한 추가 속성을 실험해 보면서 특정 사용 사례에 맞게 출력을 미세 조정해 보세요.

문제가 발생하면 커뮤니티가 [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)에서 도움을 줄 준비가 되어 있습니다. 즐거운 코딩 되세요!

---

**마지막 업데이트:** 2026-08-02  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.BarCode for .NET을 사용하여 DataMatrix ECC 000-140 바코드 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드 읽는 방법](/barcode/net/datamatrix-barcode-reading/)
- [바코드 PNG 생성 – DataMatrix 종횡비 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}