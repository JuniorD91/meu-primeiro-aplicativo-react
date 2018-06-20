# Introdução ao Reactjs

O que você irá aprender neste pequeno tutorial?

* Introdução ao react
* Configuração do ambiente
* Criação do projeto
* Analisando a estrutura do projeto
* Analisando o componente
* Criando um componente

## Introdução ao react

[React](https://reactjs.org/) é uma biblioteca JavaScript declarativa, eficiente e flexível para criar interface de usuário utilizando o conceito de componetização.

## Configuração do ambiente

Para desenvolver em react devemos primeiro configurar nosso ambiente. 
1. **Git**  : Clique aqui [Git](https://git-scm.com/) para realizar o download e em seguida instalá-lo.
> Git é um sistema de controle de versão distribuído gratuitamente e de código aberto projetado para lidar com projetos pequenos a muito grande, com velocidade e eficiência. Clique [Aqui](https://git-scm.com/book/pt-br/v1/Primeiros-passos-Configuração-Inicial-do-Git) para realizar os primeiros passos para configurá-lo.
2. **Node** : Clique aqui [Node.js](https://nodejs.org/en/) para realizar o download da **versão 8.4 ou superior**.
>Node.js é um interpretador de código JavaScript com código aberto, focado em migrar o JavaScript do lado do cliente para o servidor. **É de suma importância a instalação do node para desenvolver em react.**
1. **Yarn/npm** : Utilize [yarn](https://yarnpkg.com/pt-BR/docs/install#windows-stable) ou [npm](https://docs.npmjs.com/) para instalação do react.<br>

> Siga os passos abaixo para instalar Yarn.
> </br>**Windows** :  choco install yarn 
> </br>**macOs** : brew install yarn
> </br>**Linux** : curl -o- -L https://yarnpkg.com/install.sh | bash
> </br>Para mais informações acesse a [documentação](https://yarnpkg.com/pt-BR/docs/install#windows-stable) do yarn.
> </br>O npm não precisa ser instalado pois vem junto com nodejs.
4. **ReactJs** : Para instalar o reactjs com npm deve executar as instrunções abaixo.</br>
```
npm install -g  create-react-app
create-react-app meu-primeiro-aplicativo-react
cd meu-primeiro-aplicativo-react
npm start
```

Se você tiver o npm 5.2.0+ instalado, poderá usar o npx, executando a instrução abaixo.
```
npx create-react-app meu-primeiro-aplicativo-react 
cd meu-primeiro-aplicativo-react
npm start
```
5. **ReactJs** : Para instalar o reactjs com Yarn deve executar a instrução abaixo.

```
yarn create react-app meu-primeiro-aplicativo-react
```
O código acima equivale a  :</br>
```
yarn global add create-react-app 
create-react-app meu-primeiro-aplicativo-react
```
6. **Editor de código-fonte** : Utilizaremos o [visual code](https://code.visualstudio.com/download) para o desenvolvimento dos códigos dos nossos exemplos.
>Caso esteja  habituado a outro editor de texto ou IDE, você não terá problema ao seguir os exemplos desde tutorial.

## Criação do projeto
Para criar um projeto react teremos que seguir o passo(s) do tópico 5 ou 6 no seu terminal de preferência.
> Imagem do log da criação do projeto : https://raw.githubusercontent.com/JuniorD91/meu-primeiro-aplicativo-react/master/src/img/powerShell.PNG
 
## Analisando estrutura
![Minion](https://raw.githubusercontent.com/JuniorD91/meu-primeiro-aplicativo-react/master/src/img/meu-primeiro-aplicativo-react.PNG)

1. Na pasta src é encontrado os principais arquivos do projeto
2. Na pasta public fica o arquivo index.html onde é o arquivo inicial do projeto e a página mostrada no browser quando executado o projeto.
3. Para que seja feito alguma alteração no arquivo index.html é necessario trabalhar nos arquivos do diretorio src. As ferramentas instaladas via npm ou yarn que estão na pasta node_modules compila todo o código na exeução do seu projeto, alterando o arquivo index.html.

## Analisando o componente
![Minion](https://raw.githubusercontent.com/JuniorD91/meu-primeiro-aplicativo-react/master/src/img/componente.PNG)

## Criando um componente
Como agora já sabemos um pouco sobre o react e o conceito de componetização, vamos criar um componente para fixação do conteúdo.
1. Passo - Criação do componente : </br>
Para criar um componente em react clique com botão direito do mouse em **src->new file->nomeDoArquivo.js**, no nosso caso iremos criar um aquivo .js chamado de **Navbar.js**
1. Passo - Importando o recurso react: </br>
Depois de ter criado o arquivo .js você terá que informar a importação do react na primeira linha do arquivo da seguinte forma:
```
import react, { Component } from 'react';
```
3. Passo - Estendendo 'Component' :</br> Agora você terá que criar a classe estendendo a interface Component, dessa forma você estará permitido a implementação do método **render**  onde tem um retorno que terá o HTML onde será renderizado no browser. segue o exemplo abaixo:
```
class Navbar extends Component{
    render(){
        return(
            //Aqui terá suas tags "html"
        )
    }
}
```
1. Passo - Importando o arquivo .css:</br>Vamos importar um arquivo css para deixar nosso componente mais elegante e em seguida adicionar na nossa div um className que faz o mesmo papel de class do css convencional.
```
import react, { Component } from 'react';
import './Navbar.css';

class Navbar extends Component{
    render(){
        return(
            //Aqui terá suas tags "html"
            <div className="navbar">
                Navbar
            </div>
        )
    }
}
```
Antes de executar o projeto você terá que criar o arquivo .css no seu src. </br>**src->new file->Navbar.css**
```
div.navbar{
    background: blue;
    height: 70px;
}
```
>Dicas : É indicado que você crie seu(s) arquivo(s) .css com o mesmo nome do componente. Dessa forma seu codigo ficará mais legível e organizado.

1. Passo - Criando export:</br> O export é o ultimo trecho de código da classe e é de suma importância sua existência, pois dessa forma o componente será visível a partir de outros arquivos.
```
export default Navbar;
```
6. Passo - Utilizando o componente criado: </br>Após de ter criado o componente, iremos utilizá-lo na pagina .js que contém as tags html. Vamos utilizar esse import no arquivo App.js. 
```
import Navbar from './Navbar';
```
7. Passo  - Com o componente importado, nos já conseguiremos acessá-lo e vamos informar o seguinte código dentro da nossa div e antes da header.

```diff
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';
import './Navbar';
import Navbar from './Navbar';

class App extends Component {
    render() {
        return (
            <div className="App">
+               <Navbar/>
                <header className="App-header">
                    <img src={logo} className="App-logo" alt="logo" />
                    <h1 className="App-title">Welcome to React</h1>
                </header>
                <p className="App-intro">
                    To get started, edit <code>src/App.js</code> and save to reload.
                </p>
            </div>
        );
    }
}
```



8 - Passo : Executando o projeto react.
```
npm start
```
9 - Passo : O resultado é

![](https://raw.githubusercontent.com/JuniorD91/meu-primeiro-aplicativo-react/master/src/img/Capturar.PNG)

# Duvidas?
```
    Caso tenha alguma duvida entrar em contato pelo email : fjuniordourado@gmail.com 
```

