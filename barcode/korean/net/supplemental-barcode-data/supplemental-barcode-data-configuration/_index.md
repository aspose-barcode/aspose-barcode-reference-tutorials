---
date: 2026-03-07
description: C#와 Aspose.BarCode for .NET을 사용하여 보조 데이터가 포함된 EAN‑13 바코드를 만드는 방법을 배우세요
  – 바코드 PNG를 빠르게 생성합니다.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: 보조 데이터가 포함된 EAN‑13 바코드 생성 – Aspose.BarCode
url: /ko/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 보조 데이터가 포함된 EAN-13 바코드 생성 – Aspose.BarCode for .NET

이 실습 튜토리얼에서는 보조 EAN‑2 또는 EAN‑5 데이터를 포함하는 **EAN-13 바코드**를 **생성**하고, 몇 줄의 C# 코드만으로 **바코드 PNG** 파일을 **생성**하는 방법을 보여줍니다. 소매 결제 시스템, 물류 애플리케이션, 간단한 재고 관리 도구를 구축하든, 보조 정보를 추가하면 바코드의 활용도가 크게 향상됩니다.

## 빠른 답변
- **“보조 데이터”란 무엇인가요?** 메인 바코드 옆에 인쇄되는 추가 숫자(EAN‑2/EAN‑5)로, 주로 가격이나 호수에 사용됩니다.  
- **어떤 바코드 유형을 사용하나요?** 기본 심볼은 EAN‑13이며, 선택적으로 EAN‑2 또는 EAN‑5 보조를 사용할 수 있습니다.  
- **PNG 이미지를 출력할 수 있나요?** 예 – `Save` 메서드를 사용하면 직접 PNG로 내보낼 수 있습니다.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판을 사용할 수 있으며, 실제 운영을 위해서는 상용 라이선스가 필요합니다.  
- **.NET Core / .NET 6과 호환되나요?** 물론입니다 – Aspose.BarCode는 모든 최신 .NET 런타임을 지원합니다.

## 사전 요구 사항

Before we dive into the code, make sure you have:

- Visual Studio(또는 .NET 호환 IDE).  
- Aspose.BarCode for .NET 사본 – **[여기](https://releases.aspose.com/barcode/net/)**에서 다운로드하세요.  
- 기본 C# 지식.  
- 생성된 PNG 파일이 저장될 쓰기 가능한 폴더.

## 네임스페이스 가져오기

First, add the Aspose.BarCode namespace so you can access the generator classes:

```csharp
using Aspose.BarCode.Generation;
```

> **팁:** .NET Core를 사용하는 경우, DLL을 수동으로 참조하는 대신 NuGet 패키지 `Aspose.BarCode`를 프로젝트에 추가하세요.

## 보조 바코드란 무엇인가요?

A supplemental barcode is an auxiliary numeric string printed next to the main barcode.  
- **EAN‑2** – 두 자리 보조 숫자로, 주로 잡지 호수에 사용됩니다.  
- **EAN‑5** – 다섯 자리 보조 숫자로, 소매 품목의 가격 연장에 일반적으로 사용됩니다.

Adding these supplements does not change the primary EAN‑13 data; it simply provides extra context that scanners can read.

## 보조 데이터에 Aspose.BarCode를 사용하는 이유

- **One‑line API** – 메인 바코드와 보조 바코드를 하나의 객체에서 구성합니다.  
- **Full control over dimensions** – X‑dimension, 보조 간격, 이미지 포맷을 조정할 수 있습니다.  
- **Cross‑platform** – .NET Framework, .NET Core, .NET 5/6+에서 모두 작동합니다.

## 단계별 가이드

### 단계 1: 출력 디렉터리 설정

Define where the PNG files will be stored. Replace the placeholder with a real path on your machine.

```csharp
string path = "Your Directory Path";
```

### 단계 2: 바코드 제너레이터 초기화 (Barcode Generator C#)

Create a `BarcodeGenerator` instance, specifying **EAN‑13** as the main type and providing the 13‑digit payload.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### 단계 3: 바코드 크기 조정

Fine‑tune the visual size of the barcode and the space reserved for the supplement.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### 단계 4: EAN‑2 보조 추가

Set the supplemental data to a two‑digit value (e.g., “12”). This will appear to the right of the main barcode.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### 단계 5: EAN‑2 바코드를 PNG로 저장

Export the image. The `BarCodeImageFormat.Png` argument ensures a high‑quality PNG file.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### 단계 6: EAN‑5 보조로 전환

Change the `SupplementData` to a five‑digit string for price extensions.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### 단계 7: EAN‑5 바코드를 PNG로 저장

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **왜 이렇게 동작하나요:** 동일한 `BarcodeGenerator` 인스턴스를 재사용하므로 각 `Save` 호출 전에 `SupplementData` 속성만 수정하면 됩니다. 이렇게 하면 코드가 간결해지고 불필요한 객체 생성을 방지할 수 있습니다.

## 일반적인 문제 및 팁

- **잘못된 디렉터리 경로** – 폴더가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요.  
- **보조 길이 오류** – EAN‑2는 정확히 2자리, EAN‑5는 5자리를 요구합니다; 그렇지 않으면 예외가 발생합니다.  
- **이미지가 보이지 않음** – `BarCodeImageFormat.Png`가 사용되었는지 확인하세요; 다른 포맷(예: JPEG)은 압축 아티팩트를 발생시켜 스캐너 판독성을 저하시킬 수 있습니다.

## 자주 묻는 질문

### .NET Core 프로젝트에서 Aspose.BarCode for .NET을 사용할 수 있나요?
예, Aspose.BarCode for .NET은 .NET Core, .NET 5, .NET 6과 완전히 호환됩니다.

### Aspose.BarCode for .NET의 무료 체험판이 있나요?
예, **[이 링크](https://releases.aspose.com/)**를 방문하면 무료로 체험할 수 있습니다.

### Aspose.BarCode for .NET의 임시 라이선스는 어디서 얻을 수 있나요?
**[이 링크](https://purchase.aspose.com/temporary-license/)**에서 임시 라이선스를 받을 수 있습니다.

### Aspose.BarCode가 다양한 바코드 유형을 지원하나요?
물론입니다 – EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 등 다양한 유형을 지원합니다.

### 생성된 바코드의 외관을 맞춤 설정할 수 있나요?
예, 색상, 폰트, 여백을 수정하고, 광범위한 `Parameters` API를 사용해 배경 이미지를 추가할 수도 있습니다.

## 결론

이제 **EAN‑13 바코드**에 보조 EAN‑2 또는 EAN‑5 데이터를 추가하고 Aspose.BarCode for .NET을 사용해 **바코드 PNG** 파일을 **생성**하는 방법을 알게 되었습니다. 이 방법을 통해 바코드 크기, 보조 간격, 출력 포맷을 완벽히 제어할 수 있어 소매, 물류 및 추가 숫자 정보가 필요한 모든 상황에 이상적입니다.

더 자세히 살펴보려면 전체 레퍼런스 가이드를 확인하세요: **[Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)**.

---

**마지막 업데이트:** 2026-03-07  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}