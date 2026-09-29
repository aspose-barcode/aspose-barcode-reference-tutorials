---
date: 2026-08-17
description: Aspose.BarCode for .NET을 사용하여 매크로 문자와 함께 DataMatrix barcode를 생성하는 방법을
  배우고, 애플리케이션에서 DataMatrix를 활용하는 방법을 알아보세요.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix 매크로 구성
og_description: Aspose.BarCode for .NET을 사용하여 매크로 문자와 함께 DataMatrix barcode를 생성하는
  방법을 배우세요. 이 가이드는 단계별 코드, 커스터마이징 옵션, 신뢰할 수 있는 barcode 생성을 위한 검증 팁을 제공합니다.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Aspose.BarCode를 사용하여 매크로 문자와 함께 DataMatrix barcode 생성
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: .NET에서 매크로 문자와 함께 DataMatrix barcode 생성 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET에서 매크로 문자로 DataMatrix 바코드 생성 방법

## 소개

매크로 문자를 포함하는 **DataMatrix 바코드**를 생성하면 작은 정사각형 기호에 추가 참조 정보를 담을 수 있습니다. 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 매크로 문자가 포함된 **DataMatrix 바코드**를 **생성**하는 방법, 크기와 오류 정정 수준을 맞춤 설정하는 방법, 그리고 결과를 즉시 검증하는 방법을 배웁니다. 끝까지 진행하면 제품 라벨, 문서 또는 의료 기기에 매크로가 적용된 바코드를 삽입할 준비가 됩니다.

## 빠른 답변
- **주요 라이브러리는 무엇입니까?** Aspose.BarCode for .NET  
- **매크로 문자가 포함된 DataMatrix 바코드를 생성할 수 있나요?** Yes – set the `MacroCharacters` property.  
- **프로덕션에 라이선스가 필요합니까?** A valid Aspose license is required for production use.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **무료 체험판을 이용할 수 있나요?** Absolutely – download it from the official Aspose site.

## 전제 조건

