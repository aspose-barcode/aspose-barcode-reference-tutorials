---
date: 2026-03-07
description: .NET에서 Aspose.BarCode를 사용하여 1차원 데이터바 GS1 인코딩 바코드를 만드는 방법을 배웁니다. 이 가이드는
  GS1을 설정하고, 바코드 생성기를 구성하며, 바코드를 빠르게 생성하는 방법을 보여줍니다.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode로 1차원 데이터바 GS1 인코딩 생성
url: /ko/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode를 사용한 1차원 Databar GS1 인코딩 생성

이 튜토리얼에서는 .NET용 Aspose.BarCode 라이브러리를 사용하여 GS1 표준을 준수하는 **1차원 Databar** 바코드를 **생성**합니다. 엄격한 GS1 검증이 필요하든 보다 유연한 바코드가 필요하든, 라이브러리 설치부터 인코딩 예외 처리까지 모든 단계를 자세히 안내하므로 자체 애플리케이션에서 신뢰할 수 있는 바코드를 생성할 수 있습니다.

## 빠른 답변
- **“1차원 Databar 생성”이란 무엇인가요?** Databar 계열의 선형(1‑D) 바코드를 생성하는 것을 의미하며, 소매 및 물류 분야에서 자주 사용됩니다.  
- **GS1 검증은 어떻게 설정하나요?** `DataBar` 매개변수의 `IsAllowOnlyGS1Encoding`을 `true`로 설정합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **라이브러리는 어디서 다운로드하나요?** 공식 Aspose 릴리스 페이지에서 다운로드할 수 있습니다(전제 조건 참고).

## “1차원 Databar 생성”이란?
1차원 Databar(또는 RSS)는 숫자 데이터, 날짜, AI(응용 식별자) 문자열 등을 인코딩할 수 있는 컴팩트한 선형 바코드입니다. GS1 인코딩과 결합하면 전 세계적으로 인정받는 데이터 구조를 따르게 되어 소매, 의료, 공급망 등 다양한 시나리오에 적합합니다.

## .NET용 Aspose.BarCode를 사용하는 이유
Aspose.BarCode는 유창한 API, 완전한 GS1 지원, 바코드의 시각적 요소를 세밀하게 조정할 수 있는 기능을 제공합니다. 저수준 인코딩의 복잡성을 없애고 비즈니스 로직에 집중할 수 있게 해줍니다.

## 전제 조건

1. **Aspose.BarCode for .NET** – [here](https://releases.aspose.com/barcode/net/)에서 다운로드하여 설치합니다.  
2. **Your Directory Path** – 샘플에서 `"Your Directory Path"`를 쓰기 권한이 있는 폴더 경로로 교체합니다.

## 네임스페이스 가져오기

C# 파일 상단에 필요한 `using` 문을 추가합니다:

```csharp
using Aspose.BarCode;
using System;
```

## Step 1: 바코드 생성기 초기화

`BarcodeGenerator` 인스턴스를 생성하고 Databar Expanded 심볼을 지정합니다:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Step 2: GS1 설정 – 엄격한 GS1 검증으로 바코드 생성

GS1 전용 인코딩을 활성화하고, GS1 규격에 맞는 코드를 지정한 뒤 이미지를 저장합니다:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Step 3: Aspose를 이용한 바코드 생성 – 가변 인코딩(비 GS1 검사)

GS1 규칙을 적용하지 않는 바코드가 필요하면 검사를 끕니다:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Step 4: 바코드 생성기 GS1 검사 – 예외 처리

`IsAllowOnlyGS1Encoding`이 `true`인데 코드 텍스트가 GS1 규격에 맞지 않을 경우 Aspose가 예외를 발생시킵니다. 다음 패턴은 예외를 잡아 로그에 기록하는 방법을 보여줍니다:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### 일반적인 함정 및 팁
- **함정:** GS1 검사가 활성화된 상태에서 비‑GS1 문자열을 제공하면 바코드 생성이 중단됩니다.  
- **전문 팁:** `CodeText`에 할당하기 전에 AI 문자열을 검증하여 런타임 오류를 방지하세요.  
- **팁:** 절대 경로나 `Path.Combine`을 사용해 파일 이름을 안전하게 구성하면 플랫폼 간 호환성이 향상됩니다.

## 결론

이제 Aspose.BarCode for .NET을 사용해 GS1 인코딩이 적용된 **1차원 Databar** 바코드를 생성하고, GS1 검사를 토글하며, 관련 예외를 처리하는 방법을 알게 되었습니다. `Parameters.Barcode` 객체를 통해 바코드 크기, 색상, 여백 등 추가 스타일 옵션을 자유롭게 탐색해 보세요.

문제가 발생하면 공식 문서와 커뮤니티 포럼이 훌륭한 자료가 됩니다:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## 자주 묻는 질문

### 1. 바코드에서 GS1 인코딩이란 무엇인가요?
GS1 인코딩은 바코드 내부에 데이터(예: 제품 식별자)를 구조화하는 표준화된 방식으로, 소매업체, 제조업체, 물류 제공업체 간의 상호 운용성을 보장합니다.

### 2. 생성된 바코드의 외관을 커스터마이즈할 수 있나요?
예. Aspose.BarCode를 사용하면 `Parameters.Barcode` 설정을 통해 크기, 색상, 여백 및 인간이 읽을 수 있는 텍스트 등을 자유롭게 조정할 수 있습니다.

### 3. Aspose.BarCode에 대한 추가 자료와 문서는 어디서 찾을 수 있나요?
포괄적인 문서와 예제는 [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)에서 확인할 수 있습니다. 학습 및 문제 해결에 매우 유용합니다.

### 4. Aspose.BarCode 체험판이 제공되나요?
예. [here](https://releases.aspose.com/)에서 .NET용 Aspose.BarCode 무료 체험판을 다운로드할 수 있습니다.

### 5. Aspose.BarCode for .NET 라이선스는 어떻게 구매하나요?
Aspose 웹사이트의 [purchase page](https://purchase.aspose.com/buy)에서 Aspose.BarCode for .NET 라이선스를 구매할 수 있습니다.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}