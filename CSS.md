# CSS - Cascading Style Sheets

* Não é uma linguagem de programação. Também não é uma linguagem de marcação. CSS é uma **linguagem de folha de estilo**, utilizada para estilizar elementos HTML seletivamente. 

## Anatomia do CSS

* Toda a estrutura é chamada de _conjunto de regras_. Dividido em:
    * **Seletor**: Nome da tag HTML que será estilizada. 
    * **Declaração**: Regra única especificando qual das propriedades do elemento será estilizado.
    * **Propriedades**: Maneiras pelas quais é possível estilizar uma tag HTML, ```color``` para definir uma cor a uma tag, por exemplo. 
    * **Valor da propriedade**: Escolhe uma aparência a uma propriedade, ```red``` é o valor da propriedade ```color```.
    * Além do seletor, cada conjunto de regras deve ser colocado entre chaves {}.
    * Dentro de cada declaração, deve usar dois pontos : para separar a propriedade de seu valor ou valores, e ponto e vírgula ; para separar cada declaração da seguinte.
        ```
            p {
                color: red;
                width: 500px;
            }
        ```

    * É possível selecionar vários elementos e aplicar um único conjunto de regras. 
        ```
            p, li, h1 {
                color: red;
                width: 500px;
            }
        ```

## Diferença entre inline, interno e externo

* **Interno**: Ocorre dentro da tag ```<head``` no HTML, dentro de uma tag ```<style type="text/css">```
    * Vantagens/desvantagens: Os seletores de ID podem ser usados por stylesheet interno, não há necessidade de carregar vários arquivos; mas aumenta o tamanho do código HTML, aumentando também no tempo de carregamento. 
* **Externo**: É utilizado um arquivo externo ao HTML, chamado de ```style.css```(ou outro nome), que será apenas para o CSS e é chamado no ```<head>``` do HTML através da tag ```<link rel="stylesheet" type="text/css" href="style.css">```
    * Vantagens/desvantagens: Estrutura de código mais limpa, o arquivo CSS pode ser usado para outras páginas HTML; mas o processamento pode demorar um pouco mais.
* **Inline**: Usado dentro de um tag HTML, a partir da propriedade ```style```, seria como ```<h1 style="color:white;padding:30px;">Teste</h1>```
    * Vantagens/desvantagens: Fácil e rápido inserção, não é necessário arquivos externos; mas consome muito tempo e deixa a estrutura HTML bagunçada.
## Tipos de seletores

* Seletor da tag: ```<p>```
* Seletor de ID: ```#my-id```
* Seletor de classe: ```.my-class```
* Seletor de atributo: ```img[src]```
* Seletor de pseudoclasse: ```a:hover```
* Seleciona somente o elemento imediamente após o primeiro: ```+```
* Seleciona somente os filhos diretos: ```>```
* Seleciona todos os próximos após o primeiro: ```~```
* Exclui determinados elementos de receber a regra: ``` not```

* A **especificidade de um seletor** é o poder de escolha, no qual ajuda os navegadores a decidir o valor da propriedade que terá precedência. Feito através:
    * Id > class
    * Css inline > que outros seletores
    * Cálculo de seletor > que qualquer outro.
## CSS: boxes

* O layout CSS é baseado no _modelo de caixa_. Cada caixa com propriedades como:
    * ```padding```: Espaço ao redor do conteúdo. 
    * ```border```: Linha sólida fora do preenchimento. 
    * ```margin```: Espaço ao redor do lado de fora da borda.
## Pseudo-elementos

* Permite que sejam estilizado uma parte específica do elemento selecionado.
    * ```::``` define um pseudo-elemento
    * ```::after```: Cria um falso elemento que permite adicionar conteúdo **após** o elemento selecionado.
    * ```::before```: Cria um falso elemento que permite adicionar conteúdo **antes** do conteúdo do elemento selecionado.
    * ```::first-letter```: Customiza a primeira letra do conteúdo de um elemento.
    * ```first-line```: Customiza o conteúdo da primeira linha do elemento. 
    * ```::selection```: Utilizado para selecionar o conteúdo de um elemento e, a partir disso, customizar algumas propriedades dessa área. 

## Pseudo-classes

