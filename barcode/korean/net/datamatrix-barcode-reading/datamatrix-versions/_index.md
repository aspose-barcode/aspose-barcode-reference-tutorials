---
title: .NET용 Aspose.BarCode를 사용하여 DataMatrix 바코드 생성
linktitle: DataMatrix 버전
second_title: Aspose.BarCode .NET API
description: .NET용 Aspose.BarCode를 사용하여 .NET에서 DataMatrix 바코드를 생성하는 방법을 알아보세요. 맞춤 측정기준, ECC 지원 등
type: docs
weight: 12
url: /ko/net/datamatrix-barcode-reading/datamatrix-versions/
---
.NET 애플리케이션에서 DataMatrix 바코드를 생성하기 위한 안정적인 솔루션을 찾고 있다면 .NET용 Aspose.BarCode를 선택하세요. 이 단계별 가이드에서는 .NET용 Aspose.BarCode를 사용하여 DataMatrix 바코드를 만드는 과정을 안내합니다. 각 예를 여러 단계로 나누어서 쉽게 따라할 수 있도록 하겠습니다.

## 전제 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- .NET을 지원하는 개발 환경입니다.
-  .NET용 Aspose.BarCode 사본(다음에서 다운로드할 수 있음)[이 링크](https://releases.aspose.com/barcode/net/).
- C# 및 .NET 프레임워크에 대한 기본 지식

이제 DataMatrix 버전과 .NET용 Aspose.BarCode를 사용하여 이를 생성하는 방법을 살펴보겠습니다.

## 네임스페이스 가져오기

모든 C# 프로젝트에서는 필요한 네임스페이스를 가져오는 것이 중요합니다. Aspose.BarCode의 경우 다음을 포함해야 합니다.

```csharp
using Aspose.BarCode.Generation;
```

 이 네임스페이스는 다음에 대한 액세스를 제공합니다.`BarcodeGenerator` 바코드 생성에 중요한 클래스입니다.

이제 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 디렉터리 경로 설정

생성된 DataMatrix 바코드를 저장할 디렉터리 경로를 정의하는 것부터 시작하세요.

```csharp
string path = "Your Directory Path";
```

 바꾸다`"Your Directory Path"` 바코드 이미지를 저장하려는 실제 경로를 사용하세요.

## 2단계: 바코드 생성기 초기화

 인스턴스를 생성합니다.`BarcodeGenerator` 클래스를 선택하고 바코드 유형을 다음과 같이 지정합니다.`DataMatrix`. 바코드 내에서 인코딩하려는 데이터를 제공할 수도 있습니다.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // 바코드 생성 코드는 여기에 있습니다.
}
```

## 3단계: 바코드 속성 구성

치수, ECC(오류 수정 코드) 유형 등 DataMatrix 바코드의 다양한 속성을 사용자 정의할 수 있습니다. 다음은 X 차원을 4픽셀로 설정하고 ECC200을 선택하는 예입니다.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## 4단계: DataMatrix 버전 설정 및 저장

행과 열 수를 설정하여 DataMatrix 버전을 지정할 수 있습니다. 버전을 구성한 후 바코드 이미지를 저장하세요.

예를 들어, ECC200을 사용하여 22행과 22열의 DataMatrix 바코드를 생성하려면:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

마찬가지로 필요에 따라 버전과 ECC 유형을 변경하여 다양한 매개변수를 사용하여 바코드를 생성할 수 있습니다.

## 5단계: 다른 버전에도 반복

다른 DataMatrix 버전에 대해서는 4단계를 반복할 수 있습니다. 예를 들어, ECC200을 사용하여 12행과 64열의 바코드를 생성하려면:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## 6단계: ECC 유형 전환

ECC 유형을 Ecc140으로 변경하려면 ECC 속성을 업데이트하면 됩니다.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## 7단계: 다양한 버전 및 ECC로 바코드 생성

다른 DataMatrix 버전 및 ECC 유형에 대해 4단계를 반복하여 각 바코드를 고유한 파일 이름으로 저장합니다.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

이제 .NET용 Aspose.BarCode를 사용하여 DataMatrix 바코드를 생성하는 방법을 배웠으므로 이 기능을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.

## 결론

.NET용 Aspose.BarCode는 .NET 애플리케이션에서 DataMatrix 바코드를 생성하는 프로세스를 단순화합니다. 이 단계별 가이드를 사용하면 다양한 버전과 ECC 유형으로 바코드를 생성하여 특정 요구 사항에 맞는 유연성과 사용자 정의를 제공할 수 있습니다.

 궁금한 점이 있거나 도움이 필요하신 경우, 주저하지 마시고 방문해주세요.[.NET 문서용 Aspose.BarCode](https://reference.aspose.com/barcode/net/) 또는 다음을 확인해 보세요.[Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13) 지원을 위해.

## FAQ

### Q1: DataMatrix 바코드의 ECC란 무엇입니까?

A1: ECC(오류 수정 코드)는 데이터 무결성을 보장하는 데 도움이 되는 DataMatrix 바코드의 핵심 구성 요소입니다. ECC 수준에 따라 다양한 수준의 오류 수정이 제공됩니다.

### Q2: .NET용 Aspose.BarCode를 사용하여 사용자 정의 치수로 DataMatrix 바코드를 생성할 수 있습니까?

A2: 예, 튜토리얼에 설명된 대로 행과 열 수를 설정하여 DataMatrix 바코드의 크기를 사용자 정의할 수 있습니다.

### Q3: .NET용 Aspose.BarCode를 어디서 다운로드할 수 있나요?

 A3: 다음에서 .NET용 Aspose.BarCode를 다운로드할 수 있습니다.[이 링크](https://releases.aspose.com/barcode/net/).

### Q4: .NET용 Aspose.BarCode에 대한 무료 평가판이 있습니까?

 A4: 예, .NET용 Aspose.BarCode 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: .NET용 Aspose.BarCode의 임시 라이선스를 어떻게 얻을 수 있나요?

 A5: .NET용 Aspose.BarCode에 대한 임시 라이선스를 얻으려면 다음을 방문하세요.[이 링크](https://purchase.aspose.com/temporary-license/).