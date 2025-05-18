🔗 Apresentação no Canva
https://www.canva.com/design/DAGnuOdxo74/PQAbVoyRF6JzYYPnitoh7Q/view?utm_content=DAGnuOdxo74&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hdd527a54f2



markdown
Copiar
Editar
# 🤖 Nice Chatbot — Um aliado contra as fake news para o público idoso  
### Imersão IA 2025 | Alura + Google Gemini  
**Desenvolvido por:** Gabrielle de Azevedo Lima

---

## 📌 Visão Geral

O **Nice Chatbot** foi desenvolvido durante a Imersão IA 2025 (Alura + Google Gemini) com o objetivo de ajudar pessoas idosas a identificarem notícias falsas (fake news), especialmente em ambientes digitais como WhatsApp e Facebook. Inspirado na minha mãe, Nice, este projeto combina **Inteligência Artificial**, **responsabilidade social** e princípios de **UX/UI acessível** para democratizar o acesso à informação segura.

---

## 🧠 Motivação

> "Minha mãe, Nice, foi minha maior inspiração. Percebi que ela e outros idosos enfrentam dificuldades reais ao lidar com desinformação — e quis transformar essa dor em solução."

- **Problema:** Idosos são mais propensos a acreditar e compartilhar fake news.
- **Impacto:** Confusão, ansiedade, desinformação em saúde e golpes.
- **Objetivo:** Criar um chatbot acessível, amigável e funcional para combater esse cenário.

---

## 👩‍🦳 Persona: Ana

> 68 anos | Viúva | Costureira aposentada | Usuária básica de celular  
Ana se informa pela TV e WhatsApp, mas tem dificuldade em validar notícias. Ela precisa de uma ferramenta simples, confiável e acolhedora — como o Nice Chatbot.

---

## ✨ Funcionalidades do Chatbot

✅ Recebe perguntas/notícias via texto  
✅ Analisa veracidade e alerta sobre sinais suspeitos  
✅ Sugere fontes confiáveis (ex: Boatos.org, Lupa, Aos Fatos)  
✅ Usa **linguagem simples, tom acolhedor e respostas curtas**  
✅ Proporciona contexto sobre a origem da notícia

---

## 🧩 Processo de Criação

### 🧪 Aula 04: Introdução ao Google AI Studio

- Aprendizado sobre modelos generativos (Gemini)
- Criação do **prompt inicial** com comportamento esperado:
  - Linguagem simples
  - Análise crítica com empatia
  - Sugestão de fontes e contexto

### 🛠️ Prompt Base Utilizado

```text
Você é um chatbot inteligente e amigável, especializado em ajudar pessoas com mais de 50 anos a identificar notícias falsas (fake news)...
➡️ Veja o prompt completo clicando aqui

🐍 Transição para Google Colab + Python
Utilizei o Google Colab para executar o chatbot com o modelo Gemini 2.0 Flash, usando a biblioteca google-generativeai.
Durante a implementação, documentei erros comuns e como resolvê-los.

⚠️ Exemplo de Erro:
pgsql
Copiar
Editar
AttributeError: module 'google.generativeai' has no attribute 'client'
✅ Resolvido com:

python
Copiar
Editar
import google.generativeai as genai
🧬 Código Final
python
Copiar
Editar
!pip install google-genai

import os
from google.colab import userdata
import google.generativeai as genai
from google.generativeai import types

# Configuração da API
os.environ['GOOGLE_API_KEY'] = userdata.get('GOOGLE_API_KEY')
genai.configure(api_key=os.environ['GOOGLE_API_KEY'])

# Definindo modelo
modelo = "models/gemini-2.0-flash"
model = genai.GenerativeModel(modelo)

# Prompt principal
system_instruction = """Você é um chatbot inteligente..."""

# Iniciando sessão de chat
chat = model.start_chat(system_instruction=system_instruction)

# Loop interativo
while True:
    prompt = input("Você: ")
    if prompt.lower() == "fim":
        break
    resposta = chat.send_message(prompt=prompt)
    print("Chatbot:", resposta.text)
📌 Veja o código completo no Colab →

🧪 Iterações do Prompt e Testes
🛠️ Refinamento do Prompt
Inicial: explicativo, mas longo

Iteração 1: mais concisão

Iteração 2: mais contexto e empatia

🧪 Exemplos de Testes
Pergunta enviada	Resposta do Chatbot (resumida)
"O Lula vai implantar o comunismo?"	"Não há nenhuma evidência confiável de que isso vá acontecer. Essa é uma fake news comum..."
"Mamadeira de piroca existe mesmo?"	"Essa história é falsa e foi amplamente desmentida por agências de checagem de fatos."

💡 Pensando em UX/UI
Embora este projeto não inclua interface visual, a experiência do usuário foi pensada em cada linha do prompt e resposta. O chatbot simula o comportamento de um amigo confiável, com:

Tom acolhedor e calmo

Textos curtos, diretos e acessíveis

Foco na empatia e autonomia do usuário idoso

📎 Prompt Completo Utilizado
<details> <summary>📜 Clique para expandir</summary>
text
Copiar
Editar
Você é um chatbot inteligente e amigável, especializado em ajudar pessoas com mais de 50 anos a identificar notícias falsas (fake news).
Seja claro, use uma linguagem simples e evite termos técnicos...

1. Receba a pergunta com atenção.
2. Verifique se há sinais de fake news ou conteúdo enganoso.
3. Responda com empatia e clareza.
4. Informe que a informação pode ser falsa (se aplicável).
5. Indique fontes confiáveis (ex: Boatos.org, Lupa, Aos Fatos).
6. Explique o contexto de forma didática, sem julgamentos.
</details>
🧠 Aprendizados e Conclusões
✅ Compreensão da API do Gemini e sua integração com Python
✅ Importância da clareza na comunicação com IA
✅ Aplicação prática de UX em texto conversacional
✅ Superação de erros com documentação e tentativa/erro

📚 Tecnologias Utilizadas
Python 3.10+

Google Colab

Gemini 2.0 (via google-genai)

Prompt Engineering

Metodologias de UX Writing

📌 Próximos Passos
🔜 Criar uma interface web acessível (com botões, voz e suporte visual)
🔜 Implementar logging de conversas para melhoria contínua
🔜 Realizar testes com usuários reais (idosos)

💬 Agradecimentos
À minha mãe, Nice, por ser minha maior inspiração ❤️

À equipe da Imersão IA 2025

Ao Google e Alura, pela oportunidade incrível

E a você, que chegou até aqui 🙌
