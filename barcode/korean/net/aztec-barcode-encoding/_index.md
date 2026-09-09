---
date: 2026-05-19
description: Aspose.BarCode for .NET를 사용하여 Aztec barcode를 만드는 방법을 배우고, aspect ratios를
  사용자 지정하고, bytes 또는 text를 인코딩하며, master symbol modes를 활용하세요.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec Barcode 인코딩
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET를 사용하여 Aztec barcode 만드는 방법
url: /ko/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aztec 바코드 인코딩

Aztec 바코드 인코딩의 세계에 뛰어들 준비가 되셨나요? Aspose.BarCode for .NET을 사용하여 **Aztec 바코드 생성** 이미지를 만드는 방법을 배워보세요. 이 라이브러리는 크기, 오류 수정, 데이터 표현에 대한 완전한 제어를 제공하므로 모바일 티켓팅부터 재고 추적까지 모든 용도에 이상적입니다.

## 빠른 답변
- **Aztec 바코드를 지원하는 라이브러리는 무엇인가요?** Aspose.BarCode for .NET  
- **종횡비를 변경할 수 있나요?** Yes, via the `AspectRatio` property  
- **바이트 수준 인코딩이 가능한가요?** Absolutely – use the `EncodeBytes` method  
- **사용 가능한 오류 수정 레벨은 무엇인가요?** Levels 0 to 4 (higher = more redundancy)  
- **프로덕션에 라이선스가 필요합니까?** Yes, a commercial license removes evaluation limits  

## Aztec 바코드란?
Aztec 바코드는 최대 3,000개의 숫자 또는 2,300개의 영숫자 문자를 인코딩할 수 있는 2차원 매트릭스 코드입니다. 중앙에 찾기 패턴이 있어 저해상도로 인쇄된 경우에도 빠른 스캔이 가능합니다. 패턴이 중앙에 위치하기 때문에 코드를 어느 방향에서든 읽을 수 있어 모바일 및 산업용 애플리케이션에서 높은 신뢰성을 제공합니다.

## Aztec 바코드의 종횡비를 어떻게 맞춤 설정하나요?
`BarcodeGenerator`는 Aspose.BarCode에서 바코드를 생성할 때 사용하는 주요 클래스입니다. `BarcodeGenerator` 객체의 `AspectRatio` 속성을 원하는 가로‑세로 비율로 설정한 뒤 이미지를 생성합니다. 종횡비를 조정하면 스캔 신뢰성을 유지하면서 제한된 UI 공간이나 라벨 레이아웃에 바코드를 맞출 수 있으며, 브랜드 가이드라인이나 특정 프린터 요구 사항에 맞추는 데도 도움이 됩니다.

### 종횡비 맞춤 설정 단계
1. **`EncodeTypes.Aztec`와 함께 `BarcodeGenerator` 인스턴스를 생성합니다.**  
2. **데이터를 할당합니다** (텍스트, 바이트 또는 숫자 문자열).  
3. **`AspectRatio`를 설정합니다** – 예를 들어, 더 넓은 바를 위해 `1.5`를 사용합니다.  
4. **`Save` 또는 `GetBarCodeImage`를 사용해 이미지를 생성합니다.**  

## 원시 바이트를 Aztec 바코드에 인코딩하려면 어떻게 해야 하나요?
`EncodeBytes`는 바이트 배열을 받아 Aztec 매트릭스로 변환하는 메서드입니다. `BarcodeGenerator`의 `EncodeBytes` 메서드에 바이트 배열을 전달합니다. API는 바이너리 데이터를 자동으로 압축된 Aztec 매트릭스로 변환하여 모든 비트를 보존합니다. 이는 암호화된 페이로드, 바이너리 식별자 또는 압축 파일을 바코드에 직접 삽입할 때 이상적입니다.

