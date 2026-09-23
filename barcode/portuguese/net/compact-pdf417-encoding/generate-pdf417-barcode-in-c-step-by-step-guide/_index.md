---
category: general
date: 2026-08-09
description: Gere código de barras PDF417 em C# rapidamente. Aprenda como gerar PDF417
  com modo compacto, controle de colunas e saída PNG usando a API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: pt
lastmod: 2026-08-09
og_description: Gere código de barras PDF417 em C# com um exemplo conciso. Este guia
  mostra como configurar o modo compacto, definir colunas e salvar o resultado como
  uma imagem PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Gerar código de barras PDF417 em C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Gerar código de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras PDF417 em C# – guia passo a passo

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este tutorial mostra exatamente como fazer isso. Você verá um programa completo e executável que cria um código de barras PDF417 compacto, personaliza seu tamanho e salva a imagem como um arquivo PNG.

Gerar um código de barras PDF417 é uma necessidade comum para bilhetagem móvel, rastreamento de inventário e segurança de documentos. Este guia cobre as opções de configuração essenciais, explica por que cada ajuste é importante e fornece dicas práticas para uso no mundo real.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado  
* Uma IDE C# como Visual Studio 2022 ou Visual Studio Code  
* O pacote NuGet **Aspose.BarCode for .NET** (versão 23.10 ou mais recente)  

Você pode instalar o pacote com o seguinte comando CLI:

```bash
dotnet add package Aspose.BarCode
```

O código abaixo assume que o pacote está referenciado e que você tem permissão de escrita no diretório de saída.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e adicione as diretivas `using` necessárias. Esses namespaces expõem a classe `BarcodeGenerator` e a enumeração de formatos de imagem.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Por que isso importa:** Importar os namespaces corretos garante que o compilador consiga localizar o tipo `BarcodeGenerator` e a enumeração `BarCodeImageFormat`. A falta de um namespace resulta em um erro de compilação, que interrompe o processo de geração do código de barras.

## Etapa 2: Inicializar o `BarcodeGenerator` com codificação PDF417

O construtor `BarcodeGenerator` recebe dois argumentos: a simbologia do código de barras (`EncodeTypes.Pdf417`) e o texto que você deseja codificar. PDF417 suporta uma ampla gama de caracteres, incluindo símbolos Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Explicação:**  
* `EncodeTypes.Pdf417` indica à biblioteca que deve usar o padrão PDF417.  
* O texto de exemplo contém caracteres acentuados e um símbolo de copyright para demonstrar o tratamento de Unicode.  

Se você precisar codificar apenas dados numéricos, pode passar uma string simples como `"1234567890"`.

## Etapa 3: Ajustar a X‑dimensão para maior resolução

A X‑dimensão controla a largura de um único módulo do código de barras (o menor elemento preto ou branco). Definir um valor de pixel menor produz uma imagem de maior resolução.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que ajustá‑la?** Uma X‑dimensão padrão de 3–4 pixels pode gerar um código de barras que parece grosseiro em telas de alta DPI. Reduzi‑la para **2 pixels** equilibra a legibilidade com o tamanho do arquivo, especialmente quando você habilita o modo compacto posteriormente.

## Etapa 4: Configurar o número de colunas

PDF417 permite especificar quantas colunas o código de barras deve conter. Menos colunas tornam o código de barras mais estreito, mas mais alto, enquanto mais colunas criam um código de barras mais largo e curto.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Dica prática:** Para bilhetes móveis que precisam caber em uma etiqueta estreita, uma contagem de colunas de **3–5** funciona bem. Aumente a contagem se você tiver muitos dados e quiser um código de barras mais curto.

## Etapa 5: Habilitar modo compacto para truncar linhas vazias

Modo compacto remove linhas desnecessárias da matriz do código de barras, reduzindo o tamanho geral da imagem sem perder os dados codificados.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Quando usar:** Se você estiver gerando códigos de barras para armazenamento ou transmissão de rede, o modo compacto pode reduzir o arquivo PNG em até 30 %. No entanto, alguns leitores legados podem não suportar PDF417 truncado; teste com o hardware alvo.

## Etapa 6: Salvar o código de barras como imagem PNG

Escolha um caminho de saída e invoque `Save`. A enumeração `BarCodeImageFormat.Png` produz uma imagem sem perdas adequada para a maioria das aplicações.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Verificação do resultado:** Abra o arquivo PNG em qualquer visualizador de imagens. Você deve ver um código de barras denso e de alto contraste que corresponde ao texto de exemplo. Escanear a imagem com um leitor PDF417 (por exemplo, ZXing ou um aplicativo de smartphone) retorna a string original `"Åspóse.Barcóde©"`.

![Generated PDF417 barcode image saved as PNG](compact-pdf417.png "Generated PDF417 barcode in C#")

*The image above demonstrates the final output of the tutorial’s code.*

## Exemplo completo e executável

Juntando todas as peças, aqui está um programa de console completo que você pode copiar, colar e executar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Saída esperada

Executar o programa imprime:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

O arquivo `CompactPdf417.png` contém um código de barras PDF417 compacto que codifica a string Unicode fornecida. Escanear a imagem com um leitor PDF417 padrão retorna o texto exato.

## Variações comuns e casos de borda

| Situação | Ajuste | Motivo |
|-----------|------------|--------|
| **Carga de dados mais longa** (por exemplo, > 150 caracteres) | Aumentar `generator.Parameters.Barcode.Pdf417.Columns` para 6‑8 | Mais colunas evitam que o código de barras fique excessivamente alto. |
| **Necessidade de fundo transparente** | Usar `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG transparente integra melhor em sobreposições de UI. |
| **Gerando JPEG para web** | Alterar o formato para `BarCodeImageFormat.Jpeg` e opcionalmente definir `ImageQuality` | JPEG reduz o tamanho do arquivo ao custo da fidelidade sem perdas. |
| **Manipulação de entrada nula ou vazia** | Proteger a entrada antes de criar o gerador: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Previne exceções em tempo de execução e garante códigos de barras significativos. |

## Dicas para uso em produção

* **Manipulação de exceções:** Envolva a lógica de geração em um bloco `try/catch` para registrar erros como espaço em disco insuficiente ou parâmetros inválidos.  
* **Desempenho:** Reutilize uma única instância de `BarcodeGenerator` ao gerar muitos códigos de barras com as mesmas configurações; apenas atualize a propriedade `CodeText` entre as gravações.  
* **Segurança:** Quando o texto codificado contém informações sensíveis, considere criptografá‑lo antes de passá‑lo ao gerador e descriptografá‑lo após a leitura.  

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# usando a biblioteca Aspose.BarCode, configurar o modo compacto, controlar a contagem de colunas e exportar o resultado como uma imagem PNG. Este tutorial cobriu cada passo, desde a configuração do projeto até o tratamento de casos de borda, oferecendo uma solução pronta para uso em aplicações baseadas em códigos de barras.

Em seguida, explore tópicos relacionados como **criar códigos QR em C#**, **geração em lote de códigos de barras** e **integração de leitura de códigos de barras com aplicativos móveis**. Cada um desses se baseia nos mesmos fundamentos do `BarcodeGenerator` que você acabou de dominar.

Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar códigos de barras PDF417 – Codificação PDF417 Compacta](/barcode/english/net/compact-pdf417-encoding/)
- [Como criar código de barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}