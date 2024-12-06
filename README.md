
# Como Rodar o Projeto Localmente

Este guia explica como rodar localmente o projeto **Quantum Guard Backend**, que implementa uma API Flask para classificação utilizando modelos de aprendizado de máquina clássico e quântico.

## **Pré-requisitos**

Certifique-se de que você possui os seguintes itens instalados em seu sistema:
- Python 3.7 ou superior.
- `pipenv` (gerenciador de ambientes e dependências).

## **Passos para Configuração**

1. **Clone o repositório**  
   No terminal, execute:
   ```bash
   git clone https://github.com/Weslley-Prado/Quantum-Guard-Backend.git
   cd Quantum-Guard-Backend

Este guia explica como rodar localmente o projeto **Quantum Guard Backend**, que implementa uma API Flask para classificação utilizando modelos de aprendizado de máquina clássico e quântico.

## **Pré-requisitos**

Certifique-se de que você possui os seguintes itens instalados em seu sistema:
- Python 3.7 ou superior.
- `pipenv` (gerenciador de ambientes e dependências).

## **Passos para Configuração**

1. **Clone o repositório**  
   No terminal, execute:
   ```bash
   git clone https://github.com/Weslley-Prado/Quantum-Guard-Backend.git
   cd Quantum-Guard-Backend

2. **Instale as dependências**  
Use o `pipenv` para configurar o ambiente virtual e instalar as dependências:  

         pipenv install
         pipenv shell

3. **Estrutura do projeto**
Quantum-Guard-Backend/
├── app.py
├── adapters/
│   └── connection_models.py
├── infra/
│   ├── model_of_classical_machine_learning/
│   │   └── modelo_anti_fraude.pkl
│   └── model_of_quantum_machine_learning/
│       └── modelo_anti_fraude_quantum.pkl
├── Pipfile
└── Pipfile.lock

4. **Execute o servidor**

        python app.py
5. **Acesse a API**  
Por padrão, o servidor estará disponível em:  
http://127.0.0.1:5000


# Como Utilizar Insomnia ou Postman para Testar a API

  

Este guia explica como configurar e testar a rota `/classificar` da API do projeto **Quantum Guard Backend** usando ferramentas como **Insomnia** ou **Postman**.

---

## **Passos para Configuração**

  

### **1. Inicie o Servidor Local**

Certifique-se de que o servidor Flask está rodando localmente. No terminal, execute:


    python app.py

  
O servidor estará disponível em http://127.0.0.1:5000.
  
**2. Configurando no Insomnia**

Abra o Insomnia

Baixe o Insomnia em https://insomnia.rest/download, caso ainda não o tenha instalado.

Crie uma nova requisição

Clique em New Request.

Dê um nome à requisição, como Classificar.

Escolha o método POST.

Configure a URL: http://127.0.0.1:5000/classificar.

Configure o Corpo da Requisição

Vá até a aba Body.

Selecione o formato JSON.

Insira o seguinte payload de exemplo:

    {
    
    "valor": 1000,
    
    "tempo": 3600,
    
    "fim_de_semana": false,
    
    "idade_cliente": 30,
    
    "numero_transacoes": 5,
    
    "tipo_transacao": "compra",
    
    "cidade": "São Paulo",
    
    "perfil": "prata",
    
    "modelo_selecionado": "Clássico"
    
    }

  

Envie a Requisição

  

Clique em Send.

O Insomnia exibirá a resposta da API no painel à direita. A resposta deve ser algo como:

    {
    "resultado": "Baixo ou Sem Risco de Fraude"
    }

  
  

3. Configurando no Postman

Abra o Postman.
Baixe o Postman em https://www.postman.com/downloads/ caso ainda não o tenha instalado.
Crie uma nova requisição.
Clique em New Request.
Dê um nome à requisição, como Classificar.
Escolha o método POST.

Configure a URL: http://127.0.0.1:5000/classificar.

Configure o Corpo da Requisição

Vá até a aba Body.

Selecione raw e escolha o tipo JSON no menu suspenso à direita.

Insira o seguinte payload:

     {
    "valor": 1000,
    
    "tempo": 3600,
    
    "fim_de_semana": false,
    
    "idade_cliente": 30,
    
    "numero_transacoes": 5,
    
    "tipo_transacao": "compra",
    
    "cidade": "São Paulo",
    
    "perfil": "prata",
    
    "modelo_selecionado": "Clássico"
    }

  

**Envie a Requisição**

Clique no botão Send.

A resposta da API aparecerá abaixo, em um formato semelhante a:
    
    {    
    "resultado": "Baixo ou Sem Risco de Fraude"
     }


