---
category: general
date: 2026-08-22
description: O tutorial de gerador de código de barras em C# mostra como criar um
  código de barras Macro PDF417 com metadados e salvá-lo como PNG usando o Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: pt
lastmod: 2026-08-22
og_description: O gerador de código de barras C# permite que você produza um código
  de barras Macro PDF417 com metadados completos a nível de arquivo e o exporte como
  PNG. Siga este guia para implementar a solução.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: gerador de código de barras C# – crie códigos de barras Macro PDF417 passo
  a passo
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Como usar um gerador de código de barras C# para Macro PDF417
url: /pt/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar um gerador de código de barras C# para Macro PDF417

Se você precisa de um **barcode generator C#** que possa gerar um símbolo Macro PDF417 com metadados a nível de arquivo, este guia fornece uma solução completa, pronta‑para‑executar. Você verá como configurar a aparência do código de barras, incorporar informações macro como ID do arquivo e contagem de segmentos e, finalmente, salvar o resultado como uma imagem PNG.

O exemplo usa a biblioteca Aspose.BarCode, uma **C# barcode library** amplamente adotada que suporta o conjunto completo de recursos do PDF417. Nenhum serviço externo é necessário, e o código funciona com .NET 6 ou posterior.

## Pré-requisitos

* .NET 6 SDK (ou qualquer versão posterior) instalado.
* Visual Studio 2022, VS Code ou outra IDE C#.
* Uma referência NuGet ao **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Entender a sintaxe básica de C# e o conceito de códigos de barras PDF417 ajudará a seguir as etapas, mas o tutorial explica cada opção de configuração em detalhes.

## O que o tutorial cobre

* Inicializando uma instância de **barcode generator C#** para o formato Macro PDF417.  
* Ajustando parâmetros visuais como X‑dimension e contagem de colunas.  
* Fornecendo campos a nível de arquivo do Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender e terminator.  
* Salvando o símbolo gerado como um arquivo PNG.  
* Dicas para lidar com casos extremos, como arquivos grandes ou timestamps personalizados.

Ao final deste artigo, você terá um programa autônomo que produz um código de barras Macro PDF417 totalmente compatível.

## Etapa 1: Criar a instância do barcode generator C# 

A primeira operação é instanciar `BarcodeGenerator` com o valor enum `EncodeTypes.MacroPdf417` e o texto que você deseja codificar. O construtor também aceita a string de payload, que se torna a parte de dados do código de barras macro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Por que isso importa** – A flag `EncodeTypes.MacroPdf417` indica ao Aspose.BarCode que o símbolo deve ser tratado como um código de barras macro, habilitando os campos extras que se seguem. Sem essa flag, a biblioteca geraria um código de barras PDF417 regular sem metadados a nível de arquivo.

## Etapa 2: Ajustar a aparência básica do código de barras (configurações visuais do PDF417)

A clareza visual é crucial para a leitura confiável. Dois parâmetros comuns são a largura do módulo (`XDimension`) e o número de colunas. Definir esses valores equilibra tamanho e legibilidade.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` controla a largura de cada barra preta/branca. Um valor de **2** funciona bem para a maioria das impressoras de etiquetas.
* `Pdf417.Columns` define quantas colunas o código de barras usará. Cinco colunas produzem um símbolo compacto sem sacrificar a capacidade de dados.

## Etapa 3: Definir informações a nível de arquivo do Macro PDF417

Macro PDF417 estende o formato padrão PDF417 com campos que descrevem como um arquivo grande é dividido em vários segmentos de código de barras. Fornecer esses campos garante que scanners posteriores possam reconstruir o arquivo original.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` deve ser o mesmo para cada segmento pertencente ao mesmo arquivo lógico.
* `MacroPdf417SegmentID` incrementa de **0** até `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` informa ao decodificador quantas peças esperar.
* `MacroPdf417FileName` é opcional, mas útil para identificação legível por humanos.

## Etapa 4: Definir metadados macro adicionais

Além das informações básicas do arquivo, a especificação permite campos extras como checksum, tamanho do arquivo, timestamp, addressee, sender e uma flag terminator. Preencher esses campos melhora a integridade dos dados e a rastreabilidade.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` fornece um checksum CCITT de 16 bits para todo o arquivo; o decodificador pode verificar a integridade após a reconstrução.
* `MacroPdf417FileSize` deve refletir a contagem exata de bytes do arquivo original; valores maiores que `2^31‑1` requerem um campo de 64 bits, que o Aspose trata automaticamente.
* `MacroPdf417TimeStamp` registra quando o código de barras foi gerado. Use UTC para evitar ambiguidades de fuso horário.
* `MacroPdf417Addressee` e `MacroPdf417Sender` são strings de formato livre que podem armazenar informações de roteamento.
* `MacroPdf417Terminator` sinaliza que este é o segmento final; defina como `Set` para a última peça, caso contrário deixe o padrão (`NotSet`).

**Dica para caso extremo** – Se o tamanho do seu arquivo exceder 4 GB, divida o conteúdo em vários segmentos macro e ajuste `SegmentsCount` conforme necessário. A biblioteca gerenciará o campo de tamanho grande sem overflow.

## Etapa 5: Salvar o código de barras como imagem PNG

A etapa final grava o símbolo gerado no disco. PNG preserva as dimensões exatas dos pixels e é amplamente suportado por hardware de leitura.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo onde o processo em execução possa gravar. O enum `BarCodeImageFormat.Png` garante saída sem perdas.

**Por que PNG?** – Formatos raster como PNG mantêm as bordas dos módulos nítidas, o que é essencial para scanners que dependem de bordas de alto contraste. Se precisar de um formato vetorial, o Aspose também suporta `Pdf` e `Svg`.

## Exemplo completo executável

Abaixo está o programa completo que você pode copiar para uma aplicação console. Ele inclui as diretivas `using` necessárias e um método `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Saída esperada

Executar o programa cria um arquivo chamado **MacroPdf417.png** no diretório de trabalho do projeto. Abrir a imagem exibe um código de barras PDF417 compacto com os campos macro incorporados. Ler a imagem com um leitor compatível com PDF417 (por exemplo, ZXing, decodificador Aspose.BarCode) devolve o payload original `"Sample text"` juntamente com os metadados macro.

## Perguntas comuns e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| *E se o código de barras for muito grande para a etiqueta alvo?* | Reduza `XDimension.Pixels` ou aumente `Pdf417.Columns`. Ambos os parâmetros afetam o tamanho geral. |
| *Posso gerar uma imagem vetorial em vez de PNG?* | Sim. Chame `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` para saída escalável. |
| *Como verifico o checksum após a leitura?* | O decodificador Aspose.BarCode valida automaticamente `MacroPdf417Checksum` e relata divergências no objeto `MacroPdf417Result`. |
| *A biblioteca é compatível com .NET Core?* | O pacote NuGet suporta .NET Standard 2.0+, que cobre .NET Core, .NET 5, .NET 6 e versões posteriores. |
| *E se eu precisar incorporar dados binários em vez de texto?* | Converta o payload binário para Base64 ou use a sobrecarga `EncodeTypes.MacroPdf417` que aceita um array de bytes. |

## Dicas profissionais para uso em produção

* **Cache o gerador** – 

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}