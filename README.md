# StreamTV – IPTV Player para Samsung Smart TV (Tizen OS)

Player IPTV moderno com suporte a listas M3U externas, navegação por controle remoto e reprodução HLS/m3u8.

---

## 📦 Arquivos

```
index.html   → App principal (tudo em um único arquivo)
config.xml   → Configuração Tizen (necessário para .wgt)
```

---

## 🚀 Formas de usar

### Opção 1 – Via browser da TV (mais simples)
1. Hospede o `index.html` em qualquer servidor web (GitHub Pages, Vercel, Netlify, etc.)
2. No browser da Samsung Smart TV, acesse a URL do arquivo.
3. Digite a URL da sua lista M3U quando solicitado.

### Opção 2 – Empacotado como app Tizen (.wgt)
1. Instale o [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download)
2. Coloque `index.html` e `config.xml` na pasta do projeto
3. Crie um certificado Samsung (Tools > Certificate Manager)
4. Conecte a TV (Tools > Device Manager)
5. Clique com botão direito no projeto > Run As > Tizen Web Application

---

## 🎮 Controle remoto

| Tecla       | Ação                        |
|-------------|-----------------------------|
| ◄ Esquerda  | Focar na lista de canais    |
| ► Direita   | Focar no player             |
| ▲ ▼         | Navegar na lista / Canal +/- |
| OK / Enter  | Selecionar canal            |
| BACK        | Mostrar/ocultar menu lateral |
| CH+ / CH-   | Próximo/anterior canal      |
| ? ou /      | Mostrar ajuda de teclas     |

---

## 📡 Lista M3U

O app aceita qualquer URL pública de lista M3U/M3U8.  
Na primeira abertura, você insere a URL. Ela fica salva no `localStorage` da TV.

Para trocar a lista: recarregue a página e o app abrirá o menu de configuração novamente (ou limpe o cache do browser).

---

## 🔧 Dependências

- [HLS.js 1.5.13](https://github.com/video-dev/hls.js/) – carregado via CDN Cloudflare (incluído no HTML)
- Fontes Google Fonts (Barlow / Barlow Condensed)

> **Offline/sem internet extra:** Se quiser funcionar 100% offline, baixe o `hls.min.js` e coloque na mesma pasta, ajustando o `<script src>` no HTML.

---

## ⚠️ Notas

- Streams protegidos por DRM (Widevine) **não funcionam** via browser Tizen.
- Para CORS em listas que bloqueiam acesso direto, o app usa automaticamente `corsproxy.io` como fallback.
- Testado em Tizen OS 4.0+.
