---
date: 2026-06-09
description: Aspose.BarCode for .NET를 사용하여 datamatrix 바코드를 생성하는 방법을 배우고, 종횡비, ECC
  모드 및 datamatrix c40 인코딩을 맞춤 설정하여 효율적인 바코드 생성을 구현하세요.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix 바코드 구성
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrix 바코드 생성 – Aspose.BarCode와 함께하는 전문가 가이드
url: /ko/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix 바코드 생성 – Aspose.BarCode 전문가 가이드

Aspose.BarCode for .NET를 사용하여 **generate datamatrix barcode**에 대한 포괄적인 튜토리얼 시리즈에 오신 것을 환영합니다. 숙련된 개발자이든 바코드 출력을 미세 조정하고 있든, 기본 구성부터 고급 인코딩 기술까지 모든 단계를 안내하여 .NET 애플리케이션에서 신뢰할 수 있고 스캔 준비된 바코드를 제공할 수 있도록 도와드립니다.

## 빠른 답변
- **주된 목적은 무엇인가요?** 프로그램matically DataMatrix 바코드를 생성하고 사용자 정의합니다.  
- **사용된 라이브러리는?** Aspose.BarCode for .NET.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 라이선스는 프로덕션에 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **종횡비를 사용자 정의할 수 있나요?** 예 – “How to customize DataMatrix aspect ratio” 섹션을 참고하세요.

## generate datamatrix barcode란 무엇인가요?
DataMatrix 바코드는 흑백 셀로 구성된 2차원 매트릭스로 최대 2 300개의 영숫자 문자를 저장할 수 있습니다. Aspose.BarCode를 사용하면 .NET 코드에서 직접 **generate datamatrix barcode** 이미지, PDF 또는 SVG를 생성하고, 크기, 오류 정정 수준 및 인코딩 모드를 제어하여 모든 산업 표준을 충족할 수 있습니다.

## DataMatrix에 Aspose.BarCode를 사용하는 이유
Aspose.BarCode는 픽셀화 없이 최대 **600 dpi**까지 DataMatrix 심볼을 렌더링하여 고해상도 프린터에서도 선명한 스캔을 보장합니다. **50개 이상의 ECC 및 매크로 모드**를 모두 지원하며—ECC 000‑140, ECC 200, Macro 05/06 포함—데이터 크기에 맞는 최적의 오류 정정 수준을 선택할 수 있습니다. API는 **ASCII, C40, Text, X12, Bytes** 인코딩 옵션을 제공하여 데이터를 효율적으로 압축합니다. 통합은 단일 NuGet 패키지만 필요하고 외부 네이티브 라이브러리가 필요 없습니다.

## DataMatrix 종횡비를 사용자 정의하는 방법
`BarCodeGenerator`의 `AspectRatio` 속성은 생성된 DataMatrix 심볼의 가로‑세로 비율을 제어합니다. `BarCodeGenerator`는 Aspose.BarCode에서 바코드 이미지를 생성하는 주요 클래스입니다.

**Direct answer:** `GenerateBarCodeImage()`를 호출하기 전에 `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2`(또는 0.5에서 2.0 사이의 값)로 설정하십시오. 라이브러리는 요청된 비율을 유지하면서 스캔 신뢰성을 보존하도록 모듈 크기를 자동으로 재계산합니다.

### 단계별
1. `EncodeTypes.DataMatrix`를 사용하여 `BarCodeGenerator`를 **Instantiate**합니다.  
2. 원하는 값으로 `AspectRatio`를 **Adjust**합니다.  
3. 이미지를 **Generate**하고 스캐너 또는 Aspose의 내장 리더기로 확인합니다.

## DataMatrix ECC 000‑140 바코드 생성 방법
ECC 000‑140은 짧은 데이터 문자열에 적합한 컴팩트한 심볼을 제공하며 최대 140개의 오류 정정 코드워드를 제공합니다. `DataMatrixEccMode.Ecc000140`는 DataMatrix에 대한 ECC 000‑140 오류 정정 방식을 선택합니다.

**Direct answer:** 렌더링하기 전에 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140`를 사용하십시오. 이렇게 하면 인코더가 ECC 000‑140 알고리즘으로 전환되어 주어진 데이터에 대해 가능한 가장 작은 매트릭스를 생성하면서도 강력한 오류 정정을 제공합니다.

### 실용적인 팁
20자 미만의 숫자 데이터를 인코딩할 때, ECC 000‑140은 종종 10 × 10 매트릭스를 생성하여 라벨 공간을 절약합니다.

## DataMatrix ECC 200 바코드 생성 방법
ECC 200은 가장 널리 채택된 DataMatrix 모드로, 최대 2 335개의 영숫자 문자를 지원하고 뛰어난 오류 정정을 제공합니다. `DataMatrixEccMode.Ecc200`는 DataMatrix에 대한 ECC 200 오류 정정 방식을 선택합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200`를 설정하고 `CodeText`를 통해 페이로드를 제공하십시오. 그러면 라이브러리가 자동으로 최적의 매트릭스 크기를 선택합니다.

