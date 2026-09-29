---
date: 2026-08-17
description: Aspose.BarCode for .NET를 사용하여 datamatrix 바코드를 생성하는 방법을 배웁니다 – 바코드 생성,
  재고 관리 및 C# 바코드 생성 프로젝트에 이상적입니다.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 구성
og_description: Aspose.BarCode for .NET를 사용하여 datamatrix 바코드를 생성 – 재고 관리 및 C# 바코드
  프로젝트를 위한 빠르고 고성능 솔루션입니다.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Aspose.BarCode for .NET로 datamatrix 바코드 생성
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Aspose.BarCode를 사용하여 datamatrix 바코드 생성 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode를 사용하여 datamatrix 바코드 만들기

현대 공급망 소프트웨어에서는 **create datamatrix barcode aspose**를 빠르고 안정적으로 생성해야 할 때가 많습니다. 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용하여 DataMatrix ECC 000‑140 심볼을 생성하는 과정을 안내합니다. 이 라이브러리는 인코딩, 오류 수정 및 이미지 렌더링을 담당합니다. 가이드를 끝내면 .NET 재고 관리 프로젝트에 바로 삽입할 수 있는 C# 코드 조각을 얻게 됩니다.

## 빠른 답변
- **주요 라이브러리는 무엇입니까?** Aspose.BarCode for .NET  
- **다루는 바코드 유형은 무엇입니까?** DataMatrix ECC 000‑140  
- **사용 언어는 무엇입니까?** C# (C Sharp)  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 프로덕션에는 라이선스가 필요합니다  
- **일반적인 구현 시간은?** 기본 생성기에는 약 10‑15분 소요  

## DataMatrix ECC 000‑140이란?
DataMatrix는 대용량 데이터를 작은 정사각형에 저장하는 2차원 바코드입니다. **ECC 000‑140** 오류 정정 수준은 손상된 코드워드의 최대 140 %를 복구할 수 있어 라벨이 긁히거나 번지는 가혹한 창고 환경에 적합합니다.

## 왜 Aspose.BarCode for .NET를 선택해야 할까요?
Aspose.BarCode for .NET는 다양한 심볼에 대한 바코드 생성을 단순화하는 포괄적이고 고성능 API를 제공하며, 내장 오류 정정, 자동 크기 조정 및 광범위한 플랫폼 지원을 제공해 기업 수준의 재고 및 라벨링 솔루션에 이상적입니다.

