---
category: general
date: 2026-08-22
description: Aprenda como criar código de barras PDF417 em C# com um gerador de códigos
  de barras, definir o layout e salvar em PNG. Inclui código completo e dicas para
  projetos de gerador de códigos de barras em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- barcode generator C#
- how to save PNG
- how to generate PDF417
language: pt
lastmod: 2026-08-22
og_description: Crie código de barras PDF417 em C# usando um gerador de códigos de
  barras, personalize o layout e aprenda como salvar em PNG. Siga este tutorial passo
  a passo.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Criar código de barras PDF417 em C# – guia completo para gerar e salvar
  PNG
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create PDF417 barcode in C# with a barcode generator,
    set layout, and save PNG. Includes full code and tips for barcode generator C#
    projects.
  headline: How to create PDF417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Como criar código de barras PDF417 em C# e salvá‑lo como PNG
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 em C# e salvá-lo como PNG

Se você precisa **criar código de barras PDF417** em uma aplicação C#, este tutorial mostra os passos exatos. Você verá como uma biblioteca geradora de códigos de barras C# pode transformar qualquer string em uma imagem PDF417 escaneável e como salvar arquivos PNG sem ferramentas adicionais.

Gerar códigos de barras é comum em logística, bilhetagem e gerenciamento de documentos. Ao final deste guia você terá um programa de console executável que produz um arquivo PNG chamado `Pdf417Layout.png` na pasta que você escolher.

## Pré-requisitos

- .NET 6.0 SDK ou posterior instalado (o código também funciona com .NET Framework 4.7+).
- Visual Studio 2022 ou qualquer editor que possa compilar projetos C#.
- O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca geradora de códigos de barras C# compatível).  
  Instale-o com:

```bash
dotnet add package Aspose.BarCode
```

Nenhuma biblioteca adicional de processamento de imagem é necessária porque o gerador pode gravar PNG diretamente.

## Etapa 1: Configurar um novo projeto de console

Crie um novo projeto de console para que o exemplo permaneça autocontido.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

A pasta `Pdf417Demo` agora contém um arquivo `Program.cs` onde escreveremos o código do código de barras.

## Etapa 2: Importar o namespace do código de barras

Abra `Program.cs` e adicione a diretiva `using` necessária no topo:

```csharp
using Aspose.BarCode.Generation;
```

Este namespace fornece acesso a `BarcodeGenerator`, `EncodeTypes` e ao enum de formato de imagem necessário para **como salvar PNG**.

## Etapa 3: Criar o gerador de código de barras PDF417

O núcleo de **como gerar PDF417** é a classe `BarcodeGenerator`. Passe o tipo de codificação `EncodeTypes.Pdf417` e o texto que deseja codificar.

```csharp
// Step 3: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

`generator` agora contém todas as configurações do código de barras. O layout padrão funciona, mas vamos personalizá-lo na próxima etapa.

## Etapa 4: Definir o layout do código de barras (colunas e linhas)

PDF417 permite controlar o número de colunas (2‑30) e linhas (1‑90). Ajustar esses valores pode melhorar a legibilidade para scanners específicos.

```csharp
// Step 4a: Set the number of columns (2‑30 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Step 4b: Set the number of rows (1‑90 allowed)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

> **Dica profissional:** Se você omitir essas configurações, a biblioteca escolhe valores ótimos automaticamente. No entanto, fixar colunas e linhas fornece dimensões de imagem previsíveis, o que é útil ao incorporar o PNG em um PDF ou em um layout de UI.

## Etapa 5: Salvar o código de barras gerado como imagem PNG

Agora responda **como salvar PNG** chamando `Save`. O método aceita o caminho de destino e o enum de formato de imagem.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Layout.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
```

O arquivo `Pdf417Layout.png` aparece na pasta `bin/Debug/net6.0` do projeto após executar o programa.

## Exemplo completo executável

Abaixo está o arquivo `Program.cs` completo. Copie-o para o projeto criado na **Etapa 1** e execute `dotnet run`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 2️⃣ Define the barcode layout – set columns (2‑30) and rows (1‑90)
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // 9 rows

            // 3️⃣ Choose the output path and save as PNG
            string outputPath = Path.Combine(
                Environment.CurrentDirectory,
                "Pdf417Layout.png");

            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created and saved as PNG at:");
            Console.WriteLine(outputPath);
        }
    }
}
```

### Saída esperada

Ao executar o programa, o console imprime o caminho absoluto do arquivo PNG, e o arquivo contém um código de barras PDF417 nítido que se parece com a imagem abaixo.

![exemplo de criação de código de barras PDF417](image-placeholder.png "Código de barras PDF417 salvo como PNG")

Você pode escanear o PNG com qualquer scanner compatível com PDF417 (apps móveis, leitores de hardware) para verificar que o texto codificado é `"Sample"`.

## Tratamento de casos extremos e armadilhas comuns

| Situação | O que observar | Correção recomendada |
|-----------|-------------------|-----------------|
| **Valores de coluna/linha inválidos** | Valores fora do intervalo 2‑30 (colunas) ou 1‑90 (linhas) causam um `ArgumentException`. | Valide a entrada do usuário antes de atribuir, ou deixe a biblioteca escolher os padrões. |
| **Strings de entrada grandes** | PDF417 pode codificar até 1.850 caracteres, mas strings muito longas aumentam drasticamente o número de linhas necessárias. | Divida os dados em múltiplos códigos de barras ou use um nível de correção de erro mais alto, se necessário. |
| **Permissões de sistema de arquivos** | Salvar em uma pasta somente leitura gera um `UnauthorizedAccessException`. | Grave em `Environment.CurrentDirectory` ou em um caminho gravável pelo usuário, e trate exceções com try/catch. |
| **Pacote NuGet ausente** | A compilação falha com “type or namespace name could not be found”. | Certifique-se de que `Aspose.BarCode` está instalado (`dotnet add package Aspose.BarCode`). |

## Expandindo o exemplo

Agora que você sabe **como criar código de barras PDF417** e **como salvar PNG**, pode explorar esses tópicos relacionados:

- **Barcode generator C#**: Alterar o `EncodeTypes` para `Code128`, `QR` ou outras simbologias.
- **Cores personalizadas**: Use `generator.Parameters.Barcode.ForegroundColor` e `BackgroundColor` para combinar com a identidade visual.
- **Incorporação em PDFs**: Combine o PNG com uma biblioteca PDF (por exemplo, iText7) para criar documentos imprimíveis.
- **Dados dinâmicos**: Recupere o texto de um banco de dados ou entrada do usuário para gerar códigos de barras em tempo real.

## Conclusão

Agora você tem uma solução completa e pronta para produção para **criar código de barras PDF417** em C# e salvar o resultado como um arquivo PNG. O tutorial cobriu cada passo, desde a configuração do projeto até a personalização do layout, e destacou como evitar erros comuns ao usar uma biblioteca geradora de códigos de barras C#.

Sinta-se à vontade para experimentar diferentes configurações de coluna/linha, cores ou até mesmo outros formatos de código de barras. Se encontrar algum problema, revise a seção **como gerar PDF417** ou explore a documentação da biblioteca para recursos avançados. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar código de barras PDF417 – Codificação PDF417 compacto](/barcode/english/net/compact-pdf417-encoding/)
- [Como criar zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}