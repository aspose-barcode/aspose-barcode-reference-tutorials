---
category: general
date: 2026-07-15
description: Aspose.BarCode를 사용하여 C#에서 전방위 바코드를 빠르게 생성하세요 – 조정 가능한 바 높이와 X‑디멘션으로 C#
  바코드 생성 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: ko
lastmod: 2026-07-15
og_description: Aspose.BarCode를 사용하여 C#에서 전방위 바코드를 생성하세요. XDimension과 BarHeight를 조정하여
  완벽한 결과를 얻는 C# 바코드 생성 방법을 마스터하세요.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: C#으로 전방향 바코드 생성 – 완전한 프로그래밍 워크스루
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: C#에서 전방위 바코드 만들기 – 단계별 가이드
url: /ko/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 전방향 바코드 만들기 – 단계별 가이드

GS1 DataBar Omni‑Directional 심볼을 준수하는 바코드를 C#으로 생성하는 방법이 궁금하셨나요? 여러분만 그런 것이 아닙니다. 이번 튜토리얼에서는 **전방향 바코드** 이미지를 처음부터 만들고, X‑Dimension을 조정하며, 바 높이를 변경하는 과정을 Aspose.BarCode 라이브러리를 사용해 단계별로 살펴보겠습니다.

실제 시나리오를 따라가 보겠습니다. 소매 라벨에 사용할 고밀도, 컴팩트한 바코드가 필요하고, 시각적 크기를 완전히 제어하고 싶다고 가정합니다. 최종적으로 바 높이가 30 px인 PNG 파일 하나와 60 px인 PNG 파일 하나, 총 두 개의 파일을 얻어 어떤 인쇄 워크플로에도 바로 사용할 수 있게 됩니다.

## Prerequisites

- .NET 6 (또는 최신 .NET 런타임) 설치  
- Visual Studio 2022 또는 VS Code – 선호하는 IDE면 충분합니다.  
- 무료 Aspose.BarCode for .NET NuGet 패키지 (`Aspose.BarCode`)

다른 의존성은 필요하지 않습니다. NuGet을 처음 사용한다면, 패키지 관리자 콘솔을 열고 다음 명령을 실행하세요.

```powershell
Install-Package Aspose.BarCode
```

## create omni-directional barcode – Understanding the Basics

**GS1 DataBar Omni‑Directional** 심볼은 어느 방향에서든 스캔이 가능하도록 설계되어 선반 가장자리 라벨에 최적입니다. `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`를 호출하면 라이브러리가 데이터를 인코딩하고, 심볼 규칙을 적용하며, 래스터 이미지를 준비하는 모든 작업을 수행합니다.

> **Pro tip:** 원시 데이터를 적절한 Application Identifier (AI) 형식으로 감싸세요. 예: GTIN‑14용 `"(01)12345678901231"`. 이렇게 하면 스캐너가 해당 숫자가 무엇을 의미하는지 알 수 있습니다.

## Step 1 – Set Up the Barcode Generator (how to generate barcode c#)

먼저 생성기 객체를 만듭니다. 이것이 Aspose를 사용한 **how to generate barcode c#**의 핵심입니다.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 열거형 값은 엔진에 사용할 심볼을 알려줍니다. 두 번째 인자는 이미 GTIN AI로 감싼 원시 데이터 문자열입니다.

## Step 2 – Adjust the X‑Dimension (barcode XDimension)

**barcode XDimension**은 가장 작은 바의 너비를 제어합니다. 2 px 값은 대부분의 라벨 프린터에서 가독성과 컴팩트함 사이의 좋은 균형을 제공합니다.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

더 얇거나 굵게 보이게 하려면 숫자를 바꾸면 됩니다. 기억하세요: X‑Dimension은 기본 단위이며, 다른 모든 바 너비는 이 값의 배수입니다.

## Step 3 – Create the First Image with a 30 px Bar Height (barcode BarHeight)

