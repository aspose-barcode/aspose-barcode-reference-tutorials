---
category: general
date: 2026-08-22
description: Aspose.BarCode를 사용하여 C#에서 바코드를 생성하는 방법. C# 단계별로 바코드 이미지를 만드는 방법을 배우고,
  2‑D 구성 요소를 비활성화하며, PNG 파일로 저장합니다.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: ko
lastmod: 2026-08-22
og_description: Aspose.BarCode를 사용하여 C#에서 바코드를 생성하는 방법. 이 튜토리얼에서는 DataBar Expanded를
  사용해 C#으로 바코드 이미지를 만들고, 2‑D 구성 요소를 전환한 뒤 PNG 파일로 저장하는 방법을 보여줍니다.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: C#에서 바코드 생성 방법 – 바코드 이미지 만들기 완전 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: C#에서 바코드 생성 방법 – DataBar Expanded를 사용한 C# 바코드 이미지 만들기
url: /ko/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#에서 바코드 생성 방법 – DataBar Expanded로 바코드 이미지 c# 만들기

C#에서 바코드를 생성하는 것은 애플리케이션에 기계 판독 가능한 데이터를 삽입해야 할 때 자주 요구되는 작업입니다. 이 가이드에서는 Aspose.BarCode 라이브러리를 사용하여 C#으로 바코드 이미지를 생성하고, 2‑D 복합 구성 요소를 비활성화하며, 결과를 PNG 파일로 저장하는 방법을 보여줍니다.

전체 실행 가능한 프로그램과 모든 구성 옵션에 대한 설명, 출력 맞춤 팁을 확인할 수 있습니다. 별도의 외부 문서는 필요하지 않으며, 아래 코드와 .NET 개발 환경만 있으면 됩니다.

## 사전 요구 사항

* .NET 6.0 SDK 또는 이후 버전이 설치되어 있어야 합니다  
* Visual Studio 2022 (또는 .NET을 지원하는 IDE)  
* Aspose.BarCode for .NET NuGet 패키지 (`Aspose.BarCode`)  

다음 명령으로 패키지를 추가할 수 있습니다:

```bash
dotnet add package Aspose.BarCode
```

이 라이브러리는 본 튜토리얼 전체에서 사용되는 `BarcodeGenerator` 클래스를 제공합니다.

## 단계 1: 프로젝트 설정 및 네임스페이스 가져오기

