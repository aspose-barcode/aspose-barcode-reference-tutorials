---
category: general
date: 2026-11-23
description: Crie código de barras planetário postal em C# com Aspose.BarCode. Aprenda
  como gerar o código de barras planetário, definir a dimensão X e salvar barras preenchidas
  ou vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: pt
lastmod: 2026-11-23
og_description: Crie código de barras planetário postal em C# e aprenda a gerar código
  de barras planetário com Aspose.BarCode. Siga o exemplo completo para produzir barras
  preenchidas e vazias.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Como criar o código de barras Postal Planet em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Como criar código de barras Postal Planet em C#
url: /pt/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras postal Planet em C#

Se você precisa **criar código de barras postal Planet** em uma aplicação .NET, este guia mostra exatamente **como gerar o código de barras Planet** usando a biblioteca Aspose.BarCode. Você verá como configurar a dimensão X, alternar entre barras preenchidas e vazias e salvar as imagens no formato PNG.

Gerar um código de barras Planet é comum para serviços postais que exigem símbolos de alta densidade e legíveis por máquina. Ao final deste tutorial você terá dois arquivos PNG — um com barras sólidas e outro com barras ocas — prontos para integração em qualquer fluxo de trabalho de mailing.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior instalado.
* Visual Studio 2022 (ou qualquer editor C#) configurado para desenvolvimento .NET.
* Uma licença NuGet ativa para **Aspose.BarCode for .NET**. Instale o pacote com:

```bash
dotnet add package Aspose.BarCode
```

Nenhum serviço externo adicional é necessário; a biblioteca realiza toda a codificação localmente.

## Etapa 1 – criar código de barras postal Planet

A primeira operação é instanciar um `BarcodeGenerator` para a simbologia **Planet** e fornecer os dados a serem codificados. A string de dados deve ser numérica e ter até 12 dígitos, conforme a especificação postal.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Criar o gerador aloca todas as estruturas internas necessárias para a renderização. O valor do enum `EncodeTypes.Planet` seleciona o algoritmo de codificação correto para o formato postal.

## Etapa 2 – definir a dimensão X para melhor visibilidade

A dimensão X define a largura de um único módulo (o menor elemento da barra). Um valor de 4 pixels fornece uma representação visual clara sem ampliar a imagem geral.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Ajustar a dimensão X é essencial quando o código de barras será impresso em mídia de baixa resolução. A mesma configuração será reutilizada para a versão de barras vazias, mantendo ambas as imagens consistentes.

## Etapa 3 – salvar o código de barras com barras preenchidas

Por padrão, o gerador renderiza **barras preenchidas** (módulos pretos sólidos). Salvar a imagem é uma única chamada de método que grava o arquivo PNG no disco.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Substitua `YOUR_DIRECTORY` pelo caminho real onde deseja que os arquivos de saída sejam gravados. A enumeração `BarCodeImageFormat.Png` garante compressão sem perdas, ideal para processamento posterior.

## Etapa 4 – criar outro gerador Planet para barras vazias

Para produzir uma versão que usa **barras vazias** (módulos brancos sobre fundo preto), você precisa de uma segunda instância de `BarcodeGenerator`. Reutilizar a mesma string de dados garante que ambas as imagens representem o mesmo código postal.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Criar um gerador separado isola a propriedade `FilledBars`, permitindo alternar o estilo visual sem afetar a primeira imagem.

## Etapa 5 – configurar o gerador para renderizar barras vazias

A flag `FilledBars` inverte o modo de renderização. Definir como `false` indica à biblioteca que desenhe as barras como vazias (transparentes) mantendo o fundo sólido.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Manter a dimensão X idêntica à versão preenchida garante que ambos os arquivos PNG tenham as mesmas dimensões, simplificando os cálculos de layout em modelos de impressão.

## Etapa 6 – salvar o código de barras que renderiza barras vazias

Por fim, grave a imagem de barras vazias no disco. O mesmo formato PNG é usado, mas você pode mudar para JPEG ou BMP alterando o valor de `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Neste ponto você tem dois arquivos:

* `PostalPlanetFilledBars.png` – barras pretas sólidas.
* `PostalPlanetEmptyBars.png` – barras ocas sobre fundo preto.

Ambos atendem à especificação postal para a simbologia Planet.

## Código‑fonte completo

Juntando todas as etapas, obtém‑se um aplicativo console compacto que pode ser executado diretamente.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compile e execute o programa:

```bash
dotnet run
```

O console imprime *Barcodes generated successfully.* e os dois arquivos PNG aparecem na pasta do projeto.

## Saída esperada

Abaixo está uma representação visual da imagem com barras preenchidas. A contraparte de barras vazias é idêntica, exceto que as barras são transparentes.

![Exemplo de um código de barras postal Planet criado com barras preenchidas](postal-planet-filled.png)

*Texto alternativo da imagem:* **Exemplo de um código de barras postal Planet criado com barras preenchidas** (contém a palavra‑chave principal).

Ambas as imagens têm 150 × 150 pixels por padrão, mas você pode controlar o tamanho geral com os parâmetros `ImageWidth` e `ImageHeight` caso seja necessária outra resolução.

## Variações opcionais

### Alterar o formato da imagem

Se o seu sistema downstream preferir JPEG, substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG introduz artefatos de compressão, portanto use‑o apenas quando o tamanho do arquivo for uma restrição crítica.

### Redimensionar o código de barras

Você pode ampliar o código de barras preservando a largura do módulo ajustando a propriedade `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Valores de DPI mais altos melhoram a qualidade de impressão em impressoras a laser.

### Usar uma cor de fundo personalizada

O fundo pode ser definido com:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Isso é útil para testes visuais, mas deve ser evitado em etiquetas postais de produção, que exigem fundo branco.

## Perguntas frequentes

**Isso funciona com .NET Core?**  
Sim. A biblioteca Aspose.BarCode tem como alvo .NET Standard 2.0, que é compatível com .NET 5, .NET 6 e .NET Core 3.1.

**E se a string de dados contiver caracteres não numéricos?**  
Códigos de barras Planet aceitam apenas entrada numérica. Inserir letras ou símbolos dispara uma `BarcodeException`. Valide a entrada antes de criar o gerador.

**Posso gerar um código de barras em memória sem gravar no disco?**  
Use o método `GenerateBarCodeImage` para obter um objeto `System.Drawing.Image`, então envie‑o diretamente para uma resposta ou banco de dados.

## Conclusão

Agora você sabe como **criar código de barras postal Planet** em C# e entende **como gerar o código de barras Planet** com estilos de barra preenchida e vazia. O tutorial cobriu todo o fluxo de trabalho — desde a inicialização do gerador, configuração da dimensão X, alternância da flag `FilledBars`, até a gravação dos arquivos PNG. Experimente formatos de imagem, configurações de DPI e cores de fundo para adaptar o código de barras ao seu sistema de mailing específico.

Para o próximo passo, explore outras simbologias postais como **POSTNET** ou **Intelligent Mail** usando a mesma API Aspose.BarCode. Ajustar parâmetros como `EncodeTypes.Postnet` segue o mesmo padrão demonstrado aqui, permitindo que você construa uma suíte completa de geração de códigos de barras em uma única base de código.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar código de barras planet vazio, gerar código de barras postal em C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Como definir a largura e gerar um código de barras Planet em C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Gerar código de barras postal em C# – Guia completo com código de barras Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}