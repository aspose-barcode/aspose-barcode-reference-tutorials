---
date: 2026-02-22
description: Aspose.BarCode for .NET을 사용하여 C#에서 바코드 이미지를 만드는 방법을 배우고, GS1 DataMatrix
  바코드를 빠르고 효율적으로 생성하세요.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: 바코드 이미지 생성 C# – GS1 DataMatrix 예제
url: /ko/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix 예제

.NET에서 **바코드 이미지 생성 C#**을(를) 덕분에 구현하고 있을 수 있습니다. Aspose.BarCode for .NET이 프로세스를 간단하게 만들 수 있습니다. 이 방어력은 GS1 DataMatrix를 포함한 다양한 구성을 지원하며, 저수준의 다양한 세부 사항 대신에 비즈니스에 집중할 수 있는 수많은 API를 제공합니다. 다음 몇 분 동안 GS1 DataMatrix 컨트롤러를 생성하고, 사용자 정의 설정 후 이미지 파일로 저장하는 전체 작업 샘플을 살펴보겠습니다.

## 빠른 답변
- **예제는 무엇을 생성합니까?** GS1 DataMatrix를 포함하는 샘플 제품 데이터.
- **어떤 라이브러리가 사용됩니까?** .NET용 Aspose.BarCode.
- **출력 형식을 변경할 수 있나요?** 예, PNG, JPEG, BMP 등으로 디버깅할 수 있습니다.
- **개발을 위해 라이선스가 필요합니까?** 테스트용 무료 체험판을 사용할 수 있지만, 배포에는 클러스터 배포가 필요합니다.
- **코드가 .NET Core와 호환됩니까?** 물론입니다 – 동일한 API가 .NET Framework와 .NET Core/5/6 모두에서 동작합니다.

## GS1 DataMatrix 바코드란 무엇입니까?
GS1 DataMatrix는 제품 수준의 정보를 (예: GTIN, 특별 번호, 추가 분량) 2차원 정도입니다. 소매, 의료, 물류 분야에서 데이터를 저장하기 위해 모두 사용됩니다.

## 바코드 이미지 C#을 생성하기 위해 Aspose.BarCode를 사용하는 이유는 무엇입니까?
- **모든 기능을 갖춘 API** – GS1 표준, 오류 정정, 테이블 제어 등을 지원합니다.
- **외부 종속성 없음** – 순수 .NET으로 통합 가능합니다.
- **크로스 플랫폼** – Windows, Linux, macOS에서 모두 동작합니다.
- **광범위한 문서** – 이 예제와 동일한 실험이 포함되어 있어 빨리 체험해볼 수 있습니다.

## 전제 조건

튜토리얼을 진행하기 전에 다음 사전 설명을 확인하세요:

