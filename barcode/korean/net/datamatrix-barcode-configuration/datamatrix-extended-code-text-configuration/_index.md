---
date: 2026-09-23
description: Aspose.BarCode를 사용하여 .NET에서 확장된 code text가 포함된 DataMatrix barcode를 생성하는
  방법을 배우세요. 재고 및 물류 애플리케이션에 적합합니다.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix 확장된 Code Text 구성
og_description: Aspose.BarCode를 사용하여 .NET에서 확장된 code text가 포함된 DataMatrix barcode를
  생성하는 방법. 재고 및 물류 솔루션을 위한 빠른 단계별 가이드를 따라보세요.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Aspose.BarCode를 사용하여 .NET에서 DataMatrix 코드 텍스트를 생성하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Aspose.BarCode를 사용하여 .NET에서 DataMatrix 코드 텍스트를 생성하는 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode를 사용하여 .NET에서 DataMatrix 코드 텍스트 생성하는 방법

현대 .NET 애플리케이션에 바코드를 통합하는 것은 이제 틈새 작업이 아니라 재고, 물류 및 모바일 스캔 솔루션에 필수적인 요구 사항입니다. 이 가이드에서는 **Aspose.BarCode 사용 방법**을 배워 DataMatrix 바코드를 확장 코드 텍스트와 함께 구성하고, 이미지를 생성하며, 프로그래밍 방식으로 검증하는 방법을 알아봅니다. 이 접근 방식이 재고용 바코드 생성에 왜 이상적인지와 .NET Core 또는 .NET 6 프로젝트에 어떻게 적용되는지 확인할 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.BarCode for .NET  
- **어떤 바코드 유형인가요?** DataMatrix with extended code text  
- **.NET Core / .NET 6을 사용할 수 있나요?** 예, API는 크로스‑플랫폼입니다  
- **테스트에 라이선스가 필요합니까?** 무료 체험판은 개발에 사용할 수 있으며, 프로덕션에는 라이선스가 필요합니다  
- **구현에 얼마나 걸립니까?** 기본 예제는 약 10‑15분 정도 소요됩니다  

## Aspose.BarCode for .NET이란?
Aspose.BarCode for .NET은 DataMatrix, QR, Code 128 등을 포함한 30개 이상의 바코드 심볼을 생성하고 인식할 수 있게 해 주는 상용 라이브러리이며, 외부 종속성 없이 최대 10,000 × 10,000 픽셀 크기의 이미지를 생성할 수 있습니다. .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7을 지원합니다.

## DataMatrix 확장 코드 텍스트를 사용하는 이유
DataMatrix 확장 코드 텍스트를 사용하면 하나의 심볼에 UTF‑8, C40, Text, X12와 같은 여러 인코딩 방식을 삽입할 수 있어, 하나의 작은 정사각형에 최대 **3116 코드워드**(약 155 KB 데이터)를 담을 수 있습니다. 이 기능은 다국어 제품 라벨링, 의료 기기 추적, 알파벳-숫자 ID와 바이너리 페이로드를 결합해야 하는 스마트 포장에 이상적입니다.

## 사전 요구 사항
시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오:

1. **Aspose.BarCode for .NET** – 공식 사이트 **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**에서 다운로드하십시오.  
2. **.NET 개발 환경** – Visual Studio, Rider 또는 .NET SDK가 포함된 VS Code.  
3. **기본 C# 지식** – 클래스, 네임스페이스 및 `using` 지시문에 익숙해야 합니다.  

## 네임스페이스 가져오기
C# 파일 상단에 필요한 네임스페이스를 추가하여 컴파일러가 바코드 클래스를 찾을 수 있도록 합니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

이 네임스페이스를 통해 바코드 생성 및 인식 기능 모두에 접근할 수 있습니다.

## DataMatrix 확장 코드 텍스트 구성 방법
빌더를 로드하고 원하는 세그먼트를 추가한 뒤 Aspose.BarCode가 ECI 마커를 자동으로 처리하도록 합니다. 이 직접적인 설명에서는 정확한 단계들을 안내합니다: `DataMatrixExtCodetextBuilder`를 생성하고, Unicode, C40, 일반 텍스트 및 Text 모드 세그먼트를 추가한 뒤, 생성기에 사용할 결합된 문자열을 가져옵니다.

