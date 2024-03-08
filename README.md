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

## Comandos e asserções no Cypress

## Descrição das etapas de preparação de um testes de interface, execução e verificação no Cypress

## Como estruturar testes de forma eficiente no Cypress?