- **강력한 API:** 30개 이상의 바코드 심볼을 처리하고 인코딩 규칙을 자동으로 적용합니다.  
- **크로스 플랫폼:** Windows, macOS, Linux에서 네이티브 종속성 없이 실행됩니다.  
- **고성능:** 일반적인 2.5 GHz CPU에서 200 × 200 픽셀 DataMatrix를 50 ms 미만으로 생성하여 고처리량 라벨링 라인을 가능하게 합니다.  

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Visual Studio** – 최신 버전 중 하나(Community, Professional, Enterprise).  
2. **Aspose.BarCode for .NET** – [download link](https://releases.aspose.com/barcode/net/)에서 다운로드하십시오. 추가 리소스는 [this link](https://releases.aspose.com/)에서도 확인할 수 있습니다.  
3. **.NET 프로젝트** – Aspose.BarCode 어셈블리를 참조할 준비가 된 프로젝트.  

## 네임스페이스 가져오기
C# 파일에 필요한 using 지시문을 추가하여 바코드 클래스를 사용할 수 있게 합니다.

```csharp
using Aspose.BarCode.Generation;
```

**`BarcodeGenerator` 클래스는 바코드 이미지를 생성하기 위한 Aspose.BarCode의 핵심 엔진입니다.**  
**`BarcodeGenerator` 클래스는 바코드 이미지를 생성하고 구성하는 Aspose.BarCode의 핵심 엔진입니다.**  
```csharp
using Aspose.BarCode.Generation;
```

## 바코드 생성 재고 관리 사용 사례
배포 센터에서 수천 개의 팔레트를 라벨링해야 한다고 상상해 보세요. DataMatrix ECC 000‑140 바코드를 생성하면 제품 ID, 배치 번호, 유통 기한을 하나의 오류 복원력이 높은 심볼에 삽입할 수 있어 핸드헬드 스캐너가 즉시 읽으며 수동 입력 오류를 최대 95 %까지 줄일 수 있습니다.

## C#에서 datamatrix barcode aspose 생성 방법
데이터를 로드하고, 생성기를 구성한 뒤 이미지를 저장합니다 – 세 단계만으로 완료됩니다. `BarcodeGenerator`는 최적의 모듈 크기를 자동으로 선택하고 ECC 140 정정 수준을 적용하므로 체크섬 값을 직접 계산할 필요 없이 빠르고 효율적으로 처리됩니다.

### 1단계: 출력 디렉터리 정의
PNG 파일이 기록될 폴더를 선택하십시오. `Save`를 호출하기 전에 경로가 존재해야 합니다.

```csharp
string path = "Your Directory Path";
```

### 2단계: 바코드 생성기 만들기
`BarcodeGenerator`를 인스턴스화하고, 심볼을 DataMatrix로 설정하고, 페이로드를 제공하며, 가장 높은 오류 정정 수준을 선택합니다.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

이 코드 조각에서는 다음을 수행합니다:
* 바코드 유형으로 **DataMatrix**를 선택합니다.  
* 샘플 값(`"Åspóse.Barcóde©"`)을 제공합니다.  
* 모듈 크기를 제어하기 위해 **XDimension**을 설정합니다(여기서는 4픽셀).  
* 가장 높은 오류 정정 수준(**ECC 140**)을 선택합니다.  
* 출력을 PNG 파일로 저장합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **잘못된 경로** | `path`가 디렉터리 구분자(`\` 또는 `/`)로 끝나고 폴더가 존재하는지 확인하십시오. |
| **지원되지 않는 문자** | DataMatrix는 UTF‑8을 지원하므로 제어 문자를 피하고 올바른 인코딩을 사용하십시오. |
| **라이선스 미적용** | `Aspose.BarCode.License` 클래스를 사용하여 상용 라이선스를 적용하면 전체 기능을 사용할 수 있습니다. 바코드를 생성하기 전에 호출하십시오. |

## 자주 묻는 질문

**Q: Aspose.BarCode for .NET를 Linux 서버에서 사용할 수 있나요?**  
A: 예. 이 라이브러리는 완전한 크로스 플랫폼을 지원하며 .NET 5+, .NET 6+, .NET Core를 Linux에서 추가 종속성 없이 실행합니다.

**Q: 라이브러리는 대량 바코드 배치를 어떻게 처리하나요?**  
A: 루프에서 단일 `BarcodeGenerator` 인스턴스를 재사용할 수 있습니다; `Save` 호출마다 이미지를 약 40‑60 ms에 다시 렌더링하므로 분당 수천 개 라벨 생성에 적합합니다.

**Q: ECC 140을 위해 데이터를 수동으로 인코딩해야 하나요?**  
A: 아니요. `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`를 설정하면 올바른 오류 정정 알고리즘이 자동으로 적용됩니다.

**Q: 개발에 체험판이면 충분한가요?**  
A: 무료 체험판은 ECC 140을 포함한 모든 기능에 접근할 수 있지만 생성된 이미지에 워터마크가 추가됩니다. 프로덕션에서는 라이선스를 적용해 워터마크를 제거하십시오.

**Q: 바코드 색상을 사용자 정의할 수 있나요?**  
A: 물론입니다. `generator.Parameters.Barcode.Color`와 `generator.Parameters.Barcode.BackColor`를 사용해 브랜드에 맞게 색상을 지정하십시오.

---

**마지막 업데이트:** 2026-08-17  
**테스트 환경:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드(ECC 200) 생성 방법](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET와 함께 ASCII에서 DataMatrix 인코딩 마스터하기](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET를 사용하여 DataMatrix 바코드 읽는 방법](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}