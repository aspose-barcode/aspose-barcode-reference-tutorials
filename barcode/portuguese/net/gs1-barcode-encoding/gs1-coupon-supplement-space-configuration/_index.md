---
date: 2026-09-28
description: Aprenda a criar barcode custom space para cupons GS1 com Aspose.BarCode
  para .NET e aumente a legibilidade do barcode. Siga nosso guia passo a passo.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Configuração de Espaço de Suplemento de Cupom GS1
og_description: Aprenda a criar barcode custom space para cupons GS1 com Aspose.BarCode
  para .NET e aumente a legibilidade do barcode. Código passo a passo e dicas incluídas.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Criar barcode custom space para suplemento de cupom GS1 – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Como criar barcode custom space para suplemento de cupom GS1
url: /pt/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuração do espaço suplementar de cupom GS1

Neste tutorial você **criará espaço personalizado de código de barras** para o Espaço Suplementar de Cupom GS1 usando Aspose.BarCode for .NET. Ajustar o espaço suplementar é essencial quando você precisa **aumentar a legibilidade do código de barras** em scanners de baixa resolução ou cumprir margens exigidas pelos varejistas. Ao final deste guia, você entenderá por que o espaço suplementar é importante, como configurá-lo programaticamente e como gerar imagens com diferentes valores de pixels.

## Respostas rápidas
- **O que o espaço suplementar controla?** Ele define a área em branco (em pixels) entre os dados do cupom e o restante do código de barras.  
- **Qual tipo de código de barras é usado?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Posso alterar o tamanho do espaço?** Sim – defina `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` para qualquer valor inteiro.  
- **Preciso de uma licença para este recurso?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais formatos de saída são suportados?** PNG, JPEG, BMP, GIF, TIFF e mais via `BarCodeImageFormat`.

## O que é o espaço suplementar de cupom GS1?
O Espaço Suplementar de Cupom GS1 é uma região em branco definida que aparece em códigos de barras de cupom GS1‑Databar. Sistemas de varejo utilizam esse espaço para melhorar a confiabilidade da leitura e para cumprir especificações da indústria que exigem uma margem mínima ao redor dos dados suplementares.

## Por que configurar o espaço suplementar?
O espaço suplementar aumenta diretamente **a legibilidade do código de barras** e ajuda a atender às rigorosas diretrizes dos varejistas. Ao adicionar pixels extras, você reduz a probabilidade de leituras incorretas em scanners de baixa resolução, garante uma leitura consistente em diferentes tamanhos de etiquetas e oferece flexibilidade visual para equilibrar o código de barras dentro de um layout impresso.

## Pré-requisitos

Antes de mergulharmos na configuração do Espaço Suplementar de Cupom GS1 com Aspose.BarCode for .NET, certifique‑se de que você possui o seguinte:

1. **Visual Studio** – O IDE principal para desenvolvimento .NET.  
2. **Aspose.BarCode for .NET** – Baixe a biblioteca na [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework ou .NET 5+** – É necessário familiaridade com C# e o runtime .NET.

Agora que o ambiente está pronto, vamos prosseguir para a implementação.

## Importar namespaces

O namespace `Aspose.BarCode.Generation` contém a classe `BarcodeGenerator` e as configurações relacionadas.

```csharp
using Aspose.BarCode;
```

## Etapa 1: definir o caminho

Escolha uma pasta onde as imagens geradas serão salvas. O caminho deve terminar com o separador de diretório apropriado para o seu sistema operacional.

```csharp
string path = "Your Directory Path";
```

## Etapa 2: gerar configuração do espaço suplementar de cupom GS1

O trecho a seguir cria um código de barras, define a dimensão X e ajusta o espaço suplementar.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

Neste exemplo, nós:
1. **Criar** uma instância `BarcodeGenerator` para o tipo `UpcaGs1DatabarCoupon`.  
2. **Definir** a dimensão X para 2 pixels, que determina a largura da barra mais estreita.  
3. **Ajustar** a propriedade `SupplementSpace.Pixels` para 30 px, gerar uma imagem e, em seguida, repetir com 50 px.  

Sinta‑se à vontade para experimentar outros valores de pixels para adequar ao seu fluxo de impressão.

## Problemas comuns e dicas
- **Caminho inválido** – Certifique‑se de que a variável `path` termine com uma barra invertida (`\`) ou barra (`/`) adequada ao seu SO.  
- **Permissões insuficientes** – Execute o Visual Studio como Administrador ou escolha uma pasta onde a aplicação tenha acesso de gravação.  
- **Formato de dados incorreto** – A string de dados deve seguir a sintaxe GS1 (`(8110)` denota o identificador do suplemento).  

## Por que isso importa para o seu negócio
O Aspose.BarCode suporta **mais de 60 simbologias de código de barras** e pode renderizar imagens de até **10.000 × 10.000 pixels** sem esgotar a memória. Para implantações de varejo em grande escala, isso significa que você pode gerar cupons GS1 de alta resolução em modo batch, mantendo o tempo de processamento abaixo de um segundo por imagem em hardware de servidor típico.

## Perguntas frequentes
**Q: Qual é o objetivo do Espaço Suplementar de Cupom GS1 em códigos de barras?**  
A: Ele adiciona uma margem em branco obrigatória ao redor dos dados suplementares, melhorando a confiabilidade do scanner e atendendo às larguras mínimas especificadas pelos varejistas.

**Q: Posso personalizar a largura do Espaço Suplementar de Cupom GS1 com Aspose.BarCode for .NET?**  
A: Sim, defina `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` para qualquer valor inteiro; a biblioteca aplica instantaneamente a alteração à imagem gerada.

**Q: Onde posso encontrar documentação adicional e suporte para Aspose.BarCode for .NET?**  
A: Consulte a [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) e visite o [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) para assistência da comunidade.

**Q: O Aspose.BarCode for .NET é adequado tanto para iniciantes quanto para desenvolvedores experientes?**  
A: Absolutamente. A API oferece métodos simples para tarefas rápidas e opções avançadas para geração de código de barras afinada.

**Q: Posso obter uma licença temporária para Aspose.BarCode for .NET para avaliar seus recursos?**  
A: Sim, solicite uma licença de avaliação no [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Conclusão
Seguindo os passos acima, você agora sabe como **criar espaço personalizado de código de barras** para o Espaço Suplementar de Cupom GS1, uma técnica fundamental para **aumentar a legibilidade do código de barras** e atender aos padrões de varejo. Incorpore o código em suas soluções de leitura existentes, experimente diferentes valores de pixels e explore outros tipos de código de barras oferecidos pelo Aspose.BarCode for .NET.

---

**Última atualização:** 2026-09-28  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriais relacionados
- [Gerar código de barras Databar Aspose.BarCode usando API .NET – Configuração de Linha e Coluna](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode for .NET – Guia passo a passo](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}