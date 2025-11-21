# ⚡ Kilua Bot - Seu Arquiteto de Software via Telegram

> *"Documentation is like sex: when it's good, it's very good; when it's bad, it's better than nothing."* — Dick Brandon

O **Kilua Bot** nasceu de uma dor comum: **desenhar diagramas dá preguiça**. Todo desenvolvedor sabe que documentação é essencial, mas parar de codar para arrastar caixinhas no Lucidchart ou brigar com sintaxe de script quebra o fluxo de pensamento.

Este bot utiliza a Inteligência Artificial do **Google Gemini** integrada a motores de renderização (Mermaid.js e PlantUML) para transformar descrições simples ou código bruto em diagramas UML profissionais instantaneamente.

---

## 🎯 Qual o intuito do Kilua?

O objetivo não é apenas "fazer desenhos". O Kilua atua como um **Parceiro de Arquitetura**.

1.  **Agilidade:** Você cola uma classe em Python e recebe o diagrama UML em 5 segundos.
2.  **Validação de Ideias:** Você descreve "Um sistema onde o usuário loga e o admin aprova" e o bot gera o Caso de Uso, permitindo que você visualize se a lógica faz sentido antes de codar.
3.  **Documentação Viva:** Facilita manter a documentação atualizada, já que gerar um novo diagrama custa apenas um comando.

---

## 🛠️ O Dilema das Engines: PlantUML vs. Mermaid

O Kilua suporta dois motores de renderização. Entender a diferença entre eles é crucial para não se frustrar.

### 🥇 PlantUML (O "Tanque de Guerra") - **PADRÃO**
O PlantUML é baseado em Java e Graphviz. Ele é "feio", mas extremamente robusto.
* **Por que é o padrão?** A Inteligência Artificial (Gemini) é criativa. Às vezes, ela gera um código com um pequeno erro de espaçamento ou uma ligação "estranha". O PlantUML ignora esses pequenos erros e tenta renderizar o diagrama de qualquer jeito.
* **Confiabilidade:** 99% das vezes, ele vai entregar uma imagem legível.

### 🎨 Mermaid.js (O "Carro Esportivo")
O Mermaid é moderno, baseado em JavaScript e roda nativamente na web. Gera diagramas lindos e coloridos.
* **Qual o B.O.?** O Mermaid é **extremamente rígido (Strict Syntax)**. Se a IA esquecer um ponto e vírgula, der um espaço errado ou usar um caractere especial que o Mermaid não gosta, o renderizador quebra e não gera nada.
* **O problema da IA:** Como LLMs (Large Language Models) são probabilísticos, eles não garantem uma sintaxe 100% perfeita sempre. Para diagramas complexos (muitas conexões), a chance do Mermaid quebrar é alta.
* **Quando usar:** Para diagramas simples ou quando a estética for prioridade absoluta.

---

## 🤖 Limitações da Inteligência (Cotas e Tokens)

O Kilua utiliza a API do **Google Gemini Pro** para "pensar". Embora poderosa, ela possui limites físicos e operacionais que você deve conhecer:

### 1. O "Cansaço" Diário (Quota Limit)
O bot opera em um nível gratuito (Free Tier) da API. Isso significa que existe um número máximo de requisições que podem ser feitas por dia.
* **O Sintoma:** Se você enviar um comando e o bot não responder nada (silêncio total), provavelmento o limite diário de tokens foi atingido.
* **A Solução:** Os limites são renovados automaticamente a cada 24 horas (geralmente à meia-noite no fuso do servidor do Google). Tente novamente no dia seguinte.

### 2. Alucinação de Sintaxe
A IA entende muito de código, mas às vezes ela "inventa" conexões que não existem na sintaxe UML oficial.
* **Exemplo:** Tentar conectar três nós ao mesmo tempo em uma única linha no Mermaid.
* Se isso acontecer, tente reenviar o comando simplificando a descrição ou mude para o modo **PlantUML**, que lida melhor com essas "alucinações".

---

## 🚀 Guia de Uso Rápido

### Comandos Disponíveis

| Comando | Função | Motor Recomendado |
| :--- | :--- | :--- |
| `/genClass` | Diagrama de Classes (Atributos e Métodos) | Mermaid ou PlantUML |
| `/genFlow` | Diagrama de Atividades (Fluxogramas) | PlantUML (Mais seguro) |
| `/genCase` | Casos de Uso (Atores e Ações) | PlantUML (Essencial) |
| `/menu` | Mostra o menu interativo | - |
| `/start` | Executa o primeiro contato | - |
| `/help` | Exibe este guia | - |

### Como pedir (A Engenharia de Prompt)

Você tem duas formas de interagir:

**1. Modo Descritivo (Linguagem Natural)**
Você conta o que quer, e o Kilua projeta.
> `/genCase Sistema de Delivery onde o Cliente faz pedido, o Restaurante aceita e o Entregador finaliza.`

**2. Modo "Engenharia Reversa" (Código Puro)**
Você cola seu código, e o Kilua documenta.
> `/genClass class Produto: def __init__(self, preco): self.preco = preco ...`
*(O bot vai ler seu código Python/Java/C# e montar a estrutura de classes automaticamente)*

### Forçando um Motor Específico
Se quiser testar o visual do Mermaid, você pode especificar logo após o comando:
> `/genFlow mermaid Usuário faz login -> Sistema valida senha`

---

*Projeto desenvolvido com n8n, Google Gemini e muita cafeína.* ☕
