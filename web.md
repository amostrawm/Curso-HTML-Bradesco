# Estudos HTML, CSS, JAVASCRIPT
Em uma página da Web, a linguagem de marcação de hipertexto (HTML) fornece seu conteúdo, as folhas de estilo em cascata (CSS) definem a aparência da página e o JavaScript é usado para fornecer interatividade com o usuário, ou seja, a sua lógica de negócios.

## CONTEUDO : HTML
## ESTILO : CSS
## LÓGICA: JAVASCRIPT

Um arquivo HTML para a estrutura da página e para o conteúdo
Um arquivo CSS para apresentação e aplicação de estilos
Um arquivo JavaScript para comportamentos e interatividade

Configurar três arquivos ajuda a nos mantermos organizados!
Isso é um exemplo de melhoria progressiva.

## CSS externo
Um benefício do CSS externo é que várias páginas HTML podem ser vinculadas ao mesmo arquivo CSS.

Se você fizer uma alteração ao CSS, seu estilo será atualizado para cada página.

Designar um arquivo HTML para a estrutura da página e um arquivo CSS para a definição de estilos e arquivos JavaScript para interação ou eventos é chamado de separação de interesses.

Como mencionamos anteriormente, você também pode escrever CSS diretamente em HTML, o que é chamado de CSS interno.

Mesmo para um site básico, há tantas regras de CSS que a página HTML pode ficar desorganizada muito rapidamente. Com mais de uma página, o mesmo CSS seria repetido com frequência e se tornaria difícil de gerenciar.

## Regras de CSS
Para entender como funcionam as regras de CSS, imagine que você tenha uma chave antiga e uma série de portas em um corredor longo.

Primeiro, você seleciona uma porta. Então, você destranca a porta com a chave.

Depois de ter acesso a uma sala, você pode decorá-la como quiser. Você pode pintar as paredes de azul ou definir o piso como sendo de madeira.

Você seleciona uma sala e define as regras sobre como ela deve parecer.

Você pode aplicar o mesmo estilo a várias salas, que é exatamente como funciona o CSS!

Você pode usar regras de CSS para aplicar estilos ao HTML.

O elemento de lista não ordenada ul {} é um seletor que seleciona o elemento HTML < ul > ao qual aplicará os estilos.
A declaração é font-family: helvetica e informa o que esse estilo deve ser.

O nome da propriedade é font-family e o valor é helvetica. A propriedade e o valor juntos formam um par chave-valor.

O que você selecionará é um elemento existente que definimos anteriormente em HTML (< body > e < ul >).

## Seletores

ID e seletores de classe permitem aplicar estilos a nomes de atributos personalizados em seu HTML.

Uma ID é usada para definir o estilo de um elemento, enquanto classes podem definir o estilo de vários elementos.

## Adicionar um tema escuro

:root {
    --green: #00FF00;
    --white: #ffffff;
    --black: #000000;
}

O seletor de :root representa o elemento < html > na página HTML
Para esse tipo de tarefa, uma melhor prática é definir um conjunto de variáveis CSS globais no elemento :root.
Aqui, você define três variáveis de cor anexadas à raiz da página.

No código anterior, você deve definir algumas variáveis novas, que são 'bg' e 'fontColor', para especificar a cor da tela de fundo e a cor da fonte.

Use a palavra-chave var para especificar as variáveis que serão usadas como valores de propriedade.

Você definiu os valores anteriormente no seletor de :root.

O seletor * é universal e se aplica a todos os elementos da página (exceto quando um seletor de elemento mais específico o substitui).
Aqui, você o usa com o objetivo de definir a propriedade de cor (color) padrão para todos os elementos de página.
Para as propriedades color e background, especifique as variáveis definidas nos seletores de tema claro e escuro.

## O que é JavaScript?

O JavaScript (ou ECMAScript) é uma linguagem de programação que ajuda você a adicionar interatividade à sua página da Web.

Quando você seleciona um botão, o JavaScript é o código que define o evento ou o comportamento que ocorrerá, assim como abrir uma janela pop-up.

Usando JavaScript, você pode adicionar ou remover conteúdo, como o texto da página da Web, sem recarregá-lo.

Como um desenvolvedor para a Web, você pode usar o navegador para testar e obter comentários sobre seus scripts.

Neste módulo, você configurará o arquivo JavaScript, criará um botão para alternar entre temas claros e escuros e conectará o botão ao código JavaScript que executa a alternância de tema real.

< script src="app.js">< /script >

O elemento de script pode ser colocado no < head > ou em outro lugar no < body >.

No entanto, colocar < script > no final da seção < body > permite que todo o

conteúdo da página seja exibido na tela primeiro, carregando o script em seguida.

## Configurar o modo estrito
js 
'use strict'

## Adicionar um botão

 < div >
    < button class="btn">Dark</button >
< /div >

.btn {
    position: absolute;
    top: 20px;
    left: 250px;
    height: 50px;
    width: 50px;
    border-radius: 50%;
    border: none;
    color: var(--btnfontColor);
    background-color: var(--btnBg);
}

.btn:focus { outline-style: none;}
Ao definir a regra de outline-style como none, você elimina um contorno retangular quando o botão é selecionado (recebe foco).

## Adicionar um manipulador de eventos

const switcher = document.querySelector('.btn');

No arquivo JavaScript, use document.querySelector para obter a referência do botão.

No código a seguir, você adiciona um ouvinte para o evento click.
A função passada para o ouvinte de eventos é seu manipulador de eventos real.

switcher.addEventListener('click', function(){
    document.body.classList.toggle('dark-theme')
})

No código anterior, você usou o método toggle para alternar o elemento para a classe dark-theme.

Isso aplica, automaticamente, os estilos de tema escuro em vez do tema claro. No entanto, o rótulo do botão também precisa ser atualizado para mostrar o tema correto, portanto, você precisa adicionar uma instrução if para verificar o tema atual e atualizar o rótulo do botão.
