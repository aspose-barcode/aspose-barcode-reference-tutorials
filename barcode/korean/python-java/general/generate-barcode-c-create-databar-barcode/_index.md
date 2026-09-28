---
category: general
date: 2026-07-21
description: Aspose.BarCode를 사용하여 C#에서 바코드를 빠르게 생성하세요. DataBar 바코드 만들기, 바코드 크기 맞춤
  설정, 바코드 이미지를 몇 단계만에 내보내는 방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: ko
lastmod: 2026-07-21
og_description: Aspose.BarCode를 사용하여 C#에서 바코드를 생성합니다. DataBar 바코드를 만들고 크기를 맞춤 설정한
  뒤 이미지를 즉시 내보냅니다.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: 바코드 생성 C# – 맞춤 크기로 DataBar 바코드 만들기
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: 바코드 생성 C# – DataBar 바코드 만들기
url: /ko/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode C# – Create DataBar barcode

끝없는 문서를 뒤져볼 필요 없이 **generate barcode C#**를 원하시나요? 바로 여기입니다. 이 가이드에서는 **DataBar barcode**를 만드는 방법, 크기를 조정하는 방법, 그리고 **barcode 이미지 내보내기**까지—C# 몇 줄만으로 진행합니다.

작은 선반 태그에 들어갈 콤팩트한 제품 라벨이 필요하다고 상상해 보세요. DataBar Expanded Stacked 심볼이 딱 맞고, Aspose.BarCode를 사용하면 몇 개의 열이나 행을 사용할지 정확히 제어할 수 있습니다. 준비되셨나요? 시작해 보겠습니다.

## What you'll accomplish

- **Create a DataBar barcode** (the “expanded stacked” variant) from scratch.  
- **Customize barcode size** by setting columns or rows directly.  
- **Change barcode dimensions** on the fly without rebuilding the generator.  
- **Export barcode image** to PNG (or any format Aspose supports).  

외부 서비스 없이, 복잡한 설정 없이—깨끗하고 실행 가능한 C# 코드만 있습니다.

## Prerequisites

- .NET 6.0 이상 (코드는 .NET Framework 4.7+에서도 동작합니다).  
- 유효한 Aspose.BarCode for .NET 라이선스 (또는 체험 모드로 실행 가능).  
- 원하는 IDE—Visual Studio, Rider, 혹은 VS Code 중 하나.  

아직 NuGet 패키지를 설치하지 않으셨다면, 다음을 실행하세요:

```bash
dotnet add package Aspose.BarCode
```

그게 전부—다른 의존성은 없습니다.

## Step 1: Set up the barcode generator (How to **generate barcode C#**)

먼저 **DataBar Expanded Stacked** 심볼을 가리키는 `BarcodeGenerator` 인스턴스를 만들어야 합니다. 이 객체가 나중에 이미지를 생성하는 엔진입니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*왜 중요한가*: `EncodeTypes.DatabarExpandedStacked` 열거형은 Aspose에 스택형 버전을 원한다는 것을 알려줍니다. 이는 좁은 공간에 이상적입니다. 전달하는 텍스트는 인코딩될 값이며, 애플리케이션에 필요한 어떤 숫자 문자열로든 교체할 수 있습니다.

## Step 2: **Customize barcode size** – set columns

DataBar 바코드는 **columns** 혹은 **rows** 중 하나를 지정해 시각적 밀도를 조절할 수 있습니다. 여기서는 열부터 시작합니다. 행 수는 바코드가 유효하도록 자동 계산됩니다.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*팁*: 열 수가 많을수록 바코드의 폭이 넓어집니다. 더 많은 열 → 더 넓은 바코드, 저해상도 프린터에서도 스캔 신뢰성을 높일 수 있습니다.

## Step 3: **Export barcode image** with the column setting

이제 이미지를 디스크에 저장합니다. PNG, JPEG, BMP, 혹은 SVG 중 선택할 수 있습니다. 여기서는 선명하고 손실 없는 PNG를 사용합니다.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Expected result** – `DatabarCols4.png`를 열면 네 개의 열을 가진 깔끔하게 쌓인 DataBar를 확인할 수 있습니다. 작은 라벨에 딱 맞는 촘촘한 수직 막대 모양입니다.

## Step 4: **Change barcode dimensions** – set rows instead

때로는 넓이보다 높이가 더 필요할 때가 있습니다. 행 제어로 전환하면 Aspose가 열을 자동으로 재계산합니다.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*왜 전환하나요?* 행은 바코드의 높이에 영향을 줍니다. 행 수가 많을수록 심볼이 더 높아져, 폭은 제한되고 높이가 충분한 경우에 유용합니다.

## Step 5: **Export barcode image** with the row setting

두 번째 변형을 저장합니다. 파일 이름이 변화를 반영하므로, 비교를 위해 두 이미지를 모두 보관할 수도 있습니다.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Result** – `DatabarRows3.png`는 같은 데이터를 더 높은 버전으로 표시하지만, 여전히 완벽하게 스캔 가능합니다.

## Full working example

전체를 한 번에 보면, 바로 복사·붙여넣기해서 실행할 수 있는 콘솔 앱이 됩니다:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

프로그램을 실행하고 두 PNG 파일을 열어 보세요. 이제 **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, **export barcode image**를 1분도 채 안 되는 시간에 모두 수행했습니다.

## Common questions & edge cases

- **다른 이미지 포맷이 필요하면?**  
  `BarCodeImageFormat.Png`를 `Jpeg`, `Bmp`, `Gif`, `Svg` 등으로 교체하면 됩니다. API가 자동으로 변환합니다.

- **행과 열을 동시에 바꿀 수 있나요?**  
  기술적으로 두 값을 모두 설정할 수 있지만, Aspose는 마지막에 설정한 속성을 우선합니다. 유효한 DataBar를 만들려면 하나의 차원만 지정하고 다른 차원은 라이브러리가 계산하도록 하는 것이 안전합니다.

- **전경/배경 색을 적용하려면?**  
  `barcodeGen.Parameters.Barcode.ForegroundColor`와 `BackgroundColor`를 사용합니다. 예시:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **인코딩할 데이터에 크기 제한이 있나요?**  
  DataBar Expanded Stacked은 최대 74개의 숫자 문자(또는 30개의 영숫자)까지 지원합니다. 이를 초과하면 예외가 발생합니다.

## Next steps

이제 **create databar barcode** 기본을 마스터했으니, 다음을 고려해 보세요:

- 바코드 아래에 **텍스트 주석** 추가 (`barcodeGen.Parameters.CaptionAbove.Text`).  
- Aspose.PDF를 사용해 PNG를 PDF에 직접 삽입.  
- CSV에 있는 제품 ID 목록을 순회하면서 바코드를 대량 생성.

이 모든 주제는 동일한 `BarcodeGenerator` 객체를 기반으로 하므로, 처음부터 다시 시작할 필요가 없습니다.

---

**Bottom line**: 이제 **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, **export barcode image**를 Aspose.BarCode와 함께 사용할 수 있습니다. 열/행 값을 실험해 보고, 이미지 포맷을 바꾸고, 코드를 재고·POS 시스템에 통합해 보세요. 즐거운 코딩 되세요!


## What Should You Learn Next?


다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하여 밀접하게 관련된 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하고 있어, 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}