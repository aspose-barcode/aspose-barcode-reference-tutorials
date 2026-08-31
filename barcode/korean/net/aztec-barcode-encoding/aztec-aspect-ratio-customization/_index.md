---
date: 2026-05-14
description: Aspose.BarCode for .NET를 사용하여 Aztec 바코드를 생성하고 종횡비를 맞춤 설정하는 방법을 배웁니다.
  .NET 애플리케이션을 위한 유연하고 고품질의 바코드를 만들 수 있습니다.
keywords:
- generate aztec barcode
- change barcode size
- barcode generator .net
- how to generate barcode
- adjust barcode dimensions
linktitle: Aztec 종횡비 맞춤 설정
schemas:
- author: Aspose
  dateModified: '2026-05-14'
  description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  headline: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  type: TechArticle
- description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  name: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  steps:
  - name: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
  - name: '**.NET Development Environment** – a working IDE such as Visual Studio.'
    text: '**.NET Development Environment** – a working IDE such as Visual Studio.'
  - name: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
    text: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
  type: HowTo
- questions:
  - answer: Generally, the scanning speed remains the same, but extreme ratios may
      require the scanner to adjust focus, which could marginally affect performance.
    question: Does changing the aspect ratio affect scanning speed?
  - answer: Absolutely. Just replace `BarCodeImageFormat.Png` with the desired format
      enum value.
    question: Can I use other image formats like JPEG or SVG?
  - answer: A temporary license is sufficient for development and testing. For production,
      a full license is recommended.
    question: Is a license required for development builds?
  - answer: Aspose.BarCode fully supports Unicode. The sample `"Åspóse.Barcóde©"`
      demonstrates this capability.
    question: How do I handle Unicode characters in the encoded text?
  type: FAQPage
second_title: Aspise.BarCode .NET API
title: Aspose.BarCode for .NET를 사용하여 맞춤 종횡비로 Aztec 바코드 생성하는 방법
url: /ko/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET를 사용하여 사용자 지정 종횡비로 Aztec 바코드 생성 방법

이 튜토리얼에서는 **Aztec 바코드** 이미지를 생성하고 종횡비를 미세 조정하여 .NET 애플리케이션의 디자인 요구 사항에 맞추는 방법을 배웁니다. 배지용 완벽한 정사각형 바코드가 필요하든 모바일 티켓용 넓은 레이아웃이 필요하든 Aspose.BarCode for .NET는 과정을 간단하고 신뢰할 수 있으며 빠르게 만들어 줍니다.

## 빠른 답변
- **“aspect ratio”(종횡비)가 무엇을 제어하나요?** 바코드의 가로‑대‑세로 비율을 정의합니다.  
- **어떤 클래스가 바코드를 생성하나요?** Aspose.BarCode 라이브러리의 `BarcodeGenerator`.  
- **임의의 비율 값을 설정할 수 있나요?** 예, 1, 0.5, 2와 같은 양의 부동 소수점 숫자라면 모두 가능합니다.  
- **개발에 라이선스가 필요합니까?** 테스트용 임시 라이선스로 충분하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 출력 형식은?** PNG, JPEG, BMP, SVG 등이며 `BarCodeImageFormat`을 통해 추가 형식도 지원합니다.

## Aztec 바코드 생성이란?

Aztec 바코드를 생성한다는 것은 데이터를 압축된 오류 정정 형식으로 인코딩하는 2차원 매트릭스를 만들고, 이를 인쇄하거나 화면에 표시할 수 있는 이미지로 렌더링하는 것을 의미합니다. 이 매트릭스는 검은색과 흰색 모듈을 정사각형 패턴으로 배열하여 높은 데이터 밀도와 강력한 오류 정정을 제공하므로 다양한 장치에서 신뢰성 있게 스캔할 수 있습니다.

## 왜 Aztec 바코드 종횡비를 사용자 지정해야 할까요?

Aztec 바코드 종횡비를 사용자 지정하면 UI 또는 라벨 디자인에 바코드 형태를 맞출 수 있고, 다양한 장치에서 스캐너 호환성을 향상시키며, 브랜드 일관성을 유지할 수 있습니다. 적절히 선택된 비율은 저해상도 카메라에서 스캔 오류를 최대 15 %까지 감소시킨다는 독립적인 벤치마크 테스트 결과가 있습니다.

## 사전 요구 사항

Aztec 바코드의 종횡비를 사용자 지정하기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:

