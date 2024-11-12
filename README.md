# BootcampDIO-AI-102

![Projeto Exemplo](https://miro.medium.com/v2/resize:fit:659/0*ROmT-rhiAteKkbRK.png)

<h2 align="center">Descrição do Repositório</h2>

<p align="center">
  <img src="https://img.shields.io/badge/vers%C3%A3o-1.0.0-blue" />
  <img src="https://img.shields.io/badge/licen%C3%A7a-MIT-green" />
</p>

<p align="center">
  Este repositório contém vários projetos desenvolvidos durante o BootcampDIO-AI-102. Cada projeto tem seu próprio objetivo e fornece exemplos de como utilizar diferentes tecnologias para resolver problemas específicos.
</p>

## Projetos

### Projeto 1: Analisador de Documentos

**Descrição**: Este projeto fornece uma base para a criação de um analisador de documentos usando Python.

**Tecnologias Utilizadas**:
- Python 3.8+
- Azure Storage
- VSCode
- Git & GitHub

**Estrutura do Projeto**:
<pre>
projeto1-analisador_de_documentos/
├── DOCS/
│   ├── .env
│   ├── .gitignore
│   ├── .vscode/
│   ├── src/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   └── services/
│   │       ├── blob_service.py
│   │       └── credit_card_service.py
└── README.md
</pre>

**Como Executar o Projeto**:
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu_usuario/projeto1-analisador_de_documentos.git
   cd projeto1-analisador_de_documentos
Crie um ambiente virtual e ative-o:
python -m venv venv
source venv/bin/activate  # Para Linux e macOS
.\venv\Scripts\activate   # Para Windows
Instale as dependências:
pip install -r requirements.txt
Configure as variáveis de ambiente:

Crie um arquivo .env na pasta DOCS e adicione suas variáveis de ambiente conforme necessário.
Execute a aplicação:
python src/app.py
o outro projeto é um analisador de artigos técnicos: segue: # Azure Open AI no VNet ## Comunidade DEV ### Navegação - Pesquisa - Fazer login - Criar conta --- **Kenichiro Nakamura** Postado em 12 de outubro de 2023 Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Embora os modelos em si sejam os mesmos, existem muitas diferenças, incluindo: custo, funcionalidades, tipo de modelos e versões, geolocalização, suporte de segurança, etc. Um dos aspectos mais importantes quando usamos isso em um ambiente empresarial é, claro, a segurança. Ao usar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro do VNet, portanto, nenhuma informação flui para o público. ### Implantação de Exemplo O repositório de exemplos do Azure fornece arquivos bicep de exemplo para implantar o Azure Open AI em um ambiente VNet. GitHub: [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac) As principais funcionalidades utilizadas pelo bicep são: - Integração VNet para Web App - Endpoint Privado para Azure Open AI - Endpoint Privado para Pesquisa Cognitiva - Zona DNS Privada Ao usar esses recursos, todo o tráfego de saída do Web App é roteado apenas dentro do VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desativam o endereço IP público, portanto, não há mais um endpoint de interface pública disponível. ### Implantar O arquivo bicep implantará os seguintes recursos do Azure. Vamos implantar e confirmar como funciona. Eu criei um grupo de recursos na região East US para meu próprio teste. ```bash git clone https://github.com/Azure-Samples/openai-enterprise-iac cd openai-enterprise-iac az group create -n openaitest -l eastus az deployment group create -g openaitest -f .\infra\main.bicep Uma vez que eu execute o comando acima, vejo que a implantação começou. Espere até que a implantação seja concluída. Teste Vamos ver se a implantação foi bem-sucedida. Azure Open AI: Vamos tentar o acesso público primeiro. Eu consegui criar uma implantação sem nenhum problema. Mas quando eu tento a partir do playground do Chat no meu Portal do Azure, vejo o seguinte erro. E quanto ao acesso via API Web? A partir de uma ferramenta avançada do App Service, eu me loguei em uma sessão Bash e primeiro eu faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado está sendo retornado. Então, eu uso o comando curl para enviar uma solicitação ao endpoint. Comentários Principais (0) Inscrever-se Criar modelo Modelos permitem que você rapidamente responda a perguntas frequentes ou armazene trechos para reutilização. Código de Conduta Reportar abuso Você tem certeza de que deseja ocultar este comentário? Ele se tornará oculto na sua postagem, mas ainda será visível através do permalink do comentário. Confirme Para mais ações, você pode considerar bloquear esta pessoa e/ou reportar abuso. Leia a seguir Como criar um sistema de autenticação de imagem com python, streamlit e canva! Apresentando o Sistema DNA-KEY: Levando o Gerador de Senhas para o Próximo Nível! Apresentando o Stable Diffusion 3.5 Entendendo Tags e Checkout do Git Kenichiro Nakamura Seguindo desde 3 de fevereiro de 2018 Mais de Kenichiro Nakamura Azure ML Prompt flow: Use segurança de conteúdo antes de enviar uma solicitação para LLM Não perca tempo escrevendo README, use readme-ai em vez disso C#: Azure Open AI e Chamadas de Função Obrigado ao nosso patrocinador Diamond Neon por apoiar nossa comunidade. Comunidade DEV — Uma rede social construtiva e inclusiva para desenvolvedores de software. Com você a cada passo da sua jornada. Home DEV++ Podcasts Vídeos Tags Ajuda DEV Forem Loja Anuncie no DEV Desafios DEV Destaque DEV Sobre Contato Guias de Banco de Dados Postgres Gratuitos Comparações de Software Código de Conduta Política de Privacidade Termos de Uso Construído no Forem — o software de código aberto que alimenta o DEV e outras comunidades inclusivas. Feito com amor e Ruby on Rails. Comunidade DEV © 2016 - 2024. Estamos em um lugar onde codificadores compartilham, se mantêm atualizados e crescem em suas carreiras. ```markdown # Azure Open AI no VNet ## Comunidade DEV ### Navegação - Pesquisa - Fazer login - Criar conta --- **Kenichiro Nakamura** Postado em 12 de outubro de 2023 Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Embora os modelos em si sejam os mesmos, existem muitas diferenças, incluindo: custo, funcionalidades, tipo de modelos e versões, geolocalização, suporte de segurança, etc. Um dos aspectos mais importantes quando usamos isso em um ambiente empresarial é, claro, a segurança. Ao usar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro do VNet, portanto, nenhuma informação flui para o público. ### Implantação de Exemplo O repositório de exemplos do Azure fornece arquivos bicep de exemplo para implantar o Azure Open AI em um ambiente VNet. GitHub: [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac) As principais funcionalidades utilizadas pelo bicep são: - Integração VNet para Web App - Endpoint Privado para Azure Open AI - Endpoint Privado para Pesquisa Cognitiva - Zona DNS Privada Ao usar esses recursos, todo o tráfego de saída do Web App é roteado apenas dentro do VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desativam o endereço IP público, portanto, não há mais um endpoint de interface pública disponível. ### Implantar O arquivo bicep implantará os seguintes recursos do Azure. Vamos implantar e confirmar como funciona. Eu criei um grupo de recursos na região East US para meu próprio teste. ```bash git clone https://github.com/Azure-Samples/openai-enterprise-iac cd openai-enterprise-iac az group create -n openaitest -l eastus az deployment group create -g openaitest -f .\infra\main.bicep Uma vez que eu execute o comando acima, vejo que a implantação começou. Espere até que a implantação seja concluída. Teste Vamos ver se a implantação foi bem-sucedida. Azure Open AI: Vamos tentar o acesso público primeiro. Eu consegui criar uma implantação sem nenhum problema. Mas quando eu tento a partir do playground do Chat no meu Portal do Azure, vejo o seguinte erro. E quanto ao acesso via API Web? A partir de uma ferramenta avançada do App Service, eu me loguei em uma sessão Bash e primeiro eu faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado está sendo retornado. Então, eu uso o comando curl para enviar uma solicitação ao endpoint. Comentários Principais (0) Inscrever-se Criar modelo Modelos permitem que você rapidamente responda a perguntas frequentes ou armazene trechos para reutilização. Código de Conduta Reportar abuso Você tem certeza de que deseja ocultar este comentário? Ele se tornará oculto na sua postagem, mas ainda será visível através do permalink do comentário. Confirme Para mais ações, você pode considerar bloquear esta pessoa e/ou reportar abuso. Leia a seguir Como criar um sistema de autenticação de imagem com python, streamlit e canva! Apresentando o Sistema DNA-KEY: Levando o Gerador de Senhas para o Próximo Nível! Apresentando o Stable Diffusion 3.5 Entendendo Tags e Checkout do Git Kenichiro Nakamura Seguindo desde 3 de fevereiro de 2018 Mais de Kenichiro Nakamura Azure ML Prompt flow: Use segurança de conteúdo antes de enviar uma solicitação para LLM Não perca tempo escrevendo README, use readme-ai em vez disso C#: Azure Open AI e Chamadas de Função Obrigado ao nosso patrocinador Diamond Neon por apoiar nossa comunidade. Comunidade DEV — Uma rede social construtiva e inclusiva para desenvolvedores de software. Com você a cada passo da sua jornada. Home DEV++ Podcasts Vídeos Tags Ajuda DEV Forem Loja Anuncie no DEV Desafios DEV Destaque DEV Sobre Contato Guias de Banco de Dados Postgres Gratuitos Comparações de Software Código de Conduta Política de Privacidade Termos de Uso Construído no Forem — o software de código aberto que alimenta o DEV e outras comunidades inclusivas. Feito com amor e Ruby on Rails. Comunidade DEV © 2016 - 2024. Estamos em um lugar onde codificadores compartilham, se mantêm atualizados e crescem em sua
Vamos incluir o projeto do analisador de artigos técnicos no seu README.md, junto com o primeiro projeto. Aqui está como ficaria:

markdown
# BootcampDIO-AI-102

![Projeto Exemplo](https://miro.medium.com/v2/resize:fit:659/0*ROmT-rhiAteKkbRK.png)

<h2 align="center">Descrição do Repositório</h2>

<p align="center">
  <img src="https://img.shields.io/badge/vers%C3%A3o-1.0.0-blue" />
  <img src="https://img.shields.io/badge/licen%C3%A7a-MIT-green" />
</p>

<p align="center">
  Este repositório contém vários projetos desenvolvidos durante o BootcampDIO-AI-102. Cada projeto tem seu próprio objetivo e fornece exemplos de como utilizar diferentes tecnologias para resolver problemas específicos.
</p>

## Projetos

### Projeto 1: Analisador de Documentos

**Descrição**: Este projeto fornece uma base para a criação de um analisador de documentos usando Python.

**Tecnologias Utilizadas**:
- Python 3.8+
- Azure Storage
- VSCode
- Git & GitHub

**Estrutura do Projeto**:
<pre>
projeto1-analisador_de_documentos/
├── DOCS/
│   ├── .env
│   ├── .gitignore
│   ├── .vscode/
│   ├── src/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   └── services/
│   │       ├── blob_service.py
│   │       └── credit_card_service.py
└── README.md
</pre>

**Como Executar o Projeto**:
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu_usuario/projeto1-analisador_de_documentos.git
   cd projeto1-analisador_de_documentos
Crie um ambiente virtual e ative-o:

bash
python -m venv venv
source venv/bin/activate  # Para Linux e macOS
.\venv\Scripts\activate   # Para Windows
Instale as dependências:

bash
pip install -r requirements.txt
Configure as variáveis de ambiente:

Crie um arquivo .env na pasta DOCS e adicione suas variáveis de ambiente conforme necessário.

Execute a aplicação:

bash
python src/app.py
Projeto 2: Analisador de Artigos Técnicos
Descrição: Este projeto demonstra como utilizar o Azure Open AI em um VNet para análise de artigos técnicos.

Tecnologias Utilizadas:

Azure Open AI

Bicep

VNet

App Service

Estrutura do Projeto: <pre> projeto2-analisador_de_artigos/ ├── DOCS/ │ ├── ... └── README.md </pre>
Como Executar o Projeto:

Clone o repositório:
git clone https://github.com/seu_usuario/projeto2-analisador_de_artigos.git
cd projeto2-analisador_de_artigos

Crie um grupo de recursos no Azure:
az group create -n openaitest -l eastus

Implante os recursos usando Bicep:
az deployment group create -g openaitest -f .\infra\main.bicep
Verifique a implantação e teste o acesso via API.



