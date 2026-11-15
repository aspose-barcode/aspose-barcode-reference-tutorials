---
category: general
date: 2026-11-14
description: DataBar Omnidirectional 바코드를 생성하고 X‑디멘션을 설정하며 픽셀 단위로 바 높이를 조정하는 방법을 보여주는
  C# 바코드 생성기 튜토리얼.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: ko
lastmod: 2026-11-14
og_description: Barcode generator C# 튜토리얼은 DataBar Omnidirectional 바코드를 생성하고, 픽셀 단위로
  XDimension을 정의하며, PNG 출력 시 바 높이를 변경하는 방법을 단계별로 설명합니다.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 바코드 생성기 C# 튜토리얼 – DataBar 바코드 만들기
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: '바코드 생성기 C# 튜토리얼: DataBar 전방향'
url: /ko/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 바코드 생성기 C# 튜토리얼 – DataBar Omnidirectional 바코드 만들기

바코드 생성기 C# 튜토리얼을 찾고 계시다면, 바로 여기입니다. 이 가이드는 DataBar Omnidirectional 바코드를 만들고, XDimension을 픽셀 단위로 설정하며, 바 높이를 조정해 PNG 이미지를 생성하는 과정을 단계별로 안내합니다.

전체 실행 가능한 예제를 통해 생성기 초기화부터 서로 다른 바 높이로 여러 이미지를 저장하는 전체 흐름을 확인할 수 있습니다. 별도의 외부 문서는 필요 없으며, 코드를 복사해 실행하면 바로 사용할 수 있는 두 개의 바코드 파일이 생성됩니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

* .NET 6.0 이상이 설치되어 있음  
* `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat` 등을 제공하는 바코드 라이브러리에 대한 참조 (예: Aspose.BarCode for .NET)  
* C# 문법 및 Visual Studio 또는 선호하는 IDE에 대한 기본 지식  

> **Pro tip:** Aspose.BarCode를 사용하는 경우, 프로젝트에 NuGet 패키지 `Aspose.BarCode`를 추가하세요.

## Barcode generator C# tutorial – step 1: create the generator

첫 번째 단계는 `DatabarOmniDirectional` 인코드 타입과 인코딩할 데이터를 사용해 `BarcodeGenerator` 인스턴스를 생성하는 것입니다.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*왜 중요한가:* `EncodeTypes.DatabarOmniDirectional`은 라이브러리에게 어느 방향에서든 읽을 수 있는 바코드를 생성하도록 지시합니다. 이는 소매 포장 및 물류에 최적화된 형태입니다.

## Set XDimension pixels for the barcode

X‑dimension은 바코드에서 가장 작은 모듈(“픽셀”)의 너비를 정의합니다. 픽셀 단위로 설정하면 바코드의 시각적 밀도를 정확히 제어할 수 있습니다.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*설명:* `2` 픽셀 값은 대부분의 스캐너에 충분히 선명하면서 이미지 파일 크기를 적당히 유지합니다.

## Adjust bar height and save images

바 높이는 바가 화면에 표시되는 높이를 결정합니다. `BarHeight.Pixels` 속성을 변경하고 `Save`를 다시 호출하면 서로 다른 높이의 이미지를 여러 개 생성할 수 있습니다.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` 열거형 값은 출력이 손실 없는 PNG 파일이 되도록 보장합니다. PNG는 정확한 치수를 유지하기 때문에 바코드 그래픽에 권장되는 포맷입니다.

## Change bar height to create multiple images

같은 바코드를 다양한 크기로 필요로 하는 경우가 많습니다—예를 들어 작은 라벨용과 큰 포스터용을 각각 만들 때처럼. 바 높이를 변경하고 동일한 생성기 인스턴스를 재사용하세요:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*예외 상황:* 바 높이가 너무 낮게 설정되면(예: 10 px 이하) 일부 스캐너가 코드를 읽기 어려울 수 있습니다. 목표 스캐너 하드웨어에서 생성된 이미지를 항상 테스트하세요.

## Full source code

아래는 새 콘솔 프로젝트에 복사‑붙여넣기 할 수 있는 전체 프로그램입니다. 필요한 `using` 지시문을 모두 포함하고 바 높이 변형을 모두 보여줍니다.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

프로그램을 실행하고 `YOUR_DIRECTORY`를 유효한 폴더 경로로 바꾸면 두 개의 PNG 파일을 확인할 수 있습니다:

* `DatabarBarHeight30Pixels.png` – 바 높이 30 px  
* `DatabarBarHeight60Pixels.png` – 바 높이 60 px  

![바코드 생성기 C# 튜토리얼 출력](images/databar-example.png "바코드 생성기 C# 튜토리얼 – 두 개의 DataBar 이미지 표시")

## Common questions

| Question | Answer |
|----------|--------|
| **이미지 포맷을 변경할 수 있나요?** | 예. `BarCodeImageFormat.Png`를 필요에 따라 `Jpeg`, `Bmp`, `Gif` 등으로 교체하면 됩니다. PNG가 무손실 품질 때문에 권장됩니다. |
| **다른 XDimension이 필요하면 어떻게 하나요?** | `generator.Parameters.Barcode.XDimension.Pixels` 값을 원하는 정수로 조정하면 됩니다. 값이 클수록 전체 바코드 폭이 넓어집니다. |
| **DataBar Omnidirectional가 모바일 스캔에 적합한가요?** | 네. 인쇄된 크기가 스캐너 최소 모듈 크기(보통 0.33 mm)를 충족한다면 모바일 스캔도 가능합니다. 픽셀 기반 XDimension을 사용하면 이 요구사항을 쉽게 맞출 수 있습니다. |
| **바코드를 PDF에 삽입하려면?** | PNG를 저장한 뒤 PDF 라이브러리(예: iTextSharp)를 사용해 이미지를 PDF 페이지에 삽입하면 됩니다. |

## Conclusion

이 **바코드 생성기 C# 튜토리얼**에서는 DataBar Omnidirectional 바코드를 만들고, XDimension을 픽셀 단위로 설정하며, 서로 다른 바 높이로 PNG 파일을 생성하는 방법을 살펴보았습니다. 이제 어떤 C# 프로젝트에서도 바코드 생성을 위해 재사용 가능한 코드 스니펫을 보유하게 되었습니다.

### What’s next?

* `Code128`이나 `QR` 같은 다른 `EncodeTypes`를 탐색해 바코드 종류를 확장하세요.  
* 생성된 PNG를 PDF 생성 라이브러리와 결합해 인쇄 가능한 청구서를 만들어 보세요.  
* `generator.Parameters.Barcode.Color`를 사용해 스캐너 사양을 유지하면서 커스텀 색상을 적용해 보세요.

예제를 자유롭게 수정하고, 추가 바 높이를 시도하거나 출력 포맷을 변경해 보세요. 즐거운 코딩 되세요!

## What Should You Learn Next?

다음 튜토리얼들은 이 가이드에서 배운 기술을 기반으로 하여 밀접하게 관련된 주제를 다룹니다. 각 리소스는 완전한 동작 코드 예제와 단계별 설명을 포함해 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용할 수 있도록 도와줍니다.

- [GS1 DataBar Omni‑Directional 바코드의 너비 설정 및 높이 조정 방법](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [바코드 높이 설정 및 DataBar 바코드 C# 생성 방법](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [C#에서 Omnidirectional Databar 바코드 만들기](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}