---
date: 2026-06-09
description: Aspose.BarCode를 사용한 C40 인코딩으로 DataMatrix 바코드를 생성하고 PNG로 저장하는 방법을 배웁니다
  – .NET Core 바코드 생성에 대한 전체 가이드
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix 인코딩 모드 (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode를 사용해 C40으로 DataMatrix PNG 생성하는 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 마스터 DataMatrix 인코딩 모드 (C40)와 Aspose.BarCode for .NET

## 소개

이 튜토리얼에서는 **datamatrix 생성 방법** 바코드를 생성하고 C40 인코딩 모드를 사용하여 PNG 파일로 저장하는 방법을 배웁니다. 재고 관리 시스템, 배송 라벨 생성기 또는 고밀도 심볼이 필요한 어떤 솔루션이든 C40을 마스터하면 가독성을 유지하면서 더 작은 심볼을 만들 수 있습니다. 환경 설정부터 최종 PNG 생성까지 모든 단계를 단계별로 안내하므로 코드를 즉시 프로젝트에 통합할 수 있습니다.

## 빠른 답변
- **“how to generate datamatrix”는 무엇을 의미합니까?** 프로그램을 통해 DataMatrix 바코드 이미지를 생성합니다.  
- **어떤 인코딩 모드가 다루어집니까?** DataMatrix C40, 효율적인 영문자·숫자 인코딩 방식입니다.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판을 사용할 수 있지만, 실제 운영을 위해서는 상용 라이선스가 필요합니다.  
- **.NET Core에서 실행할 수 있나요?** 예, Aspose.BarCode는 .NET Core, .NET 5, .NET 6 및 이후 버전을 완벽히 지원합니다.  
- **어떤 파일 형식이 생성됩니까?** PNG – 손실이 없고 웹 친화적인 이미지 형식입니다.

## C40 인코딩으로 DataMatrix 생성 방법

데이터를 로드하고, 생성기를 구성한 뒤 `Save`를 호출하면 됩니다 – 세 단계로 구성된 전체 워크플로우입니다. `BarcodeGenerator` 클래스가 심볼 생성을 담당하고, `BarCodeImageFormat.Png` 열거형은 Aspose.BarCode에 결과를 PNG 파일로 기록하도록 지시합니다. `Save`는 지정된 파일 경로에 선택한 형식으로 생성된 바코드 이미지를 씁니다. 이 직접적인 답변 단락은 각 코드 라인을 살펴보기 전에 전체 솔루션을 제공합니다.

## DataMatrix 인코딩 모드 (C40)란?

`DataMatrixEncodeMode`는 Aspose.BarCode가 DataMatrix 심볼에 사용할 인코딩 방식을 지정하는 열거형입니다. `DataMatrixEncodeMode.C40` 옵션은 C40 영문자·숫자 인코딩을 선택하는데, 이는 문자, 숫자 및 제한된 구두점을 더 적은 모듈에 압축하여 전체 심볼 크기를 줄이면서 일반 재고 텍스트의 가독성을 유지합니다. 이 효율적인 스킴은 알파벳·숫자 데이터를 컴팩트하게 인코딩해야 할 때 이상적입니다.

## .NET용 Aspose.BarCode를 사용하는 이유

Aspose.BarCode는 치수, 오류 정정 수준 및 인코딩 모드에 대한 **30+ 구성 가능한 매개변수**를 제공하며, **50+ 이미지 및 바코드 형식**을 지원합니다. 이 라이브러리는 **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**에서 실행되며, 서버, 데스크톱 및 모바일 장치에서 작동하는 무종속성 생성 기능을 제공합니다.

## 사전 요구 사항

코드에 들어가기 전에 다음 항목을 준비하십시오:

1. **.NET Development Environment** – Visual Studio, Rider 또는 C#을 지원하는 모든 IDE.  
2. **Aspose.BarCode for .NET** – NuGet 또는 공식 설치 프로그램을 통해 설치합니다. 자세한 내용은 [문서](https://reference.aspose.com/barcode/net/)를 참조하십시오.  
3. **Basic C# knowledge** – 네임스페이스, 클래스 및 using 구문에 익숙해야 합니다.  
4. **Write‑access folder** – PNG가 저장될 머신상의 디렉터리.

## 필요한 네임스페이스 가져오기

`BarcodeGenerator` 클래스는 모든 바코드 생성을 위한 진입점입니다. C# 소스 파일 상단에 필요한 네임스페이스를 추가하여 생성 API에 접근할 수 있도록 합니다:

```csharp
using Aspose.BarCode.Generation;
```

## 단계별 바코드 생성

아래는 **단계별 바코드** 진행 과정입니다. 각 단계는 쉬운 언어로 설명되며, 복사‑붙여넣기를 위한 원본 자리표시자는 그대로 유지됩니다.

### 단계 1: 디렉터리 경로 정의
PNG 이미지가 저장될 폴더를 설정합니다. 자리표시자를 실제 머신 경로로 교체하십시오.

```csharp
string path = "Your Directory Path";
```

### 단계 2: 바코드 생성 설정
`BarcodeGenerator` 인스턴스를 만들고, `EncodeTypes.DataMatrix`를 지정한 뒤 인코딩할 데이터를 제공합니다.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 단계 3: 바코드 사용자 정의
X‑dimension(모듈의 픽셀 너비)을 구성하고 인코딩 모드를 C40으로 전환합니다.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 단계 4: 바코드 이미지 저장
마지막으로 생성된 바코드를 PNG 파일로 저장합니다. 이는 Aspose.BarCode를 사용한 **png 저장 방법**에 대한 구체적인 답변입니다.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

프로그램을 실행하면 지정한 폴더에 `DataMatrixEncodeModeC40.png` 파일이 생성되어 보고서, 라벨 또는 웹 페이지에 바로 사용할 수 있습니다.

## 일반적인 문제 및 팁

- **Invalid Path** – 디렉터리가 존재하고 쓰기 권한이 있는지 확인하십시오. 그렇지 않으면 `gen.Save`가 예외를 발생시킵니다.  
- **Incorrect Encoding Mode** – C40 집합에 포함되지 않은 문자를 인코딩해야 할 경우 `DataMatrixEncodeMode.Auto` 등 다른 적절한 모드로 전환하십시오.  
- **Image Size** – `XDimension.Pixels`를 조정하여 바코드 전체 크기를 늘리거나 줄일 수 있으며, 가독성에는 영향을 주지 않습니다.

## 자주 묻는 질문

**Q: DataMatrix 인코딩 모드 (C40)란?**  
A: C40은 DataMatrix 심볼을 위한 컴팩트한 영문자·숫자 인코딩 방식으로, 문자, 숫자 및 제한된 특수 문자를 포함하는 텍스트에 적합합니다.

**Q: Aspose.BarCode for .NET 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [여기](https://reference.aspose.com/barcode/net/)에서 확인할 수 있습니다. 모든 바코드 유형 및 인코딩 옵션에 대한 자세한 가이드를 제공합니다.

**Q: Aspose.BarCode for .NET가 모든 .NET 버전과 호환되나요?**  
A: 예, 이 라이브러리는 .NET Framework 4.5+부터 .NET 6 및 이후 버전까지 광범위한 .NET 버전을 지원합니다.

**Q: 구매 전에 Aspose.BarCode for .NET를 체험해볼 수 있나요?**  
A: 예, [이 링크](https://releases.aspose.com/)를 방문하면 Aspose.BarCode for .NET의 무료 체험판을 다운로드하여 기능과 성능을 테스트할 수 있습니다.

**Q: Aspose.BarCode for .NET에 대한 지원은 어디서 받을 수 있나요?**  
A: 지원 및 커뮤니티는 [Aspose 포럼](https://forum.aspose.com/c/barcode/13)에서 확인할 수 있습니다.

## 결론

이 **단계별 바코드** 가이드를 따라 하면 이제 **datamatrix 생성 방법**을 정확히 알고 C40 인코딩 모드를 사용해 Aspose.BarCode for .NET으로 PNG 파일에 저장할 수 있습니다. 이 접근 방식은 바코드의 외관, 크기 및 데이터 표현을 완전히 제어할 수 있게 해 주어, 어떤 .NET 애플리케이션에도 고품질 바코드를 손쉽게 삽입할 수 있습니다.

---

**마지막 업데이트:** 2026-06-09  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [DataMatrix Encoding in Bytes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}