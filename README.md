# 🤖 Mymy Bot

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12&height=200&section=header&text=Mymy%20Bot&fontSize=80&fontColor=fff&animation=fadeIn&fontAlignY=38&desc=Automação%20de%20Vendas%20para%20Discord&descAlignY=51&descAlign=62" />
</div>

## 🎬 Demonstração em Ação

<div align="center">
<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="800">
<br>
<em>Interface de compra interativa do Mymy Bot, construída com discord.py</em>
</div>

<br>

<div align="center">
<table border="0" cellpadding="10">
<tr align="center">
<td><img src="https://media.discordapp.net/attachments/1326972176934371421/1402092268042719312/image.png?ex=6892a7ae&is=6891562e&hm=d82dc9b0d37b767286327c35bf7a9b23c345fe2212fa6c42fa7785e03979aa81&=&format=webp&quality=lossless&width=863&height=254" width="270"><br><sub><b>1. Seleção de Produto</b></sub></td>
<td><img src="https://media.discordapp.net/attachments/1326972176934371421/1402101707248504972/image.png?ex=6892b078&is=68915ef8&hm=9cbcb729acd699d185455699d0782e8e0e7aaaebb272fe6d2690ac848b0dbaeb&=&format=webp&quality=lossless&width=426&height=249" width="270"><br><sub><b>2. Recebimento do produto</b></sub></td>
<td><img src="https://media.discordapp.net/attachments/1326972176934371421/1402092548113174609/image.png?ex=6892a7f1&is=68915671&hm=7e185470c298a150dc4a395de924c09123fd36d1a6ae88e5fe129d23235af05e&=&format=webp&quality=lossless&width=763&height=349" width="270"><br><sub><b>3. Comandos de administração</b></sub></td>
<td><img src="https://media.discordapp.net/attachments/1326972176934371421/1402100881209688166/image.png?ex=6892afb3&is=68915e33&hm=84bc86a548587a2573812d6c8e617b29acceaab16da648b7a030c3a9e5232079&=&format=webp&quality=lossless&width=715&height=670" width="270"><br><sub><b>4. Logs automaticos</b></sub></td>
</tr>
</table>
</div>

## 🚀 Sobre o Projeto

<img align="right" width="350" src="https://user-images.githubusercontent.com/74038190/229223263-cf2e4b07-2615-4f87-9c38-e37600f8381a.gif" />

**Mymy Bot** é um bot para Discord robusto e completo, projetado para automatizar todo o ciclo de vendas de produtos digitais, como keys de software. Ele oferece uma experiência de compra fluida para os usuários e ferramentas de gerenciamento poderosas para os administradores.

### 🛠️ Tecnologias Principais

- **discord.py** - Interação total com a API do Discord
- **Mercado Pago SDK** - Integração nativa para pagamentos PIX
- **aiosqlite** - Banco de dados assíncrono e eficiente
- **Estrutura de Cogs** - Código modular e organizado

> 🎯 **A automação é o pilar deste projeto, permitindo que a loja funcione 24/7 sem intervenção manual!**

## ✨ Funcionalidades Principais

<div align="center">

| 🛒 **Automação de Vendas** | 📦 **Gerenciamento de Estoque** | 🛡️ **Administração** | ⚙️ **Utilitários** |
|:------------------------:|:------------------------------:|:-------------------:|:-----------------:|
| Menus Interativos | CRUD de Produtos | Comandos Exclusivos | Comandos Úteis |
| Geração de PIX Automática | Controle de Estoque | Sistema de Permissões | Templates de Embeds |
| Verificação em Tempo Real | Adição de Keys em Massa | Logs Completos | Tratamento de Erros |
| **Entrega Automática na DM** | Consulta de Keys | Avisos Customizados | Tradução de URLs |

</div>

## 🔄 Fluxo de Funcionamento

```mermaid
graph TB
    A[🚀 Usuário] --> B[🛒 Acessa Menu de Compra]
    B --> C[📋 Seleciona Menu/Categoria]
    C --> D[📦 Escolhe Submenu/Produto]
    D --> E[🎫 Abre Ticket de Compra]
    E --> F[💵 Clica em "Gerar PIX"]
    F --> G{🤖 Bot gera QR Code<br/>e Código PIX com Valor}
    G --> H[💳 Usuário realiza o pagamento]
    H --> I{🔍 Bot verifica o<br/>pagamento via API}
    I -- Aprovado --> J[🔑 **ENVIO AUTOMÁTICO**<br/>Bot busca Key no DB<br/>e envia na DM]
    J --> K[✅ Ticket é fechado<br/>conforme tempo definido]
    I -- Pendente/Erro --> L[⏳ Aguarda ou informa o erro]
    
    style A fill:#5865F2,stroke:#fff,stroke-width:2px,color:#fff
    style I fill:#00B1EA,stroke:#fff,stroke-width:2px,color:#fff
    style J fill:#2ecc71,stroke:#fff,stroke-width:2px,color:#fff
```

