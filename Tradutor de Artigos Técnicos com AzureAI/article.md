```markdown
# Azure Open AI no VNet

## Comunidade DEV

### Navegação

- Pesquisa
- Fazer login
- Criar conta

---

**Kenichiro Nakamura**  
Postado em 12 de outubro de 2023  

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Embora os modelos em si sejam os mesmos, existem muitas diferenças, incluindo: custo, funcionalidades, tipo de modelos e versões, geolocalização, suporte de segurança, etc. Um dos aspectos mais importantes quando usamos isso em um ambiente empresarial é, claro, a segurança.

Ao usar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro do VNet, portanto, nenhuma informação flui para o público.

### Implantação de Exemplo

O repositório de exemplos do Azure fornece arquivos bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.  
GitHub: [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

As principais funcionalidades utilizadas pelo bicep são:
- Integração VNet para Web App
- Endpoint Privado para Azure Open AI
- Endpoint Privado para Pesquisa Cognitiva
- Zona DNS Privada

Ao usar esses recursos, todo o tráfego de saída do Web App é roteado apenas dentro do VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desativam o endereço IP público, portanto, não há mais um endpoint de interface pública disponível.

### Implantar

O arquivo bicep implantará os seguintes recursos do Azure. Vamos implantar e confirmar como funciona.  
Eu criei um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação começou. Espere até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.  
Azure Open AI: Vamos tentar o acesso público primeiro. Eu consegui criar uma implantação sem nenhum problema. Mas quando eu tento a partir do playground do Chat no meu Portal do Azure, vejo o seguinte erro.

E quanto ao acesso via API Web? A partir de uma ferramenta avançada do App Service, eu me loguei em uma sessão Bash e primeiro eu faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado está sendo retornado. Então, eu uso o comando curl para enviar uma solicitação ao endpoint.

---

**Comentários Principais (0)**  
**Inscrever-se**  
**Criar modelo**  
Modelos permitem que você rapidamente responda a perguntas frequentes ou armazene trechos para reutilização.

---

**Código de Conduta**  
- Reportar abuso

Você tem certeza de que deseja ocultar este comentário? Ele se tornará oculto na sua postagem, mas ainda será visível através do permalink do comentário.  
Confirme

Para mais ações, você pode considerar bloquear esta pessoa e/ou reportar abuso.

### Leia a seguir

- Como criar um sistema de autenticação de imagem com python, streamlit e canva!
- Apresentando o Sistema DNA-KEY: Levando o Gerador de Senhas para o Próximo Nível!
- Apresentando o Stable Diffusion 3.5
- Entendendo Tags e Checkout do Git

**Kenichiro Nakamura**  
Seguindo desde 3 de fevereiro de 2018

---

**Mais de Kenichiro Nakamura**  
- Azure ML Prompt flow: Use segurança de conteúdo antes de enviar uma solicitação para LLM
- Não perca tempo escrevendo README, use readme-ai em vez disso
- C#: Azure Open AI e Chamadas de Função

**Obrigado ao nosso patrocinador Diamond Neon por apoiar nossa comunidade.**  
Comunidade DEV — Uma rede social construtiva e inclusiva para desenvolvedores de software. Com você a cada passo da sua jornada.

---

**Home**  
**DEV++**  
**Podcasts**  
**Vídeos**  
**Tags**  
**Ajuda DEV**  
**Forem**  
**Loja**  
**Anuncie no DEV**  
**Desafios DEV**  
**Destaque DEV**  
**Sobre**  
**Contato**  
**Guias de Banco de Dados Postgres Gratuitos**  
**Comparações de Software**  
**Código de Conduta**  
**Política de Privacidade**  
**Termos de Uso**  

**Construído no Forem — o software de código aberto que alimenta o DEV e outras comunidades inclusivas. Feito com amor e Ruby on Rails.**  
Comunidade DEV © 2016 - 2024.  
Estamos em um lugar onde codificadores compartilham, se mantêm atualizados e crescem em suas carreiras.
```

