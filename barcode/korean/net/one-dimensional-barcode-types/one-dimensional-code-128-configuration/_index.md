---
title: 1차원 코드 128 구성
linktitle: 1차원 코드 128 구성
second_title: Aspose.BarCode .NET API
description: Aspose.BarCode를 사용하여 .NET에서 1차원 Code 128 바코드를 생성하는 방법을 알아보세요. 원활한 바코드 통합을 위한 단계별 가이드를 따르십시오.
weight: 10
url: /ko/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 1차원 코드 128 구성


애플리케이션에서 바코드를 생성하는 강력한 도구를 찾고 있는 .NET 개발자라면 .NET용 Aspose.BarCode가 적합한 솔루션입니다. 이 포괄적인 가이드는 .NET용 Aspose.BarCode의 기능을 활용하여 1차원 Code 128 바코드를 생성하는 과정을 안내하며 초보자와 숙련된 개발자 모두를 위해 설계되었습니다. 

## 전제 조건

Aspose.BarCode를 사용하여 흥미로운 바코드 생성 세계에 뛰어들기 전에 다음 전제 조건이 갖추어져 있는지 확인하십시오.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.

2.  .NET용 Aspose.BarCode: .NET용 Aspose.BarCode를 다운로드하여 설치해야 합니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/barcode/net/).

3. .NET 프로젝트: .NET 프로젝트가 설정되어 있고 바코드 생성을 통합할 준비가 되어 있어야 합니다.

이제 시작해보자!

## 네임스페이스 가져오기

첫 번째 단계는 프로젝트에 필요한 네임스페이스를 가져오는 것입니다. 이러한 네임스페이스는 Aspose.BarCode의 기능에 대한 액세스를 제공합니다.

### 1단계: 네임스페이스 가져오기

```csharp
using Aspose.BarCode.Generation;
```

## 1차원 코드 128 구성

이제 .NET용 Aspose.BarCode를 사용하여 Code 128 바코드를 만들어 보겠습니다. 각 단계를 자세히 살펴보고 프로세스를 명확하게 이해할 수 있도록 하겠습니다.

### 2단계: 경로 설정

먼저, 생성된 바코드 이미지를 저장할 디렉터리의 경로를 설정하세요.

```csharp
string path = "Your Directory Path";
```

### 3단계: Code 128 바코드 생성기 만들기

 만들기`BarcodeGenerator` Code 128 바코드 생성을 위한 인스턴스입니다. 생성하려는 바코드 유형(이 경우 Code128)과 인코딩하려는 값을 지정할 수 있습니다.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### 4단계: 바코드 매개변수 구성

바코드를 생성하기 전에 다양한 매개변수를 구성할 수 있습니다. 예를 들어 체크섬을 표시하거나 숨기도록 선택할 수 있습니다.

#### 옵션 1: 체크섬 표시 안 함

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### 옵션 2: 체크섬 표시

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### 5단계: 바코드 이미지 저장

이제 생성된 바코드 이미지를 지정된 디렉터리에 저장할 차례입니다. 이전 단계에서 선택한 구성에 따라 체크섬을 포함하거나 포함하지 않고 바코드를 저장할 수 있습니다.

#### 체크섬 없이 바코드 저장

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### 체크섬으로 바코드 저장

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

그게 다야! .NET용 Aspose.BarCode를 사용하여 1차원 Code 128 바코드를 성공적으로 생성했습니다. 재고 관리, 제품 라벨링 등과 같은 다양한 애플리케이션에서 이러한 바코드를 사용할 수 있습니다.

## 결론

Aspose.BarCode for .NET은 .NET 애플리케이션에서 바코드 생성을 위한 강력하고 사용자 친화적인 솔루션을 제공합니다. 직관적인 API와 광범위한 문서를 통해 바코드 기능을 프로젝트에 쉽게 통합할 수 있습니다. 1차원 바코드를 생성해야 하는지, 2차원 바코드를 생성해야 하는지 Aspose.BarCode가 도와드립니다.

지금 Aspose.BarCode를 .NET 애플리케이션에 통합하고 바코드 생성 프로세스를 쉽게 간소화하세요.

### 자주 묻는 질문

### .NET용 Aspose.BarCode는 .NET Core와 호환됩니까?
예, .NET용 Aspose.BarCode는 .NET Framework 및 .NET Core 모두와 호환됩니다.

### 생성된 바코드의 모양을 사용자 정의할 수 있습니까?
전적으로! Aspose.BarCode를 사용하면 크기, 색상, 텍스트 배치 등 바코드의 다양한 측면을 사용자 정의할 수 있습니다.

### Aspose.BarCode는 QR 코드 생성에 적합합니까?
Aspose.BarCode는 주로 1차원 바코드에 중점을 두지만 .NET용 Aspose.BarCode를 사용하여 QR 코드도 생성할 수 있습니다.

### 무료 평가판이 제공되나요?
 예, 평가판을 다운로드하여 .NET용 Aspose.BarCode를 무료로 사용해 볼 수 있습니다.[여기](https://releases.aspose.com/).

### .NET용 Aspose.BarCode에 대한 지원은 어디서 받을 수 있나요?
 Aspose.BarCode for .NET 포럼에서 도움을 구하고 경험을 공유할 수 있습니다.[여기](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