### ECC 200을 선호해야 할 때
긴 문자열, 혼합형 데이터, 또는 손상에 대한 최고 수준의 복원력이 필요할 때 ECC 200을 사용하십시오—심볼의 **30 %**까지 복원할 수 있습니다.

## ASCII 모드에서 DataMatrix 인코딩 마스터하기
ASCII 모드는 문자당 한 바이트로 인코딩하여 일반 텍스트에 가장 공간 효율적입니다. `DataMatrixEncodeMode.Ascii`는 생성기가 DataMatrix 심볼에 ASCII 인코딩을 사용하도록 지정합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii`를 할당하고 `CodeText`를 ASCII 문자열로 설정하십시오. 엔진은 추가 오버헤드 없이 데이터를 압축하여 순수 ASCII 콘텐츠에 대해 가능한 가장 작은 매트릭스를 생성합니다.

### 예시 시나리오
대문자와 숫자로 구성된 창고 SKU(예: “AB1234”)는 ASCII 모드에 완벽히 맞으며, 종종 12 × 12 매트릭스를 생성합니다.

## DataMatrix 모드 (Auto) 생성 방법
Auto 모드는 Aspose.BarCode가 입력을 분석하여 가장 효율적인 인코딩(ASCII, C40, Text, X12, Bytes)을 자동으로 선택하도록 합니다. `DataMatrixEncodeMode.Auto`는 이 자동 선택 기능을 활성화합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`를 설정하십시오. 라이브러리는 페이로드를 평가하고 최적의 모드를 선택하여 한 단계로 바코드를 렌더링합니다.

### 장점
Auto 모드는 개발 노력을 줄이고 혼합형 데이터에 대해 가능한 가장 작은 심볼을 보장하여 스캔 속도를 향상시킵니다.

## Bytes 모드에서 DataMatrix 인코딩 사용 방법
Bytes 모드는 암호화된 페이로드나 압축 파일과 같은 바이너리 데이터를 위해 설계되었습니다. `DataMatrixEncodeMode.Bytes`는 생성기가 각 바이트를 원시 데이터로 처리하도록 지시합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes`를 사용하고 `CodeText`에 Base64 인코딩 문자열을 제공하십시오. 인코더는 각 바이트를 원시 데이터로 처리하여 정확한 바이너리 표현을 보존합니다.

### 사용 사례
128비트 GUID 또는 작은 암호화 토큰을 DataMatrix 심볼에 직접 삽입합니다.

## C40 모드에서 DataMatrix 인코딩 마스터하기
C40 모드는 대문자 영숫자 데이터를 압축하여 ASCII에 비해 최대 **40 %** 크기 감소를 달성합니다. `DataMatrixEncodeMode.C40`는 이 압축 알고리즘을 활성화합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40`를 설정하고 대문자 문자열(예: “HELLO WORLD”)을 제공하십시오. 엔진은 세 문자를 두 개의 코드워드로 압축하여 최종 매트릭스를 축소합니다.

### 전문가 팁
C40는 페이로드가 주로 대문자, 숫자 및 공백으로 구성될 때 가장 효과적입니다. 혼합 대소문자의 경우 Auto 모드를 고려하십시오.

## DataMatrix 코드 텍스트 구성 방법
`CodeText` 속성은 바코드에 저장되는 정확한 데이터를 정의합니다. 일반 텍스트, 숫자 문자열 또는 XML 페이로드를 포함할 수 있습니다. `CodeText`는 `BarCodeGenerator`의 주요 문자열 속성으로 바코드 페이로드를 보관합니다.

**Direct answer:** 렌더링하기 전에 `generator.Parameters.Barcode.CodeText = "YourDataHere"`를 할당하십시오. 이 속성은 선택된 ECC 모드가 지원하는 최대 길이까지 모든 UTF‑8 문자열을 허용합니다.

### 고급 팁
`CodeText`와 `ExtendedDataMatrix`를 결합하여 눈에 보이는 매트릭스 크기를 늘리지 않고 추가 메타데이터를 삽입하십시오.

## DataMatrix 매크로 구성 마스터하기
Macro 모드(Macro 05 및 Macro 06)는 기본 DataMatrix 심볼 내부에 보조 DataMatrix 심볼을 삽입할 수 있게 하여 외부 데이터 소스와 연결하는 데 유용합니다. `DataMatrixMacroMode.Macro05`와 `DataMatrixMacroMode.Macro06`가 이러한 매크로 기능을 활성화합니다.

**Direct answer:** `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05`(또는 `Macro06`)로 매크로 모드를 활성화하고 보조 페이로드에 대해 `MacroPdf417` 속성을 설정하십시오. 생성기는 스캐너가 두 개의 연결된 코드를 해석할 수 있는 복합 심볼을 생성합니다.