매크로 구성을 시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Visual Studio** – 최신 버전이면 모두 작동합니다.  
2. **Aspose.BarCode for .NET** – [the download link](https://releases.aspose.com/barcode/net/)에서 다운로드하십시오.  
3. **Basic .NET knowledge** – C# 및 .NET 생태계에 익숙함.

## 네임스페이스 가져오기

바코드 생성 및 인식을 위해 필요한 네임스페이스를 가져오는 것으로 시작합니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## 매크로 문자를 사용한 “generate DataMatrix barcode”이란?

`MacroCharacters`는 DataMatrix 바코드에 추가 데이터를 참조하는 매크로 기호를 포함할 수 있게 합니다. Macro05 또는 Macro06과 같은 매크로 문자를 사용하면 하나의 바코드가 더 큰 데이터 세트나 관련 바코드 시퀀스를 가리킬 수 있어, 연결된 정보를 압축 인코딩해야 하는 물류, 제조, 문서 추적 등에 유용합니다.

## DataMatrix 바코드 생성을 위해 Aspose.BarCode를 사용하는 이유는?

Aspose.BarCode는 DataMatrix 크기, 오류 정정 수준 및 매크로 설정을 정밀하게 제어할 수 있게 해 주며, 30개 이상의 바코드 심볼을 지원하고 전체 이미지를 메모리에 로드하지 않고도 최대 10 MB 파일을 처리합니다. 크로스‑플랫폼 .NET 구현은 .NET Framework, .NET Core 및 .NET 5/6에서 작동하며, 내장된 인식 기능을 제공해 바코드를 즉시 검증할 수 있습니다.

## 단계별 가이드

### 단계 1: 프로젝트 설정

Visual Studio에서 새 콘솔 애플리케이션(또는 任意 .NET 프로젝트)를 생성합니다. 다운로드받은 Aspose.BarCode DLL에 대한 참조를 추가합니다.

### 단계 2: DataMatrix 매크로 구성

튜토리얼의 핵심 – 여기서 매크로 문자를 사용해 실제로 **DataMatrix 바코드**를 **생성**합니다.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **팁:** 인코딩하려는 문자열로 `"ASPOSE"`를 교체하십시오. 매크로 문자(`Macro05`)는 스캐너에 이 바코드가 매크로 시퀀스의 일부임을 알려줍니다.

### 단계 3: 오류 정정을 위한 바코드 매개변수 맞춤 설정

저장하기 전에 추가 설정을 조정할 수 있습니다:

- **XDimension** – 각 모듈(픽셀)의 크기를 제어합니다.  
- **Margin**, **ErrorCorrection**, 및 **EncodingMode** – 모두 `gen.Parameters.Barcode.DataMatrix`를 통해 접근할 수 있습니다.

### 단계 4: 바코드 저장

위 코드 조각은 지정한 폴더에 이미지를 `DataMatrixMacro.png` 파일로 저장합니다. PNG는 무손실 형식이므로 후속 처리에 적합합니다.

### 단계 5: 바코드 인식

`BarCodeReader`는 이미지에서 바코드를 디코딩하기 위한 Aspose.BarCode 클래스입니다. `BarCodeReader`를 사용해 생성된 이미지를 즉시 읽어 매크로 문자와 데이터가 올바른지 확인합니다. 이 왕복 검증은 자동화 테스트 시 특히 유용합니다.

## 실제 시나리오에서 DataMatrix를 활용하는 방법은?

매크로 문자가 포함된 DataMatrix 바코드는 제품 라벨링, 일련 번호를 중앙 데이터베이스와 연결, 디지털 기록에 대한 참조를 삽입하여 문서 추적, 환자 또는 장비 데이터를 작은 스캔 가능한 기호에 저장하는 의료 장비 태그 등에 적용할 수 있습니다. 이러한 사용 사례는 수동 데이터 입력을 줄이고 추적성을 향상시킵니다.

## 일반적인 문제 및 해결책

| Issue | Reason | Fix |
|-------|--------|-----|
| 바코드 인식 안 됨 | `XDimension`이 잘못되었거나 이미지 해상도가 낮음 | `XDimension.Pixels`를 4‑6으로 늘리고 PNG 또는 TIFF로 저장 |
| 매크로 문자 무시됨 | 리더가 매크로 모드를 지원하지 않음 | DataMatrix 매크로를 명시적으로 지원하는 스캐너/리더 사용 (예: 최신 ZXing 버전) |
| 경로를 찾을 수 없음 | `path` 변수가 유효하지 않음 | 디렉터리가 존재하는지 확인하거나 `Environment.CurrentDirectory`와 함께 `Path.Combine` 사용 |

## 자주 묻는 질문

**Q: Aspose.BarCode for .NET이란?**  
A: Aspose.BarCode for .NET은 .NET 개발자가 DataMatrix, QR 등 다양한 형식의 바코드를 생성하고 인식할 수 있게 해 주는 강력한 라이브러리입니다.

**Q: DataMatrix 바코드를 사용해야 하는 이유는?**  
A: DataMatrix 바코드는 작고 신뢰성이 높으며 대용량 데이터를 저장할 수 있어 제조, 물류, 의료 분야에 이상적입니다.

**Q: Aspose.BarCode for .NET 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)에서 확인할 수 있습니다.

**Q: Aspose.BarCode for .NET의 무료 체험판을 이용할 수 있나요?**  
A: 예, [the free trial link](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.BarCode for .NET 지원은 어디에서 받을 수 있나요?**  
A: 질문이나 지원이 필요하면 [the support forum](https://forum.aspose.com/c/barcode/13)에서 Aspose.BarCode for .NET 포럼을 방문하십시오.

---

**마지막 업데이트:** 2026-08-17  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [바코드 생성 Aspose .NET - DataMatrix 코드 텍스트 구성](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode for .NET으로 DataMatrix 바코드 (ECC 200) 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET을 사용한 DataMatrix 구조적 추가 구성](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}