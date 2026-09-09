---
date: 2026-04-12
description: Aprenda como criar códigos de barras Code128 com barras vazias em Java
  usando Aspose.BarCode. Este guia mostra como gerar imagens de códigos de barras
  Java rapidamente.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Gerando código de barras com barras vazias
second_title: Aspose.BarCode Java API
title: Como criar código de barras Code128 com barras vazias em Java
url: /pt/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Código de Barras Code128 com Barras Vazias em Java

## Introdução

Integrar a geração de códigos de barras em aplicações Java é uma necessidade frequente, seja ao construir sistemas de inventário, plataformas de bilhetagem ou soluções de ponto de venda. Com **Aspose.BarCode for Java**, você pode **criar imagens de código de barras Code128** em apenas algumas linhas de código. Neste tutorial, percorreremos os passos para **gerar imagens de código de barras Java** que apresentam barras vazias (não preenchidas), dando a você controle total sobre o estilo visual do código de barras.

## Respostas Rápidas
- **Qual biblioteca?** Aspose.BarCode for Java  
- **Caso de uso principal?** Criar códigos de barras Code128 com barras vazias para designs de UI personalizados  
- **Pré-requisitos?** Java JDK 8+, Aspose.BarCode JAR, acesso de escrita a uma pasta para a imagem de saída  
- **Tempo típico de implementação?** 5‑10 minutos para um exemplo básico  
- **Posso personalizar cores?** Sim – a API fornece opções extensas de estilo  

## O que é um código de barras Code128?

Code128 é uma simbologia de código de barras linear de alta densidade que codifica todo o conjunto de caracteres ASCII. É amplamente utilizada em logística, transporte e varejo porque pode representar dados alfanuméricos de forma compacta. Por padrão, Aspose.BarCode renderiza as barras Code128 como retângulos sólidos; definir a propriedade **FilledBars** como `false` as transforma em barras vazias (contorno), o que é útil para branding estilístico.

## Por que usar Aspose.BarCode para Java?

- **Conjunto de recursos rico** – suporta mais de 50 tipos de códigos de barras, incluindo QR, DataMatrix e PDF417.  
- **Sem dependências externas** – um único JAR funciona em qualquer runtime Java.  
- **Controle granular** – você pode ajustar a largura das barras, cores, fontes e a propriedade `FilledBars`.  
- **Multiplataforma** – funciona no Windows, Linux e macOS sem bibliotecas nativas.

## Pré-requisitos

Antes de começar, certifique-se de que você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8 ou posterior instalado e `JAVA_HOME` configurado.  
2. **Aspose.BarCode para Java** – faça o download do JAR mais recente na [página de download](https://releases.aspose.com/barcode/java/).  
3. **Diretório de Documentos** – uma pasta no seu computador onde a imagem do código de barras gerado será salva.

## Importar Pacotes

No seu projeto Java, importe as classes que você precisará para trabalhar com Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Essas importações dão acesso ao gerador de códigos de barras, à enumeração de formatos de imagem e ao tratamento de exceções.

## Etapa 1: Configurar o Diretório de Recursos

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto da pasta que você criou nos pré-requisitos. É aqui que o arquivo PNG será gravado.

## Etapa 2: Criar Instância do Gerador de Código de Barras Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Aqui instanciamos `BarcodeGenerator` com a simbologia **CODE_128** e o texto de exemplo `"TEXT"`. Este é um **exemplo de gerador de código de barras Java** que você pode adaptar a qualquer string que precise codificar.

## Etapa 3: Definir a Propriedade FilledBars como False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Ao definir `FilledBars` como `false`, o código de barras gerado exibirá barras vazias em vez de sólidas, alcançando o efeito visual desejado.

## Etapa 4: Salvar a Imagem do Código de Barras

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

O método `save` grava o código de barras no diretório especificado no formato PNG. Você pode mudar `BarCodeImageFormat.PNG` para `JPG`, `BMP` ou `TIFF` se for necessário um tipo de imagem diferente.

## Casos de Uso Comuns

- **Branding personalizado** – barras vazias podem ser sobrepostas com padrões ou cores de fundo.  
- **Recursos prontos para impressão** – gerar PNGs de alta resolução para inclusão em faturas ou etiquetas de envio.  
- **Geração dinâmica** – criar códigos de barras em tempo real em serviços web ou aplicações desktop.

## Dicas de Solução de Problemas

- **Caminho inválido** – garanta que `dataDir` termine com um separador de arquivos (`/` ou `\\`) ou concatene usando `File.separator`.  
- **Licença necessária** – uma versão de avaliação funciona para avaliação, mas uma licença completa é necessária para produção.  
- **Caracteres não suportados** – Code128 suporta todo o conjunto ASCII; evite caracteres Unicode a menos que você troque para outra simbologia.

## Conclusão

Você aprendeu agora como **criar imagens de código de barras Code128** com barras vazias usando Aspose.BarCode for Java. Esta abordagem simples permite gerar gráficos de códigos de barras personalizáveis rapidamente, seja construindo uma ferramenta de inventário desktop ou uma API baseada na nuvem.

## Perguntas Frequentes

### O Aspose.BarCode é compatível com todos os ambientes de desenvolvimento Java?
Sim, Aspose.BarCode foi projetado para integrar-se perfeitamente a qualquer IDE ou sistema de build Java, incluindo Maven, Gradle e projetos JAR simples.

### Posso personalizar a aparência do código de barras gerado?
Absolutamente! Além de `FilledBars`, você pode modificar cores, largura das barras, margens e até adicionar texto legível usando a API extensa.

### Existe uma versão de avaliação disponível para o Aspose.BarCode?
Sim, você pode explorar as capacidades do Aspose.BarCode obtendo uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter suporte para o Aspose.BarCode?
Para quaisquer dúvidas ou assistência, visite o [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Onde posso encontrar documentação detalhada do Aspose.BarCode?
A documentação abrangente está disponível [aqui](https://reference.aspose.com/barcode/java/).

**Perguntas Adicionais**

**Q: Como gerar uma imagem de código de barras em um formato diferente, como JPEG?**  
A: Altere o segundo argumento de `save` para `BarCodeImageFormat.JPEG`.

**Q: Posso gerar múltiplos códigos de barras em um loop?**  
A: Sim – instancie um novo `BarcodeGenerator` dentro do seu loop ou reutilize a mesma instância com um novo `CodeText`.

---

**Last Updated:** 2026-04-12  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}