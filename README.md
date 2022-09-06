

# NodeJs

------

Node.js é um ambiente de execução JavaScript que permite executar aplicações desenvolvidas com a linguagem de forma autônoma, sem depender de um navegador. Com ele, é possível criar praticamente qualquer tipo de aplicações web, desde servidores para sites estáticos e dinâmicos, até APIs e sistemas baseados em microsserviços.

<p align="center">
  <img width="700" height="456" src="https://lh3.googleusercontent.com/5tiskX5zuZ7cyRgQvrHdcb5I_dnf1E4Rf-qsjdfoVRgKTZapcPA5bZdeTEf4fy3yT-EnQg2aO7bcCMhtJh9mq9pkcSmu7rTIPryfVKlt9CdFFuVH14Vl2bWcYKx9UKcW5FUNTZypDu4egML2EUVFmpNCFBJiSCRT92qwQi2hYzGSiKcRo-55vBS319Z2E9Q">
</p>

Antes de começar a trabalhar com **Nodejs** é necessário fazer a instalação na sua máquina, só baixar o node através do site https://nodejs.org/en/.

Além do Node você também vai precisar de um **IDE** (VsCode) ou algum editor de texto.

------

O que pode ser desenvolvido com Nodejs?

- API REST (Você pode desenvolver todo o back-end de uma aplicação com o Node);

- Serveless (Serverless é um modelo de desenvolvimento nativo em nuvem para criação e execução de aplicações sem o gerenciamento de servidores.

  Os servidores ainda são usados nesse modelo, mas eles são abstraídos do desenvolvimento de aplicações. O provedor de nuvem fica responsável pelas tarefas rotineiras de provisionamento, manutenção e escala da infraestrutura do servidor. Os desenvolvedores só precisam empacotar o código em containers para fazer a implantação).

- Stream( Uma stream é uma forma de representar uma sequencia de bits. Podem ser entendidas como coleções de dados, exatamente como Arrays ou objetos, mas a diferença é que os dados em uma stream podem não estar disponíveis todos de uma vez, além disso, eles também não precisam utilizar a memória, ou seja, não é necessário que esses bits sejam armazenados na RAM).

- Entre outros.

  ------

  ## **Módulos**

  Módulo em Node é uma simples ou complexa funcionalidade organizada em um único ou múltiplos arquivos JS, no qual cada um pode ser reutilizado na aplicação.

  <p align="center">
    <img width="400" height="356" src="https://lh4.googleusercontent.com/n9VZ-e5yU3T1vtSBx3Cmt3qRUHla-AuOUxMoROPRrAqBz2unoQG7qIF5NVvcq2jKoGNADJxjeApxxCCS_h5ap0xQMNe9iO9AvyMxAG-hq3W1XwBbV09bLYljpM4YmUxTOf0oj1lm1JGEZow">
  </p>

  Sem módulo:

```
let rs = require ('readline-sync')

function criarUsuario(){
    let nome = rs.question('Digite o seu nome: ')
    let numero1 = rs.questionInt('Digite um número: ')
    let numero2 = rs.questionInt('Digite outro número: ')
    let numero3 = rs.questionInt('Digite só mais número: ')

    return{
        nome,
        numeros:[numero1, numero2, numero3]
    }
}
    let usuario1 = criarUsuario()
    let usuario2 = criarUsuario()
    console.log('usuario1: ', usuario1)
    console.log('usuario2: ', usuario2)

criarUsuario();
```

Com módulo:

```
let rs = require ('readline-sync')

function criarUsuario(){
    let nome = rs.questionInt('Digite o seu nome: ')
    let numero1 = rs.questionInt('Digite um número: ')
    let numero2 = rs.questionInt('Digite outro número: ')
    let numero3 = rs.questionInt('Digite só mais número: ')

    return{
        nome,
        numeros:[numero1, numero2, numero3]
    }

}
module.exports = {criarUsuario}
```

```
let meuModulo = require('./meuModulo')
let usuario1 = criarUsuario()
let usuario2 = criarUsuario()
console.log('usuario1: ', usuario1)
console.log('usuario2: ', usuario2)
```

------

## **NPM**

O NPM (Node Package Manager) consiste muito mais em um kit de ferramentas para desenvolvimento do que somente um instalador de pacotes. O Node utiliza o NPM como gerenciador de pacotes e bibliotecas, que por sua vez é o maior ecossistema de bibliotecas open source do mundo. 

