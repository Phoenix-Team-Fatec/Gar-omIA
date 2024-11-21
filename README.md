# GarçomIA

# Sistema de Bot de Pedidos com Reconhecimento de Voz e Resposta em Áudio

Este repositório contém um bot do Telegram que utiliza reconhecimento de voz para receber pedidos de usuários, processá-los e responder com texto e áudio. Ele também permite a manipulação do pedido em diferentes etapas, incluindo escolha de itens, ajuste de tamanho da marmita, cálculo de valores e finalização do pedido com endereço.

---

## Funcionalidades

1. **Reconhecimento de Voz com Whisper**: O bot transcreve mensagens de voz enviadas pelos usuários utilizando o modelo Whisper.
2. **Processamento de Texto com spaCy**: Identificação de comandos e nomes de itens no texto transcrito.
3. **Resposta em Texto e Áudio**: O bot envia respostas tanto em formato de texto quanto em áudio gerado com a biblioteca `gTTS`.
4. **Sistema de Pedido**:
   - Visualizar cardápio.
   - Escolher itens.
   - Ajustar o pedido (adicionar ou remover itens).
   - Definir o tamanho da marmita com ajuste de preços.
   - Finalizar pedido com endereço e valor total.
5. **Controle de Etapas**: Navegação por etapas claras no fluxo do pedido.

---

## Tecnologias Utilizadas

- **Python 3.9+**
- **Bibliotecas**:
  - [`pyTelegramBotAPI`](https://github.com/eternnoir/pyTelegramBotAPI) para comunicação com o Telegram.
  - [`Whisper`](https://github.com/openai/whisper) para transcrição de áudio.
  - [`torch`](https://pytorch.org/) para suporte ao Whisper.
  - [`gTTS`](https://pypi.org/project/gTTS/) para conversão de texto em áudio.
  - [`spaCy`](https://spacy.io/) para processamento de texto.
- **Estrutura de Dados**:
  - Cardápio armazenado como um dicionário.
  - Pedido gerenciado como uma lista de itens.
- **Diretório de Áudio**:
  - Áudios recebidos são armazenados no diretório `/content/audio_files/`.

---

## Pré-requisitos

Antes de iniciar, você precisa ter o Python 3.9 ou superior instalado em sua máquina. Além disso, instale as dependências necessárias:

```bash
pip install pyTelegramBotAPI torch gtts spacy git+https://github.com/openai/whisper.git
```
## Como Executar

1. **Clone este repositório**:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```
2. **Configuração do Bot:**
  Substitua o token do bot no seguinte trecho do código pelo seu token do Telegram:
 ```python
   bot = telebot.TeleBot("SEU_TOKEN_DO_TELEGRAM")
   ```
3. **Inicialização:**
  Execute o script:
  ```bash
  python main.py
  ```
4.**Interação com o Bot:**
Envie mensagens de voz com comandos como:

- "Gostaria de ver o cardápio." 
- "Quero arroz e suco."
- "Remover suco."
- "Médio."
- "Rua das Flores, 123."
- O bot responderá com texto e áudio conforme o fluxo configurado.

5. **Fluxo de Funcionalidade**
   
<h3> 1. Etapa 1 - Visualizar Cardápio: </h3>

O bot exibe o cardápio disponível. <br>
<h3> 2. Etapa 2 - Escolher Itens: </h3>

O usuário escolhe itens do cardápio por voz. <br>
Os itens são adicionados ao pedido.
<h3> 3. Etapa 3 - Ajustar Pedido: </h3>

O usuário pode ver o resumo do pedido, adicionar mais itens ou remover itens. <br>
<h3> 4. Etapa 4 - Escolher Tamanho:  </h3>

O tamanho da marmita é ajustado, afetando o preço final. <br>
<h3> 5. Etapa 5 - Finalizar Pedido: </h3>

O usuário informa o endereço e o bot calcula o preço final com base no tamanho escolhido.

---
<h2> **Contribuições**</h2>
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.


