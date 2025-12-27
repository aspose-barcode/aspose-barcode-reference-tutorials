---
date: 2025-12-27
description: Aprenda como adicionar legenda a imagens de código de barras em Java
  usando Aspose.BarCode. Este exemplo de gerador de código de barras em Java mostra
  como criar imagens de código de barras em Java sem esforço.
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: Como adicionar legenda ao código de barras em Java usando Aspose.BarCode
url: /pt/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Legenda a um Código de Barras em Java Usando Aspose.BarCode

## Introdução

Se você precisa **adicionar legenda** a um código de barras para melhorar a legibilidade e a identidade visual, está no lugar certo. Neste tutorial vamos percorrer os passos exatos para adicionar legendas acima e abaixo de uma imagem de código de barras usando Aspose.BarCode para Java. Ao final, você terá um código de barras totalmente estilizado que não apenas codifica dados, mas também exibe texto útil — perfeito para rótulos de produtos, sistemas de inventário ou qualquer cenário onde os usuários se beneficiem de contexto adicional.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.BarCode para Java.  
- **Posso mudar a fonte e a cor?** Sim — tanto a família da fonte da legenda quanto a cor do texto são personalizáveis.  
- **Quais tipos de código de barras funcionam?** Todas as simbologias suportadas pelo Aspose.BarCode (por exemplo, CODE_128, QR, DataMatrix).  
- **Preciso de licença para testes?** Um teste gratuito está disponível; uma licença comercial é necessária para produção.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos após a inclusão da biblioteca.

## O que é uma legenda em um código de barras?
Uma legenda é um texto simples que aparece acima ou abaixo do gráfico do código de barras. Ela pode transmitir nomes de produtos, preços ou qualquer outra informação que complemente os dados codificados.

## Por que adicionar legendas com Aspose.BarCode?
- **Experiência do usuário aprimorada:** Os usuários podem ler instantaneamente o significado de um código de barras sem precisar escaneá‑lo.  
- **Consistência da marca:** Você pode aplicar suas próprias fontes, cores e alinhamento para combinar com os guias de estilo corporativo.  
- **Controle total:** A API do Aspose.BarCode permite alternar a visibilidade, definir o alinhamento e estilizar cada legenda de forma independente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Java Development Kit (JDK) instalado.  
- Biblioteca Aspose.BarCode para Java baixada e adicionada ao seu projeto. Você pode encontrar o link de download [aqui](https://releases.aspose.com/barcode/java/).  
- Uma IDE como IntelliJ IDEA ou Eclipse.

## Importar Pacotes

No seu arquivo fonte Java, importe as classes necessárias do Aspose.BarCode e a classe `Color` do AWT:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Etapa 1: Configurar Diretórios de Documento e Recursos

Especifique onde deseja armazenar a imagem do código de barras gerada. Ajuste os caminhos para corresponder ao seu ambiente.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Etapa 2: Criar Instância do Gerador de Código de Barras

Instancie `BarcodeGenerator` com a simbologia desejada (por exemplo, CODE_128) e o texto do código que você deseja codificar.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Etapa 3: Configurar Legenda Acima do Código de Barras

Defina a legenda que aparecerá acima do código de barras. Você pode controlar o alinhamento, texto, visibilidade, família da fonte, tamanho e cor.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Etapa 4: Configurar Legenda Abaixo do Código de Barras

Da mesma forma, defina a legenda abaixo do código de barras. Sinta‑se à vontade para usar um alinhamento ou estilo diferente, se necessário.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Etapa 5: Salvar a Imagem do Código de Barras

Por fim, grave o código de barras (com legendas) em um arquivo de imagem. O formato é inferido a partir da extensão do arquivo.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Você pode repetir as etapas acima para experimentar diferentes fontes, cores ou alinhamentos, ou para gerar múltiplas imagens de códigos de barras em um loop.

## Problemas Comuns & Dicas

- **Legenda não visível?** Certifique‑se de que `setVisible(true)` foi chamado para a legenda que deseja exibir.  
- **Cores incorretas?** Use constantes de `java.awt.Color` ou crie cores personalizadas com `new Color(r, g, b)`.  
- **Problemas de caminho?** Verifique se `dataDir` aponta para uma pasta gravável existente; caso contrário, `bb.save()` lançará um `IOException`.  
- **Dica de desempenho:** Reutilize uma única instância de `BarcodeGenerator` ao gerar muitos códigos de barras; altere apenas o `EncodeTypes` ou `codetext` conforme necessário.

## Perguntas Frequentes (FAQs)

### Posso personalizar o estilo da fonte das legendas do código de barras?
Sim, você pode personalizar a família, o tamanho e a cor da fonte tanto da legenda acima quanto da legenda abaixo do código de barras.

### O Aspose.BarCode é compatível com diferentes simbologias de código de barras?
Absolutamente! O Aspose.BarCode suporta uma ampla variedade de simbologias, garantindo flexibilidade na geração de códigos de barras.

### Como posso integrar o Aspose.BarCode ao meu projeto Java?
Você pode seguir o guia de integração detalhado disponível [aqui](https://reference.aspose.com/barcode/java/) para instruções passo a passo.

### Existe uma versão de teste gratuita do Aspose.BarCode para Java?
Sim, você pode acessar a versão de teste gratuita [aqui](https://releases.aspose.com/) para explorar todos os recursos antes de comprar.

### Onde posso obter ajuda se encontrar problemas?
O fórum da comunidade Aspose.BarCode é um excelente local para suporte e discussões. Visite o fórum [aqui](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2025-12-27  
**Testado com:** Aspose.BarCode para Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}