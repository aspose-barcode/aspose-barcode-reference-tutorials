---
date: 2025-12-22
description: Aprenda como criar imagem de código de barras com barras vazias usando
  Aspose.BarCode para Java. Este exemplo passo a passo de geração de código de barras
  ajuda você a gerar código de barras em Java rapidamente.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Como criar imagem de código de barras com barras vazias em Java
url: /pt/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Imagem de Código de Barras com Barras Vazias em Java

## Introdução

Em aplicações Java modernas, a capacidade de **criar imagens de código de barras** de forma dinâmica é um recurso valioso para gerenciamento de inventário, sistemas de bilhetagem e muitos outros cenários de negócios. O Aspose.BarCode para Java oferece uma API poderosa e fácil de usar que permite gerar códigos de barras de alta qualidade em apenas algumas linhas de código. Neste tutorial, percorreremos um processo **passo a passo de criação de código de barras** que produz um código de barras com barras vazias (não preenchidas), perfeito para designs que exigem um aspecto oco.

## Respostas Rápidas
- **O que significa “barras vazias”?** As barras são renderizadas sem o preenchimento sólido padrão, proporcionando uma aparência oca.  
- **Qual tipo de código de barras é usado?** Code 128 (uma simbologia linear amplamente suportada).  
- **Preciso de licença para testar?** Uma versão de avaliação gratuita está disponível; uma licença é necessária para uso em produção.  
- **Quais formatos de saída são suportados?** PNG, JPEG, BMP, GIF, TIFF e mais.  
- **É compatível com todas as versões do Java?** Sim, a biblioteca funciona com Java 8 e posteriores.

## O que é criar imagem de código de barras?
Criar uma imagem de código de barras significa converter uma sequência de dados em uma representação visual que leitores podem interpretar. A imagem resultante pode ser salva como PNG, JPEG ou outros formatos comuns e incorporada em PDFs, impressa em etiquetas ou exibida em uma interface de usuário.

## Por que usar a biblioteca Aspose.BarCode para Java?
- **Conjunto de recursos rico** – suporta mais de 50 simbologias de código de barras, incluindo Code 128, QR, DataMatrix e mais.  
- **Controle granular** – propriedades como `FilledBars`, cores, margens e tamanho da imagem são facilmente configuráveis.  
- **Sem dependências externas** – um único arquivo JAR cuida de tudo, simplificando a implantação.  
- **Documentação abrangente** – exemplos, referência de API e fóruns ajudam você a começar rapidamente.

## Pré-requisitos

Antes de iniciarmos a jornada de geração de códigos de barras, certifique‑se de que você possui os seguintes pré‑requisitos:

1. **Ambiente de Desenvolvimento Java** – Garanta que o Java 8+ esteja instalado e que você possua uma IDE ou ferramenta de build compatível.  
2. **Aspose.BarCode para Java** – Baixe e instale a biblioteca Aspose.BarCode para Java a partir da [página de download](https://releases.aspose.com/barcode/java/).  
3. **Diretório de Documentos** – Crie um diretório em seu sistema para armazenar a imagem de código de barras gerada.

## Importar Pacotes

Em seu projeto Java, importe os pacotes necessários para trabalhar com o Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Como Criar Imagem de Código de Barras com Barras Vazias

### Etapa 1: Configurar o Diretório de Recursos

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho real onde você deseja salvar o arquivo de saída.

### Etapa 2: Criar Instância do Gerador de Código de Barras (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Aqui, estamos usando a simbologia **Code 128** — uma das mais populares códigos de barras lineares — tornando este um exemplo clássico de **code128 barcode java**.

### Etapa 3: Definir a Propriedade FilledBars como False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Definir `FilledBars` como `false` instrui o Aspose.BarCode a renderizar as barras como formas vazias (oclusas) em vez de blocos sólidos.

### Etapa 4: Salvar a Imagem do Código de Barras

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

A imagem é salva no formato PNG, mas você pode alterar o enum `BarCodeImageFormat` para gerar JPEG, BMP ou outros tipos suportados.

Repita estas etapas em sua aplicação Java para criar facilmente arquivos de **imagem de código de barras** com barras vazias usando o Aspose.BarCode para Java.

## Conclusão

Em conclusão, este tutorial guiou você por um processo **passo a passo de criação de código de barras** que demonstra como **criar imagens de código de barras** com barras vazias em Java. Com sua API intuitiva e amplas opções de personalização, o Aspose.BarCode simplifica a integração de códigos de barras, tornando‑se um recurso valioso para desenvolvedores que precisam de uma **biblioteca java barcode** confiável.

## Perguntas Frequentes

### O Aspose.BarCode é compatível com todos os ambientes de desenvolvimento Java?
Sim, o Aspose.BarCode foi projetado para integrar‑se perfeitamente com diversos ambientes de desenvolvimento Java.

### Posso personalizar a aparência do código de barras gerado?
Absolutamente! O Aspose.BarCode oferece inúmeras opções de personalização, permitindo que você ajuste o código de barras às suas necessidades específicas.

### Existe uma versão de avaliação disponível para o Aspose.BarCode?
Sim, você pode explorar as capacidades do Aspose.BarCode obtendo uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter suporte para o Aspose.BarCode?
Para quaisquer dúvidas ou assistência, visite o [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Onde posso encontrar documentação detalhada do Aspose.BarCode?
A documentação completa está disponível [aqui](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última Atualização:** 2025-12-22  
**Testado Com:** Aspose.BarCode Java 24.11 (mais recente)  
**Autor:** Aspose  

---