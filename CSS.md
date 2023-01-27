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

## Flexbox

* Modelo de layout unidimensional, ou seja, lida apenas com uma dimensão por vez, seja como uma linha ou como uma coluna. 

**Os dois eixos do flexbobx**
* O flexbox possui dois eixos para lidar com o layout:
* **Eixo Principal**: Definido pela propriedade ```flex-direction```, e possui quatro valores sendo: ```row```, ```row-reverse```, ```column``` e ```column-reverse```.
    * ```row``` e ```row-reverse``` executa o eixo principal na direção de **linha/inline**.
    * ```column``` e ```column-reverse``` executa o eixo principal na diretação de **coluna/column**.
* **Eixo Transversal**:Executado perpendicularmente ao eixo principal. 
    * Se o ```flex-direction``` estiver definido como ```row``` ou ```row-reverse```, o eixo transversal será executado em **colunas**.
    * Se o ```flex-direction``` estiver definido como ```column``` ou ```column-reverse```, o eixo transversal será executado em **linhas**.

**Flex Container**
* A área do documento disposta usando flexbobx é chamada de _flex container_. 
* Para criar um flex container, é necessário definir o valor da ```display``` como ```flex``` ou ```inline-flex```. 
* Assim que for definido, os filhos diretos desse container se tornam _flex itens_, que vão se comportar da seguinte maneira:
    * O ```flex-direction``` padrão é ```row```.
    * Os itens começam na borda inicial do eixo principal.
    * Os itens não se estendem na dimensão principal, mas podem encolher.
    * Os itens serão esticados para preencher o tamanho do eixo transversal.
    * A ```flex-basis``` propriedade está definida como ```auto```.
    * A ```flex-wrap``` propriedade está definida como ```nowrap```.
    * _Resumindo_: Os itens serão alinhados em linha, usando o tamanho do conteúdo como seu tamanho no eixo principal. Se houver mais itens do que cabem, eles transbordarão. Se alguns itens forem mais altos que outros, todos os itens se estenderão ao longo do eixo transversal para preencher seu tamanho total. 

**Propriedades do flexbox**
* ```flex-direction```: Altera a direção de exibição dos elementos;
    * ```row```(padrão): Organiza os itens em linha (da esquerda para a direita).
    * ```row-reverse```: Organiza os itens em linha (da direita para a esquerda)
    * ```column```: Organiza os itens em colunas (de cima para baixo).
    * ```column-reverse```: Organiza os itens em colunas (de baixo para cima).
* ```flex-wrap```: Organiza os itens de forma que possa ocorrer "quebra de linha".
    * ```nowrap```(padrão): Todos os itens serão dispostos em uma linha.
    * ```wrap```: Permite a quebra de linhas (linha de baixo).
    * ```wrap-reverse```: Permite a quebra de linha (linha de cima).
* ```flex-flow```: Forma abreviada para a escrita das propriedades ```flex-direction``` e ```flex-wrap```. 

* ```justify-content```: Define o alinhamento dos itens ao longo do eixo principal do container. 
    * ```flex-start```(padrão), ```flex-end```, ```center```, ```space-between``` e ```space-around```.
* ```align-content```: Define como as linhas são distribuídas ao longo do eixo transversal do container. Terá efeito se tiver elementos suficiente para quebrar a linha e a propriedade. 
    * ```stretch```(padrão): As linhas são distribuídas uniformemente ao longo do eixo transversal, ocupando todo o espaço disponível;
    * ```flex-start```, ```flex-end```, ```center```, ```space-between``` e ```space-around```.
* ```align-items```: Define como os itens são distribuídos ao longo do eixo transversal do container. 
    * ```stretch```(padrão): Os itens serão esticados para preencher toda a dimensão do eixo transversal (altura/largura).
    * ```baseline```: Os itens são alinhados a partir da base da primeira linha de texto de cada um.
    * ```flex-start```, ```flex-end``` e ```center```.
