# LuxMobile

Projeto da disciplina de **Estrutura de Dados II**.

---

## 🚀 Como Executar o Projeto

O projeto é composto por:
- **Backend:** Flask (Python)
- **Frontend / Estilos:** Tailwind CSS v4 (Node.js)

Para que as alterações de estilo sejam refletidas dinamicamente, recomenda-se rodar o Flask e o Tailwind em dois terminais separados.

---

### 1. Preparação dos Estilos (Tailwind CSS)

Certifique-se de ter o [Node.js](https://nodejs.org/) instalado.

No terminal, na raiz do projeto:

```bash
# Instala as dependências do Node (Tailwind CSS v4 e CLI)
npm install

# Compila o CSS e observa alterações em tempo real (--watch)
npm run watch:css
```

> **Alternativa direta via npx (sem npm scripts):**
> ```bash
> npx @tailwindcss/cli -i src/luxmobile/static/input.css -o src/luxmobile/static/output.css --watch
> ```

---

### 2. Executando o Servidor Flask

Abra um **segundo terminal** e escolha uma das opções abaixo:

#### Opção A: Utilizando `uv` (Recomendado)

Se você tem o [`uv`](https://docs.astral.sh/uv/) instalado:

```bash
# 1. Sincroniza o ambiente e instala as dependências
uv sync

# 2. Inicia o servidor Flask configurado no pyproject.toml
uv run server
```

O servidor iniciará automaticamente em: **`http://localhost:1436`** (ou `http://127.0.0.1:1436`).

---

#### Opção B: Sem `uv` (Python padrão / venv + pip)

Caso você não tenha o `uv` instalado, pode usar o `venv` e `pip` padrões do Python:

1. **Crie e ative o ambiente virtual:**

   - **Linux / macOS:**
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```

   - **Windows (PowerShell):**
     ```powershell
     python -m venv .venv
     .venv\Scripts\Activate.ps1
     ```

   - **Windows (CMD):**
     ```cmd
     python -m venv .venv
     .venv\Scripts\activate.bat
     ```

2. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```
   *(ou diretamente `pip install flask`)*

3. **Inicie a aplicação:**

   - **Via Flask CLI:**
     ```bash
     flask --app src/luxmobile run --port 1436 --debug
     ```

   - **Ou executando a função start diretamente:**
     ```bash
     python -c "import sys; sys.path.append('src'); import luxmobile; luxmobile.start()"
     ```

Acesse no navegador: **`http://localhost:1436`**.
