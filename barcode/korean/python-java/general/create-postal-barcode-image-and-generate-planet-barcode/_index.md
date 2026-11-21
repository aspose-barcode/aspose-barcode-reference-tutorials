---
category: general
date: 2026-11-20
description: C#에서 우편 바코드 이미지를 빠르게 생성하세요. 사용자 정의 가능한 바 스타일로 플래닛 바코드와 RM4SCC 바코드를 생성하는
  방법을 배워보세요.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: ko
lastmod: 2026-11-20
og_description: Aspose.BarCode를 사용하여 C#에서 우편 바코드 이미지를 생성합니다. 이 튜토리얼에서는 플래닛 바코드를 생성하고,
  바 스타일을 사용자 정의하며, RM4SCC 이미지를 만드는 방법을 보여줍니다.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: C#로 우편 바코드 이미지 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 우편 바코드 이미지 생성 및 행성 바코드 생성
url: /ko/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 우편 바코드 이미지 생성 및 플래닛 바코드 생성

Aspose.BarCode 라이브러리를 사용하여 C#에서 우편 바코드 이미지를 생성합니다. 우편용 플래닛 바코드 또는 RM4SCC 바코드를 생성해야 하는 경우, 이 튜토리얼은 완전하고 바로 실행 가능한 솔루션을 제공합니다.

우편 서비스용 바코드를 생성하려면 정확한 치수와 채워진 바와 비어 있는 바 스타일을 전환할 수 있는 옵션이 필요합니다. 이 가이드는 출력 폴더 설정, 채워진 플래닛 바코드와 비어 있는 플래닛 바코드 생성, 그리고 동일한 시각 설정으로 RM4SCC 바코드를 생성하는 과정을 단계별로 안내합니다. 최종적으로 우편 작업 흐름에 바로 사용할 수 있는 네 개의 PNG 파일을 얻게 됩니다.

## 사전 요구 사항

시작하기 전에 다음이 설치되어 있는지 확인하십시오:

