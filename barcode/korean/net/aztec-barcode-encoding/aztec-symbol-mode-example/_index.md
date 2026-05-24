---
date: 2026-05-24
description: Aspose.BarCode for .NET를 사용하여 Aztec 바코드 .NET을 만드는 방법을 배우고, Auto, FullRange,
  Compact, Rune 심볼 모드를 단계별로 안내합니다.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Aztec 심볼 모드 예제
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode를 사용하여 Aztec 바코드 .NET 만들기
url: /ko/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.BarCode와 함께하는 Aztec Symbol Mode 마스터하기

빠르고 안정적으로 **create aztec barcode .net**을(를) 만들고 싶다면, Aspose.BarCode for .NET은 .NET Framework, .NET Core 및 .NET 5/6+에서 작동하는 완전한 기능을 갖춘 API를 제공합니다. 이 튜토리얼에서는 네 가지 Aztec Symbol Mode—Auto, FullRange, Compact, Rune—를 살펴보고, 모드를 전환하고 결과를 이미지로 저장하는 방법을 정확히 보여드립니다. 끝까지 읽으면 몇 줄의 코드만으로 모든 .NET 애플리케이션에 Aztec 바코드를 삽입할 수 있게 됩니다.

## 빠른 답변
- **.NET에서 Aztec 바코드를 생성하는 라이브러리는 무엇인가요?** Aspose.BarCode for .NET.  
- **Aztec가 지원하는 심볼 모드는 몇 개입니까?** 네 가지: Auto, FullRange, Compact, Rune.  
- **개발에 라이선스가 필요합니까?** 평가용으로는 무료 체험판을 사용할 수 있으며, 제품 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, .NET 6+.  
- **PNG, JPEG, 또는 SVG로 출력할 수 있나요?** 예—표준 이미지 포맷이면 모두 지원됩니다.

## create aztec barcode .net이란 무엇인가요?
`create aztec barcode .net`은 .NET 환경에서 Aspose.BarCode API를 사용해 Aztec 2차원 바코드를 생성하는 과정을 의미합니다. API는 인코딩, 심볼 모드 선택 및 이미지 렌더링을 자동으로 처리하여, 개발자가 오류 정정 계산이나 픽셀 조작과 같은 저수준 세부 사항을 신경 쓰지 않고도 고품질 바코드를 만들 수 있게 합니다.

## Aztec 바코드에 Aspose.BarCode를 사용하는 이유는?
Aspose.BarCode는 **30개 이상의 바코드 심볼**을 지원하며 전체 파일을 메모리에 로드하지 않고도 **10,000 × 10,000 px**까지의 이미지를 렌더링할 수 있습니다. 일반 서버에서 500페이지 문서를 **2초** 미만에 처리하므로 고처리량 엔터프라이즈 시나리오에 이상적입니다.

## 사전 요구 사항

시작하기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:

