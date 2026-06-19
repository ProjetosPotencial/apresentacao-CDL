# CDL/BH + Parcele Aqui — Proposta Comercial

Apresentação institucional (white-label) da **Parcele Aqui / Potencial Tecnologia** para a **CDL/BH** — proposta de plataforma de parcelamento de boletos e tributos para o associado.

Site **100% estático**, em um único `index.html` autocontido: favicon, logo do CDL/BH (PNG), logotipo Parcele Aqui (SVG) e o print do app estão embutidos no próprio arquivo. As fontes (Kufam + DM Sans) vêm do Google Fonts via CDN. **Não há build** — o Vercel serve direto.

## Estrutura

```
cdl-bh-parcele-aqui/
├── index.html      # a apresentação (tudo embutido)
├── vercel.json     # headers de segurança + cleanUrls
├── .gitignore
└── README.md
```

## Subir para o Git

```bash
cd cdl-bh-parcele-aqui
git init
git add .
git commit -m "CDL/BH · apresentacao Parcele Aqui"
git branch -M main
git remote add origin https://github.com/ProjetosPotencial/apresentacao-cdl-bh.git
git push -u origin main
```

> No `git push` por HTTPS, o GitHub pede **usuário + Personal Access Token** (não a senha).
> Se o repositório já existir com um README, rode antes: `git pull --rebase origin main`.

## Deploy no Vercel

### Opção A — Dashboard (recomendado)
1. Acesse https://vercel.com/new
2. **Import** o repositório do GitHub.
3. Application Preset: **Other**.
4. Root Directory: `./` (o `index.html` está na raiz).
5. Build and Output Settings: deixe **tudo desligado/em branco** (sem build, sem install).
6. Environment Variables: **nenhuma**.
7. **Deploy**.

### Opção B — Vercel CLI
```bash
npm i -g vercel
cd cdl-bh-parcele-aqui
vercel          # preview
vercel --prod   # produção
```

## Domínio personalizado

No projeto do Vercel → **Settings → Domains**, adicione por exemplo:

```
cdlbh.parceleaqui.com.br
```

e crie no DNS um **CNAME** apontando para `cname.vercel-dns.com` (ou siga as instruções exibidas pelo Vercel).

## Editar conteúdo

Todo o conteúdo, estilos e scripts estão em `index.html`. Para trocar textos, números da calculadora ou seções, edite o arquivo e faça novo commit — o Vercel republica automaticamente a cada push na `main`.
