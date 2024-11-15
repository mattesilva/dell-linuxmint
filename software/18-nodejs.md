#Autor: Robson Vaamonde<br>
#Procedimentos em TI: http://procedimentosemti.com.br<br>
#Bora para Prática: http://boraparapratica.com.br<br>
#Robson Vaamonde: http://vaamonde.com.br<br>
#Facebook Procedimentos em TI: https://www.facebook.com/ProcedimentosEmTi<br>
#Facebook Bora para Prática: https://www.facebook.com/BoraParaPratica<br>
#Instagram Procedimentos em TI: https://www.instagram.com/procedimentoem<br>
#YouTUBE Bora Para Prática: https://www.youtube.com/boraparapratica<br>
#Data de criação: 22/12/2022<br>
#Data de atualização: 13/11/2024<br>
#Versão: 0.12<br>
#Testado e homologado no Linux Mint 20 Ulyana, 20.1 Ulyssa, 20.2 Uma e 20.3 Una x64<br>
#Testado e homologado no Linux Mint 21 Vanessa, 21.1 Vera, 21.2 Victoria e 21.3 Virginia x64<br>
#Testado e homologado no Linux Mint 22 Wilma x64<br>

#Instalação do Node.JS e NPM no Linux Mint 20.1 Ulyssa, 20.2 Uma e 20.3 Una x64<br>
#Instalação do Node.JS e NPM no Linux Mint 21 Vanessa, 21.1 Vera, 21.1 Vera, 21.2 Victoria e 21.3 Virginia x64<br>
#Instalação do Node.JS e NPM no Linux Mint 22 Wilma x64<br>

