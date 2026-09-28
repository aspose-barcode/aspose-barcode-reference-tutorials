---
date: 2026-08-28
description: Aprenda como criar imagem de código de barras java com Aspose Barcode
  Java, definir símbolos de início e fim CODABAR e gerar arquivos PNG sem marcas d'água.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Configurando símbolos de início e fim
og_description: Criar imagem de código de barras java usando Aspose Barcode Java.
  Este guia mostra como definir símbolos de início/fim CODABAR e exportar PNG sem
  marcas d'água.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Criar imagem de código de barras java – guia de símbolos de início/fim
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Criar imagem de código de barras com símbolos de início/fim
url: /pt/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Criar imagem de código de barras com símbolos de início/fim

## Introdução

Neste tutorial abrangente você **criará imagem de código de barras java** com Aspose Barcode Java e aprenderá **como definir símbolos de início e fim** para códigos de barras CODABAR. Seja você quem está construindo um terminal de ponto de venda, um sistema de gerenciamento de armazém ou qualquer aplicação que precise de geração confiável de códigos de barras, personalizar esses símbolos permite atender a especificações legadas enquanto mantém o código limpo e fácil de manter. Vamos percorrer cada passo, explicar por que cada configuração importa e mostrar como produzir uma imagem PNG que não contém marca d'água de avaliação.

## Respostas rápidas
- **Qual biblioteca cria imagens de código de barras em Java?** Aspose.BarCode for Java.  
- **Posso personalizar os símbolos de início/fim?** Sim, usando `setCodabarStartSymbol` e `setCodabarStopSymbol`.  
- **Qual tipo de código de barras é usado neste exemplo?** CODABAR.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial para uso não‑trial.  
- **Qual formato de saída é gerado?** Imagem PNG salva no disco.

## O que é Aspose Barcode Java?

Aspose Barcode Java é uma **biblioteca Java independente de dependências que gera mais de 70 simbologias de códigos de barras**, desde códigos 1D clássicos como CODABAR até códigos 2D modernos como QR e DataMatrix. Ela lida com toda a codificação de baixo nível, permitindo que você se concentre na lógica de negócios enquanto garante conformidade com os padrões da indústria.

## Por que usar Aspose Barcode Java para geração de códigos de barras sem marca d'água?

Carregue sua licença primeiro, e a biblioteca produz imagens limpas—sem sobreposição “Aspose Evaluation”. Ela também oferece **controle granular** (símbolos de início/fim, cores, tamanhos) e **compatibilidade multiplataforma** (qualquer runtime Java, incluindo Android). Com suporte para **50+ formatos de saída** e a capacidade de transmitir imagens diretamente para respostas HTTP, é a escolha ideal para criação de códigos de barras de alta performance e qualidade de produção.

## Pré-requisitos