```markdown
# Azure Open AI no VNet

## Comunidade DEV

### Navegação

- Pesquisa
- Fazer login
- Criar conta

---

**Kenichiro Nakamura**  
Postado em 12 de outubro de 2023  

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Embora os modelos em si sejam os mesmos, existem muitas diferenças, incluindo: custo, funcionalidades, tipo de modelos e versões, geolocalização, suporte de segurança, etc. Um dos aspectos mais importantes quando usamos isso em um ambiente empresarial é, claro, a segurança.

Ao usar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro do VNet, portanto, nenhuma informação flui para o público.

### Implantação de Exemplo

O repositório de exemplos do Azure fornece arquivos bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.  
GitHub: [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

As principais funcionalidades utilizadas pelo bicep são:
- Integração VNet para Web App
- Endpoint Privado para Azure Open AI
- Endpoint Privado para Pesquisa Cognitiva
- Zona DNS Privada

Ao usar esses recursos, todo o tráfego de saída do Web App é roteado apenas dentro do VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desativam o endereço IP público, portanto, não há mais um endpoint de interface pública disponível.

### Implantar

O arquivo bicep implantará os seguintes recursos do Azure. Vamos implantar e confirmar como funciona.  
Eu criei um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação começou. Espere até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.  
Azure Open AI: Vamos tentar o acesso público primeiro. Eu consegui criar uma implantação sem nenhum problema. Mas quando eu tento a partir do playground do Chat no meu Portal do Azure, vejo o seguinte erro.

E quanto ao acesso via API Web? A partir de uma ferramenta avançada do App Service, eu me loguei em uma sessão Bash e primeiro eu faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado está sendo retornado. Então, eu uso o comando curl para enviar uma solicitação ao endpoint.

---

**Comentários Principais (0)**  
**Inscrever-se**  
**Criar modelo**  
Modelos permitem que você rapidamente responda a perguntas frequentes ou armazene trechos para reutilização.

---

**Código de Conduta**  
- Reportar abuso

Você tem certeza de que deseja ocultar este comentário? Ele se tornará oculto na sua postagem, mas ainda será visível através do permalink do comentário.  
Confirme

Para mais ações, você pode considerar bloquear esta pessoa e/ou reportar abuso.

### Leia a seguir

- Como criar um sistema de autenticação de imagem com python, streamlit e canva!
- Apresentando o Sistema DNA-KEY: Levando o Gerador de Senhas para o Próximo Nível!
- Apresentando o Stable Diffusion 3.5
- Entendendo Tags e Checkout do Git

**Kenichiro Nakamura**  
Seguindo desde 3 de fevereiro de 2018

---

**Mais de Kenichiro Nakamura**  
- Azure ML Prompt flow: Use segurança de conteúdo antes de enviar uma solicitação para LLM
- Não perca tempo escrevendo README, use readme-ai em vez disso
- C#: Azure Open AI e Chamadas de Função

**Obrigado ao nosso patrocinador Diamond Neon por apoiar nossa comunidade.**  
Comunidade DEV — Uma rede social construtiva e inclusiva para desenvolvedores de software. Com você a cada passo da sua jornada.

---

**Home**  
**DEV++**  
**Podcasts**  
**Vídeos**  
**Tags**  
**Ajuda DEV**  
**Forem**  
**Loja**  
**Anuncie no DEV**  
**Desafios DEV**  
**Destaque DEV**  
**Sobre**  
**Contato**  
**Guias de Banco de Dados Postgres Gratuitos**  
**Comparações de Software**  
**Código de Conduta**  
**Política de Privacidade**  
**Termos de Uso**  

**Construído no Forem — o software de código aberto que alimenta o DEV e outras comunidades inclusivas. Feito com amor e Ruby on Rails.**  
Comunidade DEV © 2016 - 2024.  
Estamos em um lugar onde codificadores compartilham, se mantêm atualizados e crescem em suas carreiras.