[![Node.JS](http://img.youtube.com/vi/awDyXU-vIsk/0.jpg)](https://www.youtube.com/watch?v=awDyXU-vIsk "Node.JS")

Link da vídeo aula: https://www.youtube.com/watch?v=awDyXU-vIsk

Site Oficial do Node.JS: https://nodejs.org/en/<br>
Site Oficial do NPM: https://www.npmjs.com/

O QUE É E PARA QUE SERVER O NODE.JS E NPM: Node.js é um software de código aberto, multiplataforma, baseado no interpretador V8 do Google e que permite a execução de códigos JavaScript fora de um navegador web. A principal característica do Node.js é sua arquitetura assíncrona e orientada por eventos. npm é um gerenciador de pacotes para o Node.JS npm, Inc. é uma subsidiária do GitHub, que fornece hospedagem para desenvolvimento de software e controle de versão com o uso do Git. npm é o gerenciador de pacotes padrão para o ambiente de tempo de execução JavaScript Node.js.

#00_ Verificando as Informações do Sistema Operacional do Linux Mint<br>
```bash
#atalho para acessar o Terminal
Terminal: Ctrl + Alt + T

#verificando as versões e codinome do sistema operacional
#OBSERVAÇÃO IMPORTANTE: Linux Mint 20.x é derivado do Ubuntu Desktop 20.04.x Focal Fossa
#OBSERVAÇÃO IMPORTANTE: Linux Mint 21.x é derivado do Ubuntu Desktop 22.04.x Jammy Jellyfish
#OBSERVAÇÃO IMPORTANTE: Linux Mint 22.x é derivado do Ubuntu Desktop 24.04.x Noble Numbat
sudo cat /etc/os-release
sudo cat /etc/lsb-release

#modo gráfico para verificar as informações de sistema operacional e hardware
Menu
  Informações do Sistema
```

#01_ Atualização do Sistema Operacional do Linux Mint<br>
```bash
#atualizando o sistema operacional via MintUpdate (Recomendado)
A) Atualização do sistema utilizando o MintUpdate;
B) Atualização do sistema utilizando o Apt;

#atualizando o sistema operacional via Terminal
#atalho para acessar o Terminal
Terminal: Ctrl + Alt + T

#recomendo utilizando o comando: apt - o comando: apt-get e considerado obsoleto
sudo apt update
sudo apt upgrade
sudo apt full-upgrade
sudo apt dist-upgrade
sudo apt autoremove
sudo apt autoclean
```

#02_ Instalando as Dependências do Node.JS no Linux Mint<br>
```bash
#instalando as dependências do Node.JS
sudo apt install git vim curl gcc g++ make software-properties-common build-essential ca-certificates
```

#03_ Instalando a Versão LTS (Long Term Support) do Node.JS no Linux Mint<br>
```bash
#OBSERVAÇÃO IMPORTANTE: o script de adicionar o Sources List do Node.JS no Linux Mint já 
#reconhece a versão que você está usando, não sendo necessário informar o codinome do
#Ubuntu (focal, jammy ou noble).

#Script de configuração do Repositório do Node.JS foi DESCONTINUADO, não é mais indicado
#utilizar esse script em servidores de produção ou Desktop para desenvolvimento local.
#opção do comando curl: -f (fail), -s (silent), -S (show-error), -L (location)
#opção do redirecionador |: Conecta a saída padrão com a entrada padrão de outro comando
#opção do comando sudo: -E (preserve-env)
#sudo curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash

#instalando o Node.Js e suas dependências (DESCONTINUADO)
#sudo apt install nodejs

#Adicionando a Chave GPG do Node.JS via Nodesource no Linux Mint 20.x, 21.x e 22.x
#opção do comando curl: -f (fail), -s (silent), -S (show-error), -L (location)
#opção do redirecionador |: Conecta a saída padrão com a entrada padrão de outro comando
#opção do comando gpg: -o (output file)
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /usr/share/keyrings/nodesource.gpg

#Adicionando o Repositório do Node.JS no Linux Mint 20.x, 21.x e 22.x
#OBSERVAÇÃO IMPORTANTE: é indicado utilizar sempre a versão LTS (Long Time Support) do
#Node.JS em servidores de Produção, consulte sempre a versão LTS no Site Oficial do Node 
#no Link: https://nodejs.org/en e no Link: https://nodejs.org/en/about/previous-releases
#opção do redirecionador |: Conecta a saída padrão com a entrada padrão de outro comando
echo "deb [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list

#atualizando o Sources List do Apt com o novo Repositório
sudo apt update

#Instalando o Node.JS e NPM (Node Package Manager)
#opção do comando apt: --install-recommends (Consider suggested packages as a dependency for installing)
sudo apt install --install-recommends nodejs
```

#04_ Verificando as Versões do Node.JS e NPM no Linux Mint<br>
```bash
#verificando a versão do Node.JS
#opção do comando node: -v (version)
sudo node -v

#verificando a versão do NPM
#opção do comando npm: -v (version)
sudo npm -v
```

#05_ Criando um Projeto Simples para Testar o Node.JS no Linux Mint<br>
```bash
#criando o diretório do projeto de teste do Node.JS
#opção do comando mkdir: -v (verbose)
mkdir -v nodejs-hello

#acessando o diretório criado do projeto de teste do Node.JS
cd nodejs-hello

#iniciando o diretório de projeto do Node.JS
#opção do comando npm: init (create package.json file), -y (yes)
npm init -y

#instalando o módulo Express do Node.JS
#opção do comando npm: install (install package in directory)
npm install express

#listando o conteúdo do diretório de projeto do Node.JS
#opção do comando ls: -l (list), -h (human-readable)
ls -lh
```

#06_ Editando o Projeto Simples do Node.JS o VSCode no Linux Mint<br>
```bash
#OBSERVAÇÃO IMPORTANTE: nesse exemplo vamos editar o arquivo index.js utilizando o 
#Microsoft Visual Studio VSCode (O mesmo deve está instalado e configurado).

#abrindo o diretório de projeto do Node.JS no VSCode
code .

#criando o script em JavaScript do projeto do Node.JS
01) criando um novo arquivo: (Atalho) Ctrl + N
02) copiar e colar o código abaixo: 
03) salvar o arquivo com o nome: index.js (Atalho) Ctrl + S
```
```js
// Criando as variáveis express e app
var express = require ('express'); 
var app = express();

// Mensagem que será mostrada no browser (navegador) 
app.get('/', function (req, res) {
  res.send('Robson Vaamonde #BoraParaPrática!!!');
});

// Porta padrão utilizada pela aplicação do Node.JS
app.listen(3000, function() {
  console.log('Aplicativo de exemplo ouvindo na porta 3000');
});
```

#07_ Executando o Projeto Simples do Node.JS no Linux Mint<br>
```bash
Abrir o Terminal do VSCode: (Atalho): Ctrl + J
  node index.js &
```

#08_ Acessando o Projeto Simples do Node.JS no Linux Mint<br>
```bash
#listando a porta de conexão da aplicação do Node.JS
#opção do comando lsof: -n (network number), -P (port number), -i (list IP Address), -s (alone directs)
sudo lsof -nP -iTCP:'3000' -sTCP:LISTEN

#acessando o projeto via Navegador
google chrome ou firefox URL: http://localhost:3000/
```