---
category: general
date: 2026-10-08
description: C#에서 바코드 이미지를 만드는 방법을 배우고 DataBar 스택형 전방향 바코드의 종횡비를 조정하는 방법을 알아보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: ko
lastmod: 2026-10-08
og_description: C#에서 바코드 이미지를 생성하고, DataBar 스택형 전방위 바코드의 종횡비를 조정하는 방법을 전체 코드 샘플과 함께
  배워보세요.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: C#에서 바코드 이미지 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C#에서 바코드 이미지를 만들고 종횡비를 조정하는 방법
url: /ko/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 바코드 이미지 생성 및 종횡비 조정 방법

프로그래밍으로 **바코드 이미지 생성**이 필요하다면, 이 가이드는 완전한 실행 가능한 솔루션을 제공합니다. DataBar stacked omni‑directional 바코드의 **종횡비 조정 방법**을 정확히 보여주며, 이는 소매 및 물류 애플리케이션에서 자주 요구됩니다.

이 튜토리얼을 통해 배우게 될 내용:
* DataBar stacked omni‑directional 심볼을 위한 Aspose.BarCode `BarcodeGenerator` 초기화 방법  
* 바 두께를 제어하기 위한 픽셀 단위 X‑dimension(모듈 폭) 설정 방법  
* 두 가지 다른 종횡비를 적용하고 각각을 PNG 파일로 저장하는 방법  
* 출력 결과를 확인하고 종횡비가 중요한 이유 이해하기

외부 도구는 필요 없습니다—Aspose.BarCode for .NET 라이브러리와 .NET 6(이상) 개발 환경만 있으면 됩니다.

## Aspose.BarCode로 바코드 이미지 생성하기

첫 번째 단계는 원하는 심볼과 데이터 문자열을 사용해 제너레이터를 인스턴스화하는 것입니다. `EncodeTypes.DatabarStackedOmniDirectional` 열거형은 Aspose.BarCode에게 GS1‑128 애플리케이션에 널리 사용되는 DataBar stacked omni‑directional 바코드를 생성하도록 지시합니다.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**왜 중요한가:** `BarcodeGenerator` 객체는 모든 바코드 생성 작업의 진입점입니다. 심볼과 원시 데이터를 미리 지정함으로써 생성된 이미지가 GS1 표준을 준수하도록 보장합니다.

## X‑dimension(모듈 폭) 설정

X‑dimension은 가장 얇은 바(모듈)의 너비를 정의합니다. X‑dimension이 클수록 바코드가 두꺼워지며, 저해상도 프린터에서 유용할 수 있습니다.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**왜 중요한가:** X‑dimension 조정은 시각적 튜닝 과정의 일부입니다. 인코딩된 데이터에는 영향을 주지 않지만, 다양한 장치에서 스캔 신뢰도에 영향을 미칩니다.

## 종횡비 조정 – 첫 번째 버전 (15)

종횡비는 DataBar 바코드의 높이‑대‑너비 비율을 제어합니다. `DataBar.AspectRatio` 속성은 정수 값을 받으며, 값이 클수록 바가 더 높아집니다.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**왜 중요한가:** 종횡비 15는 소매 스캐너에서 일반적인 기본값입니다. 결과 PNG(`DatabarAspectRatio15.png`)는 더 높은 모습을 가지며, 핸드헬드 디바이스에서 스캔 성공률을 높일 수 있습니다.

## 종횡비 조정 – 두 번째 버전 (30)

특정 라벨 형식에 따라 더 높은 바코드가 필요할 수 있습니다. `Save`를 다시 호출하기 전에 새로운 정수 값을 할당하기만 하면 종횡비를 쉽게 변경할 수 있습니다.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**왜 중요한가:** **종횡비 조정 방법**을 보여줌으로써 동일한 데이터 소스로부터 여러 바코드 이미지를 생성하면서 제너레이터를 재생성하지 않아도 됩니다. 이는 메모리 사용량을 줄이고 배치 처리 속도를 높입니다.

