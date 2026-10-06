---
category: general
date: 2026-08-22
description: Aspose.BarCode를 사용하여 C#에서 FCC 11 바코드를 생성합니다. 단계별 코드를 배우고, 치수를 설정하며, Australia Post용
  PNG 이미지를 생성합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: ko
lastmod: 2026-08-22
og_description: Aspose.BarCode를 사용하여 C#에서 FCC 11 바코드를 생성합니다. 이 간결한 튜토리얼을 따라 호주 우편용
  PNG 바코드와 FCC 59 및 FCC 62 변형을 생성하세요.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: C#에서 FCC 11 바코드 생성 – 완전한 Aspose.BarCode 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Aspose.BarCode를 사용하여 C#에서 FCC 11 바코드 생성 방법
url: /ko/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#와 Aspose.BarCode를 사용하여 FCC 11 바코드 생성 방법

.NET 애플리케이션에서 **FCC 11 바코드**를 생성해야 하는 경우, 이 가이드는 필요한 정확한 코드를 보여줍니다. 바코드 크기 설정, 적절한 인코딩 테이블 선택, PNG 파일로 저장하는 방법을 확인할 수 있습니다.

Australia Post 바코드 생성은 물류, 우편 시스템 및 재고 추적에서 흔히 요구되는 작업입니다. 이 튜토리얼은 FCC 11 형식을 다루며, FCC 59와 FCC 62 바코드를 다른 인코딩 테이블로 생성하는 방법도 보여주어 동일한 패턴을 다른 우편 서비스에도 재사용할 수 있습니다.

## 필요 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요.

* .NET 6.0 SDK 이상 설치  
* Visual Studio 2022(또는 C#을 지원하는 IDE)  
* **Aspose.BarCode for .NET** 정식 라이선스 – 커뮤니티 에디션은 평가용으로 사용 가능  
* PNG 파일이 저장될 폴더에 대한 쓰기 권한  

이 전제 조건들은 코드가 추가 설정 없이 컴파일되고 실행될 수 있도록 보장합니다.

## Step 1: Aspose.BarCode NuGet 패키지 설치

프로젝트 폴더에서 터미널을 열고 다음을 실행합니다.

```bash
dotnet add package Aspose.BarCode
```

위 명령은 최신 안정 버전 라이브러리를 프로젝트 파일에 추가합니다. 이 패키지에는 튜토리얼 전반에 걸쳐 사용되는 `BarcodeGenerator` 클래스가 포함되어 있습니다.

## Step 2: 출력 폴더 정의

생성된 이미지가 저장될 폴더를 만듭니다. 경로는 절대 경로나 실행 파일 기준 상대 경로일 수 있습니다.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory`는 폴더가 존재하도록 보장하여 `Save` 메서드가 파일을 쓸 때 발생할 수 있는 런타임 오류를 방지합니다.

## Step 3: FCC 11 바코드 생성

FCC 11 형식은 Australia Post 우편 바코드의 기본 인코딩입니다. 다음 코드는 숫자 문자열 `1101234567`을 인코딩하는 바코드를 생성합니다.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**작동 원리:**  
* `EncodeTypes.AustraliaPost`는 라이브러리에게 Australia Post 인코딩 규칙을 적용하도록 지시합니다.  
* 데이터 문자열 `1101234567`은 FCC 11 사양을 따릅니다: 앞의 두 자리(`11`)가 형식을 식별하고, 뒤에 7자리 고객 참조가 이어집니다.  
* `XDimension`과 `BarHeight`는 인쇄된 바코드의 크기를 제어하며, 스캐너 가독성에 중요합니다.  

프로그램을 실행한 후 `Barcodes` 폴더에서 `PostalAustraliaPostFCC11.png` 파일을 찾을 수 있습니다. 이미지 예시는 다음과 같습니다:

![FCC 11 바코드 생성 예시](https://example.com/fcc11.png "Aspose.BarCode로 생성된 FCC 11 바코드")

## Step 4: 추가 Australia Post 바코드 생성 (선택 사항)

주 목표는 **FCC 11 바코드 생성**이지만, 다른 메일 클래스용으로 FCC 59 또는 FCC 62 바코드가 필요할 때가 많습니다. 아래 코드는 동일한 `BarcodeGenerator` 인스턴스를 재사용하면서 데이터 문자열과 선택적인 인코딩 테이블만 변경합니다.

### 4.1 N‑Table 인코딩을 사용한 FCC 59

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 N‑Table 인코딩을 사용한 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 C‑Table 인코딩을 사용한 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 기타 인코딩을 사용한 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

네 개의 이미지는 모두 동일한 폴더에 나란히 저장되어 시각적 차이를 쉽게 비교할 수 있습니다.

## Step 5: 인코딩 테이블 이해하기

Australia Post는 세 가지 인코딩 테이블을 정의합니다:

* **N‑Table** – 숫자형 고객 정보를 해석합니다. 페이로드가 숫자만 포함될 때 사용합니다.  
* **C‑Table** – 영문자와 숫자를 모두 지원하며, 문자와 숫자가 혼합된 참조 번호에 유용합니다.  
* **Other** – 사용자 정의 또는 확장 데이터 형식에 대한 대체 옵션입니다.

올바른 테이블을 선택하면 바코드 스캐너가 정보를 정확히 디코딩합니다. `AustralianPostEncodingTable` 속성을 생략하면 라이브러리는 기본값인 N‑Table을 사용하며, 이 경우 숫자가 아닌 문자는 잘릴 수 있습니다.

## 팁, 엣지 케이스 및 일반적인 함정

| 상황 | 권장 접근 방식 |
|-----------|----------------------|
| 데이터 문자열 길이가 요구 길이보다 짧음 | FCC 사양에 맞게 앞에 0을 채워 숫자 부분을 패딩합니다. |
| 인쇄 시 바코드가 흐릿함 | `XDimension`을 5 또는 6 픽셀로 늘리고 프린터 DPI 설정을 확인합니다. |
| 스캐너가 “잘못된 형식”을 반환 | 데이터 페이로드와 일치하는 인코딩 테이블(N‑Table, C‑Table, Other)을 사용했는지 확인합니다. |
| GUI 없이 Linux에서 실행 | `System.Drawing.Common` 패키지를 참조하거나, 디스플레이 컨텍스트가 필요 없는 `BarCodeImageFormat.Png` 로 `Save` 메서드를 사용합니다. |
| 다른 이미지 형식이 필요함 | `BarCodeImageFormat.Png`를 `BarCodeImageFormat.Jpeg` 또는 `BarCodeImageFormat.Tiff` 로 교체합니다. |

위 실용적인 팁은 실제 우편 바코드 솔루션 배포 경험을 바탕으로 합니다.

## Complete runnable example

아래는 새 콘솔 프로젝트(`dotnet new console`)에 복사해 바로 실행할 수 있는 독립 실행형 프로그램입니다.



## 다음에 배워야 할 내용

다음 튜토리얼들은 이 가이드에서 다룬 기술을 기반으로 하며, 단계별 설명과 완전한 코드 예제를 포함하고 있어 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용하는 데 도움이 됩니다.

- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}