- .NET 개발에 대한 기본 지식.  
- 머신에 Visual Studio가 설치되어 있어야 합니다.  
- Aspose.BarCode for .NET 사본. [여기](https://releases.aspose.com/barcode/net/)에서 다운로드할 수 있습니다. 다른 Aspose 제품은 [여기](https://releases.aspose.com/)에서 확인하세요.

이제 준비가 되었으니 Aztec Symbol Mode 예제로 들어가 보겠습니다.

## 네임스페이스 가져오기

먼저 Aspose.BarCode for .NET을 사용하려면 필요한 네임스페이스를 가져와야 합니다. Visual Studio 프로젝트를 열고 코드 파일 상단에 다음 using 문을 추가하십시오:

```csharp
using Aspose.BarCode.Generation;
```

네임스페이스가 준비되면 이제 Aspose.BarCode for .NET을 사용할 수 있습니다.

## Aztec 바코드용 Barcode Generator를 어떻게 설정하나요?

`BarcodeGenerator` 클래스는 선택된 심볼 및 구성 옵션을 기반으로 바코드 이미지를 생성하는 핵심 구성 요소입니다. 이 클래스는 바코드 유형, 인코딩할 데이터 및 다양한 렌더링 매개변수를 지정한 후 이미지 파일로 저장할 수 있는 간단한 API를 제공합니다.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

이 단계에서는 생성기를 설정하고 인코딩할 코드 텍스트를 제공했습니다.

## Aztec Symbol Mode를 Auto로 설정하는 방법은?

`AztecSymbolMode` 열거형은 Aztec 바코드에 사용할 수 있는 네 가지 심볼 모드를 정의하며, **Auto** 옵션을 사용하면 라이브러리가 데이터와 오류 정정 요구 사항을 모두 유지하면서 가장 작은 크기를 자동으로 선택합니다. 이 모드는 수동 조정 없이 가능한 가장 작은 바코드가 필요할 때 이상적입니다.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

이 단계는 Aztec Symbol Mode가 자동으로 결정되도록 보장하고, 결과 바코드 이미지를 저장합니다.

## FullRange Symbol Mode를 강제로 설정하는 방법은?

최대 데이터 용량이 필요할 때는 `AztecSymbolMode` 열거형의 **FullRange** 값을 선택할 수 있습니다. 이 모드는 자동 크기 축소를 비활성화하여 바코드가 전체 문자 범위를 저장하고 가능한 가장 높은 정보 밀도를 달성하도록 합니다. 대용량 데이터 세트에 유용합니다.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

이렇게 하면 FullRange Aztec Symbol Mode를 사용한 바코드가 생성됩니다.

## Compact Aztec 바코드를 생성하는 방법은?

`AztecSymbolMode` 열거형의 **Compact** 값은 매트릭스에 사용되는 레이어 수를 줄여 더 작은 바코드를 생성합니다. 이는 공간 효율적인 이미지를 제공하므로 모바일 화면이나 작은 라벨과 같이 표시 영역이 제한된 애플리케이션에 적합합니다.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

이 단계는 Compact Aztec Symbol Mode로 바코드를 생성하도록 구성합니다.

## Rune Aztec 바코드를 만드는 방법은?

**Rune** 모드는 사용자 정의 문자 집합을 사용해 숫자 데이터를 인코딩하는 Aztec 심볼의 특수 변형으로, 다른 모드와 동일한 오류 정정 강도를 유지하면서 독특한 시각적 스타일을 제공합니다. 숫자 정보를 강조해야 할 때 유용합니다.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

이 단계에서는 코드 텍스트를 "123"으로 변경하고 Rune Aztec Symbol Mode를 사용해 바코드를 생성합니다.

## 일반적인 문제 및 해결책

- **이미지가 저장되지 않음** – 출력 폴더가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오.  
- **예상치 못한 심볼 크기** – 코드에서 `EncodeMode`를 다른 곳에서 재정의하지 않았는지 확인하십시오.  
- **라이선스 예외** – 체험판은 워터마크를 추가합니다; 유효한 라이선스를 적용하면 제거됩니다.

## 자주 묻는 질문

**Q: Aztec Symbol Mode의 목적은 무엇인가요?**  
A: Aztec Symbol Mode는 라이브러리가 데이터를 레이어에 어떻게 패킹하는지를 결정하며, 크기, 용량 및 가독성에 영향을 줍니다.

**Q: Aspose.BarCode for .NET에서 Aztec 바코드의 코드 텍스트를 변경할 수 있나요?**  
A: 예, `Save`를 호출하기 전에 `CodeText` 속성에 새 문자열을 할당하면 됩니다.

**Q: Aspose.BarCode for .NET의 무료 체험 버전이 제공되나요?**  
A: 예, Aspose.BarCode for .NET의 무료 체험 버전을 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: Aspose.BarCode for .NET에 대한 전체 문서는 어디에서 찾을 수 있나요?**  
A: 전체 문서는 [여기](https://reference.aspose.com/barcode/net/)에서 확인할 수 있습니다.

**Q: Aspose.BarCode for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 임시 라이선스는 [이 링크](https://purchase.aspose.com/temporary-license/)를 통해 획득할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.BarCode를 사용해 **create aztec barcode .net**을 수행하는 방법을 살펴보았으며, Auto, FullRange, Compact, Rune 심볼 모드를 모두 다루었습니다. 이제 데스크톱, 웹 서버 또는 클라우드 서비스 등 어떤 .NET 애플리케이션에도 다목적 Aztec 바코드를 손쉽게 삽입할 수 있는 탄탄한 기반을 갖추었습니다.

질문이 있거나 추가 지원이 필요하면 Aspose.BarCode 커뮤니티의 [지원 포럼](https://forum.aspose.com/c/barcode/13)에서 언제든지 문의하십시오.

---

**마지막 업데이트:** 2026-05-24  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.BarCode for .NET를 사용한 Aztec 코드 텍스트 인코딩](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [barcode generator .net를 사용한 Aztec 바이트 인코딩](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [.NET에서 오류 정정과 함께 Aztec 바코드 생성 방법](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}