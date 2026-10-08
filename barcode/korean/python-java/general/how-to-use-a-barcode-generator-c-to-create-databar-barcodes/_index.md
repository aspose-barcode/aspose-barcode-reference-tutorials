---
category: general
date: 2026-09-07
description: 바코드 생성기 C# 튜토리얼로, 바코드 PNG 파일을 생성하고 사용자 정의 가능한 행과 열을 가진 DataBar 바코드를 만드는
  방법을 보여줍니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: ko
lastmod: 2026-09-07
og_description: '바코드 생성기 C# 튜토리얼: 바코드 PNG 파일을 생성하고 맞춤 행과 열로 DataBar 바코드를 몇 분 안에 만드는
  방법을 배워보세요'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: 바코드 생성기 C# – DataBar 바코드 및 PNG 이미지 생성
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: C# 바코드 생성기를 사용해 DataBar 바코드 생성하는 방법
url: /ko/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 바코드 생성기를 사용하여 DataBar 바코드 만들기

고품질 바코드를 생성하기 위한 **barcode generator C#**가 필요하다면, 이 가이드는 **generate barcode PNG** 파일을 만들고 **create DataBar barcodes**를 사용자 지정 행과 열로 생성하는 방법을 보여줍니다. 소매 재고 시스템이든 티켓팅 플랫폼이든, 아래 단계들을 따라 하면 단일, 독립적인 예제로 DataBar Expanded Stacked 바코드를 만들 수 있습니다.

이 튜토리얼에서 배울 내용:

* DataBar Expanded Stacked 심볼로지를 위한 `BarcodeGenerator` 인스턴스 생성 방법.  
* ISO / GS1 사양에 맞게 열 및 행 설정을 조정하는 방법.  
* PNG 이미지로 저장하여 웹 페이지에 삽입하거나 라벨에 인쇄하는 방법.  

외부 서비스는 필요하지 않습니다—Aspose.BarCode for .NET 라이브러리(또는 동일한 API를 따르는 호환 라이브러리)만 있으면 됩니다. 코드는 .NET 6+에서 실행되며 Visual Studio, Rider 또는 C#을 지원하는 모든 IDE에서 작동합니다.

## Prerequisites

시작하기 전에 다음이 준비되어 있어야 합니다:

* .NET 6 SDK 이상이 설치되어 있음.  
* `Aspose.BarCode` NuGet 패키지(또는 `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`을 제공하는 동등한 라이브러리)에 대한 참조.  
* C# 구문 및 프로젝트 구조에 대한 기본적인 이해.  

패키지는 명령줄에서 다음과 같이 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Initialize the barcode generator C# for DataBar Expanded Stacked

첫 번째 단계는 **DataBar Expanded Stacked** 심볼로지를 대상으로 하는 `BarcodeGenerator` 인스턴스를 만드는 것입니다. 이 객체는 인코딩할 텍스트를 포함한 모든 렌더링 매개변수를 보유합니다.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Why this matters:** `EncodeTypes.DatabarExpandedStacked` 열거값은 라이브러리에 적용할 바코드 표준을 알려줍니다. 올바른 열거값을 사용하면 생성된 이미지가 GS1 DataBar 사양을 준수합니다.

## Step 2: Configure the number of columns (default rows are used)

DataBar Expanded Stacked은 여러 열로 나눌 수 있습니다. 열 수를 조정하면 시각적 밀도가 변하고, 제한된 공간에 더 긴 데이터 문자열을 맞출 수 있습니다.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Pro tip:** 기본 열 수는 1입니다. 4로 설정하면 네 개의 스택된 열이 생성되어, 바코드 높이를 관리 가능한 수준으로 유지하면서 더 긴 숫자 문자열에 이상적입니다.

## Step 3: Generate barcode PNG with the column setting applied

이제 바코드를 PNG 이미지로 저장합니다. PNG는 스캐너에 필요한 선명한 가장자리를 유지하며 웹 및 인쇄 매체 모두에 잘 어울립니다.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

파일 `DatabarCols4.png`는 **barcode PNG**를 포함하고 있어 HTML에 바로 삽입할 수 있습니다:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Step 4: Create a separate generator instance for row configuration