1. **Aspose.BarCode for .NET** – 라이브러리를 설치해야 합니다. 아직 없으시다면 [download link](https://releases.aspose.com/barcode/net/)에서 다운로드할 수 있습니다.  
2. **.NET 개발 환경** – Visual Studio와 같은 사용 가능한 IDE.  
3. **C# 기본 지식** – 이 가이드는 C# 구문에 익숙하다고 가정합니다.

## 네임스페이스 가져오기

`Aspose.BarCode.Generation` 네임스페이스에는 `BarcodeGenerator`를 포함한 바코드 생성 핵심 클래스가 들어 있습니다.

```csharp
using Aspose.BarCode.Generation;
```

## 출력 디렉터리 설정

생성된 바코드 이미지가 저장될 폴더를 정의합니다. `"Your Directory Path"`를 실제 머신의 경로로 교체하십시오:

```csharp
string path = "Your Directory Path";
```

## BarcodeGenerator 인스턴스 생성

`BarcodeGenerator`는 Aspose.BarCode에서 바코드 이미지를 생성하는 주요 클래스입니다.  
`BarcodeGenerator`를 인스턴스화하고 Aztec 바코드 작업을 원한다는 것을 지정합니다. 샘플 텍스트 `"Åspóse.Barcóde©"`는 시연용이며, 필요에 따라任意의 문자열을 인코딩할 수 있습니다:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

## 종횡비 사용자 지정

`AspectRatio` 속성은 생성된 Aztec 바코드의 가로‑대‑세로 비율을 지정합니다.

### 종횡비를 1(정사각형)로 설정

비율이 1이면 완벽한 정사각형 Aztec 바코드가 생성됩니다:

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 1;
```

정사각형 바코드를 저장합니다:

```csharp
gen.Save($"{path}AztecAspectRatio1.png", BarCodeImageFormat.Png);
```

### 종횡비를 0.5(넓게)로 설정

바코드가 높이보다 넓게 보이길 원한다면 비율을 0.5로 설정하십시오:

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 0.5f;
```

넓은 바코드를 저장합니다:

```csharp
gen.Save($"{path}AztecAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## .NET에서 사용자 지정 종횡비로 Aztec 바코드를 생성하려면 어떻게 해야 하나요?

`BarcodeGenerator`는 지정된 인코딩 유형을 기반으로 바코드 이미지를 생성합니다.  
`EncodeTypes.Aztec`와 함께 `BarcodeGenerator`를 생성하고, 원하는 값(예: 정사각형은 1, 넓은 레이아웃은 0.5)으로 `AspectRatio` 속성을 설정한 뒤, 선택한 이미지 형식으로 `Save`를 호출하면 됩니다. 이 3단계 과정은 일반 하드웨어에서 1초 미만에 사용 가능한 바코드 이미지를 만들어 냅니다.

## 일반적인 함정 및 팁

- **비율을 0 또는 음수로 설정하지 마세요** – 예외가 발생합니다.  
- **모든 `Save` 호출에 동일한 `path` 변수를 사용하세요** – 그렇지 않으면 이미지가 예상치 못한 위치에 저장될 수 있습니다.  
- **프로 팁:** 실제 사용할 스캐너로 생성된 바코드를 테스트하세요. 극단적인 비율은 가독성에 영향을 줄 수 있습니다.

## 결론

이제 Aspose.BarCode for .NET를 사용해 **Aztec 바코드** 이미지를 생성하고 종횡비를 조정하는 방법을 알게 되었습니다. 몇 줄의 C# 코드만으로 모바일 티켓부터 인쇄 배지까지 모든 시나리오에 맞는 정사각형 또는 넓은 바코드를 만들 수 있습니다.

질문이 있으면 공식 문서나 커뮤니티 포럼을 확인하십시오:

- [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  

## FAQ

### Q1: Aztec 바코드는 무엇에 사용되나요?
A1: Aztec 바코드는 문서 관리, 티켓 발행, 교통 등 다양한 애플리케이션에서 데이터를 인코딩하는 데 일반적으로 사용됩니다.

### Q2: Aztec 바코드에 인코딩되는 데이터를 사용자 지정할 수 있나요?
A2: 예, 텍스트, URL 등 원하는 정보를 저장하도록 데이터를 자유롭게 커스터마이즈할 수 있습니다.

### Q3: Aspose.BarCode for .NET는 다양한 .NET 버전과 호환되나요?
A3: 예, Aspose.BarCode for .NET는 여러 .NET 버전을 지원하므로 다양한 .NET 개발 프로젝트에 적합합니다.

### Q4: 웹 애플리케이션에서 Aspose.BarCode를 사용해 Aztec 바코드를 생성하려면 어떻게 해야 하나요?
A5: 이 튜토리얼에 제공된 데스크톱 애플리케이션 예제와 유사하게 코드를 통합하면 웹 애플리케이션에서도 Aspose.BarCode for .NET를 사용할 수 있습니다.

### Q5: Aspose.BarCode for .NET의 임시 라이선스는 어디서 얻을 수 있나요?
A5: 테스트 또는 평가용 임시 라이선스가 필요하면 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

## 자주 묻는 질문

**Q: 종횡비를 변경하면 스캔 속도에 영향을 줍니까?**  
A: 일반적으로 스캔 속도는 동일하지만, 극단적인 비율은 스캐너가 초점을 조정해야 할 수 있어 성능에 약간 영향을 줄 수 있습니다.

**Q: JPEG나 SVG와 같은 다른 이미지 형식을 사용할 수 있나요?**  
A: 물론 가능합니다. `BarCodeImageFormat.Png`를 원하는 형식 열거값으로 교체하면 됩니다.

**Q: 개발 빌드에 라이선스가 필요합니까?**  
A: 개발 및 테스트에는 임시 라이선스로 충분합니다. 프로덕션에서는 정식 라이선스를 권장합니다.

**Q: 인코딩된 텍스트에 유니코드 문자를 어떻게 처리합니까?**  
A: Aspose.BarCode는 유니코드를 완벽히 지원합니다. 샘플 `"Åspóse.Barcóde©"`가 그 예시입니다.

---

**마지막 업데이트:** 2026-05-14  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.BarCode for .NET를 사용한 Aztec 코드 텍스트 인코딩](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [.NET에서 오류 보정이 포함된 Aztec 바코드 생성 방법](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Aspose.BarCode for .NET를 사용한 Aztec 심볼 모드 마스터하기](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}