### 단계 1: 출력 폴더 정의
생성된 바코드 이미지가 저장될 위치를 지정합니다. 자리 표시자를 실제 머신의 유효한 경로로 교체하십시오.

```csharp
string path = "Your Directory Path";
```

### 단계 2: 확장 코드 텍스트 빌드
`DataMatrixExtCodetextBuilder`는 DataMatrix 사양에 따라 확장 코드 텍스트를 조합하는 도우미 클래스이며, 필요한 ECI(Extended Channel Interpretation) 마커를 자동으로 삽입합니다.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

이 예시는 Unicode 문자, C40 인코딩, 일반 텍스트 및 Text 모드를 하나의 DataMatrix 심볼에 결합하는 방법을 보여줍니다.

### 단계 3: 최종 코드 텍스트 문자열 생성
모든 부분을 구성한 후, Aspose.BarCode가 바코드에 삽입할 결합된 문자열을 가져옵니다.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### 단계 4: DataMatrix 바코드 생성
`BarcodeGenerator`는 바코드 이미지를 생성하는 핵심 클래스입니다. `EncodeTypes.DataMatrix`와 확장 코드 텍스트를 사용해 인스턴스를 만들고, X‑dimension, 이미지 포맷, 선택적인 인간 판독 텍스트와 같은 시각 매개변수를 설정합니다.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

위 코드는 원하는 확장 코드 텍스트를 사용하여 **barcode aspose .net**을 생성하고 PNG 파일로 저장합니다.

### 단계 5: 바코드를 다시 읽어 검증
`BarCodeReader`는 생성된 심볼이 올바르게 디코딩되는지 검증하며, 이는 자동화 테스트 파이프라인 및 품질 보증에 필수적입니다.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

모든 설정이 올바르게 이루어지면 콘솔에 앞서 만든 정확한 확장 코드 텍스트가 출력됩니다.

## 일반적인 문제점 및 해결 방법
| 문제 | 원인 | 해결책 |
|-------|--------|-----|
| 바코드가 읽히지 않음 | X‑dimension이 너무 낮음 | `XDimension.Pixels`를 증가시킵니다 (예: 4 → 6) |
| 문자 깨짐 | 잘못된 ECI 인코딩 | `ECIEncodings.UTF8`가 문자 집합과 일치하는지 확인 |
| 파일 저장 안 됨 | 잘못된 경로 | 절대 경로를 사용하거나 폴더가 존재하는지 확인 |
| 라이선스 예외 | 체험판 만료 | 임시 또는 정식 라이선스를 적용합니다 (FAQ 참조) |

## 자주 묻는 질문

### Q1: Aspose.BarCode for .NET이란?
A1: Aspose.BarCode for .NET은 DataMatrix, QR, Code128 등 다양한 바코드 심볼을 생성하고 인식할 수 있게 해 주는 강력한 라이브러리입니다.

### Q2: Aspose.BarCode for .NET 문서는 어디에서 찾을 수 있나요?
A2: 전체 API 레퍼런스는 **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**에서 확인할 수 있습니다.

### Q3: Aspose.BarCode for .NET의 무료 체험판이 있나요?
A3: 예, 무료 체험판은 **[Aspose.BarCode free trial download](https://releases.aspose.com/)**에서 다운로드할 수 있습니다.

### Q4: 테스트용 임시 라이선스는 어떻게 얻나요?
A4: 평가용 임시 라이선스는 **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**에서 요청할 수 있습니다.

### Q5: Aspose.BarCode for .NET에 대한 지원이나 질문은 어디에서 받을 수 있나요?
A5: 공식 Aspose.BarCode 포럼이 가장 좋은 지원 채널이며, 여기에서 도움을 받을 수 있습니다: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**마지막 업데이트:** 2026-09-23  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼
- [Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드 생성 방법 – 단계별 가이드](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET (C#)으로 ASCII 모드에서 DataMatrix 바코드 생성](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET을 사용하여 텍스트 인코딩이 포함된 Aztec 바코드 생성](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}