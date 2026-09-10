---
date: 2026-06-14
description: Aprenda como criar código de barras DotCode .NET e personalizar sua proporção
  de aspecto usando Aspose.BarCode for .NET.
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: Personalização da proporção de aspecto do DotCode
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Criar código de barras DotCode .NET – Personalizar a proporção de aspecto
url: /pt/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras DotCode .NET – Personalizar proporção de aspecto

Se você precisar **criar código de barras DotCode .NET** soluções que se encaixem em espaços apertados ou requisitos de layout específicos, o Aspose.BarCode para .NET oferece controle total. Neste tutorial, percorreremos todo o processo de geração de um código de barras DotCode e ajuste da sua proporção de aspecto para que ele fique exatamente como você deseja em embalagens, etiquetas ou telas móveis.  

## Respostas rápidas
- **Posso gerar códigos de barras DotCode em .NET?** Sim, o Aspose.BarCode suporta DotCode pronto para uso.  
- **Qual propriedade controla a forma?** A propriedade `AspectRatio` de `BarcodeGenerator`.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial; um teste gratuito funciona para desenvolvimento.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo o código leva para executar?** Menos de um segundo para um código de barras típico de 200 × 200 pixels.

## Qual é o objetivo principal deste tutorial?
O tutorial tem como objetivo demonstrar como gerar um código de barras DotCode usando Aspose.BarCode para .NET e como ajustar sua proporção de aspecto para atender a restrições de layout específicas. Ao seguir os passos, você aprenderá a configurar o gerador, modificar os parâmetros de tamanho e exportar a imagem em formatos comuns.

## Como criar código de barras DotCode .NET?
Para criar um código de barras DotCode em .NET, instancie um `BarcodeGenerator` com `EncodeTypes.DotCode` e os dados que deseja codificar. Em seguida, defina as propriedades X‑Dimension e AspectRatio para controlar o tamanho e a forma, e finalmente chame o método `Save` para gravar a imagem em um arquivo no formato desejado.

## Pré-requisitos

1. **Aspose.BarCode for .NET** – baixe a biblioteca no site oficial [aqui](https://releases.aspose.com/barcode/net/).  
2. **IDE** – Visual Studio, Rider ou qualquer editor compatível com .NET.  
3. **Output folder** – substitua “Your Directory Path” no exemplo por uma pasta real em sua máquina.

## Importar namespaces

`Aspose.BarCode.Generation` fornece as classes necessárias para gerar e configurar códigos de barras em .NET.  
```csharp
using Aspose.BarCode.Generation;
```

## Etapa 1: Inicializar o Gerador de Código de Barras

`BarcodeGenerator` é a classe principal que cria uma imagem de código de barras com base na simbologia e nos dados especificados.  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## Etapa 2: Definir a X‑Dimension (Tamanho) do Código de Barras

`XDimension` define a largura de um único módulo (ponto) em pixels, afetando o tamanho geral do código de barras.  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## Etapa 3: Personalizar a Proporção de Aspecto

`AspectRatio` define a proporção altura‑largura de cada módulo, permitindo esticar ou comprimir o código de barras verticalmente.  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## Etapa 4: Salvar a Imagem do Código de Barras

`Save` grava o código de barras gerado em um arquivo no formato de imagem escolhido, como PNG ou JPEG.  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Por que usar Aspose.BarCode para personalização de DotCode?
Aspose.BarCode oferece um conjunto abrangente de recursos para geração de DotCode, incluindo saída de alta resolução, amplo suporte a formatos e controle detalhado sobre as dimensões do código de barras, como a proporção de aspecto. Ele funciona em todas as principais plataformas .NET, não requer dependências externas e oferece desempenho rápido de renderização, tornando‑o ideal para aplicações desktop e web.

## Casos de Uso Comuns

- **Saúde**: Etiquetas compactas de ID de pacientes que precisam caber em pequenas pulseiras.  
- **Serviços Postais**: Etiquetas de envio de formato amplo onde uma altura menor melhora a confiabilidade da leitura.  
- **Manufatura**: Rotulagem em linha de peças onde restrições de espaço exigem uma proporção de aspecto personalizada.

## Perguntas Frequentes

**Q:** Qual é a proporção de aspecto de um código de barras DotCode?  
**A:** É a razão entre a altura e a largura de um módulo; ajustá‑la altera a forma geral do código de barras.

**Q:** Quais indústrias se beneficiam mais dos códigos de barras DotCode?  
**A:** Saúde, serviços postais e manufatura utilizam DotCode frequentemente para codificação compacta e de alta densidade.

**Q:** Posso personalizar outros parâmetros do DotCode com Aspose.BarCode para .NET?  
**A:** Absolutamente. Você pode modificar o nível de correção de erros, cores de primeiro plano/fundo e até incorporar logotipos.

**Q:** O Aspose.BarCode é adequado para aplicações .NET web e desktop?  
**A:** Sim, a biblioteca funciona perfeitamente em ASP.NET, WPF, WinForms e aplicativos de console.

**Q:** Onde posso encontrar mais documentação e exemplos?  
**A:** Referência detalhada da API e exemplos de código estão disponíveis [aqui](https://reference.aspose.com/barcode/net/).

**Última atualização:** 2026-06-14  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Configuração de Texto de Código Estendido DotCode com Aspose.BarCode para .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Configuração do Modo Append Estruturado DotCode com Aspose.BarCode para .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}