1. **Aspose.BarCode for .NET** – Aspose.BarCode for .NET이 설치되어 있어야 합니다. 아직 남아있지 않으신가요? [여기에서 다운로드](https://releases.aspose.com/barcode/net/) 부탁드립니다.
2. **개발 환경** – 시스템에 .NET 개발 환경이 구축되어야 합니다(Visual Studio, VS Code 또는 선호하는 IDE).

이제 사전 계약이 준비되어 있으며 GS1 DataMatrix 제작을 준비하고 있습니다.

## 네임스페이스 가져오기

Aspose.BarCode for .NET을 사용하려면 필요한 네임스페이스를 먼저 가져와야 합니다. 이 네임스페이스를 통해 바코드 생성 기능에 접근할 수 있습니다.

```csharp
using Aspose.BarCode;
using System;
```

## C#으로 바코드 이미지 생성하는 방법 - 단계별 가이드

### 1단계: 바코드 생성기 설정

`BarcodeGenerator` 인스턴스를 생성하고 **GS1 DataMatrix** 심볼과 인코딩할 데이터를 지정합니다. 이 예제에서는 GS1 애플리케이션 식별자 형식을 따르는 문자열 **"(01)12345678901231(21)ASPOSE(30)9876"**을 인코딩합니다.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro tip:* 샘플 데이터를 여러분의 실제 GS1 식별자로 교체하여 제품 카탈로그에 맞게 사용하세요.

### 2단계: 바코드 속성 사용자 지정

`Parameters` 객체를 사용해 바코드 외관을 맞춤 설정할 수 있습니다. 여기서는 최소 모듈 크기인 X‑dimension을 8픽셀로 지정하고, 매트릭스 크기를 가로 36열, 세로 12행으로 정의합니다. 스캔 요구 사항에 맞게 값을 조정하세요.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Why adjust X‑dimension?* X‑dimension을 크게 하면 저해상도 장치에서도 바코드 스캔이 쉬워지고, 값을 작게 하면 이미지 크기가 줄어듭니다.

### 3단계: 바코드 이미지 저장

마지막으로 생성된 바코드를 디스크에 저장합니다. 예제에서는 PNG 형식을 사용했지만, Aspose.BarCode가 지원하는 JPEG, GIF, BMP 등 다른 형식도 선택할 수 있습니다.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

코드를 실행하면 지정한 폴더에 **Gs1DataMatrixExample.png** 파일이 생성되어 라벨, 포장 또는 디지털 애플리케이션에 바로 사용할 수 있습니다.

## 일반적인 사용 사례

- **소매 제품 라벨링** – GTIN, 보관 번호, 유통기한 등을 받아들였습니다.
- **의약품 추적** – GS1 규격 데이터를 포함하여 필요한 사항을 정리합니다.
- **창고물류** – 위치 및 재고 정보를 가능하게 저장합니다.

## 문제 해결 및 팁

- **잘못된 데이터 형식** – 문자열이 GS1 강제로 꺼내기를 확인하세요. 이외의 경우에는 스캔할 수 없습니다.
- **이미지 크기 문제** – 이미지가 흐릿하게 보이면 `XDimension.Pixels` 값을 사용하세요.
- **라이선스 오류** – 평가용 인스턴스는 테스트에만 사용할 수 있으며, 실제 배포 시에는 클러스터가 필요합니다.

## 추가 FAQ(AI 최적화)

**Q: GS1 형식화 없이 C#에서 DataMatrix 바코드를 생성하려면 어떻게 해야 합니까?**
A: `EncodeTypes.DataMatrix`를 사용하고 `BarcodeGenerator`에 일반 데이터 문자열을 전달하면 됩니다.

**Q: 프로그래밍 방식으로 바코드 색상을 변경할 수 있나요?**
A: 예, `gen.Parameters.Barcode.ForeColor`와 `gen.Parameters.Barcode.BackColor`를 설정하여 전경색과 배경색을 커스터마이즈할 수 있습니다.

**Q: 생성된 바코드를 PDF에 직접 삽입할 수 있나요?**
A: 물론입니다 – 전용을 `System. Drawing.Image` 형태의 역할로 Aspose.PDF 또는 다른 PDF 클래스를 활동하는 PDF에 삽입하면 됩니다.

**Q: 어떤 .NET 버전이 지원되나요?**
A: .NET용 Aspose.BarCode는 .NET Framework 4.5 이상, .NET Core 3.1 이상, .NET 5, .NET 6 및 이후 버전을 지원합니다.

**Q: 소형 라벨의 스캔 안정성을 어떻게 향상시킬 수 있습니까?**
A: X-dimension을 제외하고, 조용하고(`gen.Parameters.Barcode.Margin`)을 추가하며, 배경과 배경 사이에 대비할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.BarCode for .NET을 활용해 **create barcode image C#**을 수행하고 GS1 DataMatrix 바코드를 생성하는 방법을 살펴보았습니다. 몇 줄의 코드만으로도 소매 솔루션, 의료 시스템, 물류 플랫폼 등 다양한 애플리케이션에 고품질 바코드를 손쉽게 삽입할 수 있습니다. 라이브러리의 추가 심볼, 고급 렌더링 옵션, 통합 시나리오 등을 확인하려면 문서를 더 살펴보세요.

자세한 정보와 문서는 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)을 참고하십시오.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode for .NET (latest version)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