### 바이트 인코딩 단계
1. **바이트 배열을 준비합니다** (예: `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **`EncodeTypes.Aztec`와 함께 `BarcodeGenerator`를 인스턴스화합니다.**  
3. **바이너리 내용을 로드하기 위해 `EncodeBytes(data)`를 호출합니다.**  
4. **`Save` 또는 `GetBarCodeImage`를 사용해 바코드를 렌더링합니다.**  

## 텍스트를 Aztec 바코드에 인코딩하려면 어떻게 하나요?
`CodeText`는 인코딩할 평문 데이터를 보관하는 속성입니다. `BarcodeGenerator`의 `CodeText` 속성을 사용해 평문 데이터를 제공하세요. 라이브러리는 자동으로 최적의 인코딩 모드(숫자, 영숫자 또는 바이트)를 선택하고 적절한 오류 수정 레벨을 적용합니다. 이를 통해 URL, 제품 ID 또는 읽을 수 있는 문자열을 쉽게 삽입할 수 있습니다.

### 텍스트 인코딩 단계
1. **`EncodeTypes.Aztec`와 함께 생성기를 만듭니다.**  
2. **인코딩하려는 문자열을 `CodeText`에 설정합니다.**  
3. **필요에 따라 더 높은 복원력을 위해 `ErrorLevel`을 조정합니다.**  
4. **`Save` 또는 `GetBarCodeImage`를 사용해 이미지를 생성합니다.**  

## 다양한 오류 수정 레벨로 Aztec 바코드를 생성하려면 어떻게 하나요?
`ErrorLevel`은 바코드에 추가되는 중복 데이터 양을 제어하는 속성입니다. 렌더링 전에 `ErrorLevel` 속성(0‑4)을 조정하세요. 레벨이 높을수록 중복 데이터가 증가하여 심볼의 최대 30 %가 손상되어도 바코드를 읽을 수 있습니다. 이는 산업 라벨링이나 야외 표지판과 같은 가혹한 환경에서 매우 중요합니다.

### 오류 수정 설정 단계
1. **Aztec용 `BarcodeGenerator`를 인스턴스화합니다.**  
2. **데이터를 할당합니다** (텍스트 또는 바이트).  
3. **`ErrorLevel`을 설정합니다** – 예: `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **선호하는 출력 형식으로 바코드를 렌더링합니다.**  

## 다양한 Aztec 심볼 모드는 무엇이며 어떻게 사용하나요?
`SymbolMode`는 생성된 Aztec 코드의 매트릭스 크기와 데이터 용량을 결정하는 설정입니다. 라이브러리는 네 가지 모드를 제공합니다: **Auto**, **FullRange**, **Compact**, **Rune**.

- **Auto** – 생성기가 가능한 가장 작은 크기를 선택합니다.  
- **FullRange** – 매우 큰 데이터 세트를 위해 최대 매트릭스 크기를 허용합니다.  
- **Compact** – 제한된 공간에 적합한 더 작고 밀집된 심볼을 생성합니다.  
- **Rune** – 유니코드 룬을 인코딩하기 위한 특수 모드입니다.

`Generator.Parameters.Barcode.Aztec.SymbolMode`를 통해 모드를 선택합니다. 각 모드는 크기, 가독성 및 데이터 용량 사이의 균형을 맞추어 애플리케이션의 제약에 맞게 바코드를 맞춤 설정할 수 있습니다.

## Aztec 바코드 인코딩 튜토리얼
아래는 위에서 다룬 각 주제에 대해 자세히 설명하는 단계별 가이드입니다. 링크를 클릭하면 전체 코드 샘플, 전제 조건 및 모범 사례 팁을 확인할 수 있습니다.

### [Aztec 바코드 종횡비 맞춤 설정](./aztec-aspect-ratio-customization/)
Aspose.BarCode for .NET을 사용하여 Aztec 바코드 종횡비를 맞춤 설정하는 방법을 배웁니다. .NET 애플리케이션을 위한 독특하고 유연한 바코드를 생성하세요.

### [Aztec 바이트 인코딩](./aztec-bytes-encoding/)
Aspose.BarCode for .NET을 사용한 Aztec 바이트 인코딩 방법을 배웁니다. 단계별 가이드, 전제 조건 및 코드 예제가 포함되어 있습니다.

### [Aztec 코드 텍스트 인코딩](./aztec-code-text-encoding/)
Aspose.BarCode for .NET을 활용한 Aztec 코드 텍스트 인코딩의 강력함을 확인하세요. .NET 애플리케이션에서 Aztec 코드를 생성하고 인식하는 방법을 배웁니다.

### [Aztec 오류 바코드 생성](./aztec-error-level-example/)
Aspose.BarCode for .NET을 사용하여 다양한 오류 레벨의 Aztec 오류 바코드를 생성하는 방법을 배웁니다. 바코드 생성에 대한 포괄적인 가이드입니다.

### [Aztec 심볼 모드 마스터하기](./aztec-symbol-mode-example/)
Aspose.BarCode for .NET에서 Aztec 심볼 모드를 탐색하고 손쉽게 다목적 바코드를 생성하는 방법을 배웁니다. 이 포괄적인 튜토리얼에서 Auto, FullRange, Compact, Rune 모드를 직접 체험해 보세요.

## 자주 묻는 질문

**Q: Aspose.BarCode가 Aztec 인코딩을 지원하는 .NET 버전은 무엇인가요?**  
A: 라이브러리는 .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 및 이후 버전에서 작동합니다.

**Q: 인쇄용 고해상도 Aztec 바코드를 생성할 수 있나요?**  
A: 예—이미지를 저장하기 전에 `Resolution` 속성(예: 300 dpi)을 설정하면 인쇄 준비가 된 품질을 얻을 수 있습니다.

**Q: Aztec 바코드가 담을 수 있는 데이터 양은 얼마나 큰가요?**  
A: 최대 3,000개의 숫자 또는 2,300개의 영숫자 문자, 또는 Compact 모드에서는 약 1,800바이트의 원시 데이터를 담을 수 있습니다.

**Q: 회전된 Aztec 바코드를 읽을 수 있나요?**  
A: 물론입니다—Aspose.BarCode의 디코더는 자동으로 방향을 감지하고 읽기 작업 중에 이를 보정합니다.

**Q: 개발 및 테스트에 라이선스가 필요합니까?**  
A: 테스트용으로는 무료 평가 라이선스를 사용할 수 있으며, 프로덕션 배포에는 상용 라이선스가 필요합니다.

---

**마지막 업데이트:** 2026-05-19  
**테스트 환경:** Aspose.BarCode 24.12 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.BarCode for .NET을 사용하여 맞춤 종횡비로 Aztec 바코드 생성하는 방법](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [barcode generator .net을 사용한 Aztec 바이트 인코딩](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [.NET에서 오류 수정을 포함한 Aztec 바코드 생성 방법](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}