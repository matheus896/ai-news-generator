
# Gerador de Notícias com IA

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/your_streamlit_username/your_repo_name)

## Descrição do Projeto

O Gerador de Notícias com IA é uma aplicação Streamlit impulsionada pelo CrewAI que permite gerar posts de blog abrangentes sobre qualquer tópico. Aproveitando o poder de agentes de IA, esta ferramenta automatiza o processo de pesquisa, análise e criação de conteúdo, entregando artigos bem estruturados e informativos em formato markdown.

**Principais Características:**

*   **Geração de Conteúdo Impulsionada por IA:** Utiliza o CrewAI para orquestrar uma equipe de agentes de IA para pesquisa e escrita.
*   **Posts de Blog Baseados em Tópicos:** Gere artigos sobre qualquer tópico que você inserir.
*   **Pesquisa Abrangente:** Emprega um agente "Analista de Pesquisa Sênior" para conduzir uma pesquisa web completa utilizando ferramentas como SerperDevTool.
*   **Escrita de Conteúdo Envolvente:** Apresenta um agente "Escritor de Conteúdo" que transforma descobertas de pesquisa em posts de blog legíveis e envolventes.
*   **Saída em Markdown:** Gera posts de blog em formato markdown, facilmente descarregáveis e prontos para plataformas de publicação.
*   **Temperatura Personalizável:** Ajuste o nível de criatividade dos agentes de IA através de um controle deslizante de temperatura na barra lateral.
*   **Interface Streamlit Amigável ao Usuário:** Interface web simples e intuitiva para fácil inserção de tópicos e geração de conteúdo.
*   **Saída Descarregável:** Descarregue facilmente o artigo gerado como um arquivo markdown.

Este projeto demonstra as capacidades do CrewAI na automatização de fluxos de trabalho complexos de criação de conteúdo. É perfeito para criadores de conteúdo, blogueiros e qualquer pessoa que precise de artigos rápidos e informativos sobre diversos tópicos.

## Sumário

