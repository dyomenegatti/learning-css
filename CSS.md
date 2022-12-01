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

## Tipos de seletores

* Seletor da tag: ```<p>```
* Seletor de ID: ```#my-id```
* Seletor de classe: ```.my-class```
* Seletor de atributo: ```img[src]```
* Seletor de pseudoclasse: ```a:hover```

## CSS: boxes

* O layout CSS é baseado no _modelo de caixa_. Cada caixa com propriedades como:
    * ```padding```: Espaço ao redor do conteúdo. 
    * ```border```: Linha sólida fora do preenchimento. 
    * ```margin```: Espaço ao redor do lado de fora da borda.
