# Chat Jr — Seu Plano de Negócios

Interface web (HTML + CSS + JavaScript puro) para consultar o Plano de Negócios da Empresa JR usando a API da Anthropic (Claude).

## Estrutura do projeto

```
chat-jr/
├── index.html          # Estrutura da página e templates de view
├── css/
│   └── styles.css      # Estilos, tokens de tema (claro/escuro) e layout
├── js/
│   └── app.js          # Lógica: dados, roteador, IA, PDF, persistência
├── README.md
├── .gitignore
└── package.json        # Opcional (só para servir com `npm start`)
```

## Como rodar localmente

O projeto é 100% estático — não precisa de build. Duas opções:

### 1. Abrir direto no navegador
Basta abrir `index.html` no navegador. Alguns recursos (como leitura de PDF) precisam de servidor HTTP para funcionar bem.

### 2. Rodar um servidor local (recomendado)
Se você tem Node.js instalado:

```bash
npm start
```

Isso sobe um servidor estático em `http://localhost:8080`.

Ou, sem instalar nada, use a extensão **Live Server** do VS Code — clique com o botão direito no `index.html` e escolha *"Open with Live Server"*.

## Como subir no git

Dentro da pasta `chat-jr/`:

```bash
git init
git add .
git commit -m "Primeira versão do Chat Jr"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/SEU-REPO.git
git push -u origin main
```

## Configuração da IA

- Abra **Configurações → Inteligência artificial** dentro do app.
- Cole sua chave da API Anthropic (formato `sk-ant-...`).
- A chave fica **só no navegador**; nada é enviado para outro servidor.
- Sem chave, o app usa leitura local do PDF como alternativa.

## Persistência

Todos os dados (planos, abas, conversas) ficam salvos no `localStorage` do navegador. Você pode:
- Exportar em JSON pela tela de Configurações.
- Restaurar um JSON exportado antes.
- Apagar tudo e voltar ao estado de demonstração.
