# CSS
- CSS (Cascading Style Sheets) é uma linguagem usada para interagir e estilizar HTML, alterando a aparência de acordo com uma série de regras. CSS é o que faz com que os sites tenham uma boa aparência.
- O CSS pode ser aplicado ao HTML de várias maneiras:
    - O atributo `style`: ```html <h5 style="color: blue; alinhamento de texto: centro;"> </h5>```
        - As propriedades CSS separadas por ponto-e-vírgula passadas para o `style` serão aplicadas no conteúdo da tag.
    - As tags `<style> </style>`:
    ```html
    <style>
        h5, h6 {
            color: blue;
            text-align: center;
        }
    </style>
    ```
    > Este é um paradigma útil a ser usado ao reutilizar o mesmo estilo várias vezes em uma página. As propriedades listadas serão aplicadas a todas as tags listadas.
- Um arquivo `.css` separado: adicione `<link rel="stylesheet" href="caminho/para/styles.css">` ao cabeçalho (dentro da tag `head`) e mova o código CSS (mesmo formato usado nas tags `<style> </style>`.
    > Geralmente, esse é um paradigma ainda melhor porque separa duas coisas distintamente diferentes: estrutura (HTML) e estilo (CSS), além de ser mais fácil de gerenciar e ler.
- Algumas propriedades CSS comuns (aquelas que usam argumentos em pixels geralmente podem ter uma porcentagem ou simplesmente `auto`):
    - `color: blue`, `color: #0c8e05`: pode ser 1 de aprox. 140 cores nomeadas ou um valor hexadecimal que representa um valor RGB
    - `text-align: left`: alinha o texto à esquerda; outros argumentos possíveis são `center`, `right` ou `justify`
    - `background-color: teal`: define o plano de fundo como uma cor, com o mesmo formato da propriedade `color`
    - `height: 150px`: define a altura de uma área
    - `width: 150px`: define a largura de uma área
    - `margin: 30px`: define a margem ao redor dos quatro lados de uma área
        - também pode ser dividido em `maegin-left`, `margin-right`, `margin-top` e `margin-bottom`
    - `padding: 20px`: define o preenchimento em torno do texto dentro de uma área
        - pode ser dividido da mesma maneira que `margin`
    - `font-family: Arial, sans-serif`: define a família de fontes a ser usada
        - uma lista separada por vírgula fornece alternativas caso um navegador não suporte uma fonte específica
        - famílias genéricas como sans-serif usarão os padrões do navegador
    - `font-size: 28px`: define o tamanho da fonte
    - `font-weight: bold`: define o peso da fonte como qualidade, uma medida relativa (`lighter`) ou um número (200)
    - `border: 3px solid blue`: define uma borda ao redor de uma área
    - Existem muitas propriedades CSS que podem ser usadas de várias maneiras diferentes. Confira a [documentação maravilhosamente extensa](https://developer.mozilla.org/en-US/docs/Web/CSS) para obter mais informações.

## Seccionando com HTML e CSS
- Duas tags especiais nos permitem dividir uma página da Web em seções:
    - `<div></div>`: divisão vertical de uma página da web
    - `<span></span>`: seção de uma página da Web, por exemplo, texto
- `<div></div>` e `<span></span>` realmente não fazem muito sozinhos, mas permitem a identificação de seções de uma página da Web.
- Diferentes seções de uma página da web podem ser referenciadas com os atributos `id` e `class`. Os `id`s identificam exclusivamente os elementos, mas pode haver um número arbitrário de elementos com uma determinada classe.
- `id`s podem ser referenciados em CSS com `#id` e `class`es podem ser referenciadas em `.class`. `id`s e `class`es, portanto, podem ser usados ​​para estilizar os mesmos tipos de áreas (3 diferentes `<div></div>`, por exemplo) de maneiras diferentes.

## Seletores
- Os seletores de CSS são usados ​​para selecionar diferentes partes de um site para criar estilos específicos.

|expr| descr
|:-:|:-|
|`a, b`| Seletor múltiplo elementos (a E b)|
|`a b`| Seletor descendente|
|`a > b`| Seletor filho (b é filho de a)|
|`a + b`| Seletor de irmão adjacente|
|`[a=b]`| Seletor de atributo|
|`a:b`| Seletor de pseudoclasse|
|`a::b`| Seletor de pseudoelemento|

## Exemplos
- Selecione todos os `h1` e `h2`:
    ```css
    h1, h2 {
        color: red;
    }
    ```

- Selecione todos os `li` que são descendentes de `ol` (não necessariamente descendentes imediatos):
    ```css
    ol li {
        color: red;
    }
    ```

- Selecione todos os `li` que são filhos imediatos de `ol`:
    ```css
    ol > li {
        color: red;
    }
    ```

- Selecione todos os `input` com o atributo `type=text`:
    ```css
    input[type=text] {
        background-color: red;
    }
    ```

- Selecione todos os `button` com a pseudoclasse `hover`:
    ```css
    button:hover {
        background-color: orange;
    }
    ```
    - Uma **pseudoclasse** é um estado especial de um elemento HTML. Neste exemplo (`hover`), o estado é se o cursor está ou não passando o mouse sobre um botão.

- Selecione todos os pseudoelementos `before` dos elementos `a`:
    ```css
    a::before {
        content: "\21d2 Click here: ";
        font-weight: bold;
    }
    ```
    - Um **pseudoelemento** é uma maneira de afetar certas partes de um elemento HTML. Neste exemplo, o seletor `before` aplica o `content` com o estilo incluído antes do conteúdo de todos elementos `a`.
    - `\21d2` é um valor hexadecimal para um ícone Unicode, que pode representar símbolos como emoji.

- Selecionar todos os pseudoelementos `selection` dos elementos `p`:
    ```css
    p::selection {
        color: red;
        background-color: yellow;
    }
    ```

## Design Responsivo
- Design responsivo é a ideia de que um site deve ter boa aparência, independentemente da plataforma na qual ele é visualizado.
- Uma maneira de fazer isso é usando uma _media query_:
    ```html
    <style>
        @media print {
            .screen-only {
                display: none;
            }
        }
    </style>
    <body>
        <p class="screen-only">Isso não aparecerá quando impresso</p>
    </body>
    ```
- `@media` é uma consulta de mídia (_media query_), o que significa que o CSS a seguir será aplicado apenas em determinadas situações, nomeadamente, quando a página da web estiver sendo impressa (neste exemplo). `.screen-only` é um seletor de classe que identifica apenas o conteúdo que queremos que seja impresso

    ```css
    @media (min-width: 500px) {
        body {
            background-color: red;
        }
    }
    @media (max-width: 499px) {
        body {
            background-color: yellow;
        }
    }
    ```
- Quando a largura da tela é de pelo menos 500 px, a cor de fundo do `body` fica vermelha, enquanto que se for menor que 499 px, a cor de fundo do `body` fica amarela.
- Para interagir com o tamanho da tela, o seguinte deve ser incluído no `head`:
    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```
    - `viewport` é a área visível na qual a tela está sendo exibida.
    - `content` refere-se a toda a página da Web cuja largura está sendo definida como largura do dispositivo (_device-width_).

- Outra ferramenta é 'flexbox'. O Flexbox permite a reorganização do conteúdo com base no tamanho da janela de visualização.
    ```css
    .container {
        display: flex;
        flex-wrap: wrap;
    }
    ```
    - Ao definir `display: flex` e `flex-wrap: wrap`, o conteúdo será quebrado verticalmente, se necessário, para que nenhum conteúdo seja perdido quando a largura da tela for reduzida.

- Uma grade de conteúdo pode ser alcançada de maneira semelhante.
    ```css
    .grid {
        display: grid;
        grid-column-gap: 20px;
        grid-row-gap: 10px;
        grid-template-columns: 200px 200px auto;
    }
    ```
    - Ao definir `display: grid`, todas as diferentes características de um layout de grade podem ser usadas para formatar o conteúdo. Em particular, ao definir o `grid-template-colummns`, a coluna final pode ser definida como `auto`, preenchendo o espaço restante da tela. Se várias colunas estiverem definidas como `auto`, elas compartilharão igualmente o espaço restante.

## Bootstrap
- Bootstrap é uma biblioteca CSS criada para ajudar a criar sites limpos, responsivos e de boa aparência, sem ter que lembrar os detalhes sobre flexboxes ou grades toda vez que um layout precisa ser configurado.
- A única coisa necessária para usar o Bootstrap é adicionar uma única linha que vincule a folha de estilo CSS do Bootstrap:
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    ```
- O CSS do Bootstrap fará com que tudo pareça um pouco mais limpo e moderno, mas seu poder real vem com o sistema de layout. O Bootstrap usa um modelo baseado em coluna, em que cada linha de um site é dividida em 12 colunas individuais, e diferentes elementos podem receber um número diferente de colunas para preencher.
As colunas e linhas do Bootstrap são referenciadas em HTML com os atributos `class="row"` e `class="col-3"`, em que o número após `col-` é o número de colunas que o elemento deve usar.
    - Os elementos podem ocupar um número diferente de colunas com base no tamanho da tela, com atributos como `class="col-lg-3 col-sm-6"`. Em uma tela pequena, 6 colunas serão usadas, mas em uma tela grande, Serão usadas 3 colunas. Se for necessário adicionar outra linha, o Bootstrap fará isso automaticamente. Esta é uma alternativa muito mais fácil a algo como o flexbox (o Bootstrap faz isso nos bastidores).
- O Bootstrap possui uma série de outros componentes bonitos que podem ser facilmente aplicados simplesmente adicionando o atributo `class` apropriado a um elemento. Veja a [documentação do Bootstrap](https://getbootstrap.com/docs/4.4/getting-started/introduction/) para uma lista extensa.

## Sass
- Sass é uma linguagem totalmente nova, construída sobre CSS, que oferece um pouco mais de poder e flexibilidade ao projetar folhas de estilo CSS e permite a geração de folhas de estilo de maneira programática. Por fim, Sass apenas facilita a escrita de CSS.
- Para usar o Sass, ele deve primeiro ser [instalado](http://sass-lang.com/install). Uma vez instalado, podemos executar `sass style.scss style.css` para compilar nosso arquivo Sass `style.scss` em `style.css`, que pode realmente ser vinculado e interpretado por um arquivo HTML.
    - Se a recompilação for irritante, `sass --watch style.scss:style.css` para recompilar automaticamente `style.scss` como `style.css` sempre que `style.scss` for  modificado. Além disso, muitos sistemas de implantação de sites, como o GitHub Pages, criaram suporte para o Sass. Por exemplo, se um arquivo `.scss` for enviado para o GitHub, o GitHub Pages o compilará automaticamente.
- Um recurso do Sass é variável, ​​definida da seguinte forma: `$color: red;`. Em qualquer lugar `$color` é passado como um valor para uma propriedade CSS, por exemplo `color: $color`, o vermelho será usado.
- Outro recurso é o aninhamento, que é uma maneira mais concisa de estilizar elementos que estão relacionados a outros elementos de uma certa maneira.
    ```css
    div {
        font-size: 18px;
        p {
            color: blue;
        }
        ul {
            color: green;
        }
    }
    ```
- Neste exemplo, todos os `p`s dentro de `div`s terão `color: blue`, mas também `font-size: 18px`, enquanto os `ul`s dentro de `div`s terão `color: green` em vez disso, mas ainda o `font-size: 18px`.
- Um recurso mais útil é a herança, que é semelhante ao conceito orientação a objetos. A herança de Sass permite pequenos ajustes de um estilo geral para diferentes componentes.
    ```css
    %message {
        font-family: sans-serif;
        font-size: 18px;
        font-weight: bold;
    }

    .specificMessage {
        @extend %message;
        background-color: green;
    }
    ```
    - `%message` define um padrão geral que pode ser herdado em outras definições de estilo usando a sintaxe `@extend %message`. Além disso, outras propriedades de estilo podem ser adicionadas.
