# Ponderada Programação

## O que é o Cypress e para que serve?
O Cypress é uma ferramenta de teste de frontend com funcionalidades que auxiliam tanto desenvolvedores quanto engenheiros de QA.

Ele serve para efetuar testes E2E, testes de componentes, testes de integração e testes unitários, executando todos pelo próprio navegador, resumidamente: facilitar o desenvolvimento com qualidade e as melhorias contínuas em projetos Web.

## Vantagens e desvantagens do Cypress em relação a outras ferramentas de teste

Vantagens:
- Por no navegador diretamente com a aplicação, tem total acesso ao DOM e aos seus objetos, permitindo que os testes acessem tudo o que o código acessa;
-  Acesso ao network da aplicação, permitindo simular e testar até mesmo as conexões com APIs;
-  Capaz de simular e manipular estados, por ter total controle aos objetos da aplicação, pode criar e alterar estados necessários e modificar DOM;
-  Controle de temporizadores, permitindo pular esperas por execução, voltar em pontos no temporizador necessário para a execução e afins, assim como adicionar event listners para a aplicação ou manipular websockets;
-  Permite cache por sessão, criando contexto para cada suite de testes, permitindo recuperar sessões a cada suite;
-  Proteção contra falhas, por ter total controle da aplicação, conhece muito bem como ela funciona, sendo capaz de aguardar cada carregamento da aplicação e se adapatar a cada contexto;
-  É possível utilizar o modo debug do navegador enquanto executa os testes e interage com a aplicação;
-  É possível fazer screenshots instantâneos durante a execução dos testes.

Desvantagens:
- Não é possível usá-lo em dois navegadores ao mesmo tempo;
- Não suporta múltiplas guias do navegador;
- Só é possível utilizar javascript para fazer os testes;
- Alguns navegadores não possuem suporte para o Cypress, como o Safari e IE;
- Sem suporte para execução de testes em dispositivos móveis;
- Não é possível executar testes remotos;
- Suporte limitado para iFrames.

## Arquitetura do Cypress

O Cypress executa comandos no mesmo loop de execução da aplicação, tendo total acesso tanto ao frontend quanto ao backend da aplicação, permitindo a ele a capacidade de responder eventos da aplicação em tempo real, enquanto trabalha por fora do navegador em tarefas que necessitam de maiores privilégios. Para isso ocorrer, o cypress executa por trás um Node server process, estabelecendo com ele uma conexão síncrona, essa conexão permite que ambos executem tarefas em detrimento do outro, de acordo com cada contexto. 

Por conta do Cypress ter controle da Network do navegador, é capaz de tanto ler quanto manipular os tráfegos da rede em tempo real, não apenas isso, também modifica o código que possa interferir nessa automatização do navegador.

Segue abaixo uma imagem da arquitetura do Cypress:
![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/98463469-3159-4321-aa66-7a5af4d1dbff)

Test Runner: Responsável por executar a GUI do Cypress, permitindo a interação direta com os testes e a visualização da interface.

Cypress Server: Um processo Node que executa em background, responsável por gerenciar as interações entre os testes e o navegador.

Browser: Instância do navegador que executa aplicação e os testes. O Cypress se comunica com o navegador utilizando um protocolo chamado Cypress Protocol, permitindo-o controlar o navegador e suas funcionalidades, assim como a DOM e as requisições do Network. 

## Seletores de elementos no Cypress

São comandos de Query de elementos da DOM, permitindo ao Cypress o acesso direto ao elemento criado na UI, muito importante para a criação de testes do frontend.

Alguns dos selectors são:
- get: permite acessar elementos por Classe, Id, Atributos (Seletores CSS);
- contains: permite acessar elementos que possuam um texto específico;
- first, eq e last: permite acessar elementos pelo seus posicionamento, o primeiro encontrado, o igual ao índice passado, e o último encontrado;
- next: permite acessar o próximo elemento ao anterior encontrado, deve ser utilizado em conjunto com outro seletor;
- prev: permite acessar o elemento anterior encontrado, deve ser utilizado em conjunto com outro seletor;