1.  [Descrição do Projeto](#descrição-do-projeto)
2.  [Características](#características)
3.  [Instalação](#instalação)
4.  [Utilização](#utilização)
5.  [Variáveis de Ambiente](#variáveis-de-ambiente)
6.  [Contribuição](#contribuição)
7.  [Licença](#licença)
8.  [Agradecimentos](#agradecimentos)

## Características

*   **Pesquisa Automatizada:** Agente de IA realiza pesquisa aprofundada sobre o tópico fornecido, coletando informações de várias fontes online.
*   **Conteúdo Verificado e com Fontes Citadas:** Garante a precisão verificando fatos e incluindo citações para todas as informações utilizadas.
*   **Posts de Blog Estruturados:** Gera artigos bem organizados com seções claras, títulos e subtítulos em formato markdown.
*   **Criatividade Personalizável:** A configuração de temperatura permite aos usuários controlar o equilíbrio entre precisão factual e estilo de escrita criativa.
*   **Criação de Conteúdo Eficiente:** Reduz significativamente o tempo e esforço necessários para produzir conteúdo de blog de alta qualidade.
*   **Fluxo de Trabalho Multi-Agente:** Demonstra o poder do CrewAI utilizando múltiplos agentes especializados trabalhando juntos para alcançar uma tarefa complexa.
*   **Markdown Descarregável:** Fornece saída em um formato markdown amplamente compatível, fácil de integrar com várias plataformas de blogging e sistemas de gerenciamento de conteúdo.

## Instalação

Para executar o Gerador de Notícias com IA localmente, siga estes passos:

1.  **Clone o repositório:**

    ```bash
    git clone [YOUR_REPOSITORY_URL] # Substitua com o URL do seu repositório
    cd AI-news-generator
    ```

2.  **Crie um ambiente virtual (recomendado):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # No Linux/macOS
    venv\Scripts\activate  # No Windows
    ```

3.  **Instale as dependências:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure as variáveis de ambiente:**

    *   Crie um arquivo `.env` no diretório raiz do projeto.
    *   Adicione sua chave de API Serper ao arquivo `.env`. Você pode obter uma chave de API gratuita em [Serper.dev](https://serper.dev/).

        ```env
        SERPER_API_KEY=SUA_CHAVE_DE_API_SERPER
        ```

    *   **Nota:** A aplicação atualmente utiliza `cerebras/llama-3.3-70b` como o LLM padrão. Assegure-se de ter acesso a este modelo, se necessário, ou você pode modificar o arquivo `app.py` para usar um LLM diferente de sua escolha ajustando a configuração `llm` dentro da função `generate_content`. Se você mudar para outro LLM, você pode precisar configurar sua chave de API e quaisquer outras credenciais necessárias como variáveis de ambiente e atualizar o `app.py` de acordo.

## Utilização

1.  **Execute a aplicação Streamlit:**

    ```bash
    streamlit run app.py
    ```

2.  **Abra a aplicação no seu navegador:**

    O Streamlit fornecerá um URL local (geralmente `http://localhost:8501` ou `http://192.168.x.x:8501`). Abra este URL no seu navegador web.

3.  **Utilizando o Gerador de Notícias com IA:**

    *   **Insira seu tópico:** Na barra lateral, na área de texto "Digite seu tópico", digite o tópico sobre o qual você deseja gerar um post de blog. Seja o mais específico ou geral que desejar.
    *   **Ajuste a Temperatura (Opcional):** Use o controle deslizante "Temperatura" na barra lateral para ajustar o nível de criatividade dos agentes de IA.
        *   Temperatura mais baixa (mais próximo de 0.0) resulta em conteúdo mais factual e menos criativo.
        *   Temperatura mais alta (mais próximo de 1.0) resulta em conteúdo mais criativo e potencialmente menos factual. O padrão é 0.7.
    *   **Clique em "Gerar Conteúdo":** Pressione o botão "Gerar Conteúdo" na barra lateral para iniciar o processo de geração de conteúdo.
    *   **Aguarde o conteúdo ser gerado:** A aplicação exibirá uma mensagem "Gerando conteúdo..." enquanto os agentes de IA estão trabalhando. Isso pode levar alguns momentos dependendo da complexidade do tópico e da velocidade do LLM.
    *   **Revise o conteúdo gerado:** Uma vez que o conteúdo é gerado, ele será exibido na área principal da aplicação sob o título "### Conteúdo Gerado". Revise o artigo.
    *   **Descarregue o conteúdo:** Clique no botão "Baixar Conteúdo" para descarregar o post de blog gerado como um arquivo markdown (`.md`). O arquivo será nomeado com base no seu tópico.

## Variáveis de Ambiente

*   **`SERPER_API_KEY`**: Sua chave de API para acessar a ferramenta de pesquisa Serper.dev. Isso é necessário para o agente de pesquisa realizar buscas na web.
*   **`CEREBRAS_API_KEY`**: Sua chave de API para utilizar o LLM

**Importante:** Assegure-se de ter configurado seu arquivo `.env` corretamente com as chaves de API necessárias antes de executar a aplicação.

## Contribuição

Contribuições para o Gerador de Notícias com IA são bem-vindas! Se você gostaria de contribuir, por favor siga estas diretrizes:

1.  **Faça um fork do repositório.**
2.  **Crie um novo branch** para sua feature ou correção de bug: `git checkout -b feature/nome-da-sua-feature` ou `git checkout -b bugfix/sua-correcao-de-bug`.
3.  **Faça suas alterações** e comite-as: `git commit -m "Adicione sua mensagem de commit descritiva"`.
4.  **Envie seu branch** para o seu fork: `git push origin feature/nome-da-sua-feature`.
5.  **Envie um pull request** para o repositório principal.

Por favor, assegure-se de que seu código adere a boas práticas de programação e inclua comentários onde necessário. Para mudanças significativas, é recomendado discutir as mudanças propostas em uma issue primeiro.

## Licença

Este projeto é licenciado sob a **Licença MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.


MIT License

Copyright (c) [2025] [Matheus]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


## Agradecimentos

*   Construído utilizando [CrewAI](https://www.crewai.com/): Pelo poderoso framework de orquestração de agentes.
*   Construído utilizando [Streamlit](https://streamlit.io/): Por criar a aplicação web amigável ao usuário.
*   Utiliza [SerperDevTool](https://pypi.org/project/crewai-tools/): Por fornecer capacidades de pesquisa web para o agente de pesquisa.
*   Impulsionado por [cerebras/llama-3.3-70b]() (ou o LLM configurado em `app.py`): Pelo modelo de linguagem grande impulsionando a geração de conteúdo.
*   [dotenv](https://pypi.org/project/python-dotenv/): Para gerenciar variáveis de ambiente.

---

**Feliz geração de conteúdo!**
