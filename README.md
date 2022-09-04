# React-Tutorial-Pratico
## O que é React?
- Uma **biblioteca JS** para criação de interfaces;
- Utilizado para construir **SPAs** (Single Page Application);
- Baseado em **componentes**;
- Utiliza o **JSX** para renderizar HTML;
- E aplica o **Virtual Dom** para realizar as alterações de DOM;
- Podemos **adicionar a um projeto** ou criar um projeto com ele;

## Como instalar o React?
- Para instalar o React vamos utilizar o uma ferramenta chamada **[Create React App](https://create-react-app.dev/)**;
- Recebemos todos os arquivos da biblioteca e temos como executá-la;
- Para utilizar precisamos do **Node e também npm**;
- Esta ferramenta também otimiza o app gerado para **produção**;
- É Possível iniciar a aplicação com **npm start**;

## Entendendo o JSX
- O **JSX é como um HTML, porém dentro do código JavaScript;
- É a principal maneira de escrever HTML com o React;
- Podemos **interpolar variáveis**, inserindo ela entre {};
- É possível também **executar funções** em JSX;
- Inserir **valores em atributos de tags** também é válido em JSX;

## Componentes
- Permite **dividir a aplicação** em partes;
- Os componentes **renderizam JSX**, assim como App.js (que é um componente);
- Precisamos **criar um arquivo** de componente;
- E **importá-lo** onde precisamos utilizar;
- Normalmente ficam em uma pasta chamada **components**;
- O arquivo inicia com letras maiúscula + CamelCase; 
- Veja o modelo:
![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)
`` 
function HelloWorld() {
   return (
      <div>HTML</div>
   )
}
export default HelloWorld
`` 
- Precisa ser importado no App.js da seguinte maneira:
`import HelloWorld from './components/HelloWorld`
- Para utilizar o componente você precisa chamar através de uma tag JSX:
`<HelloWorld />`
- Componentes são reutilizados. Um componente pode ser importado apenas dentro de outro componente;

## Props
- As **props** são valores passados para componentes;
- Podemos deixá-los **dinâmicos**;
- Ou seja, **mudando a execução** por causa do valor da prop;
- O valor é **passado como um atribudo** na chamada do componente;
- E precisa ser **resgatado dentro de uma propriedade/argumento** chamada props na função de definição do componente;
- As props são somente de leitura!
![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)
```
function HelloWorld(props) {
   return (
      <div>
         <p>Fala aí {props.nome}, tudo bem?</p>
      </div>
   )
}
export default HelloWorld
```
- E deve ser chamado como um atributo:
`<HelloWorld nome="Héber" />`
- E pode ser reaproveitado o componente de forma dinâmica, apenas passando um novo nome como atributo na nova chamada.
`<HelloWorld nome="João" />`

#### Desestruturando 
![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)
```
function Pessoa(props) {
   return (
      <div>
         <img src={props.foto} alt={props.nome} />
         <h2>Meu nome é: {props.nome}</h2>
         <p>Minha idade: {props.idade}</p>
         <p>Minha profissão: {props.profissao}</p>
      </div>
   )
}
export default Pessoa
```
- Podemos simplesmente destruturar transformando as propriedades em variáveis:
![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)
```
function Pessoa({nome, idade, profissão, foto}) {
   return (
      <div>
         <img src={foto} alt={nome} />
         <h2>Meu nome é: {nome}</h2>
         <p>Minha idade: {idade}</p>
         <p>Minha profissão: {profissao}</p>
      </div>
   )
}
export default Pessoa
```
## Adicionando CSS
- O **CSS** pode ser **adicionado de forma global** na aplicação, por meio do arquivo index.css por exemplo;
- Porém é possível estilizar a nível de componentes;
- Utilizamos o **CSS modules** para isso;
- Basta criar um arquivo como: **Component.module.css**;
- E chamar este **CSS** no componente;