1. **Java Development Kit (JDK)** – Instale o JDK mais recente a partir da [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Baixe-o a partir do [link de download](https://releases.aspose.com/barcode/java/).

Ter esses itens prontos garante que você possa **criar imagem de código de barras java** sem componentes ausentes.

## Importar pacotes

Os imports a seguir dão acesso às classes principais necessárias para a geração de códigos de barras:

O enum `CodabarSymbol` define os caracteres de início/fim permitidos para códigos de barras CODABAR.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia passo a passo

### Como definir a pasta de saída para a imagem do código de barras?

Especifique a pasta onde o arquivo PNG será gravado. Usar `Paths.get` torna o código portátil entre Windows, macOS e Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Como criar um gerador de código de barras para CODABAR?

A classe `BarcodeGenerator` cria uma imagem de código de barras para uma simbologia e dados fornecidos.  

Instancie `BarcodeGenerator` com a simbologia CODABAR e a string de dados que deseja codificar.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Como definir o símbolo de início CODABAR?

`setCodabarStartSymbol` define o caractere que marca o início de um código de barras CODABAR.  

Chame `setCodabarStartSymbol` e passe um dos caracteres suportados (`A`, `B`, `C`, `D`). Neste exemplo usamos `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Como definir o símbolo de fim CODABAR?

`setCodabarStopSymbol` define o caractere que marca o fim de um código de barras CODABAR.  

Use `setCodabarStopSymbol` com o caractere de parada correspondente—`D` neste caso.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Como salvar o código de barras gerado como um arquivo PNG?

O enum `SaveFormat` especifica o formato de arquivo para salvar a imagem do código de barras.  

Chame o método `save`, fornecendo o nome completo do arquivo e o valor do enum `SaveFormat.Png`. A imagem é gravada sem marca d'água assim que uma licença válida é aplicada.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Armadilhas comuns e dicas

A classe `License` carrega um arquivo de licença Aspose para habilitar o modo de recursos completos.

- **Caminho de diretório incorreto** – Certifique-se de que `dataDir` termina com o separador de arquivos apropriado ou construa o caminho com `Paths.get`.  
- **Caracteres de início/fim não suportados** – CODABAR aceita apenas `A`, `B`, `C` ou `D`. Fornecer qualquer outro valor gera uma `IllegalArgumentException`.  
- **Licença não aplicada** – No modo trial a saída contém uma marca d'água. Carregue seu arquivo de licença com `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` antes de criar o gerador para evitar isso.  
- **Geração em larga escala** – Ao gerar milhares de códigos de barras, reutilize uma única instância de `BarcodeGenerator` e altere apenas o texto do código para reduzir a sobrecarga de criação de objetos.

## Perguntas frequentes

### Posso usar Aspose.BarCode para Java em um projeto comercial?

Sim. Adquira uma licença comercial [purchase a commercial license](https://purchase.aspose.com/buy) para remover a marca d'água de avaliação e obter suporte técnico completo.

### Existe uma versão de avaliação gratuita disponível?

Absolutamente. Baixe a versão de avaliação [download the trial version](https://releases.aspose.com/) para avaliar todos os recursos antes de comprar.

### Como posso obter suporte para Aspose.BarCode para Java?

Visite o fórum Aspose.BarCode [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) para ajuda da comunidade, ou abra um ticket de suporte através do portal da sua conta Aspose.

### Como obtenho uma licença temporária para testes?

Você pode solicitar uma licença temporária de 30 dias [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). Isso permite executar testes semelhantes a produção sem uma compra completa.

### Quais outras simbologias de código de barras o Aspose.BarCode suporta?

A biblioteca suporta **70+ simbologias**, incluindo Code128, EAN‑13, QR, DataMatrix, PDF417 e muitas outras. Consulte a lista completa na documentação oficial.

## Perguntas adicionais (compatível com IA)

**Q:** Quais formatos de imagem posso exportar além de PNG?  
**A:** Aspose.BarCode suporta PNG, JPEG, BMP, GIF e TIFF. Escolha o formato desejado alterando o valor do enum `SaveFormat` na chamada `save`.

**Q:** Posso gerar imagens de código de barras em memória sem gravar no disco?  
**A:** Sim. Chame `generator.save(OutputStream)` para escrever diretamente em um stream—ideal para APIs web que retornam a imagem como resposta HTTP.

**Q:** A biblioteca funciona no Android?  
**A:** A versão Java roda no Android, mas você deve incluir manualmente as dependências necessárias (não há Maven Central para Android). A API principal permanece idêntica.

## Conclusão

Você aprendeu agora como **criar imagem de código de barras java** e definir precisamente **símbolos de início/fim** para um código de barras CODABAR usando Aspose Barcode Java. Essa abordagem oferece a flexibilidade necessária para atender a especificações legadas enquanto mantém sua base de código limpa e fácil de manter. Explore personalizações adicionais—como alterar cores, adicionar texto legível ou mudar para outras simbologias—consultando a referência oficial da API em [documentation](https://reference.aspose.com/barcode/java/).

---

**Última atualização:** 2026-08-28  
**Testado com:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Validar soma de verificação e criar código de barras Codabar em Java com Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Criar código de barras com Aspose - Definir dimensões X e Y em Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Como gerar código de barras java: criar uma imagem de código de barras exata](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}