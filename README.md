<div align="center">

<img src="https://img.shields.io/badge/Cloudflare-Workers-F6821F?style=for-the-badge&logo=cloudflare&logoColor=white"/>
<img src="https://img.shields.io/badge/Edge-Ready-00e87a?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Zero%20Dependencies-black?style=for-the-badge"/>

<br/><br/>

```
  ███████╗███████╗██╗     ███████╗ ██████╗██╗      ██████╗  █████╗ ██╗  ██╗
  ██╔════╝██╔════╝██║     ██╔════╝██╔════╝██║     ██╔═══██╗██╔══██╗██║ ██╔╝
  ███████╗█████╗  ██║     █████╗  ██║     ██║     ██║   ██║███████║█████╔╝ 
  ╚════██║██╔══╝  ██║     ██╔══╝  ██║     ██║     ██║   ██║██╔══██║██╔═██╗ 
  ███████║███████╗███████╗██║     ╚██████╗███████╗╚██████╔╝██║  ██║██║  ██╗
  ╚══════╝╚══════╝╚══════╝╚═╝      ╚═════╝╚══════╝ ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝
```

**Traffic cloaking at the edge. Zero infra. Zero latency. 100% Cloudflare Workers.**

[🔑 Obter Licença](https://selfcloak.com) · [📖 Documentação](https://selfcloak.com/docs) · [💬 Suporte](https://selfcloak.com/support)

</div>

---

## O que é o SelfCloak?

SelfCloak é um sistema de **traffic cloaking** que roda diretamente nos **Cloudflare Workers** — sem servidor, sem custo de infra, com latência de borda global.

Ele analisa cada visita em tempo real e decide, em milissegundos, se o visitante deve ver sua **oferta real** ou uma **página segura** — protegendo seus criativos e campanhas de bots, revisores de plataforma, VPNs e tráfego indesejado.

```
Visitante → Cloudflare Edge → SelfCloak → [ Oferta ✅ | Safe Page 🛡️ ]
```

---

## ✨ Recursos

| Recurso | Descrição |
|---|---|
| 🌍 **Filtro por País** | Permite ou bloqueia países específicos |
| 📱 **Filtro por Dispositivo** | Desktop, mobile, tablet |
| 🤖 **Bot Detection** | Bloqueia crawlers, revisores e spiders |
| 🔒 **VPN / Datacenter Block** | Detecta IPs de proxy e datacenter |
| 🏢 **Bloqueio por ASN** | Bloqueia redes específicas (Meta, Google, TikTok...) |
| 🎯 **Presets de Plataforma** | Configurações prontas para Meta Ads, Google Ads, TikTok, Taboola |
| 🔑 **Token de URL** | Parâmetro secreto obrigatório para acesso à oferta |
| 📊 **Logs no Supabase** | Registro completo de visitas com país, device, ASN, ação |
| 🖼️ **Modos de Entrega** | Redirect, iFrame, ReverseProxy ou SelfPage |
| 🛡️ **Painel Admin** | Interface web embutida no próprio Worker |
| 🔐 **Proteção por Senha** | Admin protegido com hash SHA-256 + tokens JWT |
| ⚡ **Rate Limiting** | Proteção contra brute force no login |
| 📜 **HTTP/TLS antigos** | Bloqueia requisições com protocolos obsoletos |

---

## 🚀 Deploy com 1 Clique

### Via Botão Oficial do Cloudflare

> Requer conta Cloudflare. O processo é guiado e leva menos de 2 minutos.

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/leobbortoluzzi/selfcloak)

---

### Variáveis de Ambiente

Configure em **Cloudflare Dashboard → Worker → Settings → Variables and Secrets**:

| Variável | Obrigatória | Descrição |
|---|---|---|
| `SECRET` | ✅ | String aleatória longa para assinar tokens JWT |
| `SUPABASE_URL` | ✅ | URL do projeto Supabase para logs |
| `SUPABASE_KEY` | ✅ | Chave anon do Supabase |

---

## 🖥️ Painel Admin

Após o deploy, acesse `https://seu-worker.workers.dev/admin`.

Na primeira vez, você será solicitado a criar uma senha. O painel permite:

- Configurar URL da oferta e modo de entrega
- Configurar URL safe e modo de fallback
- Gerenciar regras de bloqueio
- Ativar presets de plataforma
- Injetar scripts no `<head>` e `<body>`
- Gerenciar whitepages customizadas
- Visualizar logs de visitas

---

## 🛡️ Modos de Entrega

```
offer_mode / safe_mode:

  "redirect"   → HTTP 302 para a URL configurada
  "iframe"     → Carrega a URL dentro de um iframe fullscreen
  "reverse_proxy"      → Faz proxy transparente do conteúdo
  "selfpage"  → Exibe HTML customizado armazenado no banco de dados
```

---

## 📦 Estrutura do Projeto

```
selfcloak/
├── _worker.js        ← Bundle principal (Cloudflare Workers)
├── wrangler.toml     ← Configuração de deploy
└── README.md
```

---

## ⚠️ Licença e Uso

Este repositório contém a versão **pública e obfuscada** do SelfCloak.  
O uso completo, incluindo o painel admin e todos os recursos, **requer uma licença ativa** vinculada ao seu email.

Sem uma licença válida, o painel admin retornará erro de autorização.

<div align="center">

---

### 🔑 Precisa de uma licença?

**Acesse [selfcloak.com](https://selfcloak.com) e ative o seu Cloaker em minutos.**

Planos disponíveis para uso pessoal/agências.

[→ Ver Planos e Preços](https://selfcloak.com/#pricing)

---

</div>

**Este software é fornecido "como está", sem garantias de qualquer tipo.**  
Você é responsável pelo uso em conformidade com os termos das plataformas de anúncios que utilizar.

---

<div align="center">
<sub>Built on Cloudflare Workers · © SelfCloak · <a href="https://selfcloak.com">selfcloak.com</a></sub>
</div>
