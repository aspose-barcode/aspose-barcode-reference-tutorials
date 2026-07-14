---
date: 2026-01-27
description: Aspose.BarCode for .NET를 사용해 DotCode 확장 코드 텍스트를 만드는 방법을 배우세요 – 확장 코드
  텍스트가 포함된 DotCode 바코드를 생성하기 위한 단계별 가이드.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET를 사용하여 도트코드 확장 코드텍스트 생성 방법
url: /ko/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET을 사용하여 dotcode 확장 codetext 생성 방법

## 소개

.NET용 Aspose.BarCode는 다재다능하고 효율적인 솔루션으로 돋보입니다. 제품, 재고 또는 기타 서비스를 구성하는 것이 필요합니다. Aspose.BarCode for .NET이 여러분을 지원합니다. 이 전반적인 인 튜토리얼에서는 **dotcode 확장 코드 텍스트**를 생성하고, 이 기능이 풍부한 현대 환경에서 왜 중요한지 살펴보겠습니다. DotCode는 텍스트와 바이너리 데이터를 모두 이해할 수 있는 2차원 매트릭스로, 다양한 산업 분야에서 유용하게 활용됩니다.

## 빠른 답변
- **“dotcode 축소 코드 텍스트 생성”이란 무엇입니까?** DotCode 범위에 FNC1, ECICodetext, 일반 텍스트 및 아래쪽 구분자를 하나의 확장 페이로드로 포함시키는 작업을 의미합니다.
- **필요한 라이브러리는?** .NET용 Aspose.BarCode.
- **라이선스가 필요한가요?** 평가용 기계 능력으로 테스트할 수 있으며, 실제 운영 환경에서는 능력이 필요합니다.
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.
- **구현 소요 시간은?** 기본 예제 기준 약 10-15분 정도 소요됩니다.

## 도트코드 확장 코드텍스트를 생성하는 방법

아래는 확장 코드텍스트를 구축하고 대상 이미지를 처리하는 것을 방해하는 것으로 보이기 위한 가이드입니다.

## 전제 조건

다음 사전 안내를 따라가기 전에 사전 안내를 준비하시기 바랍니다:

1. Aspose.BarCode for .NET: Aspose.BarCode for .NET을 설치해야 합니다. 아직 설치하지 않으셨다면 [Aspose.BarCode for .NET 문서](https://reference.aspose.com/barcode/net/)에서 다운로드하실 수 있습니다.

2. 개발 환경: Visual Studio와 같은 .NET 개발 환경이 시스템에 설치되어야 합니다.

위 사전 조건이 준비되면 이제 DotCode 축소 Codetext를 생성하여 넘어갈 수 있습니다.

## 네임스페이스 가져오기

먼저 Aspose.BarCode 라이브러리의 필요한 기능에 접근하기 위해 .NET 프로젝트에 네임스페이스를 추가해야 합니다. 방법은 다음과 같습니다:

```csharp
using Aspose.BarCode.Generation;
```

이제 사전 조건을 마쳤으니, DotCode 확장 Codetext 생성 과정을 단계별로 살펴보겠습니다.

## 1단계: 디렉토리 경로 정의

생성된 DotCode 확장 Codetext 이미지를 저장할 디렉터리 경로를 지정합니다.

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"`를 실제 시스템 경로로 교체하세요.

## 2단계: DotCode 확장 코드 텍스트 생성

DotCode 확장 Codetext를 만들려면 다음 하위 단계들을 수행합니다:

### 2.1 FNC1 형식 식별자 추가

FNC1 포맷 식별자는 새로운 데이터 필드의 시작을 나타내는 데 사용됩니다. DotCode 확장 Codetext의 필수 요소입니다.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ECI 코드텍스트 추가

ECICodetext를 사용하면 특수 문자와 국제 텍스트를 인코딩할 수 있습니다. 이 예제에서는 UTF‑8 인코딩을 사용해 `"犬Right狗"`를 인코딩했습니다.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 일반 코드텍스트 추가

일반 텍스트도 DotCode 확장 Codetext에 추가할 수 있습니다. 여기서는 `"Plain text"`를 추가했습니다.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 FNC3 심볼 구분자 추가

FNC3 심볼 구분자는 코드의 서로 다른 섹션을 구분하는 데 사용됩니다.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 FNC3 판독기 초기화 추가

이 단계에서는 FNC3 리더 초기화 정보를 추가합니다.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 코드텍스트 생성

`textBuilder` 객체의 `GetExtendedCodetext` 메서드를 호출해 DotCode 확장 Codetext를 생성합니다.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 3단계: 도트코드 이미지 생성

DotCode 확장 Codetext를 이미지로 생성하려면 다음 하위 단계들을 수행합니다:

#### 4.1 바코드 생성기 초기화

`BarcodeGenerator`를 적절한 매개변수와 함께 초기화합니다. 여기서는 `EncodeTypes.DotCode`와 앞서 생성한 codetext를 사용합니다.

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

이렇게 하면 완료됩니다! Aspose.BarCode for .NET을 사용해 DotCode 확장 Codetext를 성공적으로 생성했습니다.

## 결론

Aspose.BarCode for .NET은 바코드 생성을 간소화하는 강력한 도구입니다. 이 튜토리얼에서는 **dotcode 확장 codetext 생성**에 초점을 맞추었으며, 특히 다국어 및 특수 문자 인코딩이 필요한 다양한 산업 분야에서 필수적인 기능임을 강조했습니다. 위 단계들을 따라 하면 필요에 맞는 DotCode 확장 Codetext를 손쉽게 만들 수 있습니다.

추가 안내가 필요하거나 질문이 있으면 언제든지 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)을 방문하거나 [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)에서 커뮤니티와 소통하세요.

## 자주 묻는 질문

**Q: 생성된 바코드를 모바일 앱에서 사용할 수 있나요?**  
A: 네. 생성된 PNG 이미지는 iOS, Android 또는 크로스‑플랫폼 모바일 애플리케이션에 임베드할 수 있습니다.

**Q: 텍스트 대신 바이너리 데이터를 인코딩하려면 어떻게 해야 하나요?**  
A: `AddECICodetext` 메서드와 적절한 `ECIEncodings`(예: `ECIEncodings.Base64`)를 사용해 바이너리 페이로드를 삽입하면 됩니다.

**Q: 가독성을 유지하면서 바코드 크기를 조정하려면 어떻게 해야 하나요?**  
A: `XDimension.Pixels` 속성을 조정하세요. 값이 클수록 모듈 크기가 커지고, 작을수록 바코드가 더 컴팩트해집니다.

**Q: 바코드 주변에 여백(quiet zone)을 추가할 수 있나요?**  
A: 네. `gen.Parameters.Barcode.Margin` 속성을 설정해 원하는 픽셀 단위의 여백을 정의할 수 있습니다.

**Q: 라이브러리가 .NET 8을 지원하나요?**  
A: 최신 Aspose.BarCode 릴리스는 .NET 8과 호환됩니다. 해당 NuGet 패키지 버전을 참조하면 됩니다.

---

**Last Updated:** 2026-01-27  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}