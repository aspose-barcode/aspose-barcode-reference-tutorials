---
date: 2026-09-28
description: Aprenda como criar 2d matrix barcode com Aspose.BarCode for .NET – um
  guia passo a passo para gerar códigos de barras DotCode com extended code text.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Configuração de Extended Code Text do DotCode
og_description: Aprenda a criar 2d matrix barcode usando Aspose.BarCode for .NET.
  Este guia mostra passo a passo como gerar códigos de barras DotCode com extended
  code text.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Criar 2d matrix barcode com Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Como criar 2d matrix barcode via Aspose.BarCode for .NET
url: /pt/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras matricial 2d via Aspose.BarCode para .NET

## Introdução

No universo da geração e gerenciamento de códigos de barras, o Aspose.BarCode para .NET destaca‑se como uma solução versátil que suporta **mais de 50 formatos de entrada e saída** e pode processar documentos com centenas de páginas sem carregar o arquivo inteiro na memória. Seja para rastreamento de produtos, controle de inventário ou aplicações ricas em dados, criar um **código de barras matricial 2d** como o DotCode com codetexto estendido permite incorporar cargas úteis textuais e binárias em um símbolo quadrado compacto. Este tutorial orienta passo a passo na construção desse codetexto estendido e na renderização da imagem final.

## Respostas rápidas
- **O que significa “criar codetexto estendido dotcode”?** Significa construir um código de barras DotCode que inclui FNC1, ECICodetext, texto simples e separadores de símbolo em uma única carga útil estendida.  
- **Qual biblioteca é necessária?** Aspose.BarCode para .NET.  
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico.

## Como criar codetexto estendido dotcode

Carregue seu projeto, defina o diretório, construa o codetexto estendido e gere a imagem – tudo em menos de uma dúzia de linhas de código. A resposta direta a seguir resume todo o processo:

Carregue o `BarcodeGenerator` com `EncodeTypes.DotCode`, construa o codetexto estendido usando `DotCodeExtendedCodetextBuilder` (adicionando FNC1, ECICodetext, texto simples e separadores FNC3), então chame `Save` para gravar um arquivo PNG. Essa sequência cria um código de barras matricial 2d totalmente compatível em uma única chamada.

## O que é codetexto estendido dotcode?

O **codetexto estendido dotcode** é uma string composta que combina múltiplos segmentos de dados — como identificadores FNC1, ECICodetext, texto simples e separadores FNC3 — em uma única carga útil que o DotCode pode decodificar. Ele permite a codificação de texto multilíngue, blobs binários e dados estruturados dentro de um único código de barras matricial 2d, tornando‑o ideal para cadeias de suprimentos, saúde e cenários de IoT.

## Por que usar Aspose.BarCode para esta tarefa?

O Aspose.BarCode processa **até 500 páginas por segundo** em hardware de servidor típico e suporta **mais de 30 simbologias de código de barras**, incluindo DotCode. Sua API `GetExtendedCodetext` garante o posicionamento correto dos caracteres de controle, eliminando erros de concatenação manual de strings e assegurando conformidade com a ISO/IEC 24724. Além disso, oferece correção de erro embutida e tratamento automático da zona silenciosa, reduzindo a necessidade de ajustes manuais.

## Pré‑requisitos

- **Aspose.BarCode para .NET** – faça o download na [documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/).  
- Um ambiente de desenvolvimento .NET (Visual Studio 2022 ou posterior recomendado).  
- Opcional: um arquivo de licença temporário para avaliação.

## Importar namespaces

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Esses namespaces expõem a classe `BarcodeGenerator` e o auxiliar `DotCodeExtendedCodetextBuilder` necessários para o exemplo.

```csharp
using Aspose.BarCode.Generation;
```

Agora que cobrimos os pré‑requisitos, vamos detalhar o processo de geração do DotCode Extended Code Text em um guia passo a passo.

## Etapa 1: definir o caminho do diretório