<details>
<summary><b>📋 Clique para ver o Passo a Passo Detalhado</b></summary>

1. **🛒 Início**: O administrador usa `/menu_compra` para exibir o painel de vendas.
2. **🖱️ Navegação**: O usuário navega pelos menus e submenus organizados hierarquicamente.
3. **📦 Seleção**: O usuário escolhe o produto desejado dentro do submenu específico.
4. **🎫 Ticket**: Um canal de ticket privado é criado automaticamente para o usuário e a staff.
5. **💵 Pagamento**: Dentro do ticket, o usuário clica no botão para gerar o pagamento PIX com o valor configurado.
6. **🤖 Automação**: O bot se comunica com o Mercado Pago e exibe o QR Code e o código "copia e cola".
7. **🔍 Verificação**: O bot monitora o status do pagamento em tempo real.
8. **🔑 Entrega Automática**: Assim que o pagamento é aprovado, o bot **automaticamente** busca uma key válida no banco de dados (usando produto_id) e a envia na mensagem direta (DM) do usuário.
9. **✅ Finalização**: O bot envia uma confirmação no ticket e o fecha conforme o tempo de entrega configurado.

</details>

## 🏗️ Arquitetura do Sistema

```mermaid
graph TD
    subgraph "📱 Interface (Discord)"
        A[👤 Usuário] <--> B[🤖 Bot discord.py]
        B -- Comandos --> C[🔨 Cogs de Comandos]
        B -- Eventos --> D[👂 Listeners de Eventos]
    end

    subgraph "⚙️ Core do Bot"
        C --> E[📦 Produtos]
        C --> F[💵 Pagamentos]
        C --> G[🛡️ Administração]
        C --> H[🎵 Miscelânea]
    end

    subgraph "🔗 Serviços Externos"
        F <--> I[🏦 API Mercado Pago]
        H <--> J[🎶 API SongLink]
    end

    subgraph "🗄️ Camada de Dados"
        E <--> K[📁 db/pagamentos.db]
        F <--> K
    end

    style A fill:#5865F2,stroke:#fff,stroke-width:2px,color:#fff
    style B fill:#7289DA,stroke:#fff,stroke-width:2px,color:#fff
    style I fill:#00B1EA,stroke:#fff,stroke-width:2px,color:#fff
    style K fill:#003B57,stroke:#fff,stroke-width:2px,color:#fff
```

## 📦 Estrutura do Projeto

```
📁 Mymy-Bot/
├── 🐍 main.py                 # Ponto de entrada do bot
├── 📁 cogs/
│   ├── 🛡️ administracao.py    # Comandos de administração
│   ├── 🛒 menu_compra.py      # Lógica do menu de compras e tickets
│   ├── 🎵 misc.py             # Comandos diversos
│   ├── 💵 pagamentos.py       # Integração com Mercado Pago
│   └── 📦 produtos.py         # Gerenciamento de produtos e keys
├── 📁 core/
│   ├── 👑 administracao.py    # Funções de verificação de permissão
│   └── ⚙️ sistema_config.py   # Configurações de canais e categorias
├── 📁 db/
│   ├── 📝 database.py         # Funções de interação com o banco de dados
│   └── 🗄️ pagamentos.db       # Banco de dados SQLite
├── 📁 template/
│   └── 🎨 embed.py            # Templates de embeds padronizados
├── 📁 config/
│   └── 🔑 .env                # Arquivo para credenciais e tokens
├── 📋 requirements.txt        # Dependências Python
└── 📖 README.md               # Esta documentação
```

## ⚡ Instalação e Configuração

### 📋 Pré-requisitos

- **Python 3.10+**
- **Git**
- **🤖 Conta de Desenvolvedor Discord**
- **💳 Conta no Mercado Pago**

### 🚀 Instalação em 4 Passos

```bash
# 1️⃣ Clone o repositório
git clone https://github.com/Ansbach-0/Mymy-Bot.git
cd Mymy-Bot

# 2️⃣ Instale as dependências
pip install -r requirements.txt

# 3️⃣ Configure as variáveis de ambiente
# Crie um arquivo .env dentro da pasta 'config/'

# 4️⃣ Execute o bot
python main.py
```

### 🔧 Configuração do Ambiente (config/.env)

```env
# Token do seu bot do Discord
TOKEN_DISCORD="SEU_TOKEN_AQUI"

# Access Token do Mercado Pago
MERCADO_PAGO_ACCESS_TOKEN="SEU_ACCESS_TOKEN_AQUI"

# ID do seu servidor (guild) do Discord
GUILD_ID=SEU_ID_DE_SERVIDOR_AQUI

# ID do cargo de administrador
ADMIN_ROLE_ID=ID_DO_CARGO_ADMIN_AQUI
```

## 🎮 Como Usar

### 👑 Comandos de Administrador

