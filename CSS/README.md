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
    </style>```
        - Este é um paradigma útil a ser usado ao reutilizar o mesmo estilo várias vezes em uma página. As propriedades listadas serão aplicadas a todas as tags listadas.
- Um arquivo `.css` separado: adicione `<link rel="stylesheet" href="caminho/para/styles.css">` ao cabeçalho (dentro da tag `head`) e mova o código CSS (mesmo formato usado nas tags `<style> </style>`.
    - Geralmente, esse é um paradigma ainda melhor porque separa duas coisas distintamente diferentes: estrutura (HTML) e estilo (CSS), além de ser mais fácil de gerenciar e ler.
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
