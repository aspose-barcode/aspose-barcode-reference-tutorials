---
date: 2026-09-08
description: Aspose.BarCode for .NET를 사용한 C#에서 code 128 바코드를 생성하고 GS1 바코드를 만드는 방법을
  배웁니다. 단계별 가이드, 전제 조건 및 코드 없이 커스터마이징을 제공합니다.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 예제
og_description: Aspose.BarCode for .NET를 사용한 C#에서 code 128 바코드를 생성하고 GS1 바코드를 만드는
  방법을 배웁니다. 단계별 가이드를 따라 바코드 이미지를 빠르게 생성하고 저장하세요.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Aspose.BarCode를 사용하여 GS1과 함께 code 128 바코드 생성 방법
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Aspose.BarCode를 사용하여 GS1과 함께 code 128 바코드 생성 방법
url: /ko/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode를 사용하여 GS1 코드 128 바코드 생성 방법

이 튜토리얼에서는 .NET용 Aspose.BarCode 라이브러리를 사용하여 GS1 표준을 준수하는 **코드 128 바코드**를 만드는 방법을 배웁니다. 재고 관리, 배송, 또는 POS(판매 시점)용 바코드가 필요하든, 이 가이드는 개발 환경 설정부터 최종 이미지 저장까지 모든 단계를 안내하므로 몇 분 안에 신뢰할 수 있는 바코드를 생성할 수 있습니다.

## 빠른 답변
- **바코드를 생성하기 위한 주요 클래스는 무엇인가요?** `BarcodeGenerator`는 바코드 이미지를 생성하고 구성합니다.  
- **GS1 Code 128은 어떤 심볼리지를 사용하나요?** GS1‑특정 데이터 형식과 함께 `EncodeTypes.Code128` 타입을 사용합니다.  
- **개발에 라이선스가 필요합니까?** 평가용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **이미지 형식을 변경할 수 있나요?** 예—파일 확장자를 PNG, JPEG, BMP, 또는 TIFF로 변경하여 저장할 수 있습니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, .NET 6+.

## 코드 128 바코드 생성이란 무엇인가요?
`create code 128 barcode`는 Code 128 심볼리지를 사용하여 영숫자 데이터를 인코딩하는 1차원 바코드를 생성하는 것을 의미합니다. Code 128은 전체 ASCII 세트를 지원하고 GS1 애플리케이션 식별자를 삽입할 수 있어 물류 분야에서 널리 채택됩니다. 이 바코드는 제품 식별자, 일련 번호 및 기타 사용자 정의 데이터를 저장할 수 있어 다양한 비즈니스 시나리오에 적합합니다.

## GS1 Code 128에 Aspose.BarCode를 사용하는 이유
Aspose.BarCode는 **30개 이상의 바코드 심볼리지를** 지원하며 **10,000 × 10,000 px**까지 이미지 품질 손실 없이 렌더링할 수 있어 고해상도 라벨 인쇄에 적합합니다. 이 라이브러리는 GS1 데이터 구조를 자동으로 검증하여 생산 라인에서 잘못된 바코드가 발생할 위험을 줄여줍니다. 또한 크기, 색상, 레이아웃에 대한 광범위한 사용자 정의 옵션을 제공해 엄격한 산업 표준을 충족하도록 돕습니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **.NET 개발 환경** – Visual Studio 2022, Rider, 또는 .NET 6+를 지원하는 모든 IDE.  
2. **Aspose.BarCode for .NET** – **Aspose.BarCode for .NET 다운로드 페이지**([https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/))에서 다운로드하고 NuGet 패키지 `Aspose.BarCode`를 프로젝트에 추가하십시오.  
3. **기본 C# 지식** – 콘솔 또는 Windows 애플리케이션을 만드는 데 익숙해야 합니다.  
4. **GS1 Code 128에 대한 이해** – 선택 사항이지만 도움이 됩니다; GS1은 GTIN에 `(01)`, 일련 번호에 `(21)`과 같은 애플리케이션 식별자(AI)를 사용합니다.

## 코드 128 바코드 생성 단계별 가이드
라이브러리를 로드하고, 바코드 유형을 구성하고, GS1 데이터를 설정하고, 크기를 사용자 정의한 뒤 마지막으로 이미지를 저장합니다. “코드 128 바코드를 어떻게 생성하나요?”라는 질문에 대한 직접적인 답은: **`EncodeTypes.Code128`와 GS1‑형식 데이터로 `BarcodeGenerator`를 인스턴스화하고, 필요하면 `XDimension`을 조정한 뒤, 원하는 파일 이름과 형식으로 `Save`를 호출**하는 것입니다. 다음 섹션에서는 각 단계를 자세히 설명합니다.

### 단계 1: 디렉터리 경로 설정
생성된 이미지가 저장될 폴더를 정의합니다. 경로를 구성 가능하게 유지하면 다양한 환경에서 코드를 재사용할 수 있습니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

`"Your Directory Path"`를 애플리케이션이 쓸 수 있는 절대 경로나 상대 경로로 교체하십시오. 예: `@"C:\Barcodes"` 또는 `Path.Combine(Environment.CurrentDirectory, "Output")`.

### 단계 2: GS1 Code 128 바코드 생성
바코드 생성기를 만들고, 심볼리지를 지정한 뒤, GS1‑형식 데이터를 제공하십시오. 데이터 문자열에는 괄호로 감싼 애플리케이션 식별자가 포함되어야 합니다.

