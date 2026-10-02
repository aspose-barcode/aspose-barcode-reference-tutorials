---
category: general
date: 2026-09-13
description: Aprenda como criar códigos de barras PDF417 em C# e gerar imagens de
  códigos de barras PDF417 rapidamente com um exemplo completo e executável.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- generate pdf417 barcode
- create barcode image c#
language: pt
lastmod: 2026-09-13
og_description: Crie código de barras PDF417 em C# e gere imagens de código de barras
  PDF417 com este tutorial conciso. Siga o exemplo completo e obtenha um arquivo PNG
  instantaneamente.
og_image_alt: Screenshot of a PDF417 barcode generated in C#
og_title: Criar código de barras pdf417 em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create pdf417 barcode in C# and generate pdf417 barcode
    images quickly with a complete, runnable example.
  headline: How to create pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Como criar código de barras pdf417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras pdf417 em C# – guia passo a passo

Se você precisa **criar código de barras pdf417** em uma aplicação .NET, este tutorial mostra exatamente como fazer isso. Você verá como gerar imagens de código de barras pdf417 em C# usando a biblioteca Aspose.BarCode e terminará com um arquivo PNG pronto para uso.

Criar um código de barras é uma necessidade comum para sistemas de inventário, soluções de bilhetagem ou verificação de documentos. Ao final deste guia você será capaz de **criar imagens de código de barras pdf417** programaticamente, personalizar parâmetros chave como largura do módulo, colunas e linhas, e salvar o resultado como PNG sem ferramentas externas.

## O que você precisará

- .NET 6.0 ou superior (o código também funciona no .NET Framework 4.7+)
- Uma referência ao pacote NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Conhecimento básico de sintaxe C# e um ambiente de desenvolvimento (Visual Studio, VS Code ou Rider)

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console (ou adicione o código a um existente) e importe os namespaces necessários. Esta etapa prepara o ambiente para a geração do código de barras.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enumeration
```

**Por que isso importa:** Importar `Aspose.BarCode.Generation` lhe dá acesso ao `BarcodeGenerator`, a classe que realmente cria o código de barras. O namespace `Aspose.BarCode` contém o enum de formato de imagem que você usará ao **salvar a imagem do código de barras**.

## Etapa 2: Inicializar o BarcodeGenerator com configurações PDF417

O construtor `BarcodeGenerator` recebe dois argumentos: a simbologia do código de barras (`EncodeTypes.Pdf417`) e o texto que você deseja codificar. Aqui codificamos a string `"Layout demo"`.

```csharp
// Step 2: Initialise generator for PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
{
    // All further configuration goes inside this block
```

**Por que isso importa:** Selecionar `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia 2‑D PDF417, ideal para armazenar grandes quantidades de dados e amplamente suportada em logística e cartões de identificação.

## Etapa 3: Configurar a X‑dimension (largura do módulo)

A X‑dimension controla a largura de cada módulo individual (o menor elemento preto ou branco). Defini‑la em pixels lhe dá controle preciso sobre o tamanho final da imagem.

```csharp
    // Step 3: Set module width to 2 pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Uma X‑dimension menor gera um código de barras mais compacto, enquanto um valor maior facilita a leitura à distância. Ajuste esse valor com base no ambiente de digitalização da sua aplicação.

## Etapa 4: Definir o layout – colunas e linhas

PDF417 permite especificar quantas colunas e linhas o código de barras deve usar. Isso influencia tanto o tamanho quanto a capacidade de dados.

```csharp
    // Step 4: Define layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // Number of data columns
    barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // Number of rows (height)
```

**Por que isso importa:** Controlar colunas e linhas permite afinar o código de barras para dimensões específicas de etiqueta ou restrições de impressão. Muitas linhas podem deixar o código de barras muito alto; poucas colunas podem reduzir a capacidade de dados.

## Etapa 5: Salvar o código de barras como imagem PNG

Finalmente, grave o código de barras gerado no disco. O método `Save` aceita o caminho de saída e o formato de imagem desejado.

```csharp
    // Step 5: Save as PNG
    barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
}
```

Ao executar o programa, um arquivo chamado **LayoutPdf417.png** aparece no diretório de saída. Abrir o arquivo mostra um código de barras PDF417 limpo que codifica o texto `"Layout demo"`.

### Saída esperada

![Screenshot of a PDF417 barcode generated in C#](placeholder-image.png "PDF417 barcode created with C#")

*Texto alternativo da imagem:* **Captura de tela de um código de barras PDF417 gerado em C#** (corresponde a `og_image_alt` para acessibilidade).

## Exemplo completo, executável

Juntando todas as peças, aqui está um aplicativo de console autocontido que você pode copiar, colar e executar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise generator for PDF417 with the desired text
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
            {
                // Set the X‑dimension (module width) in pixels
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Define layout: 4 columns and 9 rows
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
                barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

                // Save the generated barcode as a PNG image
                barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode created successfully: LayoutPdf417.png");
        }
    }
}
```

