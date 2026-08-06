---
category: general
date: 2026-08-06
description: Crie códigos de barras DataBar empilhados em C# rapidamente. Aprenda
  a definir a dimensão X, ajustar a proporção e exportar arquivos PNG usando o gerador
  DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: pt
lastmod: 2026-08-06
og_description: Crie código de barras Databar empilhado em C# com Aspose.BarCode.
  Este tutorial mostra como configurar a dimensão X, alterar a proporção e salvar
  imagens PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Crie código de barras Databar empilhado em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Crie código de barras Databar empilhado em C# – guia passo a passo
url: /pt/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar databar stacked barcode em C# – guia passo a passo

Se você precisa **criar databar stacked barcode** imagens em C#, este guia mostra exatamente como fazer isso usando a biblioteca Aspose.BarCode. Você aprenderá a definir a dimensão X, alterar a proporção do código de barras e salvar o resultado como arquivos PNG — tudo em alguns passos concisos.

Gerar um DataBar Stacked barcode é comum quando você precisa codificar dados GS1‑128 para leitura no varejo ou rastreamento logístico. Nas seções a seguir, cobrimos tudo, desde a configuração do projeto até a verificação da saída, para que você possa integrar a solução em qualquer aplicação .NET sem perder nenhum detalhe.

## Pré-requisitos

* **.NET 6.0** (ou posterior) instalado – o código tem como alvo o SDK moderno.
* Uma cópia **licenciada** de **Aspose.BarCode for .NET**. A avaliação gratuita funciona para testes, mas adiciona uma marca d'água.
* Uma IDE como **Visual Studio 2022** ou **VS Code** com a extensão C#.
* Familiaridade básica com a sintaxe **C#** e o conceito de Identificadores de Aplicação GS1.

> **Dica profissional:** Se você usar o gerenciador de pacotes NuGet, o comando `dotnet add package Aspose.BarCode` resolve todas as dependências automaticamente.

## Etapa 1: Criar um novo projeto de console

Abra um terminal ou o Console do Gerenciador de Pacotes e execute:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

O comando `dotnet new console` gera um arquivo **Program.cs** mínimo. Adicionar o pacote **Aspose.BarCode** disponibiliza a classe `BarcodeGenerator`.

## Etapa 2: Inicializar o gerador DataBar Stacked Omnidirectional

Abra **Program.cs** e substitua o conteúdo padrão pelo código a seguir. A primeira linha cria um **BarcodeGenerator** configurado para a simbologia **DataBar Stacked Omnidirectional** e fornece uma carga útil GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Por que isso importa:** O valor enum `EncodeTypes.DatabarStackedOmniDirectional` indica à biblioteca que ela deve gerar um **databar stacked barcode**, que é a variante empilhada da família DataBar omnidirecional. Essa simbologia pode conter até 14 caracteres numéricos, tornando‑a ideal para códigos GTIN‑14.

## Etapa 3: Definir a dimensão X (largura do módulo)

A dimensão X controla a largura da barra mais fina (o módulo). Um valor muito pequeno pode ser renderizado de forma ruim em impressoras de baixa resolução, enquanto um valor muito grande pode exceder o espaço da etiqueta.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dica:** A propriedade `Pixels` é conveniente para testes baseados em tela. Para cenários focados em impressão, use `generator.Parameters.Barcode.XDimension.Millimeters` em vez disso.

## Etapa 4: Ajustar a proporção e salvar a primeira imagem

A **proporção** influencia a relação altura‑largura do código de barras empilhado. O tipo DataBar Stacked Omnidirectional suporta proporções de 10 a 30. Geraremos duas imagens para ilustrar o impacto visual.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

A chamada a `generator.Save` grava um arquivo **PNG** no diretório de trabalho atual. O enum `BarCodeImageFormat.Png` garante compressão sem perdas, o que é ideal para processamento adicional ou incorporação em PDFs.

## Etapa 5: Alterar a proporção para 30 e salvar a segunda imagem

Agora aumentamos a altura das barras empilhadas alterando a proporção para **30**. Isso torna o código de barras mais alto sem mudar a dimensão X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Executar o programa agora produz dois arquivos PNG:

* **DatabarAspectRatio15.png** – um código de barras compacto adequado para etiquetas pequenas.
* **DatabarAspectRatio30.png** – um código de barras mais alto que melhora a confiabilidade da leitura em superfícies de baixo contraste.

Você pode abrir as imagens em qualquer visualizador para verificar se as barras estão corretamente empilhadas e se os dados codificados correspondem à string GS1 original.

## Etapa 6: Verificar o valor codificado (opcional)

Se precisar confirmar que o código de barras realmente representa a string de entrada, você pode decodificá‑lo com a mesma biblioteca:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

O decodificador deve exibir `(01)12345678901231`, provando que o processo de **create databar stacked barcode** preservou os dados.

## Armadilhas comuns e como evitá‑las

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| Código de barras aparece borrado | Dimensão X definida muito baixa para a resolução de saída | Aumente `XDimension.Pixels` ou use `Millimeters` para impressão |
| Scanner relata “símbolo não encontrado” | Proporção fora do intervalo suportado de 10‑30 | Mantenha a proporção entre 10 e 30; 15 e 30 são valores padrão seguros |
| PNG contém marca d'água | Usando a licença de avaliação gratuita do Aspose.BarCode | Adquira uma licença completa ou use a versão de teste apenas para testes |
| Decodificação falha na segunda imagem | O decodificador foi configurado para a simbologia errada | Use `DecodeType.DatabarStackedOmniDirectional` ao ler códigos de barras empilhados |

## Próximos passos

Agora que você pode **create databar stacked barcode** imagens, talvez queira:

* **Incorporar os PNGs em faturas PDF** usando uma biblioteca PDF como **Aspose.PDF**.
* **Gerar códigos de barras sob demanda em uma API web** – retornar os bytes PNG diretamente de um controlador ASP.NET Core.
* **Experimentar outras variantes DataBar** (por exemplo, `DatabarExpanded`, `DatabarLimited`) alterando o enum `EncodeTypes`.
* **Ajustar cores** definindo `generator.Parameters.Barcode.ForeColor` e `BackColor` para designs específicos da marca.

Cada um desses tópicos se baseia nos mesmos conceitos centrais abordados aqui: inicializar `BarcodeGenerator`, configurar parâmetros visuais e salvar o resultado com `BarCodeImageFormat`.

---

### Conclusão

Este tutorial demonstrou como **create databar stacked barcode** imagens em C# usando Aspose.BarCode. Você aprendeu a definir a **dimensão X**, modificar a **proporção do código de barras** e exportar o resultado como arquivos **PNG** com `BarcodeGenerator`. Com a etapa opcional de decodificação, você também pode verificar se os dados GS1 codificados estão corretos. Aplique esses padrões em seus próprios aplicativos de inventário, envio ou ponto de venda, e explore as diversas opções de personalização que a biblioteca oferece. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Ajuste de Altura de Código de Barras Databar Unidimensional](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Gerar imagem de código de barras – Cupom GS1 UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}