* Usada para definir um estado especial de um elemento. Pode ser usado para: _estilizar um elemento quando um usuário passa o mouse sobre ele, estilizar links visitados e não visitados, estilizar um elemento quando recebe foco_ entre outros. 
    * ```:``` define uma pseudo-classe
    * ```a:link```: link visitado.
    * ```a:visited```: link visitado.
    * ```a:hover```: mouse por cima. 
    * ```a:active```: link selecionado. 
    * ```:focus```: elemento ganha foco. 
## Diferença entre **px**, **em** e **rem**?

* ```px```: Unidade absoluta e não escalável. A mudança do seu valor não afeta outros valores de unidades absolutas, ou seja, o valor do pixel continua imutável mesmo após configurações do usuário. 
    * Usar em ajustes finos, ou pequenas margens, espessuras de uma borda, ajuste fino na hora de posicionar um elemento com posicionamento absoluto. 
* ```rem```: Unidade escalável e relativa, ele varia de acordo com a dimensão root do navegador (por padrão é de 16px), na maior parte das vezes 1rem = 16px. Relativo ao tamanho da fonte do elemento raiz, ou seja, relativo ao ```font-size``` declaro no elemento HTML.
* ```em```: Unidado dinâmica, porém sua referência não é o valor raiz do navegador, e sim o valor calculado da propriedade font-size do elemento no qual ela é usada. É relativo a fonte do elemento pai - a fonte será 2x a fonte do elemento pai. 
    * Ótima opção para preenchimentos, alturas de linhas e margens. 

## Floats

* Determina que um elemento deve ser retirado do seu fluxo normal e colocado à esquerda ou diretia do container, onde os textos e elementos em linha irão se posicionar ao seu redor. 
* Floats são utilizados para posicionar uma imagem ao lado de um bloco de texto, criar layouts para web e layouts de pequenas instâncias.

**Problemas:**
* Floats são _frágeis_; são cheios de contratempos e cross-browser quirks. 
* Para isso existe a necessidade de "limpar" floats (propriedade _clear_). Exemplos:
    * Arumar o float para ajustar a altura do elemento pai
    * Limpar o float para começar uma nova linha
    * Dando clear somente à esqueda ou à direita 

## Position

* Define como um elemento qualquer pode ser posicionado no documento da página.
* Acompanhada de 4 propriedades: ```top```,  ```bottom```, ```right``` e ```left``` - elas determinam a localização final do objeto/deslocar o objeto conforme for especificado.
    * ```position: static```: Padrão para todos os elementos;
    * ```position: fixed```: O elemento fica fixo na página independente do scroll, isso acontece porque ele fica fixo em relação a viewport;
    * ```position: relative```: Está posicionado em relação a sua posição normal, em relação a ele mesmo;
    * ```position: absolute```: Será posicionado em relação a o elemento mais próximo dele que tenha um ```position: relative```;
    * ```position: sticky```: Fixo em relação ao scroll do usuário, como se fosse um adesivo ele fica fixo quando 'chega' no scroll dele.

## Box Model

* O modelo básico de um elemento é em _caixas_, e a posição e propriedades (como cor, plano de fundo, tamanho de borda, etc) são definidas atráves do CSS. 
* Cada caixa é composta por quatro partes:

**Content area**
* Contém o conteúdo do elemento (como imagem, texto etc).
* Se a ```box-sizing``` é definida como ```content-box```(padrão) e se o elemento for um elemento de bloco, o tamanho da área de conteúdo poderá ser explicitamente definido com as propriedades: ```width```, ```min-width```, ```max-width```, ```height```, ```min-height``` e ```max-height```.

**Padding area**
* Define a área de preenchimento interno de um elemento box. 
* A espessura do preechimento é determinada pelas propriedades ```padding-top```, ```padding-right```, ```padding-bottom```, ```padding-left``` e abreviadas ```padding```.

**Border area**
* Estende a área de preenchimento para incluir bordas do elemento. 
* A espessura das bordas é determinada pelas propriedades ```border-widht``` abreviadas e ```border```. 
* Se a ```box-sizing``` propriedade for definida como ```border-box```, o tamanho da área da borda poderá ser explicitamente definido com as propriedades ```width```, ```min-width```, ```max-width```, ```height```, ```min-height``` e ```max-height```. 

**Margin area**
* Define a área de preenchimento externo de um elemento box. 
* O tamanho da área de margem é determinado pelas propriedades ```margin-top```, ```margin-right```, ```margin-left``` e ```margin-bottom```. 

