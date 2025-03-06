---
title: .NET용 Aspose.BarCode를 사용하여 아즈텍 기호 모드 마스터하기
linktitle: 아즈텍 기호 모드 예
second_title: Aspose.BarCode .NET API
description: .NET용 Aspose.BarCode에서 Aztec 기호 모드를 탐색하고 다양한 바코드를 쉽게 생성하는 방법을 알아보세요. 이 종합 튜토리얼에서 Auto, FullRange, Compact 및 Rune 모드를 직접 사용해 보세요.
weight: 14
url: /ko/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.BarCode를 사용하여 아즈텍 기호 모드 마스터하기

강력한 바코드 생성 기능을 .NET 애플리케이션에 통합하려는 경우 Aspose.BarCode for .NET은 환상적인 솔루션입니다. 이 튜토리얼에서는 Aztec 기호 모드를 자세히 살펴보고 .NET용 Aspose.BarCode를 사용하여 다양한 옵션을 살펴보겠습니다. 전제 조건을 다루고, 네임스페이스를 가져오고, 프로세스를 안내하기 위해 각 예제를 여러 단계로 분류합니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET 개발에 대한 실무 지식.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET용 Aspose.BarCode 사본. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/barcode/net/).

이제 모든 설정이 완료되었으므로 Aztec 기호 모드 예제를 살펴보겠습니다.

## 네임스페이스 가져오기

먼저 .NET용 Aspose.BarCode를 사용하려면 필요한 네임스페이스를 가져와야 합니다. Visual Studio 프로젝트를 열고 코드 파일 맨 위에 다음 using 문을 추가합니다.

```csharp
using Aspose.BarCode.Generation;
```

네임스페이스가 준비되면 이제 .NET용 Aspose.BarCode를 사용할 수 있습니다.

## 1단계: 바코드 생성기 설정

Aztec 인코딩 유형으로 바코드 생성기를 초기화하고 코드 텍스트를 제공하여 시작하십시오. 수행 방법은 다음과 같습니다.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

이 단계에서는 생성기를 설정하고 인코딩을 위한 코드 텍스트를 제공했습니다.

## 2단계: 기호 모드를 자동으로 설정

이제 Aztec 기호 모드를 "자동"으로 설정하고 바코드 이미지를 PNG 파일로 저장해 보겠습니다. 방법은 다음과 같습니다.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

이 단계를 통해 Aztec 기호 모드가 자동으로 결정되고 결과 바코드 이미지가 저장됩니다.

## 3단계: 기호 모드를 FullRange로 설정

Aztec 기호 모드를 "FullRange"로 지정하려면 다음 코드를 사용하면 됩니다.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

그러면 FullRange Aztec 기호 모드로 바코드가 생성됩니다.

## 4단계: 기호 모드를 압축으로 설정

Aztec 기호 모드를 "Compact"로 설정하여 바코드를 생성하려면 다음 코드를 사용하십시오.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

이 단계에서는 Compact Aztec 기호 모드로 생성되도록 바코드를 구성합니다.

## 5단계: 기호 모드를 룬으로 설정

마지막으로 "룬" 아즈텍 기호 모드를 사용하려면 다음과 같이 설정하면 됩니다.

```csharp
gen.CodeText = "123"; // 필요한 경우 코드 텍스트를 변경하세요.
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

이 단계에서는 코드 텍스트를 "123"으로 변경하고 Rune Aztec 기호 모드를 사용하여 바코드를 생성합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.BarCode에서 Aztec 기호 모드를 살펴보았습니다. 바코드 생성기 설정, Aztec 기호 모드를 Auto, FullRange, Compact 및 Rune으로 구성하고 생성된 바코드 이미지를 저장하는 방법을 다루었습니다. 이러한 지식을 바탕으로 이제 다양한 바코드 생성을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.

 질문이 있거나 추가 지원이 필요한 경우 주저하지 말고 Aspose.BarCode 커뮤니티에 문의하세요.[지원 포럼](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: 바코드 생성에서 Aztec 기호 모드의 목적은 무엇입니까?

A1: Aztec 기호 모드를 사용하면 Aztec 바코드의 인코딩 방법을 지정하여 바코드 생성에 유연성을 제공할 수 있습니다.

### Q2: .NET용 Aspose.BarCode에서 Aztec 바코드의 코드 텍스트를 변경할 수 있습니까?

A2: 예, Aztec 바코드를 생성할 때 특정 요구 사항에 따라 코드 텍스트를 쉽게 변경할 수 있습니다.

### Q3: .NET용 Aspose.BarCode의 무료 평가판이 있습니까?

A3: 예, .NET용 Aspose.BarCode의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: .NET용 Aspose.BarCode에 대한 전체 설명서는 어디에서 찾을 수 있습니까?

 A4: .NET용 Aspose.BarCode에 대한 전체 설명서를 참조할 수 있습니다.[여기](https://reference.aspose.com/barcode/net/).

### Q5: .NET용 Aspose.BarCode의 임시 라이선스를 어떻게 얻을 수 있나요?

 A5: 다음 사이트를 방문하여 Aspose.BarCode for .NET에 대한 임시 라이선스를 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