이제 **barcode BarHeight**를 30 px로 설정하고 이미지를 저장합니다. 표준 라벨에 잘 맞는 적당한 크기의 바코드가 생성됩니다.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` 메서드는 PNG 파일을 디스크에 기록합니다. JPEG 출력을 원한다면 `BarCodeImageFormat.Jpeg`으로 교체하면 됩니다.

## Step 4 – Increase Bar Height to 60 px for Larger Labels (barcode BarHeight)

때때로 더 큰 바코드가 필요합니다—예를 들어 스캐너와 거리가 먼 선반 라벨 같은 경우. 높이를 두 배로 늘려보겠습니다.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

생성기를 다시 만들 필요가 **없음**을 확인하세요; 파라미터만 조정하고 같은 객체를 재사용하면 메모리를 절약하고 코드가 깔끔해집니다.

## Step 5 – Save the Second Image (how to generate barcode c#)

마지막으로 두 번째 PNG를 저장합니다. 이제 바 높이만 다른 두 파일을 갖게 됩니다.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Expected output

- `DatabarBarHeight30Pixels.png` – 30 px 높이의 전방향 바코드.  
- `DatabarBarHeight60Pixels.png` – 동일한 데이터이지만 60 px 높이의 바코드.

이미지 뷰어로 파일을 열면 GS1 DataBar Omni‑Directional 사양을 충족하는 선명하고 스캔 가능한 바를 확인할 수 있습니다.

## Common Questions & Edge Cases

### What if I need a different X‑dimension?

`Save` 호출 전에 새로운 값을 할당하면 됩니다. 초고밀도 인쇄를 위해 1 px까지 낮출 수 있지만, 먼저 스캐너에서 테스트하세요—일부 장치는 2 px 이하의 바에 어려움을 겪습니다.

### Can I add human‑readable text below the barcode?

가능합니다. `barcodeGenerator.Parameters.Barcode.CodeText`에 문자열을 지정하고, 필요에 따라 `barcodeGenerator.Parameters.Barcode.CodeLocation`을 `BarCodeTextLocation.Below`로 설정하면 됩니다. 이는 GTIN 숫자를 눈으로 확인해야 하는 소매 환경에 유용합니다.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Is PNG the best format for printing?

PNG는 무손실 포맷으로 바코드 스캐너에 필요한 선명한 가장자리를 유지합니다. 다운스트림 시스템이 다른 포맷(TIFF, BMP 등)을 요구한다면 `BarCodeImageFormat` 열거형을 해당 포맷으로 바꾸면 됩니다.

## Full Working Example (create omni-directional barcode)

아래는 완전한 실행 가능한 프로그램 예제입니다. 새 콘솔 프로젝트에 복사‑붙여넣기하고 **F5**를 눌러 실행하세요.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

프로그램을 실행하고 출력 폴더를 확인하면 앞서 설명한 두 PNG 파일이 정확히 생성된 것을 볼 수 있습니다.

## Recap

우리는 Aspose.BarCode를 사용해 **how to generate barcode C#** 코드를 작성하고, **create omni-directional barcode**를 구현하는 방법을 보여주었습니다. **barcode XDimension**과 **barcode BarHeight**를 조정함으로써 시각적 크기를 세밀하게 제어하면서 스캔 신뢰성을 유지할 수 있습니다.

## What’s Next?

- `Color`나 `Margin` 같은 다른 **GS1 DataBar Omni-Directional** 설정을 실험해 보세요.  
- `Graphics`를 사용해 하나의 캔버스에 여러 바코드를 결합해 복잡한 라벨 디자인을 만들어 보세요.  
- 생성기를 웹 API에 통합해 전자상거래 플랫폼이 필요할 때마다 바코드를 실시간으로 발행하도록 하세요.

새로운 아이디어가 있나요? 댓글로 공유해 주세요. 계속해서 이야기를 나눠요. Happy coding!

## What Should You Learn Next?

다음 튜토리얼은 이번 가이드에서 다룬 기술을 확장하는 관련 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}