새 콘솔 애플리케이션을 만들고 필요한 네임스페이스를 가져옵니다:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` 네임스페이스에는 바코드를 구성하고 렌더링하는 데 필요한 모든 클래스가 포함되어 있습니다.

## 단계 2: DataBar Expanded 바코드 생성기 초기화

첫 번째 실행 라인은 **DataBar Expanded** 심볼로지를 위한 `BarcodeGenerator`를 생성하고 원시 데이터 문자열을 제공합니다. 데이터 문자열은 GS1 애플리케이션 식별자 형식 `(01)12345678901231`을 따릅니다.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

생성기를 만들면 내부 비트맵 캔버스가 할당되므로 렌더링 전에 크기와 모양을 조정할 수 있습니다.

## 단계 3: 모듈 폭 (X‑dimension) 정의

X‑dimension은 가장 작은 바코드 요소의 폭을 제어합니다. 픽셀 단위로 설정하면 최종 이미지 크기를 정확히 제어할 수 있습니다.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 픽셀 값은 화면 표시용으로 적합하며, 고해상도 인쇄가 필요하면 값을 늘리세요.

## 단계 4: 2‑D 복합 구성 요소 비활성화

DataBar Expanded는 추가 정보를 담는 2‑D 구성 요소를 옵션으로 포함할 수 있습니다. 이 구성 요소 없이 바코드를 생성하려면 플래그를 `false`로 설정합니다.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

구성 요소를 비활성화하면 시각적 복잡성이 감소하고 PNG 파일 크기도 작아집니다.

## 단계 5: 2‑D 구성 요소 없이 바코드 이미지 저장

출력 디렉터리를 선택하고 이미지를 디스크에 기록합니다. `BarCodeImageFormat.Png` 열거형은 무손실 PNG 파일을 보장합니다.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

이 호출 이후 `Databar2DComponentDisabled.png` 파일에 2‑D 구성 요소가 없는 깨끗한 DataBar Expanded 바코드가 저장됩니다.

## 단계 6: 2‑D 복합 구성 요소 활성화

추가 데이터 레이어가 필요하면 플래그를 다시 `true`로 설정합니다. 동일한 생성기 인스턴스를 재사용하면 두 번째 객체를 만들 필요가 없어 효율적입니다.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## 단계 7: 2‑D 구성 요소가 활성화된 바코드 이미지 저장

2‑D 플래그만 제외하고 동일한 설정으로 두 번째 이미지를 렌더링합니다.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

이제 `Databar2DComponentEnabled.png` 파일에 추가된 2‑D 패턴이 포함된 바코드가 표시됩니다.

## 전체 소스 코드

아래 전체 코드를 `Program.cs`에 복사하고 프로젝트를 실행하세요. 지정한 폴더에 두 개의 PNG 파일이 생성됩니다.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### 예상 출력

프로그램을 실행하면 다음과 같이 출력됩니다:

```
Barcode images generated successfully.
```

그리고 두 개의 파일이 생성됩니다:

* `Databar2DComponentDisabled.png` – 2‑D 구성 요소가 없는 바코드  
* `Databar2DComponentEnabled.png` – 2‑D 구성 요소가 포함된 바코드  

이미지 뷰어에서 PNG 파일을 열어 시각적 차이를 확인하세요.

## 일반적인 변형 및 엣지 케이스

| Situation | Adjustment |
|-----------|------------|
| **다른 심볼** | `EncodeTypes.DatabarExpanded`를 다른 값으로 교체합니다. 예: `EncodeTypes.Code128`. |
| **고해상도** | `XDimension.Pixels` 값을 4 또는 5로 늘리거나 `barcodeGenerator.Parameters.Image`의 `Resolution`을 설정합니다. |
| **다른 이미지 포맷** | `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, `BarCodeImageFormat.Svg` 중 하나를 사용합니다. |
| **웹 앱에서 실행** | 디스크에 저장하는 대신 이미지 바이트를 HTTP 응답 스트림으로 직접 전송합니다. |
| **메모리 관리** | .NET Framework를 대상으로 하는 경우 `using` 블록으로 생성기를 감싸서 비관리 리소스가 해제되도록 합니다. |

## 전문가 팁

* **생성기 재사용** – 2‑D 플래그만 변경하면 객체를 다시 인스턴스화할 필요가 없어 CPU 사이클을 절약합니다.  
* **데이터 검증** – GS1 데이터는 정확한 길이와 체크섬 규칙을 따라야 하며, 잘못된 입력은 `ArgumentException`을 발생시킵니다.  
* **배치 처리** – 데이터 문자열 컬렉션을 순회하면서 필요에 따라 2‑D 플래그를 토글하고, 고유 파일명으로 각 이미지를 저장합니다.  

## 결론

이제 C#에서 바코드를 생성하고 2‑D 복합 구성 요소를 완전히 제어하면서 바코드 이미지를 만들 수 있게 되었습니다. 예제는 생성기 초기화, X‑dimension 설정, 구성 요소 토글, PNG 파일 저장 과정을 보여줍니다. 이를 바탕으로 다른 심볼을 탐색하거나 이미지를 PDF에 삽입하거나 ASP.NET Core 서비스에 바코드 생성을 통합할 수 있습니다.

--- 

*다음 단계*: QR 코드를 생성해 보고, 다양한 이미지 해상도를 실험하거나 Aspose.PDF를 사용해 생성된 PNG를 PDF에 삽입해 보세요. 이러한 확장은 동일한 `BarcodeGenerator` API를 기반으로 하며 워크플로우의 일관성을 유지합니다.

## 다음에 배울 내용은?

다음 튜토리얼은 이 가이드에서 시연한 기술을 기반으로 하는 밀접한 주제를 다룹니다. 각 리소스는 완전한 동작 코드 예제와 단계별 설명을 포함하여 추가 API 기능을 마스터하고 프로젝트에 적용할 수 있는 대체 구현 방법을 탐색하도록 돕습니다.

- [Aspose.BarCode for .NET을 사용하여 DataMatrix 바코드 생성하기 – 단계별 가이드](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET을 사용하여 1차원 Databar 바코드 높이 생성 및 조정하기](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Aspose.BarCode for .NET을 사용하여 사용자 정의 종횡비로 Aztec 바코드 생성하기](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}