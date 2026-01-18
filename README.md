🤖 Chatbot de Clima no Telegram com n8n + OpenWeather

Este projeto implementa um chatbot no Telegram que informa o clima atual de uma cidade, utilizando n8n como orquestrador no-code / low-code e a API pública do OpenWeather.

O usuário envia o nome da cidade pelo Telegram e o bot retorna uma mensagem clara e amigável com informações meteorológicas em tempo real.

Projeto desenvolvido como entrega do Desafio Fase 2 – Rocketseat.

🚀 Funcionalidades

Recebe mensagens de texto no Telegram

Consulta o clima atual via OpenWeather

Retorna temperatura, sensação térmica, condição do tempo, umidade e vento

Trata erros de cidade não encontrada

Workflow no-code / low-code (sem scripts externos)

🧩 Tecnologias Utilizadas

n8n – Orquestração do workflow (no-code / low-code)

Telegram Bot API – Interface de conversa

OpenWeather API – Dados meteorológicos

📁 Estrutura do Repositório

workflow-chatbot-telegram.json → Workflow exportado do n8n

README.md → Documentação do projeto

⚙️ Como importar e executar o workflow
1️⃣ Importar o workflow no n8n

Acesse o painel do n8n

Clique em Import workflow

Selecione o arquivo workflow-chatbot-telegram.json

Salve o workflow

🔐 Configuração de Credenciais e Variáveis
🌤️ OpenWeather (obrigatório)

Este projeto utiliza variável de ambiente para a API do OpenWeather.

Você deve configurar no ambiente onde o n8n está rodando:

OPENWEATHER_API_KEY=sua_api_key_aqui

No workflow, essa variável é acessada via expressão:

$env.OPENWEATHER_API_KEY

⚠️ Nunca inclua a API Key diretamente no JSON ou no repositório.

🤖 Telegram Bot (obrigatório)

O Telegram não utiliza variável de ambiente neste projeto.

O n8n exige o uso de Credenciais internas para o Telegram Trigger e Telegram Send Message.

Passos:

No n8n, vá em Credentials

Crie uma nova credencial do tipo Telegram API

Cole o TELEGRAM_BOT_TOKEN gerado pelo BotFather

Salve a credencial

Selecione essa credencial nos nós:

Telegram Trigger

Telegram Send Message

ℹ️ Isso é uma limitação do próprio n8n:
o Telegram Trigger não aceita token via variável de ambiente, apenas via credencial.

🧪 Como testar o chatbot

Após ativar o workflow no n8n:

Abra o bot no Telegram

Envie o nome de uma cidade, por exemplo:

Pato Branco

Curitiba

São Paulo

Exemplo de resposta:

🌤️ Clima agora em Pato Branco (BR)
🌡️ Temperatura: 19°C
🤗 Sensação térmica: 19°C
☁️ Condição: algumas nuvens
💧 Umidade: 96%
🌬️ Vento: 1.5 m/s

❌ Exemplo de erro

Se a cidade não for encontrada:

❌ Cidade não encontrada.
Use apenas o nome da cidade (ex.: Curitiba, São Paulo).

🛡️ Observações importantes

O repositório é público

Nenhuma credencial real está presente no JSON ou README

O workflow funciona após importação

Projeto segue o conceito no-code / low-code

Apenas expressões simples foram utilizadas quando necessário

✅ Status final da entrega

✔ Workflow funcional
✔ Tratamento de erros implementado
✔ Uso correto de variáveis de ambiente (OpenWeather)
✔ Uso correto de credenciais do n8n (Telegram)
✔ Documentação clara e avaliável

🏁 Conclusão

Este projeto demonstra, de forma prática, a criação de um chatbot funcional integrando Telegram + n8n + OpenWeather, com foco em boas práticas de integração, tratamento de erros e organização de fluxos no-code.
