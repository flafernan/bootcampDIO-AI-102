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
2. Crie um ambiente virtual e ative-o:
    python -m venv venv
    source venv/bin/activate  # Para Linux e macOS
    .\venv\Scripts\activate   # Para Windows

3. Instale as dependências:
    pip install -r requirements.txt
    Configure as variáveis de ambiente:
4. Configure as variáveis de ambiente:
    Crie um arquivo .env na pasta DOCS e adicione suas variáveis de ambiente conforme necessário.
    Execute a aplicação:
    python src/app.py

**Projeto 2 Desenvolver uma solução de Informação de Documentos**:

Descrição: Este projeto demonstra como utilizar o Azure Open AI em um VNet para análise de artigos técnicos.

Tecnologias Utilizadas:

Azure Open AI
Bicep
VNet
App Service

**Como Executar o Projeto**:
  Clone o repositório:
  
  Crie um grupo de recursos no Azure:
    "az group create -n openaitest -l eastus"
    
  Implante os recursos usando
  
  Verifique a implantação e teste o acesso via API.
  