| Comando | Descrição | Exemplo de Uso |
|---------|-----------|----------------|
| `/criar_produto` | Cria um produto com menu, submenu, valor e tempo de entrega. | `/criar_produto menu:"Jogos" submenu:"Minecraft" valor:25.99 tempo:"Instantâneo"` |
| `/adicionar_keys` | Adiciona keys via arquivo .txt enviado no Discord. | `/adicionar_keys produto_id:1 keys:[arquivo.txt]` |
| `/menu_compra` | Envia o painel de compras no canal. | `/menu_compra` |
| `/aviso` | Envia um aviso customizado. | `/aviso titulo:"Manutenção" msg:"Em 10min"` |
| `/enviar_key` | **⚠️ APENAS para correções manuais** - Envia key quando há falhas no sistema automático. | `/enviar_key usuario:@user produto:"Minecraft"` |

> **🔥 IMPORTANTE**: O sistema de entrega é **100% automático**! O comando `/enviar_key` existe apenas como backup para situações excepcionais onde o envio automático falhar por algum erro técnico.

### 🛒 Fluxo do Usuário

1. **Encontre** o canal com o menu de compras.
2. **Navegue** pelos menus organizados por categoria.
3. **Selecione** um submenu específico do produto desejado.
4. **Aguarde** a abertura do ticket privado automático.
5. **Clique** em "Gerar PIX" dentro do ticket.
6. **Pague** o valor configurado via QR Code ou código PIX.
7. **Receba automaticamente** sua key por mensagem direta conforme o tempo de entrega!

### 🚀 Sistema de Entrega Automática

O **Mymy Bot** foi projetado para funcionar de forma **completamente automatizada**:

- ✅ **Detecção automática**: O bot monitora pagamentos em tempo real
- ✅ **Busca automática**: Localiza automaticamente uma key válida no estoque
- ✅ **Envio automático**: Entrega a key diretamente na DM do usuário
- ✅ **Confirmação automática**: Notifica sobre a entrega e fecha o ticket
- ✅ **Logs automáticos**: Registra toda a transação para auditoria

**Nenhuma intervenção manual é necessária!** O sistema funciona 24/7.

### 📊 Estrutura de Produtos

O sistema organiza os produtos de forma hierárquica:

```
📋 Menu (Categoria Principal)
└── 📦 Submenu (Produto Específico)
    ├── 💰 Valor (Preço configurado)
    ├── ⏱️ Tempo (Tempo de entrega)
    └── 🔑 Keys (Armazenadas por produto_id)
```

**Exemplo prático:**
- **Menu**: "Jogos"
- **Submenu**: "Minecraft Premium"
- **Valor**: R$ 25,99
- **Tempo**: "Instantâneo"
- **Keys**: Carregadas via arquivo .txt

## 🛠️ Stack Tecnológica

<div align="center">

| Tecnologia | Versão/SDK | Função |
|:----------:|:----------:|:-------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) | 3.10+ | Linguagem principal |
| ![Discord.py](https://img.shields.io/badge/Discord.py-5865F2?style=for-the-badge&logo=discord&logoColor=white) | 2.3+ | Interação com a API do Discord |
| ![Mercado Pago](https://img.shields.io/badge/Mercado%20Pago-00B1EA?style=for-the-badge&logo=mercadopago&logoColor=white) | 2.1.2+ | Gateway de Pagamento PIX |
| ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white) | 0.17+ | Banco de Dados Assíncrono |
| ![aiohttp](https://img.shields.io/badge/aiohttp-2C5282?style=for-the-badge&logo=aiohttp&logoColor=white) | 3.8+ | Requisições HTTP Assíncronas |

</div>

## 📊 Roadmap

| Status | Funcionalidade |
|:------:|:---------------|
| ✅ | Sistema básico de vendas com tickets |
| ✅ | Integração completa com Mercado Pago PIX |
| ✅ | Entrega automática de keys e logs |
| 🔄 | Dashboard web para administração |
| 💡 | Integração com outros gateways de pagamento |
| 💡 | Sistema de cupons de desconto |
| 💡 | Relatórios de vendas avançados |
| 💡 | API REST para integrações externas |

## 📄 Licença

Distribuído sob a **Licença MIT**. Veja `LICENSE` para mais informações.

> MIT License - Copyright (c) 2024 Vinícius Ansbach Costa

## 👨‍💻 Desenvolvedor

<div align="center">
  <img src="https://github.com/Ansbach-0.png" width="150px" style="border-radius: 50%;" alt="Vinícius Ansbach"/>
  <br><br>
  <h3>Vinícius Ansbach Costa</h3>
  <p><em>Desenvolvedor Python & Entusiasta de Automação</em></p>
  
  [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ansbach-0)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/vinicius-ansbach)
</div>

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12&height=120&section=footer&animation=fadeIn" />
  <br>
  <h3>⭐ Se este projeto foi útil para você, considere dar uma estrela! ⭐</h3>
  <br>
  <img src="https://visitor-badge.laobi.icu/badge?page_id=Ansbach-0.Mymy-Bot" alt="Contador de Visitantes"/>
  <br><br>
  <em>Feito com ❤️ e muito 🧉 por Vinícius Ansbach</em>
</div>
