
## Guia de Configuração Completo: Construindo seu Assistente de IA de Comunicação

Este guia fornece um passo a passo detalhado para criar seu assistente de comunicação virtual low-code usando n8n e Google AI Studio.

---

### Parte 1: Configure seu Backend no n8n

Nosso workflow do n8n atuará como o "backend" central para o nosso chatbot.

1.  **Crie uma Conta Gratuita no n8n:** Navegue até o [site oficial do n8n](https://n8n.io/) e inscreva-se no plano inicial gratuito (cloud). Esta é a maneira mais rápida de começar sem gerenciar servidores.
2.  **Inicie um Novo Workflow:** Após fazer login, você estará no seu painel do n8n. Crie um novo workflow em branco.

---

### Parte 2: Configure o Cérebro da IA no Google AI Studio

Precisamos de uma **Chave de API (API Key)** do Google, que funciona como uma senha segura que permite ao n8n se comunicar com o modelo de IA Gemini.

1.  **Navegue até o Google AI Studio:** Acesse [aistudio.google.com](https://aistudio.google.com/).
2.  **Obtenha a Chave de API:** Procure pelo botão **`< > Get API key`** no canto superior esquerdo e clique nele.
3.  **Crie a Chave de API:** Clique em **Create API key in new project**.
4.  **Copie sua Chave:** Sua nova chave de API será gerada. **Copie esta chave imediatamente** e salve-a em um local seguro para o próximo passo.

---

### Parte 3: Construa o Workflow no n8n

Agora, retornaremos ao n8n para construir a lógica principal.

1.  **Adicione o Nó (Node) AI Agent:** No seu workflow do n8n, clique no botão **`+`** e adicione o nó **AI Agent**.
2.  **Conecte-se ao Google Gemini:**
    - Clique no nó AI Agent. Em 'Chat Model', clique em **`+`** e escolha **Google Gemini**.
    - No menu suspenso 'Credential', selecione **Create New**.
    - Dê um nome para sua credencial (ex: `Minha Chave Gemini Cafe`) e cole a **Chave de API** que você copiou do Google AI Studio.
    - Clique em **Save**.
3.  **Dê Instruções ao seu Agente:**
    - Nas configurações do nó AI Agent, clique em **Add Option** -> **System Message**.
    - Na caixa de texto, defina a personalidade e o conhecimento do seu assistente. Exemplo:
      > Você é o BrewBot, o assistente virtual amigável e prestativo do "Café Grão do Dia".
      > **Cardápio:** Latte: R$14,50, Espresso: R$8,00.
      > **Horários:** Seg-Sex 7h - 18h, Sáb-Dom 8h - 16h.
      > Se não souber a resposta, diga "Vou verificar com nossa equipe humana!"
4.  **Dê Memória ao seu Agente:**
    - Clique no menu suspenso **Memory** e selecione **Simple Memory**.
    - Defina o **Context Window Length** como `15` para que ele se lembre das últimas 15 mensagens.

---

### Parte 4: Torne seu Assistente Público e Teste

Finalmente, vamos criar uma URL pública para receber as mensagens dos usuários.

1.  **Ative e Publique:**
    - No canto superior direito, mude o seletor de "Inactive" para **"Active"**.
    - Clique no nó onde o chat inicia.
    - Copie o link **chat URl** e cole no seu navegador.

    **Exemplo usando seu formato de URL específico:**
    ```
   https://cafeproject.app.n8n.cloud/webhook/fbf80255-9246-486c-8434-58adc96a8e42/chat
    ```

### Parabéns!
Você construiu e implementou com sucesso um assistente de IA low-code. Agora você pode usar a URL deste projeto para alimentar um chatbot em qualquer site ou aplicativo.
````