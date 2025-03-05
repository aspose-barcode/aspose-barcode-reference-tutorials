---
title: 1차원 광폭-협폭 구성
linktitle: 1차원 광폭-협폭 구성
second_title: Aspose.BarCode .NET API
description: .NET용 Aspose.BarCode를 사용하여 맞춤형 바코드를 쉽게 생성하세요. 1차원 광폭-협폭 비율 구성을 위한 단계별 가이드입니다.
type: docs
weight: 22
url: /ko/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

.NET 애플리케이션에서 손쉽게 바코드를 생성하고 사용자 정의하고 싶으십니까? 더 이상 보지 마세요! Aspose.BarCode for .NET은 바코드 생성 및 사용자 정의를 쉽게 만들어주는 강력한 라이브러리입니다. 이 단계별 가이드에서는 Aspose.BarCode for .NET의 기능을 활용하여 넓고 좁은 비율 구성의 바코드를 만드는 방법을 살펴보겠습니다.

## 전제 조건

.NET용 Aspose.BarCode를 사용하여 바코드의 세계에 뛰어들기 전에 다음 전제 조건을 충족해야 합니다.

### 1. 비주얼 스튜디오 환경
   - .NET 애플리케이션을 사용하려면 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
   
### 2. .NET 라이브러리용 Aspose.BarCode
   -  .NET용 Aspose.BarCode 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/barcode/net/).

### 3. 라이센스 키(선택사항)
   -  라이센스 키가 있는 경우 이를 사용하여 라이브러리의 추가 기능을 잠금 해제할 수 있습니다. 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

이제 전제 조건이 준비되었으므로 .NET용 Aspose.BarCode를 사용하여 넓고 좁은 비율 구성으로 1차원 바코드를 만들어 보겠습니다.

## 네임스페이스 가져오기

먼저 .NET용 Aspose.BarCode의 기능에 액세스하려면 프로젝트에 필요한 네임스페이스를 포함해야 합니다. 코드 상단에 다음 using 문을 추가하면 됩니다.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 1단계: 디렉터리 경로 정의

생성된 바코드 이미지를 저장할 경로를 정의하는 것부터 시작하세요. 다음 코드를 사용하여 이 작업을 수행할 수 있습니다.

```csharp
string path = "Your Directory Path";
```

 바꾸다`"Your Directory Path"` 바코드 이미지를 저장하려는 실제 디렉터리 경로를 사용하세요.

## 2단계: 1차원 광폭-협폭 비율 바코드 생성

이제 Aspose.BarCode for .NET을 사용하여 넓고 좁은 비율 구성의 1차원 바코드를 만들어 보겠습니다. 이 예에서는 Code39Extended 인코딩 유형을 사용하고 데이터를 "ASPOSE"로 설정합니다.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

이 코드 줄은 지정된 인코딩 유형 및 데이터를 사용하여 바코드 생성기를 초기화합니다.

## 3단계: 넓음/좁음 비율 설정

넓은-좁은 비율은 바코드의 넓은 요소와 좁은 요소 사이의 비율을 결정합니다. 이 단계에서는 광각 비율을 2로 설정합니다.

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

그런 다음 생성된 바코드 이미지를 지정된 경로에 저장합니다.

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## 4단계: 광각 비율 조정

원하는 바코드 모양을 얻기 위해 다양한 광폭 비율과 좁은 비율을 실험해 볼 수 있습니다. 예를 들어, 더 넓은 바코드를 원할 경우 넓은-좁은 비율을 5로 설정하십시오.

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

그리고 바코드 이미지를 저장합니다.

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

이제 .NET용 Aspose.BarCode를 사용하여 다양한 가로-세로 비율의 1차원 바코드를 성공적으로 만들었습니다. 이 라이브러리는 특정 요구 사항에 맞는 바코드를 생성할 수 있는 유연성을 제공합니다.

## 결론

Aspose.BarCode for .NET은 .NET 애플리케이션에서 바코드 생성 및 사용자 정의를 단순화하는 다목적 라이브러리입니다. 이 튜토리얼에서는 넓고 좁은 비율 구성으로 1차원 바코드를 생성하는 기본 사항을 다루었습니다. 다양한 매개변수를 미세 조정하는 기능을 통해 필요에 완벽하게 맞는 바코드를 생성할 수 있습니다.

## 자주 묻는 질문

### 1. .NET용 Aspose.BarCode 라이선스를 어떻게 얻을 수 있나요?
 다음에서 라이센스를 구입할 수 있습니다.[Aspose 웹사이트](https://purchase.aspose.com/buy).

### 2. 라이선스 없이 .NET용 Aspose.BarCode를 사용할 수 있나요?
예, 제한된 기능을 제공하는 임시 라이센스로 사용할 수 있습니다.

### 3. .NET용 Aspose.BarCode는 .NET Core와 호환됩니까?
예, .NET용 Aspose.BarCode는 .NET Core 및 .NET Framework와 호환됩니다.

### 4. 생성할 수 있는 바코드 유형에 제한이 있나요?
.NET용 Aspose.BarCode는 QR Code, Code 39 등을 포함한 광범위한 바코드 기호를 지원합니다.

### 5. Aspose.BarCode for .NET에 대한 지원을 받거나 질문하려면 어떻게 해야 합니까?
 당신은 방문 할 수 있습니다[Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13) 지원과 토론을 위해.
