---
title: .NET용 Aspose.BarCode를 사용하여 추가 바코드 데이터 생성
linktitle: 보충 바코드 데이터 구성
second_title: Aspose.BarCode .NET API
description: .NET용 Aspose.BarCode를 사용하여 보충 바코드 데이터를 생성합니다. EAN-2 및 EAN-5 바코드를 손쉽게 사용자 정의하세요. .NET 개발자를 위한 단계별 가이드입니다.
weight: 10
url: /ko/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.BarCode를 사용하여 추가 바코드 데이터 생성


바코드 생성 및 사용자 정의 분야에서 Aspose.BarCode for .NET은 강력하고 다재다능한 도구로 돋보입니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드는 .NET용 Aspose.BarCode를 사용하여 보충 바코드 데이터를 구성하는 과정을 안내합니다. 

## 전제 조건

보충 바코드 데이터의 세계로 뛰어들기 전에 다음 전제 조건이 갖추어져 있는지 확인하십시오.

- Visual Studio 또는 기타 .NET 개발 도구를 사용하여 설정된 개발 환경입니다.
-  .NET용 Aspose.BarCode 사본. 아직 다운로드하지 않았다면 다운로드할 수 있습니다.[여기](https://releases.aspose.com/barcode/net/).
- C# 프로그래밍에 대한 기본 지식.
- 생성된 바코드 이미지를 저장할 수 있는 디렉터리입니다.

## 네임스페이스 가져오기

먼저 .NET용 Aspose.BarCode를 사용하기 위해 C# 코드에 필요한 네임스페이스가 포함되어 있는지 확인하세요. C# 파일 시작 부분에서 필수 네임스페이스를 가져옵니다.

```csharp
using Aspose.BarCode.Generation;
```

이제 보충 바코드 데이터를 구성하는 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: 디렉터리 경로 설정

 C# 코드에서 생성된 바코드 이미지를 저장할 디렉터리의 경로를 정의합니다. 바꾸다`"Your Directory Path"` 실제 디렉토리 경로로.

```csharp
string path = "Your Directory Path";
```

## 2단계: 바코드 생성기 만들기

 인스턴스 만들기`BarcodeGenerator` 바코드 유형과 인코딩하려는 데이터를 지정하여 이 예에서는 "1234567890128" 데이터가 포함된 EAN-13 바코드를 사용하고 있습니다.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## 3단계: 바코드 크기 사용자 정의

X 치수(바코드에서 가장 작은 요소의 너비) 및 보조 공간 등 바코드의 치수를 설정합니다. 이 예에서는 X 치수를 2픽셀로 설정하고 보조 공간을 20픽셀로 설정했습니다.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## 4단계: EAN-2 보충 구성

EAN-2 보충 바코드를 구성하려면 보충 데이터를 원하는 값으로 설정하십시오. 이 경우에는 "12"로 설정했습니다. 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## 5단계: 바코드 이미지 저장

생성된 바코드 이미지를 의미 있는 이름으로 지정된 디렉터리에 저장합니다. 이 예에서는 EAN-2 보충 바코드를 "SupplementEAN2.png"로 저장합니다.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## 6단계: EAN-5 보충 구성

 EAN-5 보충 바코드를 구성하려면 간단히`SupplementData` 원하는 값으로. 여기서는 "12345"로 설정했습니다.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## 7단계: 바코드 이미지 저장(EAN-5)

마지막으로 지정된 디렉터리에 EAN-5 보조 바코드 이미지를 저장합니다. 이 경우 "SupplementEAN5.png"로 저장합니다.

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

이제 .NET용 Aspose.BarCode를 사용하여 추가 바코드 데이터를 성공적으로 구성하고 생성했습니다. 이 접근 방식을 사용하면 다양한 보충 데이터로 광범위한 바코드 유형을 생성할 수 있습니다.

## 결론

Aspose.BarCode for .NET은 바코드 생성 및 사용자 정의를 위한 강력한 도구입니다. 이 가이드에서는 보충 바코드 데이터를 구성하고 생성하는 과정을 단계별로 살펴보았습니다. 올바른 전제 조건과 약간의 코딩만 있으면 바코드 데이터로 효율적으로 작업하고 특정 요구 사항을 충족할 수 있습니다.

 자세한 내용과 고급 사용법은 다음을 참조하세요.[.NET 문서용 Aspose.BarCode](https://reference.aspose.com/barcode/net/).

## 자주 묻는 질문

### 내 .NET Core 프로젝트에서 .NET용 Aspose.BarCode를 사용할 수 있나요?
예, .NET용 Aspose.BarCode는 .NET Core와 호환됩니다.

### .NET용 Aspose.BarCode에 대한 무료 평가판이 있습니까?
 네, 방문하시면 무료로 체험해 보실 수 있습니다.[이 링크](https://releases.aspose.com/).

### .NET용 Aspose.BarCode의 임시 라이선스는 어디서 구할 수 있나요?
 임시면허를 취득하실 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode는 광범위한 바코드 유형을 지원합니까?
예, EAN-13, QR 코드, 코드 128 등을 포함한 다양한 바코드 유형을 지원합니다.

### 생성된 바코드의 모양을 사용자 정의할 수 있습니까?
물론, 요구 사항에 맞게 바코드의 치수, 색상 및 기타 측면을 사용자 정의할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
