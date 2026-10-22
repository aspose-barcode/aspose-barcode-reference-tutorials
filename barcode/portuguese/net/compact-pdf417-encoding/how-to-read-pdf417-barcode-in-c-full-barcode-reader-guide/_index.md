---
category: general
date: 2026-10-21
description: Como ler o código de barras PDF417 em C# usando um leitor de código de
  barras a partir de uma imagem. Siga este exemplo passo a passo de leitor de código
  de barras em C# para uma decodificação confiável.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: pt
lastmod: 2026-10-21
og_description: Como ler código de barras PDF417 em C# com um exemplo completo de
  leitor de códigos de barras. Aprenda a decodificar imagens Macro PDF417 e acessar
  todos os campos estendidos.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Como ler código de barras PDF417 em C# – guia detalhado
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Como ler código de barras PDF417 em C# – guia completo do leitor de códigos
  de barras
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras PDF417 em C# – guia completo de leitor de códigos de barras

Se você precisa de **how to read PDF417 barcode** em uma aplicação .NET, este guia mostra uma solução pronta‑para‑executar. Você verá como **read barcode from image C#** usando uma biblioteca popular de códigos de barras e obter todos os atributos Macro PDF417 sem ferramentas adicionais.

O tutorial cobre tudo o que é necessário para um **C# barcode reader example**: configuração do projeto, walkthrough do código e dicas para lidar com casos extremos. Ao final, você pode colar o código em um projeto console e começar a decodificar imagens PDF417 instantaneamente.

## O que você precisará

Antes de começar, confirme os seguintes pré‑requisitos:

