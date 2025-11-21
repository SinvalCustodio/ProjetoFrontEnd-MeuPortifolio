# Meu Portfólio Front-end — 1_versão_MeuPortifolio

Olá — este repositório contém a versão inicial do meu portfólio front-end. Abaixo estão informações atualizadas e coerentes com o código-fonte presente na pasta Pagina_do_portifólio.

Resumo

- Protótipo estático: `[Pagina_do_portifólio/1_versão_MeuPortifolio.html](https://github.com/SinvalCustodio/ProjetoFrontEnd-MeuPortifolio/blob/main/1_vers%C3%A3o_MeuPortifolio.html)`.

- Tecnologias: Vue 3 (CDN), Tailwind CSS (CDN), Font Awesome.

- Dados dinâmicos (nav, skills, projects, contatos, redes) são mantidos em arrays reativos e renderizados com `v-for`.

Stack

- Vue 3 (CDN) — Composition API: const { createApp, ref, onMounted } = Vue;

- Tailwind CSS (CDN) — utilitários de estilo.

- Font Awesome — ícones.

- IntersectionObserver — animação das barras de skill.

Onde está o código

- Arquivo principal: (https://github.com/SinvalCustodio/ProjetoFrontEnd-MeuPortifolio/blob/main/1_vers%C3%A3o_MeuPortifolio.html)

Como executar localmente (Windows)

- Recomendo usar um servidor HTTP simples para evitar bloqueios de CORS.

  - Python 3:

    - Abra o terminal na pasta do projeto e execute:

      - python -m http.server 8000

    - Abra no navegador:

      - http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html

  - npx http-server:

    - npx http-server . -p 8000

    - Abra:

      - http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html

Onde editar os dados

- Abra (https://github.com/SinvalCustodio/ProjetoFrontEnd-MeuPortifolio/blob/main/1_vers%C3%A3o_MeuPortifolio.html) e edite o bloco `<script>` com `createApp()`.

  - navItems — itens do menu

  - skills — { name, percentage }

  - projects — { title, description, technologies[], demoUrl, githubUrl } (carregado de `./projects.json`)

  - contactForm — { name, email, message }

  - contactInfos — { icon, text, link? }

  - socialLinks — { icon, link }

Exemplo projects.json

```json
[
  {
    "title": "E-commerce Responsivo",
    "description": "Loja virtual com carrinho e integração de pagamento.",
    "technologies": ["Vue.js", "Tailwind CSS", "Node.js"],
    "demoUrl": "#",
    "githubUrl": "https://github.com/usuario/repo"
  }
]
```

Licença

- Atualização em andamento, aberto para sujestões e melhorias.


