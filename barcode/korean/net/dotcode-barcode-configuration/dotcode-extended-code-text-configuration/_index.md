---
date: 2026-09-28
description: Aspose.BarCode for .NET를 사용하여 2D 매트릭스 바코드를 만드는 방법 – 확장 코드 텍스트가 포함된 DotCode
  바코드를 생성하는 단계별 가이드.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode 확장 코드 텍스트 구성
og_description: Aspose.BarCode for .NET를 사용하여 2D 매트릭스 바코드를 만드는 방법을 배웁니다. 이 가이드는 확장
  코드 텍스트가 포함된 DotCode 바코드를 단계별로 생성하는 방법을 보여줍니다.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Aspose.BarCode for .NET로 2D 매트릭스 바코드 만들기
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Aspose.BarCode for .NET를 사용하여 2D 매트릭스 바코드 만드는 방법
url: /ko/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET을 사용하여 2D 매트릭스 바코드 생성 방법

## 소개

바코드 생성 및 관리 분야에서 Aspose.BarCode for .NET은 **50개 이상의 입력 및 출력 형식**을 지원하고 전체 파일을 메모리에 로드하지 않고도 수백 페이지 문서를 처리할 수 있는 다목적 솔루션으로 돋보입니다. 제품 추적, 재고 관리 또는 데이터 중심 애플리케이션을 위한 바코드가 필요하든, 확장된 코드텍스트를 가진 **2D 매트릭스 바코드**(예: DotCode)를 생성하면 텍스트와 바이너리 페이로드를 컴팩트한 정사각형 심볼에 삽입할 수 있습니다. 이 튜토리얼에서는 확장된 코드텍스트를 단계별로 구축하고 최종 이미지를 렌더링하는 방법을 안내합니다.

## 빠른 답변
- **“create dotcode extended codetext”가 의미하는 바는?** DotCode 바코드에 FNC1, ECICodetext, 일반 텍스트 및 심볼 구분자를 하나의 확장 페이로드에 포함시키는 것을 의미합니다.  
- **필요한 라이브러리는?** Aspose.BarCode for .NET.  
- **라이선스가 필요합니까?** 평가용으로는 임시 라이선스가 작동하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **구현에 걸리는 시간은?** 기본 예제의 경우 약 10‑15분 정도 소요됩니다.

## DotCode 확장 코드텍스트 생성 방법

프로젝트를 로드하고, 디렉터리를 설정하고, 확장 코드텍스트를 구축한 뒤 이미지를 생성합니다 – 모두 12줄 미만의 코드로 가능합니다. 다음 직접 답변이 전체 과정을 요약합니다:

`BarcodeGenerator`를 `EncodeTypes.DotCode`와 함께 로드하고, `DotCodeExtendedCodetextBuilder`를 사용하여 확장 코드텍스트를 구축(FNC1, ECICodetext, 일반 텍스트 및 FNC3 구분자 추가)한 뒤 `Save`를 호출해 PNG 파일을 저장합니다. 이 순서로 단일 호출만으로 완전하게 규격을 준수하는 2D 매트릭스 바코드를 생성합니다.

## DotCode 확장 코드텍스트란?

**dotcode extended codetext**는 FNC1 식별자, ECICodetext, 일반 텍스트 및 FNC3 구분자와 같은 여러 데이터 세그먼트를 하나의 페이로드로 결합한 복합 문자열이며, DotCode가 이를 디코딩할 수 있습니다. 이를 통해 다국어 텍스트, 바이너리 블롭 및 구조화된 데이터를 단일 2D 매트릭스 바코드에 인코딩할 수 있어 공급망, 의료 및 IoT 시나리오에 이상적입니다.

## 이 작업에 Aspose.BarCode를 사용하는 이유

Aspose.BarCode는 일반 서버 하드웨어에서 **초당 최대 500페이지**를 처리하고 **30가지 이상의 바코드 심볼**(DotCode 포함)을 지원합니다. `GetExtendedCodetext` API는 제어 문자 배치를 정확히 보장하여 수동 문자열 연결 오류를 없애고 ISO/IEC 24724 준수를 보장합니다. 또한 내장 오류 정정 및 자동 여백(quiet‑zone) 처리를 제공해 수동 조정 필요성을 줄여줍니다.

## 사전 요구 사항

