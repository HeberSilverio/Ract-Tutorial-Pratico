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
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/HelloWorld.JPG)
``` 
function HelloWorld() {
   return (
      <div>HTML</div>
   )
}
export default HelloWorld
``` 
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
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/props1.JPG)
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
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/desetruturando1.JPG)
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
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/desetruturando2.JPG)
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
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/module-css.JPG)
- E chamar este **CSS** no componente;
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/module-css-import.JPG)

## Fragmentos
- Os **React Fragments** permite a criação de um componente sem elemento pai;
- O propósito é **descomplicar os nós do DOM**;
- A sintaxe é **<> e </>**, não há um nome para a tag;
- Criamos no próprio JSX;
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/fragments.JPG)

## Avançando em props
- Podemos **definir tipos para as props**, realizando uma espécie de validação;
- Definimos em um objeto chamado propTypes no próprio componente; 
- E ainda há a possiblidade de **definir um valor padrão**;
- Neste caso utilizamos o objeto **defaultProps**;
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/propTypes1.JPG)
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/propTypes2.JPG)
![](https://github.com/HeberSilverio/React-Tutorial-Pratico/blob/main/react-tutorial/src/dist/img/propTypes3.JPG)

## Eventos
- Os **eventos de React** são os mesmo eventos do DOM;
- Ou seja, temos eventos para responder a um click;
- **O evento é atrelado a uma tag** que irá executá-lo;
- Geralmente um **método** é atribuído ao evento;
- Este método deve ser criado no componente;
![](https:evento.JPG)

## UseState
- O **useState** é um hook do React;
- Com ele conseguimos **manusear o estado** de um componente de forma simples;
- Este hook **funciona muito bem com eventos**;
- Podemos **atrelar um evento** a mudança de state;

```
T* useState -> onChange={(e) => setName(e.target.value)}
```