# World Games

Uma aplicação web de e-commerce desenvolvida com Python e Streamlit, oferecendo uma experiência intuitiva para exploração e compra de produtos relacionados a jogos.

## Descrição

World Games é uma plataforma de vendas que demonstra boas práticas de desenvolvimento orientado a objetos (POO) em Python, combinando um frontend responsivo em Streamlit com uma arquitetura bem estruturada de backend. O projeto implementa funcionalidades como autenticação de usuários, catálogo de produtos, carrinho de compras e histórico de pedidos.

## Principais Tecnologias

**Frontend & UI:**
- **Framework:** [Streamlit](https://streamlit.io/)
- **Linguagem:** [Python](https://www.python.org/)
- **Processamento de Dados:** [Pandas](https://pandas.pydata.org/), [NumPy](https://numpy.org/)
- **Visualização:** [Altair](https://altair-viz.github.io/), [Pillow](https://python-pillow.org/)
- **HTTP Client:** [Requests](https://docs.python-requests.org/)

**Backend & Banco de Dados:**
- **Banco de Dados:** [SQLite](https://www.sqlite.org/)
- **Driver SQL:** Python `sqlite3` (nativo)

**Arquitetura:**
- **Design Pattern:** MVC (Model-View-Controller)
- **Data Access:** DAO (Data Access Objects)
- **Session Management:** Streamlit `session_state`

## Principais Funcionalidades

- **Autenticação de Usuários:** Sistema de login e cadastro seguro
- **Catálogo de Produtos:** Exploração de 16+ produtos com imagens e descrições
- **Carrinho de Compras:** Adicionar e gerenciar itens no carrinho
- **Histórico de Pedidos:** Visualizar pedidos finalizados por usuário
- **Cadastro Completo:** Registro de contato com nome, telefone e data de nascimento
- **Interface Responsiva:** Design adaptável com Streamlit
- **Gerenciamento de Dados:** Persistência em SQLite com camadas de acesso estruturadas

## Como Começar

Siga as instruções abaixo para configurar e executar o projeto em seu ambiente local.

### Pré-requisitos

- [Python](https://www.python.org/) (versão 3.8 ou superior)
- [pip](https://pip.pypa.io/en/latest/) (gerenciador de pacotes Python)
- [Git](https://git-scm.com/)

### Instalação

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/FernandoHN99/World-Games.git
   cd World-Games
   ```

2. **Crie um ambiente virtual (opcional, mas recomendado):**
   ```bash
   python3 -m venv venv
   ```

3. **Ative o ambiente virtual:**
   
   **No macOS/Linux:**
   ```bash
   source venv/bin/activate
   ```
   
   **No Windows:**
   ```bash
   venv\Scripts\activate
   ```

4. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```

### Executando a Aplicação

**Modo de desenvolvimento local:**
```bash
streamlit run src/main.py
```

A aplicação estará disponível em `http://localhost:8501`

## Estrutura do Projeto

```
World-Games/
├── src/
│   ├── main.py              # Ponto de entrada da aplicação
│   ├── controllers/         # Controladores da lógica de negócio
│   │   ├── app_controller.py
│   │   ├── usuario_controller.py
│   │   ├── item_controller.py
│   │   ├── pedido_controller.py
│   │   └── contato_controller.py
│   ├── dao/                 # Data Access Objects
│   │   ├── usuario_dao.py
│   │   ├── item_dao.py
│   │   ├── pedido_dao.py
│   │   └── contato_dao.py
│   ├── models/              # Modelos de dados
│   │   ├── usuario/
│   │   ├── item/
│   │   ├── pedido/
│   │   ├── contato/
│   │   ├── util/
│   │   └── enum/
│   └── view/                # Views do Streamlit
│       ├── login_view.py
│       ├── cadastro_view.py
│       └── home_view.py
├── databases/
│   └── sqlite.db            # Banco de dados SQLite
├── assets/                  # Imagens dos produtos (16 items)
├── requirements.txt         # Dependências do projeto
├── .streamlit/
│   └── config.toml          # Configuração do Streamlit
└── README.md                # Este arquivo
```

## Padrões Implementados

### Model-View-Controller (MVC)
- **Models:** Classes de domínio (Usuario, Item, Pedido, Contato)
- **Views:** Componentes Streamlit para diferentes páginas
- **Controllers:** Lógica de negócio intermediária

### Data Access Objects (DAO)
Implementação de DAOs para cada entidade:
- `Usuario_DAO`: Gerenciamento de usuários
- `Item_DAO`: Gerenciamento de produtos
- `Pedido_DAO`: Gerenciamento de pedidos
- `Contato_DAO`: Gerenciamento de dados de contato

### Singleton Pattern
Todos os DAOs implementam o padrão Singleton para garantir uma única instância no ciclo de vida da aplicação.

## Deploy

A aplicação está configurada para deploy no [Render](https://render.com/) com deploy automático:

- **URL:** https://world-games.onrender.com
- **Runtime:** Python 3
- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `streamlit run src/main.py --server.port $PORT --server.address 0.0.0.0`

### Variáveis de Ambiente

Nenhuma variável de ambiente é obrigatória para execução, pois o banco SQLite é criado localmente.

## Estrutura de Banco de Dados

A aplicação utiliza as seguintes tabelas:

- **Usuarios:** email, senha, contato_id
- **Contatos:** id, nome, sexo, telefone, data_nascimento
- **Itens:** id, nome, descricao, valor, plataforma, imagem
- **Pedidos:** id, email_usuario, id_item, quantidade, status, data_hora, numero_pedido

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para fazer um fork do projeto, criar uma branch com suas mudanças e submeter um pull request.

## Licença

Este projeto é fornecido como está para fins educacionais.

## Contato

Para dúvidas ou sugestões sobre o projeto, entre em contato através do GitHub.

---

**Desenvolvido com ❤️ utilizando Python e Streamlit**
