---
date: 2026-01-15
description: Aspose.BarCode for .NET를 사용해 DataMatrix 인코딩 모드(C40)로 PNG 파일을 저장하는 방법을
  배워보세요 – 단계별 바코드 튜토리얼.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode를 사용하여 DataMatrix C40로 PNG 저장하는 방법
url: /ko/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET를 사용한 마스터 DataMatrix 인코딩 모드 (C40)

## 소개

## 빠른 답변
- **“how to save png”가 의미하는 바는 무엇인가요?** 생성된 바코드를 PNG 이미지 파일로 저장하는 것입니다.  
- **어떤 인코딩 모드가 다루어지나요?** DataMatrix C40 인코딩.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **.NET Core에서 실행할 수 있나요?** 예, Aspose.BarCode는 .NET Framework와 .NET Core를 지원합니다.  
- **어떤 파일 형식이 생성되나요?** PNG (Portable Network Graphics) 이미지.

## DataMatrix C40 인코딩으로 PNG 저장 방법
바코드를 PNG로 저장하는 것은 생성기를 구성한 후의 최종 단계입니다. `Save` 메서드는 파일 경로, 원하는 파일 이름, 이미지 형식(`BarCodeImageFormat.Png`)을 받습니다. 이를 통해 바코드가 손실 없는 형식으로 저장되어 브라우저, 프린터 및 모바일 장치에서 모두 작동합니다.

## DataMatrix 인코딩 모드 (C40)란 무엇인가요?
C40는 알파벳과 숫자 데이터를 효율적으로 표현할 수 있는 문자 집합으로, 더 작은 DataMatrix 심볼에 더 많은 정보를 담을 수 있게 해줍니다. 문자, 숫자 및 제한된 특수 문자 집합을 포함하는 텍스트를 인코딩할 때 특히 유용합니다.

## 왜 Aspose.BarCode for .NET를 사용해야 할까요?
- **전체 제어**: 바코드 크기, 오류 정정 및 인코딩 모드를 완벽히 제어합니다.  
- **Zero‑dependency** 생성 – 외부 서비스가 필요 없습니다.  
- **크로스‑플랫폼** 지원: .NET Framework, .NET Core 및 .NET 5/6+.

## 전제 조건

코드에 들어가기 전에 다음 항목을 준비하세요:

1. **.NET 개발 환경** – Visual Studio, Rider 또는 C#을 지원하는 모든 IDE.  
2. **Aspose.BarCode for .NET** – NuGet 또는 공식 설치 프로그램을 통해 설치합니다. 자세한 내용은 [documentation](https://reference.aspose.com/barcode/net/)을 참조하세요.  
3. **기본 C# 지식** – 네임스페이스, 클래스 및 using 문에 익숙해야 합니다.  
4. **쓰기 권한이 있는 폴더** – PNG가 저장될 로컬 디렉터리.

## 필요한 네임스페이스 가져오기

바코드 생성 클래스를 사용하려면 C# 소스 파일 상단에 필요한 네임스페이스를 추가하세요:

```csharp
using Aspose.BarCode.Generation;
```

## 단계별 바코드 생성

아래는 **단계별 바코드** 진행 과정입니다. 각 단계는 쉬운 설명과 함께 제공되며, 원본 코드 블록은 복사‑붙여넣기를 위해 그대로 유지됩니다.

### 1단계: 디렉터리 경로 정의
PNG 이미지가 저장될 폴더를 설정합니다. 자리표시자를 실제 경로로 교체하세요.

```csharp
string path = "Your Directory Path";
```

### 2단계: 바코드 생성 설정
`BarcodeGenerator` 인스턴스를 생성하고, `EncodeTypes.DataMatrix`를 지정한 뒤 인코딩할 데이터를 제공하세요.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 3단계: 바코드 사용자 정의
X‑dimension(모듈의 픽셀 너비)을 설정하고 인코딩 모드를 C40으로 전환합니다.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 4단계: 바코드 이미지 저장
마지막으로, 생성된 바코드를 PNG 파일로 저장합니다. 이것이 Aspose.BarCode를 사용한 **how to save png**에 대한 구체적인 답변입니다.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

프로그램을 실행하면 지정한 폴더에 `DataMatrixEncodeModeC40.png` 파일이 생성되며, 보고서, 라벨 또는 웹 페이지에서 바로 사용할 수 있습니다.

## 일반적인 문제 및 팁
- **잘못된 경로** – 디렉터리가 존재하고 쓰기 권한이 있는지 확인하세요. 그렇지 않으면 `gen.Save`가 예외를 발생시킵니다.  
- **잘못된 인코딩 모드** – C40 집합에 포함되지 않는 문자를 인코딩해야 하면 `DataMatrixEncodeMode.Auto` 또는 다른 적절한 모드로 전환하세요.  
- **이미지 크기** – `XDimension.Pixels`를 조정하여 바코드 전체 크기를 늘리거나 줄일 수 있으며, 가독성에는 영향을 주지 않습니다.

## 자주 묻는 질문

**Q: DataMatrix 인코딩 모드 (C40)란 무엇인가요?**  
A: C40는 문자, 숫자 및 제한된 특수 문자를 포함하는 텍스트에 적합한 DataMatrix 심볼용 압축 알파벳-숫자 인코딩 방식입니다.

**Q: Aspose.BarCode for .NET 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [here](https://reference.aspose.com/barcode/net/)에서 확인할 수 있습니다. 모든 바코드 유형 및 인코딩 옵션에 대한 자세한 안내를 제공합니다.

**Q: Aspose.BarCode for .NET가 모든 .NET 버전과 호환되나요?**  
A: 네, 이 라이브러리는 .NET Framework 4.5 이상부터 .NET 6 및 그 이후 버전까지 다양한 .NET 버전을 지원합니다.

**Q: 구매 전에 Aspose.BarCode for .NET를 체험할 수 있나요?**  
A: 예, [this link](https://releases.aspose.com/)를 방문하면 Aspose.BarCode for .NET의 무료 체험판을 이용할 수 있습니다. 이를 통해 라이브러리 기능과 성능을 테스트해 볼 수 있습니다.

**Q: Aspose.BarCode for .NET에 대한 지원은 어디서 받을 수 있나요?**  
A: [Aspose forum](https://forum.aspose.com/c/barcode/13)에서 활발한 커뮤니티와 지원을 받을 수 있습니다.

## 결론

이 **단계별 바코드** 가이드를 따라 하면 Aspose.BarCode for .NET를 사용해 DataMatrix C40 인코딩으로 생성된 **PNG 저장 방법**을 정확히 알게 됩니다. 이 방법을 통해 바코드의 모양, 크기 및 데이터 표현을 완전히 제어할 수 있어, 어떤 .NET 애플리케이션에도 고품질 바코드를 손쉽게 통합할 수 있습니다.

---

**마지막 업데이트:** 2026-01-15  
**테스트 대상:** Aspose.BarCode 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}