**Como verificar:** Após executar o programa, navegue até a pasta que contém o binário compilado. Você deverá ver `LayoutPdf417.png`. Abra-o com qualquer visualizador de imagens; o código de barras deve estar claramente visível e ser escaneável com leitores PDF417 padrão.

## Variações comuns e casos de borda

| Situação | O que mudar | Por quê |
|-----------|----------------|-----|
| **Maior densidade de dados** | Aumentar `Columns` (ex.: para 6) e opcionalmente reduzir `Rows` | Mais colunas compactam mais dados horizontalmente, útil para etiquetas estreitas. |
| **Área de impressão grande** | Aumentar `XDimension.Pixels` (ex.: para 4) | Módulos maiores facilitam a leitura à distância. |
| **Formato de imagem diferente** | Usar `BarCodeImageFormat.Jpeg` ou `Bmp` na chamada `Save` | Escolha um formato que corresponda ao seu fluxo de processamento posterior. |
| **Cores de primeiro plano/fundo personalizadas** | Definir `barcodeGenerator.Parameters.Barcode.ForeColor` e `BackColor` | Melhora a legibilidade em fundos coloridos ou ao imprimir em mídia escura. |
| **Codificação de caracteres Unicode** | Passar uma string Unicode (ex.: `"Пример"`). PDF417 suporta Unicode nativamente. | Permite texto internacional sem configuração extra. |

**Dica profissional:** Sempre teste o código de barras gerado com o hardware de scanner real que você pretende usar. Alguns scanners têm requisitos mínimos de tamanho de módulo; ajustar `XDimension` adequadamente evita erros de leitura.

## Perguntas frequentes

**P: Isso funciona com .NET Core?**  
Sim. O pacote `Aspose.BarCode` tem como alvo .NET Standard 2.0, que é compatível com .NET Core, .NET 5+, e .NET Framework.

**P: Posso gerar múltiplos códigos de barras em um loop?**  
Com certeza. Coloque o bloco `using` dentro de um `foreach` e altere o texto ou os parâmetros de layout a cada iteração.

**P: E se eu precisar incorporar o código de barras em um PDF?**  
Depois de gerar o PNG, você pode carregá‑lo em uma biblioteca PDF (ex.: iText7 ou Aspose.PDF) e posicioná‑lo em uma página. A etapa de geração do código de barras permanece a mesma.

## Conclusão

Agora você sabe como **criar código de barras pdf417** em C# usando Aspose.BarCode. O tutorial abordou a inicialização do gerador, a configuração da X‑dimension, a definição de colunas e linhas e o salvamento do resultado como arquivo PNG. Com essa base você pode **gerar gráficos pdf417** para etiquetas de inventário, cartões de embarque ou qualquer cenário que exija códigos de barras 2‑D compactos e de alta capacidade.

Em seguida, experimente **criar imagem de código de barras c#** para outras simbologias como QR, Code‑128 ou DataMatrix, substituindo `EncodeTypes.Pdf417` pelo tipo desejado. Experimente cores, níveis de correção de erro e incorpore a imagem diretamente em PDFs ou relatórios para expandir ainda mais a solução.

Happy coding!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Create PDF417 Barcode in C# – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}