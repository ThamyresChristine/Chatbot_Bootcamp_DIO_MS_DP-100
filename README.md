# Criação de Chatbot no Azure AI Foundry

#### Criação de um modelo de chatbot alimentado por conteúdo de PDF's. 

## _Criação do Resource Group_

Na página inicial do Azure, crie um grupo de recursos ou resource group.
<center><img src="Prints-desafioDois/00.png" width="650"></center>

Dê um nome a sua _subscription_, _resource group name_ e escolha a região.
<center><img src="Prints-desafioDois/01.png" width="650"></center>

Após ser criado o resource group fica assim:
<center><img src="Prints-desafioDois/02.png" width="500"></center>

## _Hub do Azure AI Foundry_

Dentro do resource group clique em _create_, pesquise e escolha o _Azure AI Foundry_.
<center><img src="Prints-desafioDois/03.png" width="400"></center>

Confirme a _subscription_, o _resource group_, escolha a região e dê um nome ao recurso do Foundry.
<center><img src="Prints-desafioDois/04.png" width="600"></center>

Após ser criado o resource fica assim:
<center><img src="Prints-desafioDois/05.png" width="400"></center>

Clique em _Launch Azure AI Foundry_ para entrar no hub.
<center><img src="Prints-desafioDois/06.png" width="400"></center>

A página inicial do hub é assim:
<center><img src="Prints-desafioDois/07.png" width="400"></center>

Crie um novo projeto.
<center><img src="Prints-desafioDois/08.png" width="550"></center>

A página do _playground_, local para desenvolvimento do bot, fica assim:
<center><img src="Prints-desafioDois/09.png" width="750"></center>

Vá em _Modelos + pontos de extremidade_, _implantar o modelo_.
<center><img src="Prints-desafioDois/10.png" width="400"></center>

## _Implantação do Modelo_

Escolha o modelo básico.
<center><img src="Prints-desafioDois/11.png" width="400"></center>

Escolha um modelo de acordo com o bot que deseja criar. Nesse caso, o escolhido foi o _gpt-4o_
<center><img src="Prints-desafioDois/13.png" width="600"></center>

Além do _gpt-4o_, também é necessário escolher o _text-embedding-3-large_ para a criação do chatbot.
<center><img src="Prints-desafioDois/15.png" width="500"></center>

Os dois modelos escolhidos aparecem assim:
<center><img src="Prints-desafioDois/16.png" width="400"></center>

Vá em _Playgrounds_ e clique em _Experimentar o chat_.
<center><img src="Prints-desafioDois/17.png" width="500"></center>

Configure com o bot, indicando instruções sobre qual o conteúdo o bot irá abordar/responder. Aplique as alterações.
<center><img src="Prints-desafioDois/18.png" width="400"></center>

Faça um teste no chat.
<center><img src="Prints-desafioDois/19.png" width="800"></center>

## _Recurso do Azure AI Search para vetorização da pesquisa_

Antes de adicionar os dados para alimentar o bot, é necessário configurar como ele vai pesquisar/ler o conteúdos dos arquivos PDF's. Para isso é necessário o _Azure AI Search_.

De volta a página do _resource group_, clique em _create_ e pesquise pelo _Azure AI Search_.
<center><img src="Prints-desafioDois/20.png" width="400"></center>

Confirme a _subscription_, o _resource group_, escolha a região (mesma do Foundry) e dê um nome ao recurso do AI Search.
<center><img src="Prints-desafioDois/21.png" width="600"></center>

Após ser criado o resource fica assim. Clique em _Go to resource_.
<center><img src="Prints-desafioDois/22.png" width="400"></center>

Temos o recurso, mas não temos nenhum vetor de indexação.
<center><img src="Prints-desafioDois/23.png" width="550"></center>

## _Upload dos arquivos PDF's e configurações finais_

Voltando para o Playground do AI Foundry, vamos em _Adicionar seus dados_ e fazemos o upload dos arquivos PDF's.
<center><img src="Prints-desafioDois/24.png" width="600"></center>

Na configuração do índice, procuramos por um recurso e adicionamos a conexão do recurso criado no AI Search.
<center><img src="Prints-desafioDois/25.png" width="600"></center>

Adicionamos a busca em vetor ao recurso de pesquisa.
<center><img src="Prints-desafioDois/26.png" width="600"></center>

Clicamos em _criar índice de vetor_ e aguardamos.
<center><img src="Prints-desafioDois/27.png" width="600"></center>

## _Criação do Índice, Teste Final no Playground e Implantação como Aplicativo Web_

Após o índice ser criado, ele aparece na seção _Indexes_ do AI Search
<center><img src="Prints-desafioDois/28.png" width="600"></center>

Podemos ver o mesmo índice selecionado no playground do chat.
<center><img src="Prints-desafioDois/29.png" width="500"></center>

Um novo teste, baseado agora em um dos arquivos PDF's enviados ao banco de dados do AI Foundry.
Podemos ver que o chatbot responde perfeitamente.
<center><img src="Prints-desafioDois/30.png" width="800"></center>

Se está tudo certo, podemos implantar nosso chatbot como um aplicativo web.
<center><img src="Prints-desafioDois/31.png" width="400"></center>

Damos um nome a ele, confirmamos a _subscription_, o _resource group_, escolha a região e o plano de preços. Também é importante habilitar o histórico de chats no aplicativo web.
<center><img src="Prints-desafioDois/32.png" width="400"></center>

Aguarde a implantação, leva alguns minutos.
<center><img src="Prints-desafioDois/33.png" width="400"></center>

Seu chatbot está pronto para uso!
<center><img src="Prints-desafioDois/35.png" width="600"></center>