### 예상 출력

프로그램을 실행하면 실행 디렉터리에 두 개의 PNG 파일이 생성됩니다:

| 파일 이름                     | 종횡비 | 시각적 설명 |
|-------------------------------|--------|-------------|
| `DatabarAspectRatio15.png`    | 15     | 표준 높이, 대부분의 POS 스캐너에 적합 |
| `DatabarAspectRatio30.png`    | 30     | 바가 더 높아 라벨이 크거나 저해상도 프린터에 유용 |

두 이미지 모두 동일한 GTIN `(01)12345678901231`을 인코딩하지만, 시각적 비율은 설정한 종횡비에 따라 다릅니다.

## 흔히 묻는 질문 및 예외 상황 처리

### 다른 X‑dimension이 필요하면?

`barcodeGenerator.Parameters.Barcode.XDimension.Pixels` 값을 0보다 큰 정수로 변경하면 됩니다. 매우 고해상도 출력(예: 300 dpi)에서는 3‑4 픽셀 값이 더 선명한 결과를 제공합니다.

### 적절한 종횡비는 어떻게 선택하나요?

최적의 비율은 스캔 환경에 따라 다릅니다:
* **저프로파일 라벨** – 바코드를 컴팩트하게 유지하려면 작은 비율(예: 10‑15) 사용
* **대형 배송 컨테이너** – 거리에서 가독성을 높이려면 높은 비율(예: 25‑35) 사용
* **규제 요구사항** – 일부 표준은 최소 높이를 규정하므로 GS1 사양을 참고하세요.

### 같은 코드로 다른 바코드 형식을 생성할 수 있나요?

예. `EncodeTypes.DatabarStackedOmniDirectional`을 다른 `EncodeTypes` 값(예: `EncodeTypes.Code128`)으로 교체하면 됩니다. 나머지 코드—X‑dimension, 종횡비(해당되는 경우), 저장—는 동일하게 유지됩니다.

### 이미지를 다른 형식으로 저장하려면?

`BarCodeImageFormat`은 PNG, JPEG, BMP, GIF, TIFF를 지원합니다. `Save`의 두 번째 인자를 변경하면 됩니다. 예:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## 팁: 배치 처리 시 제너레이터 재사용

수십 개의 바코드를 동일한 시각적 설정으로 생성해야 할 경우, 제너레이터를 한 번만 인스턴스화하고 `CodeText` 속성만 업데이트한 뒤 `Save`를 반복 호출하세요. 내부 버퍼를 반복 할당하는 오버헤드를 피할 수 있습니다.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## 결론

이제 Aspose.BarCode를 사용해 C#에서 **바코드 이미지 생성**과 DataBar stacked omni‑directional 심볼의 **종횡비 조정** 방법을 정확히 알게 되었습니다. X‑dimension과 종횡비를 제어함으로써 어떤 스캔 환경이나 레이아웃 요구사항에도 맞는 바코드를 간단하고 유지보수하기 쉬운 방식으로 만들 수 있습니다.

### 다음 단계

* `EncodeTypes` 값을 교체해 **Code128**이나 **QR Code**와 같은 다른 심볼을 탐색하세요.  
* Aspose.PDF와 결합해 바코드를 청구서 등에 직접 삽입하는 PDF 생성 작업을 시도해 보세요.  
* 라벨 크기에 따라 동적으로 종횡비를 선택하도록 구현하면 **종횡비 조정 방법** 패턴을 전체 라벨 디자인 엔진으로 확장할 수 있습니다.

샘플을 자유롭게 수정하고 결과를 공유하거나 댓글로 추가 질문을 남겨 주세요. 즐거운 코딩 되세요!


## 다음에 배워야 할 내용은?


다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하며, 밀접하게 연관된 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용할 수 있도록 돕습니다.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}