### 실제 예시
매크로 부분에 URL을 삽입하고 기본 매트릭스에 제품 식별자를 유지하여 웹‑바코드 통합을 원활하게 구현합니다.

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## DataMatrix 바코드 구성 튜토리얼
### [DataMatrix 종횡비 사용자 정의](./datamatrix-aspect-ratio-customization/)
Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드 종횡비를 사용자 정의하는 방법을 배웁니다. 바코드 생성에 대한 단계별 가이드.

### [DataMatrix ECC 000-140 바코드 생성](./datamatrix-ecc-000-140-configuration/)
Aspose.BarCode for .NET를 사용하여 DataMatrix ECC 000-140 바코드를 손쉽게 생성합니다. 재고 관리 등에서 효율성을 높입니다.

### [DataMatrix ECC 200 바코드 생성](./datamatrix-ecc-200-configuration/)
.NET에서 Aspose.BarCode를 사용하여 DataMatrix ECC 200 바코드를 생성하는 방법을 배웁니다. 효율적인 바코드 생성으로 운영을 간소화합니다.

### [ASCII 모드에서 DataMatrix 인코딩 마스터](./datamatrix-encoding-mode-ascii/)
Aspose.BarCode for .NET를 사용하여 ASCII 모드에서 DataMatrix 바코드를 만드는 방법을 배웁니다. 개발자를 위한 단계별 가이드.

### [DataMatrix 모드 (Auto) 생성](./datamatrix-encoding-mode-auto/)
Aspose.BarCode for .NET를 사용하여 DataMatrix 모드 (Auto)를 생성하는 방법을 배웁니다. 전제 조건부터 바코드 읽기까지 모든 것을 다루는 단계별 가이드.

### [DataMatrix 인코딩 모드 (Bytes)](./datamatrix-encoding-mode-bytes/)
Aspose.BarCode for .NET와 함께 Bytes 모드로 DataMatrix 형식으로 데이터를 인코딩하는 방법을 배웁니다. 바코드 생성 및 인식에 대한 단계별 가이드를 따르세요.

### [C40 모드에서 DataMatrix 인코딩 마스터](./datamatrix-encoding-mode-c40/)
Aspose.BarCode for .NET와 함께 DataMatrix 인코딩 모드 (C40)를 배웁니다. 맞춤형 바코드를 효율적으로 생성합니다. 단계별 가이드를 탐색하세요.

### [DataMatrix 코드 텍스트 구성](./datamatrix-extended-code-text-configuration/)
Aspose.BarCode for .NET를 사용하여 DataMatrix 확장 코드 텍스트를 구성하는 방법을 배웁니다. .NET 애플리케이션에서 바코드를 생성, 인식 및 통합합니다.

### [DataMatrix 매크로 구성 마스터](./datamatrix-macro-configuration/)
Aspose.BarCode for .NET와 함께 DataMatrix 매크로 바코드를 구성하는 방법을 배웁니다. .NET 애플리케이션에서 DataMatrix 바코드를 생성, 사용자 정의 및 인식합니다.

## 자주 묻는 질문

**Q: ECC 모드를 어떻게 선택하나요?**  
A: 작은 데이터 세트와 제한된 오류 정정이 필요할 경우 ECC 000‑140를, 더 큰 데이터와 높은 신뢰성이 필요할 경우 ECC 200을 선택하십시오. 매크로 모드는 연결을 위한 추가 데이터 레이어를 제공합니다.

**Q: DataMatrix 바코드에 사용자 정의 텍스트를 삽입할 수 있나요?**  
A: 예, `CodeText` 속성을 원하는 문자열로 설정한 다음 적절한 인코딩 모드(ASCII, C40 등)를 선택하여 크기를 제어하십시오.

**Q: 최적의 인코딩 모드를 자동으로 선택하는 방법이 있나요?**  
A: `EncodeMode`를 `Auto`로 설정하십시오; Aspose.BarCode가 페이로드를 평가하여 자동으로 가장 공간 효율적인 모드를 선택합니다.

**Q: 대량 바코드 배치의 성능 고려 사항은 무엇인가요?**  
A: 단일 `BarCodeGenerator` 인스턴스를 재사용하고, 멀티스레딩을 활성화하며, 무손실 품질을 위해 PNG 이미지를, 파일 크기를 줄이려면 JPEG를 생성하십시오. 표준 8코어 서버에서 10 000개의 심볼을 처리하는 데 보통 30초 미만이 소요됩니다.

**Q: Aspose.BarCode가 .NET Core 및 .NET 5/6을 지원하나요?**  
A: 물론입니다 – 이 라이브러리는 .NET Framework, .NET Core 및 최신 .NET 릴리스와 완전히 호환되며 모든 플랫폼에서 동일한 기능 세트를 제공합니다.

**마지막 업데이트:** 2026-06-09  
**테스트 환경:** Aspose.BarCode 24.12 for .NET  
**작성자:** Aspose

## 관련 튜토리얼
- [Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드 (ECC 200) 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET와 함께 ASCII 모드에서 DataMatrix 인코딩 마스터](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [바코드 PNG 생성 – DataMatrix 종횡비 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}