| Pré-requisito | Motivo |
|--------------|--------|
| .NET 6.0 SDK ou posterior | Fornece o runtime para o aplicativo console em C# |
| Visual Studio 2022 (ou qualquer IDE C#) | Permite a criação fácil de projetos e depuração |
| Aspose.BarCode for .NET (pacote NuGet) | Fornece as classes `BarCodeReader` e `DecodeType` |
| Um arquivo de imagem Macro PDF417 (ex.: `MacroPdf417.png`) | Serve como entrada para a decodificação |

Você pode instalar a biblioteca com a CLI do dotnet:

```bash
dotnet add package Aspose.BarCode
```

## Como ler código de barras PDF417 a partir de uma imagem em C#

O núcleo do fluxo de trabalho de **read barcode from image C#** consiste em três ações:

1. Inicialize o `BarCodeReader` para o `DecodeType` específico.  
2. Itere através da coleção `BarCodeResult` retornada.  
3. Acesse os campos básicos e estendidos do PDF417.

Abaixo está o código completo e executável. Salve‑o como `Program.cs` dentro de um projeto console.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Explicação de cada passo

* **Passo 1 – Inicialize o leitor**  
  O construtor `BarCodeReader` recebe o caminho do arquivo de imagem e um `DecodeType`. `DecodeType.MacroPdf417` indica à biblioteca que procure símbolos Macro PDF417, que contêm metadados adicionais além dos códigos de barras PDF417 comuns.

* **Passo 2 – ReadBarCodes()**  
  Este método devolve um `IEnumerable<BarCodeResult>` que pode conter múltiplos códigos de barras se a imagem possuir mais de um. O laço `foreach` garante que cada símbolo detectado seja processado.

* **Passo 3 – Informação básica**  
  `CodeTypeName` identifica o formato do código de barras (ex.: “MacroPDF417”). `CodeText` contém a string de dados bruta codificada no símbolo.

* **Passo 4 – Campos estendidos**  
  Macro PDF417 adiciona um conjunto de propriedades estendidas em `barcodeResult.Extended.Pdf417`. Esses campos expõem dados de nível de arquivo como `FileID`, `SegmentID` e `FileName`. Acessá‑los diretamente permite reconstruir documentos multi‑segmento ou verificar a integridade.

#### Saída esperada no console

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Os valores exatos refletem o conteúdo codificado em seu `MacroPdf417.png`. Se a imagem contiver um único segmento, `SegmentsCount` será 1 e `SegmentID` será 0.

## Configure o ambiente do leitor de código de barras C#

Um **C# barcode reader example** confiável depende de uma configuração de projeto limpa:

1. **Crie um novo projeto console**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Adicione o pacote Aspose.BarCode** (conforme mostrado anteriormente).  
3. **Copie o arquivo de imagem** para a pasta do projeto ou referencie‑o com um caminho absoluto.  
4. **Compile e execute**  
   ```bash
   dotnet run
   ```

Se a compilação falhar com um erro de referência ausente, verifique se as instruções `using Aspose.BarCode;` correspondem à versão do pacote instalado. A API da biblioteca é estável entre .NET 6 e .NET 8, portanto você pode atualizar o runtime sem alterações no código.

## Decodifique o código de barras Macro PDF417

Ao chamar `ReadBarCodes()`, a biblioteca executa internamente:

* **Pré‑processamento de imagem** – converte o bitmap em uma matriz binária, corrigindo rotação e ruído.  
* **Detecção de padrão** – procura pelos padrões de início/fim do PDF417 e extrai a largura do módulo.  
* **Correção de erros** – aplica códigos Reed‑Solomon para recuperar codewords danificados.  
* **Extração de macro** – analisa o cabeçalho de segmento PDF417 estendido e preenche o objeto `Extended.Pdf417`.

Entender esse pipeline ajuda a decidir quando ajustar opções do decodificador. Por exemplo, se suas imagens têm baixo contraste, você pode habilitar a propriedade `ReadQuality` do `BarCodeReader` (disponível em versões posteriores) para melhorar as taxas de detecção.

## Interprete os campos estendidos do PDF417

Os campos estendidos mapeiam diretamente para a especificação Macro PDF417:

| Campo | Significado |
|-------|-------------|
| `MacroPdf417FileID` | Identificador único para todo o arquivo em todos os segmentos |
| `MacroPdf417SegmentID` | Índice baseado em zero do segmento atual |
| `MacroPdf417SegmentsCount` | Número total de segmentos que compõem o arquivo |
| `MacroPdf417FileName` | Nome original do arquivo armazenado durante a codificação |
| `MacroPdf417Checksum` | Checksum de 16 bits para verificação de integridade |
| `MacroPdf417FileSize` | Tamanho do arquivo original em bytes |
| `MacroPdf417TimeStamp` | Timestamp UTC quando o código de barras foi gerado |
| `MacroPdf417Addressee` | Destinatário pretendido do documento |
| `MacroPdf417Sender` | Originador do documento |
| `MacroPdf417Terminator` | String literal “END” que marca o último segmento |

Você pode usar esses valores para reconstruir um PDF multi‑segmento, verificar se nenhum segmento está faltando ou registrar informações de auditoria para fins de conformidade.

## Problemas comuns e solução de problemas

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| Nenhuma saída aparece | Caminho da imagem incorreto ou formato não suportado | Use um caminho absoluto e assegure que o arquivo seja PNG/JPEG suportado pelo Aspose.BarCode |
| `CodeType` mostra “PDF417” em vez de “MacroPDF417” | A imagem contém um símbolo PDF417 regular, não uma variante macro | Verifique se o código de barras de origem foi codificado com extensões Macro PDF417 |
| Alguns campos estão vazios | O código de barras foi gerado sem esses campos macro | Codifique o código de barras com um payload macro completo, ou trate valores nulos no código |
| O decodificador lança `ArgumentException` | `DecodeType` especificado incorretamente | Altere `DecodeType.MacroPdf417` para `DecodeType.Pdf417` se precisar apenas de dados PDF417 padrão |

**Dica profissional:** Envolva o acesso aos campos em verificações de nulidade se você antecipar códigos de barras não‑macro. O objeto `Extended.Pdf417` devolve valores padrão (ex.: `0` para campos numéricos) quando os dados estão ausentes.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Recapitulação do exemplo completo em funcionamento

Juntando tudo, o programa final consiste nas diretivas `using`, no método `Main` e no laço de quatro passos mostrado anteriormente. Nenhum arquivo de configuração adicional é necessário. Compile e execute o projeto para ver a saída no console com todas as propriedades Macro PDF417.

## Conclusão

Agora você sabe **how to read PDF417 barcode** em C# usando um conciso **C# barcode reader example**. O guia conduziu você pela configuração do ambiente, implementação do código e interpretação de cada campo estendido Macro PDF417. Com essa base, você pode integrar a leitura de códigos de barras em sistemas de inventário, fluxos de trabalho de gerenciamento de documentos ou back‑ends móveis.

### Próximo

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler PDF417 em C# – guia completo de leitor de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Como decodificar PDF417 em C# com um exemplo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Como criar imagem de código de barras PDF417 em C# com opções Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}