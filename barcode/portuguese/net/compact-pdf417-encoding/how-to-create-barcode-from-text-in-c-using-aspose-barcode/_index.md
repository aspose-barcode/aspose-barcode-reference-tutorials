---
category: general
date: 2026-10-28
description: Crie código de barras a partir de texto em C# com Aspose.BarCode. Aprenda
  a gerar imagem de código de barras PDF417, definir colunas, ajustar a dimensão X
  e habilitar o modo compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: pt
lastmod: 2026-10-28
og_description: Crie código de barras a partir de texto em C# usando Aspose.BarCode.
  Este tutorial mostra como gerar uma imagem de código de barras PDF417, personalizar
  tamanho, colunas e modo compacto.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Crie um código de barras a partir de texto em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Como criar código de barras a partir de texto em C# usando Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras a partir de texto em C# usando Aspose.BarCode

Se você precisa **criar código de barras a partir de texto** em uma aplicação .NET, este guia fornece uma solução pronta‑para‑executar. Você verá como **gerar imagens de código de barras PDF417**, controlar a largura do módulo, a contagem de colunas e ativar o modo compacto sem sair do seu IDE.

O tutorial cobre tudo o que é necessário para **gerar código de barras C#**, desde a instalação da biblioteca até a gravação do arquivo PNG final. Ao final, você poderá incorporar um código de barras PDF417 de alta densidade em relatórios, ingressos ou etiquetas de inventário.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer editor que suporte .NET)  
* Acesso à internet para baixar o pacote NuGet Aspose.BarCode for .NET  

Esses itens são suficientes para compilar e executar o exemplo no Windows, Linux ou macOS.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

A biblioteca que alimenta a geração de códigos de barras é **Aspose.BarCode for .NET**. Instale‑a usando a CLI do .NET:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém a classe `BarcodeGenerator` usada ao longo deste tutorial.

## Etapa 2: Criar um projeto de console e adicionar o código

Crie um novo projeto de console e substitua o `Program.cs` gerado pelo código a seguir. O programa demonstra como **criar código de barras a partir de texto** e salvá‑lo como uma **imagem de código de barras PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Por que cada linha importa

* **`EncodeTypes.Pdf417`** seleciona a simbologia PDF417, que é ideal para codificar grandes quantidades de dados em um formato bidimensional.  
* **`XDimension.Pixels = 2`** reduz a largura do módulo, tornando o código de barras mais denso e mais adequado para espaços limitados.  
* **`Pdf417.Columns = 3`** controla o número de colunas de dados verticais; uma contagem menor gera um código de barras mais alto, porém mais estreito.  
* **`Pdf417.Truncate = true`** ativa o modo compacto, recortando colunas não utilizadas no lado direito. Esta é a configuração chave que transforma um PDF417 regular em uma **imagem de código de barras PDF417 compacta**.  

## Etapa 3: Compilar e executar o projeto

Execute os seguintes comandos no diretório do projeto:

```bash
dotnet build
dotnet run
```

Quando o programa terminar, você verá uma mensagem no console confirmando a localização do arquivo. Abra `CompactPdf417.png` com qualquer visualizador de imagens para verificar o resultado.

**Saída esperada** – um PNG de alto contraste mostrando um código de barras PDF417 compacto que codifica a string `Åspóse.Barcóde©`. Escanear a imagem com um leitor de código de barras padrão retorna o texto original, confirmando que **gerar código de barras pdf417** foi bem‑sucedido.

## Etapa 4: Personalizando o código de barras para diferentes cenários

Embora o exemplo use uma contagem fixa de colunas e X‑dimension, você pode adaptar o gerador para outros requisitos:

| Cenário | Ajuste |
|----------|------------|
| Carga de dados maior | Aumentar `Pdf417.Columns` ou definir `Pdf417.Rows` manualmente |
| Maior confiabilidade de leitura | Aumentar `XDimension.Pixels` para 3 ou 4 |
| Formato de imagem diferente | Substituir `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` |
| Fundo transparente | Definir `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Essas opções permitem que você **gere soluções de código de barras C#** que se adequam a aplicativos móveis, relatórios de desktop ou serviços web.

## Etapa 5: Lidando com casos extremos e boas práticas

* **Suporte a Unicode** – O gerador codifica automaticamente caracteres Unicode, mas assegure que sua string de origem esteja codificada em UTF‑8 se você a ler de um arquivo.  
* **Texto grande** – PDF417 pode codificar até 1.850 caracteres alfanuméricos. Se você ultrapassar esse limite, a biblioteca lança uma exceção; divida os dados em vários códigos de barras ou troque para uma simbologia de maior capacidade.  
* **Tratamento de erros** – Envolva o código de geração em um bloco `try/catch` para capturar `BarCodeException` e fornecer uma mensagem de erro amigável.  
* **Desempenho** – Gerar muitos códigos de barras em um loop se beneficia de reutilizar uma única instância de `BarcodeGenerator` e atualizar apenas `CodeText` entre as iterações.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Listagem completa do código-fonte

Abaixo está o programa completo e autocontido que você pode copiar para `Program.cs`. Nenhum arquivo adicional é necessário.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Executar este programa cria a **imagem de código de barras pdf417** mostrada na ilustração abaixo.

![Código de barras PDF417 compacto criado a partir de texto usando C#](/images/compact-pdf417.png){.img-fluid alt="exemplo de criação de código de barras a partir de texto mostrando uma imagem de código de barras PDF417 compacto"}

*Descrição da imagem: O arquivo PNG exibe um código de barras PDF417 compacto que codifica a string “Åspóse.Barcóde©”.*  

## Conclusão

Agora você sabe como **criar código de barras a partir de texto** em C# e produzir uma **imagem de código de barras PDF417** com dimensões personalizadas e modo compacto. O exemplo demonstra as etapas essenciais para **gerar código de barras C#**, lidar com dados Unicode e ajustar parâmetros visuais para diferentes cenários de implantação.

Em seguida, explore tópicos relacionados como **gerar QR code em C#**, **adicionar código de barras a documentos PDF**, ou **incorporar códigos de barras em APIs ASP.NET Core**. Cada um desses se baseia nos mesmos fundamentos do `BarcodeGenerator` abordados aqui.

Feliz codificação, e aproveite integrar códigos de barras em suas soluções .NET!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar código de barras PDF417 em C# – Criar código de barras PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Como gerar código de barras PDF417 com Aspose.BarCode em C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Como criar imagem de código de barras PDF417 em C# – guia completo](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}