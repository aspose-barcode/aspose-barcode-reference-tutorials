---
date: 2026-05-30
description: Aprenda como criar PNG de código de barras com uma proporção personalizada
  do DataMatrix usando Aspose.BarCode para .NET. Guia passo a passo para geração de
  códigos de barras e personalização de tamanho.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Personalização da Proporção do DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Criar PNG de Código de Barras – Proporção do DataMatrix – Aspose.BarCode
url: /pt/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PNG de Código de Barras – Proporção do DataMatrix – Aspose.BarCode

Gerar um **barcode PNG** com uma proporção personalizada do DataMatrix é uma necessidade comum quando você precisa **criar arquivos barcode PNG** que se ajustem a restrições de layout específicas. Neste tutorial, percorreremos os passos exatos para **criar arquivos barcode PNG** usando Aspose.BarCode para .NET, explicaremos por que você pode querer ajustar a proporção e mostraremos como refinar a saída para sua aplicação.

## Respostas Rápidas
- **O que controla a “aspect ratio”?** Define a proporção largura‑altura dos módulos do DataMatrix.  
- **Posso gerar PNG, JPEG ou SVG?** Sim – o método `Save` suporta PNG, JPEG, BMP, GIF, TIFF, SVG e PDF.  
- **Preciso de licença para este recurso?** Um teste gratuito funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Quantos valores de aspect‑ratio são válidos?** Qualquer número de ponto flutuante positivo; valores típicos são 0.5 – 2.0.

## O que é um código de barras DataMatrix e por que ajustar sua proporção?
Um código de barras DataMatrix é um código matricial bidimensional que armazena grandes quantidades de dados em um quadrado compacto. Ajustar a **aspect ratio** permite esticar ou comprimir os módulos horizontalmente, o que é útil quando você precisa encaixar o código de barras em colunas estreitas ou etiquetas largas sem sacrificar a confiabilidade da leitura.

## Por que usar Aspose.BarCode para criar barcode PNG?
Aspose.BarCode suporta **7 formatos de imagem** — PNG, JPEG, BMP, GIF, TIFF, SVG e PDF — e pode processar **mais de 50 formatos de entrada e saída** na memória, manipulando documentos com centenas de páginas sem carregar o arquivo inteiro. A biblioteca fornece uma API fluente que permite gerar um código de barras DataMatrix em uma única linha de código, garantindo renderização pixel‑perfeita e total compatibilidade com .NET.

## Pré-requisitos

Antes de começarmos a personalizar as proporções do DataMatrix, certifique‑se de que você tem os seguintes pré-requisitos configurados:

1. **Visual Studio** – qualquer versão recente serve.  
2. **Aspose.BarCode for .NET** – faça o download [aqui](https://releases.aspose.com/barcode/net/).  
3. Você também pode explorar outras versões de produtos Aspose [aqui](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – seu projeto deve target uma versão suportada.

## Importar Namespaces

Primeiro, você precisa importar o namespace necessário em seu projeto C#:

`using Aspose.BarCode.Generation;` importa o namespace que contém as classes de geração de código de barras.  

```csharp
using Aspose.BarCode.Generation;
```

> **Dica:** Mantenha esta instrução `using` no topo do seu arquivo para que a classe `BarcodeGenerator` esteja sempre disponível.

## Como criar barcode PNG com proporção personalizada?

Carregue o `BarcodeGenerator`, defina o tipo DataMatrix, ajuste a propriedade `AspectRatio` e chame `Save`. Esse padrão de uma linha cria um barcode PNG que respeita a proporção especificada, e a biblioteca lida automaticamente com o dimensionamento dos módulos e as zonas silenciosas.

`BarcodeGenerator` cria uma imagem de código de barras a partir da simbologia e dos dados especificados.  

### Etapa 1: Configurar Seu Projeto
Crie um novo projeto de console ou Windows Forms no Visual Studio e adicione uma referência ao DLL do Aspose.BarCode.

### Etapa 2: Inicializar um Barcode Generator
Instancie‑o com a simbologia DataMatrix e os dados que você deseja codificar:

`BarcodeGenerator` cria uma imagem de código de barras a partir da simbologia e dos dados especificados.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Esta linha cria um gerador pronto para produzir um código de barras DataMatrix que contém o texto de exemplo.

### Etapa 3: Personalizar a Proporção e Salvar Arquivos PNG
Agora você pode alterar a **aspect ratio** e salvar cada versão como uma imagem PNG:

`AspectRatio` define a proporção largura‑altura dos módulos do DataMatrix.  
`Save` grava a imagem de código de barras gerada em um arquivo no formato escolhido.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- A primeira chamada cria um código de barras com proporção quadrada (`AspectRatio = 1`).  
- A segunda chamada comprime o código de barras horizontalmente (`AspectRatio = 0.5`), produzindo uma aparência mais larga.

Agora você tem dois arquivos **barcode PNG** com diferentes proporções, prontos para uso em relatórios, etiquetas ou elementos de UI.

## Problemas Comuns & Soluções

| Problema | Solução |
|----------|----------|
| **Imagem gerada está borrada** | Aumente o parâmetro `Resolution` antes de salvar (`gen.Parameters.ImageResolution = 300`). |
| **Código de barras não escaneia** | Garanta que a aspect ratio permaneça entre 0.5 – 2.0 e mantenha uma zona silenciosa suficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Erros de caminho de arquivo** | Use `Path.Combine` para construir o caminho de saída e verifique se a pasta existe. |

## Perguntas Frequentes

**Q: Posso personalizar a aspect ratio de outros tipos de código de barras usando Aspose.BarCode para .NET?**  
A: Sim, muitos códigos de barras 2‑D (por exemplo, QR, PDF417) suportam ajustes de aspect‑ratio através de seus objetos de parâmetro específicos.

**Q: Existe um teste gratuito disponível para Aspose.BarCode para .NET?**  
A: Sim, você pode acessar um teste gratuito do Aspose.BarCode para .NET [aqui](https://releases.aspose.com/).

**Q: Onde posso comprar uma licença para Aspose.BarCode para .NET?**  
A: Você pode comprar uma licença no site da Aspose [aqui](https://purchase.aspose.com/buy).

**Q: O Aspose.BarCode para .NET é compatível com diferentes versões do .NET Framework?**  
A: Sim, funciona com .NET Framework 4.x, .NET Core 3.1+ e as versões mais recentes do .NET.

**Q: Posso gerar códigos de barras em diferentes formatos com Aspose.BarCode para .NET?**  
A: Absolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG e PDF são todos suportados nativamente.

## Conclusão

Personalizar a **aspect ratio** de um código de barras DataMatrix e **criar arquivos barcode PNG** é simples com Aspose.BarCode para .NET. Seguindo os passos acima, você pode gerar códigos de barras com tamanho perfeito que atendem aos requisitos exatos de layout do seu projeto. Explore parâmetros adicionais como `Resolution`, `Margin` e `Color` para ajustar ainda mais a saída, e considere as capacidades de `generate datamatrix barcode` ao criar aplicações amigáveis à leitura em Visual Studio.

Para uma exploração mais aprofundada, consulte a [documentação](https://reference.aspose.com/barcode/net/) oficial ou participe da comunidade no [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2026-05-30  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Gerar Código de Barras DataMatrix – Guia Profissional com Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Como Gerar Códigos de Barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Dominar a Codificação DataMatrix em ASCII com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}