* ```order```: Altera a ordem de exibição dos itens.
* ```flex-grow```: Define a proporção com que um item deve crescer caso seja necessário. 
* ```flex-shrink```: Define a proporção com que um item deve encolher caso seja necessário.
* ```flex-basis```: Define o tamanho inicial que um item deve ter antes que o espaço ao seu redor seja distribuído. Ou seja, dependendo da direção do eixo principal, essa propriedade define a largura ou altura mínima do elemento antes que ele seja redimensionado por outras propriedades.
* ```flex```: Forma abreviada para a escrita das propriedades ```flex-grow```, ```flex-shirink``` e ```flex-basis```.
* ```align-self```: Permite sobrescrever no item o comportamento que foi definido pela propriedade align-items. 
    * ```auto```(padrão): Respeita o comportamento definido no container por meio do align-items.
    * ```stretch```, ```flex-start```, ```flex-end```, ```center``` e ```baseline```.

* _Observação_:  
* A propriedade ```justify``` está relacionada ao eixo principal.
* A propriedade ```align``` está relacionada ao eixo transversal.

## Grid

* Modelo de layout bidimensional, ou seja, lida com duas dimensões *linhas e colunas*.

**Propriedades**
* Container
    * ```display: grid```: Define que o layout será em grade.
    * ```grid-template-columns```: Fatia o layout em colunas.
    * ```grid-template-rows```: Fatia o layout em linhas.
    * ```grid-gap```: Define os espaçamentos.
        * ```grid-row-gap```
        * ```grid-column-gap```
    * ```grip-template-areas```: Delimita as áreas.

* Itens
    * ```grid-column```: Define onde estará as colunas do layout.
        * ```grid-column-start```
        * ```grid-column-end```
    * ```grid-row```: Define onde estará as linhas do layout.
        * ```grid-row-start```
        * ```grid-row-end```
    * ```grid-area```: Define a área de grades.

**Alinhamento**
* ```justify-content```
* ```align-content```
* ```justify-items```
* ```align-items```
* ```justify-self```
* ```align-self```

* Sabendo que o grid é bidimensional, nós temos o eixo x e o y. 
  * O *eixo x* é o posicionamento horizontal, da esquerda para a direita. 
  * O *eixo y* é o posicionamento vertical, de cima para baixo. 

* **Content, Itens e Self**
  * Justando o ```justify```, ou ```align```, com esses elementos: ```content```, ```itens``` e ```self```, nós observamos nossas propriedades. 
  * **Content**
    * ```justify-content``` e ```align-content``` nos permite alinhar o próprio grid, relativo ao espaço fora do grid. 
    * O uso dessas propriedades são raras, pois só é aplicado caso o grid seja menor que a área definida. (Por exemplo, quando usamos em px o tamanho do grid, podemos terminar com um grid pequeno, para o tamanho da área do grid)
    * 7 valores: ```start```, ```end```, ```center```, ```stretch```, ```space-between```, ```space-around``` e ```space-evenly```
  * **Itens**
    * ```justify-items``` e ```align-items``` vai permitir alinhar os items do nosso grid, em qualquer espaço disponível, na célula que ele habitar. 
    * 4 valores: ```start```, ```end```, ```center``` e ```strech```
  * **Self**
    * ```justify-self``` e ```align-self``` vai nos permitir alinhar o item em si.
    * Faz a mesma coisa que o ```justify-items``` e ```align-items```, porém, aplicado diretamente no item de um grid.

## Grid ou Flexbox?

* **Flexbox**: 
  * Uma dimensão (ou linha, ou coluna)
  * A partir do conteúdo
  * Distribuição de espaços
  * Para porções de layout
  * Elementos de UI
* **Grid**: 
  * Duas dimensões (linhas e colunas)
  * A partir da definição da grid
  * Ocupação de espaços pré-definidos
  * Para layouts completos
  * Layouts mais abrangentes
  * Requer menos media queries
* Um complementa o trabalho do outro