```csharp
string path = "Your Directory Path";
```

예제에서는 GTIN `(01)12345678901231`, 일련 번호 `(21)ASPOSE`, 추가 사용자 정의 AI `(30)9876`를 사용합니다. Aspose.BarCode는 GS1 준수를 위해 필요한 FNC1 문자를 자동으로 삽입합니다.

### 단계 3: 바코드 매개변수 사용자 정의
`XDimension`(좁은 바의 너비)과 같은 시각적 매개변수를 조정하여 바코드 밀도를 제어합니다. 높이, 색상, 여백도 수정할 수 있습니다.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

`XDimension = 2`로 설정하면 대부분의 핸드헬드 리더기로 쉽게 스캔할 수 있으면서 이미지 크기가 적당한 바코드가 생성됩니다.

### 단계 4: 바코드 이미지 저장
생성된 바코드를 디스크에 저장합니다. 무손실 품질을 원하면 PNG, 파일 크기를 줄이려면 JPEG, 인쇄 워크플로우에는 TIFF를 선택할 수 있습니다. `Save` 메서드는 파일 확장자에 따라 이미지 파일 형식을 지정합니다.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

`GS1Code128Example.png`를 원하는 출력 형식에 맞는 유효한 파일명 및 확장자로 교체하십시오.

### 단계 5: 바코드 검증 (선택 사항)
저장 후 이미지를 애플리케이션으로 다시 로드하거나 바코드 스캐너를 사용해 인코딩된 데이터가 원본 문자열과 일치하는지 확인할 수 있습니다. 이 단계는 개발 및 자동 테스트 시 유용합니다.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## 일반적인 문제 및 해결 팁
- **FNC1이 감지되지 않음** – 데이터 문자열이 여는 괄호로 시작하고 유효한 GS1 AI를 포함하는지 확인하십시오; 라이브러리는 인식된 패턴에 대해서만 FNC1을 자동으로 삽입합니다.  
- **이미지가 저장되지 않음** – 대상 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오. `Directory.CreateDirectory(path)`를 사용해 즉시 생성할 수 있습니다.  
- **바코드가 너무 조밀함** – `XDimension`을 줄이거나 이미지 높이를 늘려 스캐너가 좁은 바를 읽을 여유를 줍니다.  
- **지원되지 않는 문자** – Code 128은 전체 ASCII 세트만 인코딩할 수 있으므로 이 범위를 벗어나는 유니코드 문자는 피하십시오.

## 자주 묻는 질문

**Q: 전체 .NET Framework를 설치하지 않고 웹 API에서 바코드를 생성할 수 있나요?**  
A: 예, Aspose.BarCode는 .NET Core 및 .NET 5/6와 호환되므로 필요에 따라 바코드 이미지를 반환하는 경량 REST 엔드포인트를 제공할 수 있습니다.

**Q: 라이브러리가 여러 바코드의 배치 생성을 지원하나요?**  
A: 물론입니다. 데이터 문자열 컬렉션을 순회하면서 각 항목에 대해 `BarcodeGenerator`를 인스턴스화하고 루프 내에서 `Save`를 호출하십시오. 라이브러리는 병렬 처리를 위한 스레드 안전성을 제공합니다.

**Q: 바코드를 PDF에 직접 삽입할 수 있는 방법이 있나요?**  
A: Aspose.PDF를 사용해 PDF 문서를 만든 뒤, 바코드 이미지 스트림을 `PdfPage.AddImage`에 전달하십시오. 이렇게 하면 중간 파일을 디스크에 쓰는 것을 피할 수 있습니다.

**Q: 바코드가 ISO/GS1 품질 표준을 충족하도록 하려면 어떻게 해야 하나요?**  
A: `BarcodeGenerator.Options.Barcode.XDimension`을 최소 0.33 mm로 설정하고 라벨 크기에 맞게 `BarHeight`를 지정하십시오. Aspose.BarCode는 AI 형식을 검증하고 잘못된 데이터에 대해 예외를 발생시킵니다.

**Q: 프로덕션 사용을 위한 라이선스 옵션은 무엇이 있나요?**  
A: Aspose는 영구 라이선스, 구독 라이선스, 클라우드 기반 라이선스 모델을 제공합니다. 평가용으로는 체험 라이선스를 사용할 수 있지만, 유료 라이선스를 구매하면 평가 워터마크가 제거되고 모든 기능을 사용할 수 있습니다.

## 추가 리소스

- **문서** – 전체 API 레퍼런스는 [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/)에서 확인하십시오.  
- **다운로드** – 최신 라이브러리 릴리스는 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/)에서 받으십시오.  
- **무료 체험** – 30일 체험판은 [https://releases.aspose.com/](https://releases.aspose.com/)에서 시작하십시오.  
- **구매** – 상용 라이선스는 [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)에서 구매하십시오.  
- **지원** – 문제 해결을 위해 커뮤니티 포럼 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13)에 참여하십시오.

---

**마지막 업데이트:** 2026-09-08  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [ITF-14 바코드 .NET 생성 방법 – 포괄적인 Aspose.BarCode 튜토리얼](/barcode/net/)
- [Aspose.BarCode .NET API를 사용하여 1차원 Databar 2D 바코드 생성](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}