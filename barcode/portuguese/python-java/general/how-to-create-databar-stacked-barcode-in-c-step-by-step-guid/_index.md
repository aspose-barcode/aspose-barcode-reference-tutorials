---
category: general
date: 2026-10-21
description: Crie códigos de barras Databar empilhados rapidamente usando C#. Aprenda
  a definir a dimensão X, ajustar a proporção e salvar imagens PNG neste tutorial
  completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: pt
lastmod: 2026-10-21
og_description: crie um código de barras Databar empilhado em C# com Aspose.BarCode.
  siga este guia para configurar a dimensão X, mudar a proporção e exportar arquivos
  PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Crie código de barras Databar empilhado em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Como criar código de barras databar empilhado em C# – guia passo a passo
url: /pt/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras databar empilhado em C# – guia passo a passo

Se você precisar **criar código de barras databar empilhado** em uma aplicação .NET, este guia mostra exatamente como fazer. Você verá como configurar a X‑dimension, alterar a proporção e salvar o código de barras como arquivos PNG.

Gerar um código de barras DataBar empilhado não requer um pipeline de build complexo. Este tutorial cobre tudo o que você precisa: pacotes necessários, explicação linha por linha do código e dicas para armadilhas comuns. Ao final, você poderá produzir várias imagens de código de barras com diferentes proporções em um único método.

## O que você precisará

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte C#)  
* **Aspose.BarCode for .NET** pacote NuGet – a biblioteca que fornece `BarcodeGenerator` e `EncodeTypes`  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console ou adicione o código a um existente. Importe os namespaces necessários para que o compilador reconheça as classes de código de barras.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Essas declarações `using` expõem `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` usados mais adiante no exemplo.

## Etapa 2: Definir a pasta de saída

Escolha uma pasta onde os arquivos PNG gerados serão gravados. Usar um caminho absoluto ou relativo funciona da mesma forma; o exemplo usa uma pasta relativa chamada `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Criar a pasta programaticamente evita erros em tempo de execução quando o diretório está ausente.

## Etapa 3: Inicializar o gerador de **criar código de barras databar empilhado**

Crie uma instância de `BarcodeGenerator` com `EncodeTypes.DatabarStackedOmniDirectional`. Os dados de exemplo `(01)12345678901231` seguem o formato GS1‑128 exigido pelo DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

O objeto gerador contém todos os parâmetros que afetam a aparência visual do código de barras.

## Etapa 4: Definir a X‑dimension (largura em pixels da barra mais fina)

A X‑dimension controla o tamanho geral do código de barras sem alterar os dados codificados. Um valor de `2` pixels fornece uma imagem clara e legível para a maioria das resoluções de tela.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ajuste esse valor se precisar de um código de barras maior ou menor; mantenha a proporção entre largura e altura consistente.

## Etapa 5: Configurar a proporção e salvar a primeira imagem

A proporção determina a relação altura‑largura de um código de barras DataBar empilhado. Uma proporção de `15` é um padrão comum que produz um visual compacto.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

O método `Save` grava um arquivo PNG na pasta definida anteriormente. O nome do arquivo indica claramente a proporção usada.

### Saída esperada para a proporção 15

O `DatabarAspectRatio15.png` gerado tem aparência semelhante à ilustração abaixo.

![Imagem de código de barras gerada com proporção 15](https://example.com/images/databar-aspect15.png "Imagem de código de barras gerada com proporção 15")

*Texto alternativo:* `create databar stacked barcode image saved with aspect ratio 15`

## Etapa 6: Alterar a proporção e salvar uma segunda imagem

Você pode reutilizar a mesma instância de `BarcodeGenerator` para produzir variações. Alterar o `AspectRatio` para `30` dobra a altura de cada pilha de barras, o que pode ser necessário para impressão em alta resolução.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Saída esperada para a proporção 30

A imagem `DatabarAspectRatio30.png` é mais alta, preservando a mesma largura enquanto aumenta a legibilidade para scanners distantes.

![Imagem de código de barras gerada com proporção 30](https://example.com/images/databar-aspect30.png "Imagem de código de barras gerada com proporção 30")

*Texto alternativo:* `create databar stacked barcode image saved with aspect ratio 30`

## Código-fonte completo

Juntando todas as etapas resulta em um programa autônomo que você pode executar imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Compile e execute o programa. Após a execução, o diretório `Barcodes` contém dois arquivos PNG, cada um representando um **criar código de barras databar empilhado** com uma proporção diferente.

## Dicas profissionais e armadilhas comuns

* **Dica profissional:** Mantenha a X‑dimension entre 1 px e 4 px para a maioria dos casos de uso em tela. Valores maiores aumentam o tamanho do arquivo sem melhorar a confiabilidade da leitura.  
* **Armadilha:** Alterar o valor de `EncodeTypes` após a criação do gerador não atualiza a codificação interna. Sempre especifique o `EncodeTypes` correto no construtor.  
* **Dica profissional:** Quando precisar de mais de duas proporções, itere sobre um array de valores inteiros e chame `Save` dentro do loop. Isso reduz a duplicação de código.  
* **Armadilha:** Salvar em um caminho sem permissão de escrita gera uma `UnauthorizedAccessException`. Garanta que a aplicação seja executada com os direitos de sistema de arquivos adequados.

## Conclusão

Agora você sabe como **criar código de barras databar empilhado** em C# usando Aspose.BarCode. O guia abordou a configuração do ambiente, a configuração da X‑dimension, o ajuste da proporção e a gravação de arquivos PNG. Com essa base, você pode gerar variações adicionais, integrar a criação de códigos de barras em APIs web ou incorporar as imagens em relatórios PDF.

Em seguida, explore tópicos relacionados, como as melhores práticas de leitura de **DataBar Stacked Omnidirectional**, incorporação de códigos de barras em respostas **ASP.NET Core**, ou geração de **QR codes** com a mesma biblioteca. Experimente diferentes `EncodeTypes` e formatos de imagem para atender às necessidades da sua aplicação.

Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar imagens PNG de databar com C# e Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Como definir colunas para um código de barras Databar Expanded Stacked – guia completo em C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Código de barras databar stacked omnidirectional em C# – Guia completo](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}