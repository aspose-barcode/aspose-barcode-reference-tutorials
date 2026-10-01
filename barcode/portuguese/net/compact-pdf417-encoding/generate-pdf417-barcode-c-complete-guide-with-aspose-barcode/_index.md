---
category: general
date: 2026-08-03
description: Gerar código de barras PDF417 em C# usando Aspose.BarCode. Aprenda passo
  a passo como adicionar metadados Macro PDF417 e salvar como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: pt
lastmod: 2026-08-03
og_description: Gerar código de barras PDF417 em C# com Aspose.BarCode. Este tutorial
  mostra como incorporar metadados Macro PDF417 e exportar o resultado como uma imagem
  PNG.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Gerar código de barras PDF417 C# – tutorial passo a passo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Gerar código de barras PDF417 C# – guia completo com Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar PDF417 barcode C# – guia completo

Se você precisa **gerar PDF417 barcode C#** para um sistema de logística ou gerenciamento de documentos, este tutorial mostra exatamente como fazer isso com Aspose.BarCode. Você verá como configurar o código de barras, incorporar metadados Macro PDF417 e salvar o resultado como uma imagem PNG em apenas algumas linhas de código.

Gerar um código de barras PDF417 em C# geralmente significa lidar com informações extras, como identificadores de arquivos, números de segmento ou timestamps. Este guia cobre esses detalhes, para que você não precise procurar em documentação dispersa. Ao final do artigo, você terá um programa pronto‑para‑executar que produz uma imagem de código de barras Macro PDF417 compatível.

## O que você precisará

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
- Aspose.BarCode para .NET (v23.9 ou mais recente) – instale via NuGet `Install-Package Aspose.BarCode`
- Um ambiente de desenvolvimento como Visual Studio 2022 ou Visual Studio Code
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** Use a versão mais recente do Aspose.BarCode para se beneficiar de correções de bugs e suporte às especificações mais recentes do PDF417.

## Como gerar PDF417 barcode C# com Aspose.BarCode

O processo consiste em quatro etapas lógicas. Cada etapa está encapsulada em um bloco de código claro para que você possa copiar, colar e executar imediatamente.

### Etapa 1: Criar um gerador de código de barras Macro PDF417

Primeiro, instancie `BarcodeGenerator` com o enum `EncodeTypes.MacroPdf417`. O construtor também aceita o texto que você deseja codificar – neste exemplo usamos uma string que contém caracteres Unicode para demonstrar suporte a largura total.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Por que isso importa*: O tipo `MacroPdf417` indica ao Aspose.BarCode que o símbolo deve ser tratado como um macro barcode, que pode transportar metadados adicionais ao nível de arquivo. Sem essa flag, os campos extras definidos posteriormente seriam ignorados.

### Etapa 2: Ajustar a aparência básica do código de barras

Em seguida, defina o tamanho visual do código de barras. `XDimension.Pixels` controla a largura de um único módulo (o menor quadrado preto/branco), enquanto `Pdf417.Columns` influencia a forma geral definindo o número de colunas.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Por que isso importa*: Um `XDimension` menor gera uma imagem de maior resolução, o que é útil quando o código de barras precisa ser escaneado a partir de uma tela. Alterar a contagem de colunas pode ajudar a encaixar o código de barras em espaço limitado sem sacrificar a capacidade de dados.

### Etapa 3: Preencher metadados Macro PDF417

Macro PDF417 permite incorporar informações ao nível de arquivo que muitos sistemas de back‑office dependem (por exemplo, ID do arquivo, ID do segmento, timestamp). As propriedades a seguir ilustram os campos mais comuns.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Por que isso importa*: Cada campo mapeia diretamente para um segmento da especificação do macro barcode. Por exemplo, `MacroPdf417FileID` identifica unicamente o arquivo lógico, enquanto `MacroPdf417SegmentsCount` informa ao scanner quantas partes esperar. Fornecer metadados precisos garante que os sistemas downstream possam reconstruir o documento original sem erro.

### Etapa 4: Salvar a imagem do código de barras como PNG

Finalmente, chame `Save` para gravar o código de barras no disco. PNG é sem perdas, tornando‑o ideal para escaneamento de alta qualidade.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Por que isso importa*: O enum `BarCodeImageFormat.Png` garante que o arquivo de saída contenha exatamente os dados de pixel que você configurou. Se precisar de um formato vetorial para dimensionamento, substitua `Png` por `Svg` – Aspose.BarCode oferece suporte a isso nativamente.

#### Saída esperada

Executar o programa completo cria um arquivo chamado **ExtPDF417Meta.png**. A imagem mostra um símbolo PDF417 denso e de múltiplas linhas que inclui o texto “Åspóse.Barcóde©” e os metadados macro que você forneceu. Escanear o código de barras com um leitor compatível com PDF417 devolve o texto original mais um bloco de dados estruturado contendo o ID do arquivo, ID do segmento, timestamp e outros campos.

![Captura de tela do PDF417 barcode gerado](/images/pdf417-example.png){: .center-image alt="exemplo de saída de geração de PDF417 barcode C#"}

## Código-fonte completo (pronto para copiar e colar)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Como verificar o resultado

1. Abra `ExtPDF417Meta.png` em qualquer visualizador de imagens.  
2. Use um aplicativo de scanner PDF417 (por exemplo, *Zebra Scanner* ou *BarCode Reader* no Android/iOS).  
3. Confirme que a carga decodificada inclui o texto original e um bloco semelhante a JSON com os campos macro que você definiu.

## Perguntas comuns e tratamento de casos extremos

| Pergunta | Resposta |
|----------|----------|
| **Posso gerar uma imagem vetorial em vez de PNG?** | Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg`. O restante do código permanece inalterado. |
| **E se meus dados excederem a capacidade padrão?** | Aumente `Pdf417.Columns` ou defina `Pdf417.Rows` manualmente. Valores maiores permitem mais codewords por segmento. |
| **Unicode é suportado no texto codificado?** | Absolutamente. O exemplo usa “Åspóse.Barcóde©”. Aspose.BarCode muda automaticamente para codificação UTF‑8 quando necessário. |
| **Preciso assinar uma licença para Aspose.BarCode?** | Para produção você deve aplicar uma licença para evitar a marca d'água de avaliação. Chame `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` antes de criar o gerador. |
| **Como lidar com erros ao salvar o arquivo?** | Envolva a chamada `Save` em um bloco try/catch e registre `IOException` ou `BarCodeException` para solução de problemas. |

## Conclusão

Agora você sabe como **gerar PDF417 barcode C#** usando Aspose.BarCode, incorporar metadados completos Macro PDF417 e exportar o resultado como uma imagem PNG de alta qualidade. As etapas — criar o gerador, ajustar a aparência, preencher os metadados e salvar a imagem — formam um padrão reutilizável que você pode adaptar para faturas, etiquetas de envio ou qualquer cenário que exija dados ricos em códigos de barras.

### Próximos passos

- Experimente outros formatos de código de barras (por exemplo, QR, Code128) alterando `EncodeTypes`.  
- Explore `Pdf417.ErrorCorrectionLevel` para melhorar a confiabilidade da leitura em baixa iluminação.  
- Integre a imagem gerada em um relatório PDF usando Aspose.PDF para automação de documentos de ponta a ponta.  

Sinta-se à vontade para modificar os campos de metadados para atender às suas regras de negócio, e deixe a geração de códigos de barras se tornar uma parte integrada de suas aplicações C#. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar Barcode – Compact PDF417 com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como criar um Barcode – PDF417 Compacto com Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [biblioteca de barcode java – Adicionar barcode ao PDF usando Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}