열 대신 행 수를 제어해야 하는 경우, 새로운 `BarcodeGenerator`를 인스턴스화합니다. 차원을 변경한 뒤 동일 인스턴스를 재사용하면 예상치 못한 레이아웃 오류가 발생할 수 있으므로, 새 객체를 사용하는 것이 가장 안전합니다.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: Set the number of rows (default columns are used)

행은 바코드 모듈의 수직 스택에 영향을 줍니다. 행을 늘리면 바코드가 더 높아져 특정 라벨 크기에 필요할 수 있습니다.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Why rows vs. columns:** 열은 바코드를 가로로 나누고, 행은 세로로 확장합니다. 라벨 레이아웃에 가장 잘 맞는 방향을 선택하세요.

## Step 6: Generate barcode PNG with the row setting applied

마지막으로 행 조정된 바코드를 PNG 파일로 저장합니다.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

이제 두 개의 구별된 PNG 파일이 생성되었습니다:

* `DatabarCols4.png` – 4열, 1행.  
* `DatabarRows3.png` – 1열, 3행.

두 이미지 모두 애플리케이션, 보고서 또는 인쇄 라벨에 즉시 사용할 수 있습니다.

## How to generate barcode PNG files in C# with custom dimensions

위 패턴은 라이브러리가 지원하는 모든 DataBar 변형이나 다른 심볼로지에도 재사용할 수 있습니다. 다음은 유틸리티 클래스에 복사‑붙여넣기 할 수 있는 간결한 템플릿입니다:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

메서드는 다음과 같이 호출합니다:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Edge cases to consider**

* **Data length** – DataBar Expanded Stacked은 최대 74개의 숫자 문자를 인코딩할 수 있습니다. 이 한도를 초과하면 예외가 발생합니다. 생성기를 호출하기 전에 입력 길이를 검증하세요.  
* **Invalid dimensions** – 이 심볼로지에 대해 라이브러리는 열을 1‑4, 행을 1‑3으로 제한합니다. 범위를 벗어난 값을 제공하면 무시되거나 오류가 발생합니다.  
* **Image DPI** – 인쇄용 고해상도가 필요하면 저장하기 전에 `generator.Parameters.ImageResolution`을 설정하십시오.

## Expected output

`DatabarCols4.png` 또는 `DatabarRows3.png`를 열면 선명하고 고대비인 DataBar 바코드가 표시됩니다. GS1‑호환 스캐너로 이미지를 스캔하면 원본 텍스트 `"Databar Expanded Stacked long"`이 반환됩니다.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Alt text: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#*

## Conclusion

이 튜토리얼은 **barcode generator C#**를 사용하여 **create DataBar barcodes**와 **generate barcode PNG** 파일을 사용자 지정 행 및 열 설정으로 만드는 방법을 보여주었습니다. 여섯 단계—생성기 초기화, 열 또는 행 구성, PNG 저장—를 따르면 재고 시스템, 티켓팅 또는 신뢰할 수 있는 바코드 렌더링이 필요한 모든 시나리오에 적합한 생산 준비 이미지가 얻어집니다.

다음 단계로 탐색해 볼 내용:

* PNG에 색상이나 배경 이미지를 추가하기(대부분의 스캐너와 여전히 호환).  
* 동일한 `BarcodeGenerator` API를 사용해 QR, Code 128, PDF417 등 다른 심볼로지 활용하기.  
* 생성된 PNG를 ASP.NET Core MVC 뷰나 Blazor 컴포넌트에 직접 삽입하기.

다양한 데이터 문자열, 차원 및 이미지 포맷(JPEG, BMP 등)을 실험해 보세요. 동일한 패턴이 적용되므로 **barcode generator C#**는 모든 .NET 개발자 도구함에서 다재다능한 도구가 됩니다. 즐거운 코딩 되세요!

## What Should You Learn Next?

다음 튜토리얼들은 이 가이드에서 시연한 기술을 기반으로 하여 밀접하게 관련된 주제를 다룹니다. 각 리소스는 완전한 코드 예제와 단계별 설명을 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}