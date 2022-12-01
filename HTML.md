# HTML - HyperText Markup Language

* É uma linguagem de marcação, usada para definir a estrutura do conteúdo na web. 
* Consiste em uma série de elementos, usados para delimitar ou agrupar diferentes partes do conteúdo, para que apareçam de uma determinada maneira. 
* _HyperText ou HiperTexto_ refere-se aos links que conectam páginas web entre si, seja dentro de um único site ou em vários. E _marcação_ são textos, imagens e outros conteúdos, são as _tags_ que estruturam o conteúdo da página. 

**As principais partes de uma tag são:**
* **Tag de abertura**: Elemento será envolvido por <>. 
* **Tag de fechamento**: Elemento será envolvido por </>.
* **Conteúdo**: O que será exibido na web.
* **Elemento**: A tag em questão (p, div, img, por exemplo).
* Também existem os elementos (tags) **vazios**, que são marcações que possuem apenas a tag de abertura e não possui a tag de fechamento - ```input``` e ```br``` por exemplo.

* Tags também podem conter atributos, que possuem uma informação adicional a tag usada em questão. Mas não é necessário ser exibido, pode apenas estar modificando o conteúdo que deverá ser exibido. 
* **Atributos globais**, são os atributos que podem ser incluídos em qualquer tag HTML - ```id``` e ```class``` por exemplo.

## Anatomina do documento HTML

* ```<!doctype html>```: Informa ao navegador a espeficicação do código HTML;
* ```<html lang="pt-br"></html>```: Inicia o código HTML indicando o idioma principal do documento;
* ```metadados```: Conjunto de informações sobre a página;
* ```charset```: Indica a codificação de caracteres que a página possui;
* ```UTF-8```: Padrão de codificação também chamado de **unicode**, ele uniformiza as informações ao redor do mundo para todos os navegadores, atende o maior número possível de idiomas, praticamente universalizando a codificação de informações, incluindo emojis, acentos e símbolos;
* ```link```: Referencia o documento que será usado. Utiliza o atributo **rel** que indica o tipo de documento que está sendo referenciado;
* ```scripts```: Declara o tipo de linguagem que será trabalhada.
    > A tag script é considerada um bloqueador de recursos. Na renderização de um código HTML, ao se deparar com um código ```script``` a renderização do HTML para e só continua após a execução completa do código script. 
    > Por isso geralmente essa tag é colocada após o </body>, para evitar o bloqueio na renderização do HTML. 
    > Mas é possível evitar esse bloqueio também com dois atributos. O ```async```, que indica que a tag script deverá ser executada em paralelo com o HTML e o ```defer```, que indica que o código script será executado apenas ao final do código HTML. 

## HTML semântico

* Utiliza de tag semânticas. As tags representam um significado ao que está sendo inserido em cada divisão da página, organizando e padronizando o desenvolvimento. 

    * ```header```: Usada para definir o cabeçalho - _logo, títulos, menu de navegação, campo de busca_ entre outros;
    * ```nav```: Serve para agrupar uma lista de links para outras partes do site - _lista de navegação_ por exemplo;
    * ```section```: Serve para dividir o conteúdo em diferentes seções - _header ou article_ por exemplo;
    * ```article```: Serve para identificar um conteúdo independente e de maior relevância dentro da página - _feed, post, artigo ou bloco de comentário_;
    * ```aside```: Exibirá conteúdos que fazem referência ao conteúdo principal - _informações, blocos de navegação, publicidade_;
    * ```footer```: Rodapé do documento ou de uma seção - _informações do autor, copyright, blocos de navegação ou links relacionados_.

## Formulários e Validações em HTML

**Diferentes tipos de validação de formulário:**
* **Validação do lado do cliente**: Ocorre no navegador antes que os dados sejam enviados ao servidor. Podendo ser através de código JS ou validação integrada através do HTML. 
* **Validação do lado do servidor**: ocorre no servidor após o envio dos dados. O código do lado do servidor é usado para validar os dados antes de serem salvos no banco de dados. Se os dados falharem na autenticação, uma resposta será enviada de volta ao cliente para informar ao usuário quais correções devem ser feitas. 