Especifique onde o PNG gerado será salvo. Use um caminho absoluto ou relativo que sua aplicação possa gravar.

```csharp
string path = "Your Directory Path";
```

Substitua `"Your Directory Path"` pelo caminho real em seu sistema.

## Etapa 2: criar codetexto estendido dotcode

A classe `DotCodeExtendedCodetextBuilder` monta os vários segmentos em uma única string de codetexto estendido.

Para criar o DotCode Extended Code Text, siga estas sub‑etapas:

### 2.1 adicionar identificador de formato fnc1

O identificador de formato FNC1 marca o início de um novo campo de dados. É obrigatório para símbolos DotCode compatíveis com GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 adicionar ecicodetext

O ECICodetext codifica caracteres especiais e texto internacional. Neste exemplo codificamos `"犬Right狗"` usando UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 adicionar codetexto simples

Você também pode adicionar texto simples ao DotCode Extended Code Text. Aqui, adicionamos `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 adicionar separador de símbolo fnc3

O separador de símbolo FNC3 separa diferentes seções do código, melhorando a legibilidade para os scanners.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 adicionar inicialização do leitor fnc3

Esta etapa adiciona as informações de Inicialização do Leitor FNC3, que indicam ao scanner como interpretar os dados subsequentes.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 gerar codetexto

Agora gere o DotCode Extended Codetext chamando o método `GetExtendedCodetext` no objeto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Etapa 3: gerar imagem dotcode

Renderize a imagem do código de barras a partir do codetexto estendido.

#### 3.1 inicializar gerador de código de barras

A classe `BarcodeGenerator` é o objeto central do Aspose.BarCode para criar qualquer código de barras. Você a instancia com a simbologia desejada (`EncodeTypes.DotCode`) e o codetexto estendido que acabou de montar.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Por fim, chame `Save` para gravar o arquivo PNG no disco. A imagem está pronta para ser incorporada em relatórios, aplicativos móveis ou etiquetas impressas.

## Problemas comuns e soluções

- **Codificação incorreta** – Certifique‑se de usar `ECIEncodings.UTF8` ao adicionar texto multilíngue; caso contrário, os caracteres podem aparecer corrompidos.  
- **Erros de acesso ao arquivo** – Verifique se a aplicação tem permissão de gravação no diretório de destino.  
- **Zona silenciosa ausente** – Defina `gen.Parameters.Barcode.Margin` se os scanners exigirem espaço branco extra ao redor do símbolo.

## Perguntas frequentes

**P: Posso usar o código de barras gerado em um aplicativo móvel?**  
R: Sim. A imagem PNG produzida pelo gerador pode ser incorporada em iOS, Android ou qualquer aplicativo móvel multiplataforma.

**P: E se eu precisar codificar dados binários em vez de texto?**  
R: Use o método `AddECICodetext` com o `ECIEncodings` apropriado (por exemplo, `ECIEncodings.Base64`) para incorporar cargas binárias.

**P: Como altero o tamanho do código de barras sem afetar a legibilidade?**  
R: Ajuste a propriedade `XDimension.Pixels`; valores maiores aumentam o tamanho dos módulos, enquanto valores menores tornam o código mais compacto.

**P: Existe uma maneira de adicionar uma zona silenciosa ao redor do código de barras?**  
R: Sim. Defina `gen.Parameters.Barcode.Margin` para especificar a zona silenciosa desejada em pixels.

**P: A biblioteca suporta .NET 8?**  
R: As versões mais recentes do Aspose.BarCode são compatíveis com .NET 8; basta referenciar a versão apropriada do pacote NuGet.

Se precisar de mais orientações ou tiver dúvidas, visite a [documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/) ou participe da comunidade no [fórum de suporte do Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2026-09-28  
**Testado com:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar código de barras DotCode .NET (Modo Automático) com Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/net/datamatrix-barcode-configuration/)
- [Como criar código de barras Aztec com Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}