# CEP Explorer · entrega-intermediaria

> Aplicação web que consome a API pública **ViaCEP** (`viacep.com.br`) com testes de integração incluídos.

## 🔗 Deploy

**[https://cep-explorer.vercel.app](https://cep-explorer.vercel.app)** 

---

## 📋 Issue de Origem

Esta entrega foi desenvolvida a partir da **Issue #1** do repositório:

> **"Integrar API pública de consulta de CEP e implementar testes de integração"**
> Branch: `entrega-intermediaria`

---

## 🌐 API Utilizada

| Campo | Valor |
|---|---|
| Nome | ViaCEP |
| Endpoint | `https://viacep.com.br/ws/{CEP}/json/` |
| Método | `HTTP GET` |
| Autenticação | Nenhuma (API aberta) |
| Formato | JSON |

**Exemplo de requisição:**
```
GET https://viacep.com.br/ws/01310100/json/
```

**Exemplo de resposta:**
```json
{
  "cep": "01310-100",
  "logradouro": "Avenida Paulista",
  "complemento": "de 610 a 1062 - lado par",
  "bairro": "Bela Vista",
  "localidade": "São Paulo",
  "uf": "SP",
  "ibge": "3550308",
  "ddd": "11"
}
```

---

## 🧪 Testes de Integração

Os testes validam a comunicação real com a API (sem mock) e são executados diretamente na interface:

| # | Teste | Descrição |
|---|---|---|
| 1 | Status 200 | API retorna status 200 para CEP válido |
| 2 | Campo logradouro | Resposta contém o campo `logradouro` |
| 3 | Campo localidade | Resposta contém o campo `localidade` preenchido |
| 4 | CEP inválido | CEP inexistente retorna `{ erro: true }` |
| 5 | Campo UF | Campo `uf` possui exatamente 2 caracteres |

Para executar: clique em **"▶ Executar Testes"** na interface.

---

## 🚀 Como Rodar Localmente

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo

# Checkout na branch correta
git checkout entrega-intermediaria

# Abra no navegador (sem dependências!)
open index.html
```

Não há dependências externas além de fontes do Google Fonts (carregadas via CDN).

---

## 📦 Deploy

### Vercel (recomendado para web)
```bash
npm i -g vercel
vercel --prod
```

### GitHub Pages
1. Vá em **Settings → Pages**
2. Selecione a branch `entrega-intermediaria`
3. Selecione `/ (root)` como pasta
4. Clique em **Save**

### Netlify
Arraste a pasta do projeto para [app.netlify.com/drop](https://app.netlify.com/drop)

---

## 🔀 Fluxo Git

```
main
 └── entrega-intermediaria   ← desenvolvimento aqui
       └── PR → merge em main (closes #1)
```

---

## 🛠️ Tecnologias

- HTML5 + CSS3 + JavaScript (vanilla)
- Fetch API para requisições HTTP
- API REST pública: ViaCEP

---

*Desenvolvido como parte da Etapa Intermediária do desafio de desenvolvimento.*
