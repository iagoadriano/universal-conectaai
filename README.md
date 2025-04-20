# Documentação do Projeto Universal ConectaAI

## Visão Geral

O Universal ConectaAI é uma plataforma modular para saúde e negócios que centraliza comunicações, automatiza processos e integra sistemas através de uma abordagem omnichannel com inteligência artificial.

Este documento fornece uma visão geral da arquitetura, componentes e instruções para executar o projeto.

## Arquitetura

O projeto segue uma arquitetura modular baseada em Python e Flask, organizada da seguinte forma:

```
universal_conectaai/
│
├── backend/                  # Aplicação backend principal
│   ├── app/                  # Código da aplicação
│   │   ├── __init__.py       # Inicialização da aplicação
│   │   ├── config.py         # Configurações da aplicação
│   │   ├── models/           # Modelos de dados
│   │   ├── api/              # Endpoints da API
│   │   ├── services/         # Serviços da aplicação
│   │   └── utils/            # Utilitários
│   │
│   ├── tests/                # Testes unitários e de integração
│   └── requirements.txt      # Dependências do backend
│
├── modules/                  # Módulos específicos da plataforma
│   ├── omnichannel/          # Módulo de comunicação omnichannel
│   ├── chatbot/              # Módulo de chatbot inteligente
│   ├── dashboard/            # Módulo de dashboard analítico
│   └── integration/          # Módulo de integração com sistemas externos
│
├── app.py                    # Ponto de entrada da aplicação
└── requirements.txt          # Dependências globais do projeto
```

## Componentes Principais

### 1. Backend

O backend é construído com Flask e fornece uma API RESTful para interação com os diferentes módulos da plataforma.

#### Modelos de Dados

- **User**: Gerenciamento de usuários do sistema
- **Channel**: Canais de comunicação (WhatsApp, e-mail, SMS, chat)
- **ChatbotFlow**: Fluxos configuráveis para o chatbot
- **Integration**: Integrações com sistemas externos
- **Conversation**: Conversas com usuários/clientes
- **Message**: Mensagens em uma conversa

#### Serviços

- **OmnichannelService**: Gerenciamento de comunicação omnichannel
- **ChatbotService**: Gerenciamento de chatbots inteligentes
- **DashboardService**: Gerenciamento de dashboard analítico e indicadores
- **IntegrationService**: Gerenciamento de integrações com sistemas externos

### 2. Módulos

Cada módulo é uma aplicação Flask independente que pode ser executada separadamente ou como parte da plataforma completa:

- **Omnichannel**: Centraliza a comunicação via WhatsApp, e-mail, SMS e chat online
- **Chatbot**: Implementa chatbots inteligentes com fluxos configuráveis
- **Dashboard**: Fornece métricas e relatórios analíticos
- **Integration**: Gerencia a integração com sistemas externos (EHR, CRM, ERP)

## Tecnologias Utilizadas

- **Backend**: Python, Flask, SQLAlchemy
- **Autenticação**: JWT (JSON Web Tokens)
- **Banco de Dados**: SQLite (desenvolvimento), PostgreSQL (produção)
- **Processamento de Linguagem Natural**: NLTK, spaCy
- **Testes**: Pytest

## Configuração do Ambiente

### Pré-requisitos

- Python 3.10 ou superior
- pip (gerenciador de pacotes Python)
- Ambiente virtual Python (venv)

### Instalação

1. Clone o repositório:
   ```
   git clone https://github.com/seu-usuario/universal-conectaai.git
   cd universal-conectaai
   ```

2. Crie e ative um ambiente virtual:
   ```
   python -m venv venv
   source venv/bin/activate  # No Windows: venv\Scripts\activate
   ```

3. Instale as dependências:
   ```
   pip install -r backend/requirements.txt
   ```

4. Configure as variáveis de ambiente (opcional):
   ```
   export FLASK_APP=app.py
   export FLASK_ENV=development
   ```

### Execução

1. Inicie a aplicação:
   ```
   python app.py
   ```

2. Acesse a aplicação em:
   ```
   http://localhost:5000
   ```

## Endpoints da API

### Autenticação

- `POST /api/auth/login`: Autenticação de usuários

### Canais de Comunicação

- `GET /api/channels`: Lista canais de comunicação disponíveis

### Chatbot

- `GET /api/chatbot/flows`: Lista fluxos de chatbot disponíveis

### Dashboard

- `GET /api/dashboard/metrics`: Obtém métricas para o dashboard

### Integrações

- `GET /api/integrations`: Lista integrações disponíveis

## Testes

Execute os testes com o comando:
```
python -m pytest
```

Para executar testes específicos:
```
python -m pytest backend/tests/test_services.py
```

## Próximos Passos

O projeto foi implementado seguindo uma abordagem de MVP (Produto Mínimo Viável), com foco em estabelecer a estrutura base e os componentes essenciais. As próximas etapas incluem:

1. Implementação de interfaces de usuário (frontend)
2. Integração com provedores reais de comunicação (WhatsApp API, serviços de e-mail, etc.)
3. Implementação de algoritmos avançados de NLP para o chatbot
4. Desenvolvimento de conectores específicos para sistemas de saúde e negócios
5. Implementação de funcionalidades avançadas de segurança e conformidade

## Contribuição

Para contribuir com o projeto:

1. Crie um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Faça commit das suas alterações (`git commit -m 'Adiciona nova feature'`)
4. Envie para o branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request
