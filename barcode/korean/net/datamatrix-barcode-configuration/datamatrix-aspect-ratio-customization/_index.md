---
date: 2026-01-12
description: Aspose.BarCode for .NET을 사용하여 사용자 지정 DataMatrix 종횡비로 바코드 PNG를 만드는 방법을
  배웁니다. 바코드 생성 및 크기 맞춤을 위한 단계별 가이드.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 바코드 PNG 만들기 – DataMatrix 종횡비 – Aspose.BarCode
url: /ko/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 바코드 PNG 생성 – DataMatrix 종횡비 – Aspose.BarCode

맞춤형 DataMatrix 종횡비를 사용하여 **barcode PNG**를 생성하는 것은 바코드가 특정 레이아웃 제약에 맞도록 해야 할 때 흔히 요구되는 작업입니다. 이 튜토리얼에서는 Aspose.BarCode for .NET을 사용해 **barcode PNG** 파일을 **생성**하는 정확한 단계들을 안내하고, 종횡비를 조정하고 싶은 이유를 설명하며, 애플리케이션에 맞게 출력물을 미세 조정하는 방법을 보여드립니다.

## 빠른 답변
- **“aspect ratio”가 무엇을 제어하나요?** DataMatrix 모듈의 가로‑세로 비율을 정의합니다.  
- **PNG, JPEG, 또는 SVG를 출력할 수 있나요?** 예 – `Save` 메서드는 PNG, JPEG, BMP, GIF 등을 지원합니다.  
- **이 기능에 라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있지만, 운영 환경에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **유효한 aspect‑ratio 값은 몇 개인가요?** 양의 실수이면 모두 가능하며, 일반적인 값은 0.5 – 2.0입니다.

## DataMatrix 바코드란 무엇이며 왜 종횡비를 조정해야 하나요?
DataMatrix는 작은 공간에 대량의 데이터를 저장하는 2차원 매트릭스 바코드입니다. **aspect ratio**를 조정하면 모듈을 가로로 늘리거나 압축할 수 있어, 가독성을 유지하면서 좁은 열이나 넓은 라벨에 바코드를 맞추는 데 유용합니다.

## 전제 조건
DataMatrix 종횡비를 커스터마이징하기 전에, 다음 전제 조건이 준비되어 있는지 확인하십시오:

1. **Visual Studio** – 최신 버전이면 모두 사용 가능합니다.  
2. **Aspose.BarCode for .NET** – [여기](https://releases.aspose.com/barcode/net/)에서 다운로드하십시오.  
3. **.NET Framework / .NET Core** – 프로젝트가 지원되는 버전을 대상으로 해야 합니다.

## 네임스페이스 가져오기
먼저, C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** 이 `using` 문을 파일 상단에 유지하면 `BarcodeGenerator` 클래스를 언제든 사용할 수 있습니다.

## 단계별 가이드

### Step 1: 프로젝트 설정
Visual Studio에서 새 콘솔 또는 Windows Forms 프로젝트를 만들고 Aspose.BarCode DLL에 대한 참조를 추가하십시오.

### Step 2: 바코드 생성기 초기화
`BarcodeGenerator`를 DataMatrix 유형과 인코딩하려는 데이터로 인스턴스화합니다:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 이 코드는 샘플 텍스트를 포함하는 DataMatrix 바코드를 생성할 준비가 된 제너레이터를 만듭니다.

### Step 3: 종횡비 맞춤 설정 및 PNG 파일 저장
이제 **aspect ratio**를 변경하고 각 버전을 PNG 이미지로 저장할 수 있습니다:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 첫 번째 호출은 정사각형 비율의 바코드(`AspectRatio = 1`)를 생성합니다.  
- 두 번째 호출은 바코드를 가로로 압축(`AspectRatio = 0.5`)하여 더 넓은 모양을 만듭니다.

이제 서로 다른 종횡비를 가진 두 개의 **barcode PNG** 파일이 준비되어 보고서, 라벨 또는 UI 요소에 사용할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **생성된 이미지가 흐릿함** | 저장하기 전에 `Resolution` 매개변수를 증가시킵니다 (`gen.Parameters.ImageResolution = 300`). |
| **바코드가 스캔되지 않음** | 종횡비가 0.5 – 2.0 범위 내에 있는지 확인하고 충분한 여백(`gen.Parameters.Barcode.CodeTextParameters.Margin`)을 유지하십시오. |
| **파일 경로 오류** | `Path.Combine`를 사용해 출력 경로를 만들고 폴더가 존재하는지 확인하십시오. |

## 자주 묻는 질문

**Q: Aspose.BarCode for .NET를 사용해 다른 바코드 유형의 종횡비를 맞춤 설정할 수 있나요?**  
A: 예, 많은 2‑D 바코드(예: QR, PDF417)는 해당 파라미터 객체를 통해 종횡비 조정을 지원합니다.

**Q: Aspose.BarCode for .NET의 무료 체험판을 이용할 수 있나요?**  
A: 예, Aspose.BarCode for .NET의 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: Aspose.BarCode for .NET 라이선스는 어디서 구매할 수 있나요?**  
A: Aspose 웹사이트의 [여기](https://purchase.aspose.com/buy)에서 라이선스를 구매할 수 있습니다.

**Q: Aspose.BarCode for .NET가 다양한 .NET Framework 버전과 호환되나요?**  
A: 예, .NET Framework 4.x, .NET Core 3.1+, 최신 .NET 릴리스와 모두 호환됩니다.

**Q: Aspose.BarCode for .NET를 사용해 다양한 형식으로 바코드를 생성할 수 있나요?**  
A: 물론입니다 – PNG, JPEG, BMP, GIF, TIFF, SVG, PDF 등 모든 형식을 기본적으로 지원합니다.

## 결론
DataMatrix 바코드의 **aspect ratio**를 맞춤 설정하고 **barcode PNG** 파일을 **생성**하는 것은 Aspose.BarCode for .NET을 사용하면 간단합니다. 위 단계들을 따르면 프로젝트의 정확한 레이아웃 요구사항을 충족하는 완벽한 크기의 바코드를 생성할 수 있습니다. `Resolution`, `Margin`, `Color`와 같은 다른 파라미터를 탐색하여 출력을 더욱 세밀하게 조정해 보세요.

더 자세히 알아보려면 공식 [문서](https://reference.aspose.com/barcode/net/)를 확인하거나 [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)에서 커뮤니티에 참여하십시오.

---

**마지막 업데이트:** 2026-01-12  
**테스트 환경:** Aspose.BarCode 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}