<p align="center">
  <img width="400" height="356" src="https://lh6.googleusercontent.com/58XfwIxoxumcBJ_cnG0Dajf45PZPmbIxq479rYkaqS_WMLcKxQh9VXPB9tJrPTYLq7eFjLYL-uiX3U9RuykOCejMaIStCHuYHAgwGDzEHvByFeTQ2Tgvdz960FXNF5dlFD1NdeLmOPpCFFOVhbJhD7B3dcxTrDNluN3qjgwUzRlDIYAaKMpQhCjvkkxRKYA">
</p>

O NPM consiste muito mais em um kit de ferramentas para desenvolvimento do que somente um instalador de pacotes. Através do **npm config** é possível realizar uma série de tarefas, como efetuar o login/logout do npm.org para controlar pacotes próprios por exemplo. Enquanto isso, através de um arquivo .npmrc é possível ter acesso às configurações diretamente para uso no shell, interagindo automaticamente com o binário sem a necessidade de enviar parâmetros extras. Com o .npmrc, é possível ter configurações exclusivas para diferentes projetos em uso, o que torna a solução flexível para quando se possui diversos ambientes/projetos simultâneos. Através do npm config também são feitas configurações padrões com o comando para nomes de autoria, licença de software e outras informações.

------

### **Por que utilizar Módulos?**

Quando trabalhamos em aplicações, se desenvolvermos elas de qualquer forma, sem padrão, com o tempo fica impossível mexer no código ou fazer manutenção.

|                             PRÓS                             |                           CONTRAS                            |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| Podemos adicionar funcionalidades no nosso projeto e distribuir rapidamente para o time de desenvolvimento; | Não é difícil adicionarmos referencias que não precisamos ou deixaram de ser utilizadas; |
| É possível salvar em repositórios (NPM) privados ou públicos para compartilhamento; | Dependendo o tamanho do projeto o setup inicial de baixar pode demorar algum tempo; |
| Já é um padrão estabelecidos em vários frameworks e linguagens; | Módulos podem mudar de versão e quebrar nosso sistema sem que percebemos; |
| É fácil dar downgrade ou upgrade de uma versão da biblioteca; | Em ambientes de produção, se houve alteração manual no ambiente dos módulos, é possível dificultar o diagnóstico do que está acontecendo. |
| Permite ajudar a distinguir o que é tecnologia e o que é negócio. |                                                              |

------

## **REQUIRE**

Lembram dessa linha?

```
let rs = require('readline-sync')
```

Está sempre no começo da linha e falamos que é uma biblioteca para ler dados do console, ou devemos chamar de “readline-sync”?

Quando fazemos isso o Node procura por um módulo chamado “readline-sync”. Assim como se pedíssemos o módulo “Bruce”, o Node tentaria procurar um módulo chamado “Bruce”.

Podemos também procurar um módulo por nome do arquivo (ao invés do nome do módulo), basta passarmos um caminho para o require. 

Ex:

```
let meuModulo = require('./meuModulo')
```

**SCRIPT QUE UTILIZA O MÓDULO**:

```
var modulo = require('./meuModulo')
modulo.moduloBruce();
```

Quando queremos referenciar um módulo criado na nossa pasta, temos que referenciar em relação ao diretório do arquivo que está importando.

**MÓDULO:**

```
var moduloBruce = function(){
console.log("Olá Bruce, esse é o meu primeiro módulo")
}
exports.moduloBruce = moduloBruce;
```

Exports é o que faz o node entender o que queremos utilizar do “require”.

Quando utilizamos o comando **npm install “módulo”** estamos solicitando que **instale o módulo na pasta atual** que estamos rodando o comando. Isso faz com que o **npm crie uma pasta chamada node_modules** e coloque o pacote lá dentro.Ao utilizar o **require**, o Node tenta procurar esse módulo dentro de **node_modules**.

O NPM (Node package manager) é a ferramenta que faz a gestão para controlar nossos módulos.
Para ele entender todos os pacotes daquela versão que precisam ser atualizados/baixados existe o arquivo chamado package.json que controla toda a estrutura de dependência do nosso projeto.Por causa da existência desse arquivo não precisamos subir a pasta node_modules no GitHub, já que seria apenas gasto desnecessário de rede e disco no repositório de fonte.

O site que hospeda os módulos do Node:[ https://www.npmjs.com/](https://www.npmjs.com/)
