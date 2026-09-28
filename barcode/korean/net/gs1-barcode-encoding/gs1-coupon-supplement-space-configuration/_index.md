---
date: 2026-09-28
description: Aspose.BarCode for .NET를 사용하여 GS1 쿠폰에 barcode 맞춤 공간을 만드는 방법을 배우고 barcode
  가독성을 높이세요. 단계별 가이드를 따라보세요.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 Coupon Supplement Space 구성
og_description: Aspose.BarCode for .NET를 사용하여 GS1 쿠폰에 barcode 맞춤 공간을 만드는 방법을 배우고 barcode
  가독성을 높이세요. 단계별 코드와 팁이 포함되어 있습니다.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: GS1 쿠폰 보충을 위한 barcode 맞춤 공간 만들기 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: GS1 쿠폰 보충을 위한 barcode 맞춤 공간 만드는 방법
url: /ko/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 쿠폰 보조 공간 구성

이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 **바코드 맞춤 공간**을 생성합니다. 보조 공간을 조정하는 것은 저해상도 스캐너에서 **바코드 가독성을 향상**시키거나 소매업체가 요구하는 여백을 충족시키는 데 필수적입니다. 이 가이드를 마치면 보조 공간의 중요성을 이해하고, 프로그래밍 방식으로 설정하는 방법과 다양한 픽셀 값으로 이미지를 생성하는 방법을 알게 됩니다.

## 빠른 답변
- **보조 공간은 무엇을 제어합니까?** 쿠폰 데이터와 바코드 나머지 부분 사이의 빈 영역(픽셀 단위)을 정의합니다.  
- **사용되는 바코드 유형은 무엇입니까?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **공간 크기를 변경할 수 있나요?** 예 – `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels`를 원하는 정수 값으로 설정하십시오.  
- **이 기능에 라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 동작하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 출력 형식은 무엇입니까?** PNG, JPEG, BMP, GIF, TIFF 등이며 `BarCodeImageFormat`을 통해 더 많은 형식을 지원합니다.

## GS1 쿠폰 보조 공간이란?
GS1 쿠폰 보조 공간은 GS1‑Databar 쿠폰 바코드에 나타나는 정의된 빈 영역입니다. 소매 시스템은 이 공간을 사용하여 스캔 신뢰성을 향상하고, 보조 데이터 주변에 최소 여백을 요구하는 산업 사양을 준수합니다.

## 왜 보조 공간을 구성해야 합니까?
보조 공간은 직접적으로 **바코드 가독성을 향상**시키며 엄격한 소매업체 가이드라인을 충족하도록 도와줍니다. 추가 픽셀을 넣음으로써 저해상도 스캐너에서 오류 읽기의 가능성을 줄이고, 다양한 라벨 크기에서 일관된 스캔을 보장하며, 인쇄 레이아웃 내에서 바코드의 균형을 맞출 시각적 유연성을 제공합니다.

## 사전 요구 사항

Aspose.BarCode for .NET를 사용하여 GS1 쿠폰 보조 공간을 구성하기 전에 다음 항목을 준비하십시오:

1. **Visual Studio** – .NET 개발을 위한 주요 IDE입니다.  
2. **Aspose.BarCode for .NET** – 라이브러리를 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)에서 다운로드하십시오.  
3. **.NET Framework 또는 .NET 5+** – C# 및 .NET 런타임에 대한 이해가 필요합니다.

환경이 준비되었으니 구현 단계로 넘어갑시다.

## 네임스페이스 가져오기

`Aspose.BarCode.Generation` 네임스페이스에는 `BarcodeGenerator` 클래스와 관련 설정이 포함되어 있습니다.

```csharp
using Aspose.BarCode;
```

## 단계 1: 경로 정의

생성된 이미지가 저장될 폴더를 선택하십시오. 경로는 운영 체제에 맞는 디렉터리 구분자로 끝나야 합니다.

```csharp
string path = "Your Directory Path";
```