- **Aspose.BarCode for .NET** – [Aspose.BarCode for .NET 문서](https://reference.aspose.com/barcode/net/)에서 다운로드하십시오.  
- .NET 개발 환경(Visual Studio 2022 이상 권장).  
- 선택 사항: 평가용 임시 라이선스 파일.

## 네임스페이스 가져오기

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

이 네임스페이스는 예제에 필요한 `BarcodeGenerator` 클래스와 `DotCodeExtendedCodetextBuilder` 도우미를 제공합니다.

```csharp
using Aspose.BarCode.Generation;
```

이제 사전 요구 사항을 충족했으니, DotCode 확장 코드텍스트 생성 과정을 단계별 가이드로 나누어 보겠습니다.

## 1단계: 디렉터리 경로 정의

생성된 PNG가 저장될 위치를 지정합니다. 애플리케이션이 쓸 수 있는 절대 경로나 상대 경로를 사용하십시오.

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"`를 시스템의 실제 경로로 교체하십시오.

## 2단계: DotCode 확장 코드텍스트 생성

`DotCodeExtendedCodetextBuilder` 클래스는 다양한 세그먼트를 하나의 확장 코드텍스트 문자열로 조합합니다.

DotCode 확장 코드텍스트를 만들려면 다음 하위 단계들을 따르세요:

### 2.1 fnc1 형식 식별자 추가

FNC1 형식 식별자는 새로운 데이터 필드의 시작을 표시합니다. GS1 규격을 따르는 DotCode 심볼에 필요합니다.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ecicodetext 추가

ECICodetext는 특수 문자와 국제 텍스트를 인코딩합니다. 이 예제에서는 UTF‑8을 사용해 `"犬Right狗"`를 인코딩합니다.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 일반 코드텍스트 추가

DotCode 확장 코드텍스트에 일반 텍스트도 추가할 수 있습니다. 여기서는 `"Plain text"`를 추가합니다.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 fnc3 심볼 구분자 추가

FNC3 심볼 구분자는 코드의 서로 다른 섹션을 구분하여 스캐너의 가독성을 향상시킵니다.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 fnc3 리더 초기화 추가

이 단계는 스캐너에게 이후 데이터를 해석하는 방법을 알려주는 FNC3 리더 초기화 정보를 추가합니다.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 코드텍스트 생성

`textBuilder` 객체에서 `GetExtendedCodetext` 메서드를 호출하여 DotCode 확장 코드텍스트를 생성합니다.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 3단계: DotCode 이미지 생성

확장 코드텍스트에서 바코드 이미지를 렌더링합니다.

#### 3.1 바코드 생성기 초기화

`BarcodeGenerator` 클래스는 Aspose.BarCode의 핵심 객체로, 모든 바코드를 생성합니다. 원하는 심볼(`EncodeTypes.DotCode`)과 방금 만든 확장 코드텍스트로 인스턴스화합니다.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

마지막으로 `Save`를 호출해 PNG 파일을 디스크에 저장합니다. 이 이미지는 보고서, 모바일 앱 또는 인쇄 라벨에 삽입할 준비가 되었습니다.

## 일반적인 문제와 해결책

- **잘못된 인코딩** – 다국어 텍스트를 추가할 때 `ECIEncodings.UTF8`을 사용했는지 확인하십시오; 그렇지 않으면 문자가 깨질 수 있습니다.  
- **파일 접근 오류** – 애플리케이션이 대상 디렉터리에 쓰기 권한이 있는지 확인하십시오.  
- **Quiet zone 누락** – 스캐너가 심볼 주변에 추가 여백을 필요로 하면 `gen.Parameters.Barcode.Margin`을 설정하십시오.

## 자주 묻는 질문

**Q: 생성된 바코드를 모바일 앱에서 사용할 수 있나요?**  
A: 예. 생성기가 만든 PNG 이미지는 iOS, Android 또는 모든 크로스‑플랫폼 모바일 애플리케이션에 삽입할 수 있습니다.

**Q: 텍스트 대신 바이너리 데이터를 인코딩해야 하면 어떻게 하나요?**  
A: 적절한 `ECIEncodings`(예: `ECIEncodings.Base64`)와 함께 `AddECICodetext` 메서드를 사용해 바이너리 페이로드를 삽입합니다.

**Q: 가독성을 해치지 않으면서 바코드 크기를 어떻게 조절하나요?**  
A: `XDimension.Pixels` 속성을 조정하십시오; 값이 높을수록 모듈 크기가 커지고, 낮을수록 바코드가 더 컴팩트해집니다.

**Q: 바코드 주변에 quiet zone을 추가할 방법이 있나요?**  
A: 예. 원하는 quiet zone을 픽셀 단위로 정의하려면 `gen.Parameters.Barcode.Margin`을 설정하십시오.

**Q: 라이브러리가 .NET 8을 지원하나요?**  
A: 최신 Aspose.BarCode 릴리스는 .NET 8과 호환됩니다; 적절한 NuGet 패키지 버전을 참조하면 됩니다.

추가 안내가 필요하거나 질문이 있으면 [Aspose.BarCode for .NET 문서](https://reference.aspose.com/barcode/net/)를 방문하거나 [Aspose.BarCode 지원 포럼](https://forum.aspose.com/c/barcode/13)에서 커뮤니티와 소통하십시오.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## 관련 튜토리얼

- [Aspose.BarCode를 사용한 DotCode 바코드 .NET (자동 모드) 생성](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Aspose.BarCode for .NET을 사용한 DataMatrix 바코드 생성 방법 – 단계별 가이드](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET으로 Aztec 바코드 생성 방법](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}