* .NET 6.0 이상  
* Visual Studio 2022 (또는 선호하는 C# IDE)  
* **Aspose.BarCode** NuGet 패키지 (`Install-Package Aspose.BarCode`)  

추가 설정은 필요하지 않습니다. 코드는 기본 폰트와 PNG 인코더만 사용합니다.

## 우편 바코드 이미지 생성 – 개요

이 프로세스의 핵심은 `BarcodeGenerator` 클래스입니다. 이 클래스는 바코드 심볼을 결정하는 `EncodeTypes` 값을 받습니다(예: 플래닛 바코드의 경우 `EncodeTypes.Planet`). 생성기를 구성한 후 `Save`를 호출하여 이미지 파일을 저장합니다.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: 채워진 바와 비어 있는 바를 보여주는 우편 바코드 이미지 예시.*

## 1단계: 출력 폴더 설정

먼저 PNG 파일을 저장할 폴더를 정의합니다. 절대 경로나 상대 경로나 동일하게 작동하므로, 폴더가 존재하는지 확인하거나 코드가 자동으로 생성하도록 합니다.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

프로그램이 새 머신에서 실행될 때 `DirectoryNotFoundException`을 방지하려면 폴더를 프로그래밍 방식으로 생성하는 것이 좋습니다.

## 2단계: 채워진 바가 있는 플래닛 바코드 생성

채워진 바 스타일의 플래닛 바코드는 기본 시각 스타일입니다. 아래 코드는 바코드를 생성하고, X‑dimension을 4 픽셀(우편용으로 일반적인 크기)로 설정한 뒤 이미지를 저장합니다.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**작동 원리:**  
* `EncodeTypes.Planet`은 생성기가 플래닛 심볼을 사용하도록 지정합니다. 이는 많은 우편 서비스에서 요구됩니다.  
* `XDimension.Pixels`는 각 바의 너비를 제어합니다; 4 px는 파일 크기가 과도하지 않으면서도 선명하고 스캔 가능한 이미지를 제공합니다.  
* `Save` 메서드는 `BarCodeImageFormat` 열거형을 기반으로 PNG 인코더를 자동으로 선택합니다.

## 3단계: 비어 있는 바가 있는 플래닛 바코드 생성

일부 우편 사양에서는 어두운 배경에 흰색(비어 있는) 바를 선호합니다. `FilledBars`를 `false`로 설정하면 이를 구현할 수 있습니다.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**팁:** `FilledBars`가 `false`이면 생성기는 바를 배경색(기본값은 흰색)으로, 공간을 전경색(기본값은 검정색)으로 그립니다. 다른 색 구성표가 필요하면 `Parameters.Barcode.ForeColor`와 `BackColor`를 조정하십시오.

## 4단계: 채워진 바가 있는 RM4SCC 바코드 생성

RM4SCC는 영국에서 사용되는 또 다른 우편 심볼입니다. 생성 단계는 플래닛 예제와 동일하며, `EncodeTypes` 값만 변경됩니다.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**예상 결과:** 생성된 PNG는 영국 우편 가이드라인을 준수하는 컴팩트한 RM4SCC 바코드를 표시합니다. X‑dimension이 동일하기 때문에 이미지 크기도 플래닛 바코드와 비슷합니다.

## 5단계: 생성된 이미지 확인

프로그램을 실행한 후 `Barcodes` 폴더에 있는 네 파일을 엽니다. 다음과 같은 파일이 표시되어야 합니다:

* `PostalPlanetFilledBars.png` – 밝은 배경에 어두운 바  
* `PostalPlanetEmptyBars.png` – 어두운 배경에 밝은 바(역전)  
* `PostalRM4SCCFilledBars.png` – 표준 RM4SCC 패턴  

이미지가 왜곡된 경우 다음 항목을 확인하십시오:

* **X‑dimension** – 2 px 미만이면 흐릿해지고, 10 px 초과이면 라벨 크기 제한을 초과할 수 있습니다.  
* **데이터 문자열** – `"123456"` 값은 선택한 심볼의 길이 요구사항을 만족해야 합니다(플래닛은 6자리, RM4SCC도 6자리).  
* **폴더 권한** – 애플리케이션이 출력 디렉터리에 쓸 수 있는 권한이 있는지 확인하십시오.

## 일반적인 변형 및 예외 상황

| 시나리오 | 조정 |
|----------|------------|
| **다른 바코드 데이터** | `"123456"`을 유효한 숫자 문자열로 교체하십시오. 플래닛은 정확히 6자리여야 하며, RM4SCC도 6자리여야 합니다. |
| **사용자 정의 색상** | `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` 및 `BackColor = System.Drawing.Color.LightYellow;`와 같이 설정합니다. |
| **고해상도** | 더 큰 인쇄를 위해 `XDimension.Pixels`를 6 또는 8로 증가시킵니다. |
| **다른 이미지 형식** | `Save` 호출에서 `BarCodeImageFormat.Jpeg` 또는 `BarCodeImageFormat.Bmp`를 사용합니다. |
| **배치 생성** | 문자열 컬렉션을 순회하면서 동일한 생성 로직을 루프 안에서 호출하고, `outputFolder` 경로를 재사용합니다. |

## 전체 실행 가능한 예제

아래 코드를 새 C# 콘솔 프로젝트에 복사하십시오. .NET 6.0에서 컴파일되며 네 개의 바코드 이미지를 자동으로 생성합니다.



## 다음에 배워야 할 내용은?

다음 튜토리얼은 이 가이드에서 다룬 기술을 기반으로 하는 관련 주제를 다룹니다. 각 리소스는 단계별 설명과 완전한 코드 예제를 포함하여 추가 API 기능을 마스터하고 프로젝트에 다양한 구현 방식을 적용할 수 있도록 돕습니다.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}