## 단계 2: GS1 쿠폰 보조 공간 구성 생성

다음 코드 조각은 바코드를 생성하고, X‑dimension을 설정하며, 보조 공간을 조정합니다.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

이 예제에서는 다음을 수행합니다:

1. **Create** `UpcaGs1DatabarCoupon` 유형에 대한 `BarcodeGenerator` 인스턴스를 생성합니다.  
2. **Set** X‑dimension을 2 픽셀로 설정합니다. 이는 가장 좁은 바의 너비를 결정합니다.  
3. **Adjust** `SupplementSpace.Pixels` 속성을 30 px로 설정하고 이미지를 생성한 뒤, 50 px로 다시 반복합니다.  

인쇄 워크플로에 맞게 다른 픽셀 값을 자유롭게 실험해 보세요.

## 일반적인 문제 및 팁

- **잘못된 경로** – `path` 변수가 OS에 맞는 뒤쪽 백슬래시(`\`) 또는 슬래시(`/`)로 끝나는지 확인하십시오.  
- **권한 부족** – Visual Studio를 관리자 권한으로 실행하거나 애플리케이션에 쓰기 권한이 있는 폴더를 선택하십시오.  
- **잘못된 데이터 형식** – 데이터 문자열은 GS1 구문을 따라야 합니다(`(8110)`은 보조 식별자를 나타냅니다).

## 이것이 비즈니스에 중요한 이유

Aspose.BarCode는 **60개 이상의 바코드 심볼**을 지원하며 메모리를 소모하지 않고 **10,000 × 10,000 픽셀**까지의 이미지를 렌더링할 수 있습니다. 대규모 소매 배포의 경우, 일반 서버 하드웨어에서 이미지당 1초 미만의 처리 시간으로 배치 모드에서 고해상도 GS1 쿠폰을 생성할 수 있음을 의미합니다.

## 자주 묻는 질문

**Q: 바코드에서 GS1 쿠폰 보조 공간의 목적은 무엇입니까?**  
A: 보조 데이터 주변에 필수적인 빈 여백을 추가하여 스캐너 신뢰성을 향상하고 소매업체가 지정한 최소 너비를 충족합니다.

**Q: Aspose.BarCode for .NET를 사용하여 GS1 쿠폰 보조 공간의 너비를 사용자 정의할 수 있습니까?**  
A: 예, `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels`를 원하는 정수 값으로 설정하면 라이브러리가 즉시 생성된 이미지에 적용합니다.

**Q: Aspose.BarCode for .NET에 대한 추가 문서 및 지원은 어디에서 찾을 수 있습니까?**  
A: 다음 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)을 참고하고, 커뮤니티 지원을 위해 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)을 방문하십시오.

**Q: Aspose.BarCode for .NET는 초보자와 숙련된 개발자 모두에게 적합합니까?**  
A: 물론입니다. API는 빠른 작업을 위한 간단한 메서드와 정교한 바코드 생성을 위한 고급 옵션을 제공합니다.

**Q: Aspose.BarCode for .NET의 기능을 평가하기 위해 임시 라이선스를 얻을 수 있습니까?**  
A: 예, [Aspose temporary license website](https://purchase.aspose.com/temporary-license/)에서 체험 라이선스를 요청하십시오.

## 결론

위 단계들을 따라 하면 이제 GS1 쿠폰 보조 공간을 위한 **바코드 맞춤 공간 생성** 방법을 알게 되었으며, 이는 **바코드 가독성 향상**과 소매 표준 충족을 위한 핵심 기술입니다. 코드를 기존 스캔 솔루션에 통합하고, 다양한 픽셀 값을 실험하며, Aspose.BarCode for .NET가 제공하는 다른 바코드 유형도 탐색하십시오.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## 관련 튜토리얼

- [Aspose.BarCode Databar 바코드 생성 (.NET API) – 행 및 열 구성](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드 생성 방법 – 단계별 가이드](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}