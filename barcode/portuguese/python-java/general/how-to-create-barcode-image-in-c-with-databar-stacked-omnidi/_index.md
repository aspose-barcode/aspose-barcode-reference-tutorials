---
category: general
date: 2026-11-17
description: Crie uma imagem de código de barras em C# usando a biblioteca Barcode
  Generator. Siga este guia para aprender a gerar códigos DataBar empilhados omnidirecionais
  passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: pt
lastmod: 2026-11-17
og_description: Crie uma imagem de código de barras em C# com um exemplo conciso.
  Aprenda a gerar códigos de barras DataBar empilhados omnidirecionais usando a biblioteca
  Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Criar imagem de código de barras em C# – guia completo para códigos DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar imagem de código de barras em C# com DataBar empilhado omnidirecional
url: /pt/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar **criar imagem de código de barras** em C# com DataBar stacked omnidirectional

Se você precisa **criar imagem de código de barras** em uma aplicação .NET, este tutorial mostra uma solução completa, pronta‑para‑executar. Você verá exatamente como usar a API **Barcode Generator C#** para produzir um DataBar stacked omnidirectional, que é o formato abordado na consulta *how to generate databar*.

O guia percorre cada passo necessário — desde a instalação da biblioteca até o ajuste fino da proporção — para que você possa copiar o código, executá‑lo e obter imediatamente um arquivo PNG. Nenhuma consulta a documentação externa é necessária.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado (o exemplo também funciona com .NET Framework 4.7+)
* Um ambiente de desenvolvimento como Visual Studio 2022 ou VS Code
* O pacote NuGet **Aspose.BarCode for .NET** (a biblioteca que fornece `BarcodeGenerator`)

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

> **Dica profissional:** Use a flag `--version` para fixar o pacote na versão estável mais recente, por exemplo, `dotnet add package Aspose.BarCode --version 23.9`.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e faça referência aos namespaces necessários. Esta etapa prepara o ambiente para o código **barcode generator c#** que segue.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

O namespace `Aspose.BarCode.Generation` contém a classe `BarcodeGenerator`, que é o núcleo do fluxo de trabalho **criar imagem de código de barras**.

## Etapa 2: Inicializar o BarcodeGenerator para um DataBar stacked omnidirectional

O gerador precisa de duas informações: o tipo de código de barras e os dados a serem codificados. O valor do enum `EncodeTypes.DatabarStackedOmniDirectional` seleciona a variante exata de DataBar necessária para cenários *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Por que isso importa:* Selecionar o valor correto de `EncodeTypes` garante que a imagem resultante esteja em conformidade com as especificações da indústria para leitura em varejo.

## Etapa 3: Definir o tamanho do módulo (dimensão X) em pixels

A densidade visual de um código de barras é controlada pela dimensão X. Definir um valor de pixel sensato garante que a imagem seja legível tanto na tela quanto na impressão.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se precisar de um código de barras maior para impressão de baixa resolução, aumente o valor em pixels conforme necessário.

## Etapa 4: Ajustar a proporção do DataBar para tornar as linhas mais altas

O DataBar stacked omnidirectional consiste em duas linhas. Modificar o `AspectRatio` permite controlar a altura de cada linha, o que pode ser útil quando o tamanho padrão parece apertado.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Uma proporção de `15` é uma escolha comum para etiquetas de varejo; você pode experimentar valores entre `10` e `20` para atender a requisitos de layout específicos.

## Etapa 5: Salvar o código de barras gerado como imagem PNG

Por fim, grave a imagem no disco. PNG é sem perdas, tornando‑a ideal para processamento posterior ou incorporação em PDFs.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Executar o programa gera um arquivo chamado **DatabarAspectRatio15.png** no diretório de saída do projeto. Abrir o arquivo mostra um código de barras limpo, de alto contraste, pronto para leitura.

### Saída esperada

A imagem salva tem aparência semelhante à ilustração abaixo (o visual real foi omitido por brevidade).

*Texto alternativo para a imagem de exemplo:* **criar imagem de código de barras** – um arquivo PNG exibindo um DataBar stacked omnidirectional com proporção de 15.

## Variações comuns e casos extremos

| Situação | Ajuste |
|-----------|------------|
| **Comprimento de carga útil diferente** | Substitua a string GTIN por qualquer conteúdo válido de DataBar (por exemplo, `(01)01234567890123`). |
| **Resolução mais alta para impressões grandes** | Aumente `XDimension.Pixels` para 4 ou 5 e, opcionalmente, defina `Resolution` em `Parameters.Image`. |
| **Outros formatos DataBar** | Use `EncodeTypes.DatabarStacked` para uma variante empilhada de duas linhas sem capacidade omnidirecional. |
| **Salvar como JPEG** | Altere `BarCodeImageFormat.Png` para `BarCodeImageFormat.Jpeg` e, opcionalmente, defina `Quality`. |

Essas variações respondem à pergunta mais ampla *how to generate databar* ao mostrar que o mesmo gerador pode ser reconfigurado para múltiplas famílias de DataBar.

## Recapitulação do código‑fonte completo

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Copie o código para `Program.cs`, restaure os pacotes NuGet e execute `dotnet run`. O console confirmará a localização da imagem, e você poderá abrir o PNG para verificar o resultado **criar imagem de código de barras**.

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C# usando a biblioteca Barcode Generator e como **gerar DataBar** com controle preciso sobre tamanho e proporção. O exemplo completo demonstra todas as configurações necessárias — desde a inicialização do `BarcodeGenerator` até a exportação de um arquivo PNG — para que você possa integrar a criação de códigos de barras em qualquer aplicação .NET sem pesquisas adicionais.

### O que vem a seguir?

* Explore outras simbologias de código de barras com `EncodeTypes` (por exemplo, QR, Code128) – uma extensão natural do fluxo **barcode generator c#**.
* Combine a imagem gerada com relatórios PDF ou Excel usando Aspose.PDF ou Aspose.Cells.
* Ajuste cor, adicione margens ou incorpore o código de barras em uma API web para geração sob demanda.

Sinta‑se à vontade para experimentar os parâmetros, e deixe o código servir como uma base confiável para todos os seus projetos futuros relacionados a códigos de barras. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}