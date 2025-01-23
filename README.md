# InfoCripto 🪙
![License](https://img.shields.io/badge/lucaspanzera-InfoCripto-darkblue) ![Badge em Desenvolvimento](https://img.shields.io/badge/Status-Finalizado-darkblue)</br>
Aplicação web que permite ao usuário consultar valores, porcentagens, notícias e falar sobre Criptomoedas.
![InfoCripto](content/header.png)

Projeto desenvolvido com integração da API da <a href="https://api.binance.com/api/v3/ticker/24hr">Binance<a> para informações sobre <b>Criptomoedas</b>, e da <a href="https://cointelegraph.com">Cointelegraph</a> para as notícias.

![InfoCripto](content/1.gif)

## Funcionalidades 📱
#### 📰🔍 Vizualização das últimas notícias ligadas a <b>Criptomoedas</b>.
![InfoCripto](content/2.gif)

#### 📈⏱️ Mercado de <b>Criptomoedas</b> atualizando em tempo real.
#### 🔬📊 Detalhes sobre a <b>Criptomoedas</b> selecionada. 
![InfoCripto](content/3.gif)


#### 💱🔄 Converter valores em <b>Criptomoedas</b>.
![InfoCripto](content/4.gif)

#### 💬🌐 Blog interativo.
![InfoCripto](content/5.gif)

## Tecnologias Utilizadas 🛠️
<div align="left">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/Supabase-262626?style=for-the-badge" />
</div>

## 🚀 Como Executar o Projeto
```bash
# Acesse
https://infocripto.vercel.app

# Ou

# Clone este repositório
$ git clone https://github.com/lucaspanzera1/InfoCripto.git

# Acesse a pasta do projeto
$ cd InfoCripto

# Abra o arquivo index.html em seu navegador
```

⚡ Configurando o Banco de Dados na Supabase
```bash

Para utilizar as funcionalidades do Blog, você precisará de um banco de dados no Supabase.
Siga os passos:

1. Acesse o Supabase
  Vá para https://supabase.com
  Crie uma conta ou faça login se já tiver

2. Em https://supabase.com/dashboard/project
    Salve as keys de Project URL e API Key

3. Agora em SQL Editor, rode o script abaixo

CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

CREATE TABLE posts (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    author_name TEXT,
    content TEXT,
    created_at TIMESTAMP DEFAULT now()
);

CREATE TABLE likes (
    id SERIAL PRIMARY KEY,
    post_id UUID REFERENCES posts(id) ON DELETE CASCADE,
    user_id TEXT
);

CREATE TABLE comments (
    id SERIAL PRIMARY KEY,
    post_id UUID REFERENCES posts(id) ON DELETE CASCADE,
    author_name TEXT,
    content TEXT,
    created_at TIMESTAMP DEFAULT now()
);

4. No arquivo blog.html
  Localize no Script
   const supabaseClient = supabase.createClient(
            'Sua Key Project URL',
            'Sua Api Key'
        );
    E altere conforme escrito.
```