## Comandos e asserções no Cypress

São funcionalidades do Cypress que permitem diversas ações do Cypress com a aplicação (queries, assertions, actions e outras).

Assertions: são comandos Cypress que validam estados da aplicação, pausando a aplicação até que a condição seja atendida ou que tenha chegado ao seu tempo limite. Dentre eles temos o .and() e o .should().

A grande maioria dos testes utilizarão queries para acessar os elementos da DOM, e assertions para a validação dos elementos, dados e estados da aplicação. 

## Descrição das etapas de preparação de um testes de interface, execução e verificação no Cypress

### Instalar o Cypress

Instale o Cypress para executá-lo.

Comandos:
``cd /your/projcet/path``
``npm install cypress --save-dev``

### Abrir o Cypress

Abra o Cypress para executar as etapas posteriores.

Comandos:
``npx cypress open``
ou
``yarn cypress open``

### Adicione um arquivo de test

Após rodar o comando para abrir o Cypress, será exibida a interface dele.

Sendo necessário escolher a configuração do Cypress, entre teste de componente e e2e.

Após essa etapa, deverá ser escolhido um navegador para executar o Cypress.

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/e511f908-278a-4387-b17a-7b67683595ba)

Agora é necessário apenas seguir os passos das imagens a seguir para testar uma interface:
![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/40d27208-1aab-4083-ba84-b76d6b6820dc)

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/33bb6b10-b843-4aee-8740-a170025ccf45)

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/13c1338e-8e5e-4cee-add9-14892b6d0f57)

Também é possível criar testes customizados de acordo com a interface criada por meio do Scaffold examples specs.

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/f0abb870-59bc-4c0d-a77d-610b78d3727a)

Exemplo de uma das execuções de testes criadas pelo Scaffold (testando uma tabela da interface):
![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/6bd8723f-8fed-4a7c-b670-dd7e10576896)

Agora para fazer testes com scripts customizados, é necessário abrir o projeto em uma IDE.

Acessar o arquivo spec.cy.ts ou criar um novo.

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/c83f1e3b-275f-4b5b-9227-a5c8abca21dc)

E customizar o código de teste como no exemplo abaixo:

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/2a031c81-c72d-4138-a7e6-f1662a1ac316)

Após criar os testes, é necessário apenas clicar em qualquer um dos testes na lista de execução que será executado o teste com a sua visualização.

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/f46dbfb0-989e-4626-88bc-91c3cf134f9e)

![image](https://github.com/FelipeSaadi/Ponderada-08-03/assets/54749257/0bb393fe-52da-4791-8e59-a3b64013110e)

## Como estruturar testes de forma eficiente no Cypress?

Existem alguns padrões a serem seguidos dos testes para torná-los mais eficientes. A seguir será descrito alguns deles:

- Test Specs isolados, de acordo com sua programação;
- Usar data-* com os atributos para acessar elementos da DOM;
- Usar aliases e closures para acessar e guardar comnados;
- Apenas testar aplicações que temos controle, se for necessário acessar 3rd party servers, utilizar o cy.request();
- Testes devem rodar de forma independente um do outro e ainda passar;
- Adicionar multiplas assertions (para e2e);
- Limpar estados antes de rodar testes.

Como adicional (e mais importante), ao pensar na elaboração dos testes, levar em conta as regras de negócios, as funcionalidades desenvolvidas e a experiência do usuário, esses aspectos auxiliam na construção de testes que cobrem uma maior variedade de possibilidades e protegem a aplicação de possíveis falhas.

É possível seguir também a aplicação completa e profissional criada pelo próprio Cypress para exemplificar o seu uso em cenários reais: [Real World App](https://github.com/cypress-io/cypress-realworld-app).