Em HTML o atributo obrigatório para uma tag é o ```required```.

[Mais exemplos de validações](https://developer.mozilla.org/pt-BR/docs/Learn/Forms/Form_validation)

## Acessibilidade

* A acessibilidade na web é voltada para pessoas com algum tipo de deficiência, seja visual, auditiva, motora ou cognitiva. 
* Foram desenvolvidas tecnologias assistivas para proporcionar maior independência e autonomia a esses usuários. 
* **WAI-ARIA**, uma especificação escrita pelo W3C, que define um conjunto de atributos HTML para acessibilidade. Esses atributos podem ser reconhecidos por navegadores e tecnologias assistivas, conferindo semântica adicional ao elemento. 
* A especificação possui três recursos principais:
    * **Atributos ```role```: Define o que o elemento é ou faz. São atribuídos geralmente a _landmarsk_.
    * **Propriedades**: Conferem semântica adicional. 
    * **Estados**: Propriedades especiais que definem condições atuais dos elementos. 
* Dicas para trazer acessibilidade ao HTML:
    * ```<html lang="pt-br">```: Além de ser ótimo para o SEO e ferramentas de tradução, a definição do idioma ajuda tecnologias assistivas a definirem o perfil de voz e conjunto de caracteres. 
    * Utilizar tags semânticas, auxiliam ao leitor de telas a identificar cada elemento para o usuário, permitindo a navegação. 
    * Evitar pular níveis de títulos, para não influenciar em leitor de telas. 
    * Não utilizar hífen na estrutura de frases. 
    * Expandir abreviações e acrônimos pelo menos uma vez no texto. 
    * Fazer uso das _landmarks_, pois são pontos de referência utilizado por leitor de telas para saltos no conteúdo. Devem ser usados para marcar blocos importantos, como menu de navegação, conteúdo principal, campos de busca, entre outros. Permitindo que o usuário chegue diretamente a esses elementos. 
    * **Controles de User Interface (UI)** são elementos com os quais o usuário interage, como botões, links e formulários. Navegadores permitem que esses controles sejam acessados pelo teclado. 
    * Imagens devem possuir o atributo ```alt``` com um texto alternativo que descreva seu conteúdo. 
    * Evitar fontes de ícones, pois não são um formato acessível.
    * Não transmitir informações somente através de cores (em tabelas, por exemplo).
    * Links sublinhados são úteis para usuários com dificuldade para discernir contraste.
    * Textos de links devem ser descritivos (e não apenas com "clique aqui").
    * A rolagem infinita pode ser problemática para navegação por teclado.
    * Teste a página sem o CSS, para avaliar a estrutura e verificar se o conteúdo continua fazendo sentido.
    * Teste a navegação por teclado e o leitor de tela.
    * Se possível, disponibilizar uma visualização em "modo noturno".

## SEO

* Search Engine Optimization (Otimização de Mecanismos de Busca) é o conjunto de técnicas usadas, geralmente, dividas entre tecnologia, conteúdo e autoridade, para alcançar bom posicionamento de páginas de um site no Google e em outros buscadores, gerando tráfego orgânico. 
* Sua maior preocupação é em disponibilizar conteúdo útil, relevante e bem organizado. 
* Dicas:
    * ```<title>```: Deve ser único, que descreva seu conteúro corretamente e diferencie dos demais títulos. 
    * ```<h1>``` a ```<h6>```: Devem ser usadas para organizar o texto em tópicos, tornando mais fácil para o visitante encontrar o que ele procura. 
    * As principais palavras-chave do site deve aparecer no título e é importante que apareçam no texto, mas sem muitas repetições, utilizando de sinônimos e podendo ter um peso maior ao utilizar ```<strong>``` e ```<em>``` por exemplo.
    * A página inicial deve ser o cartão principal e ter um maior cuidado. 
    * As imagens são parte do conteúdo e podem ser igualmente otimizadas para os sites de busca. Posicionamento da imagem na página, utilização da propriedade ```alt``` com nomes otimizados, são dicas de grande importância. 
* São algumas dicas que podem auxiliar na otimização do site de busca.