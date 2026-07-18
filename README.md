<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tu n'es pas seul | Chat Anti-Harcèlement</title>
<style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Arial, sans-serif; }
  body { background: linear-gradient(180deg, #1a1a2e 0%, #0f0f1a 100%); color: #fff; }
  
  header { background: linear-gradient(90deg, #16213e 0%, #0f3460 100%); padding: 40px 20px; text-align: center; }
  header h1 { font-size: 8vw; color: #e94560; text-shadow: 2px 2px 10px #000; margin-bottom: 15px; }
  .slogan { font-size: 4vw; max-width: 700px; margin: 0 auto; line-height: 1.6; background: rgba(233,69,96,0.1); padding: 20px; border-radius: 15px; border: 2px solid #e94560; }
  .slogan span { color: #00ff88; font-weight: bold; }
  
  .container { max-width: 900px; margin: 0 auto; padding: 30px 20px; }
  
  .alerte { background: #e94560; padding: 15px; border-radius: 10px; text-align: center; font-size: 4vw; margin-bottom: 30px; }
  
  .conseils { display: grid; gap: 20px; margin-bottom: 40px; }
  .card { background: #1e1e3a; padding: 25px; border-radius: 15px; border-left: 5px solid #00aaff; transition: 0.3s; }
  .card:hover { transform: translateX(10px); border-color: #e94560; }
  .card h3 { font-size: 5vw; color: #00aaff; margin-bottom: 10px; }
  .card p { font-size: 4vw; line-height: 1.6; opacity: 0.9; }
  
  /* CHAT ANONYME */
  .chat-box { background: #0f3460; padding: 25px; border-radius: 20px; margin: 40px 0; border: 3px solid #00aaff; }
  .chat-box h2 { font-size: 6vw; color: #00ff88; text-align: center; margin-bottom: 10px; }
  .chat-info { font-size: 3.5vw; text-align: center; opacity: 0.8; margin-bottom: 20px; }
  .chat-messages { background: #111; height: 400px; overflow-y: auto; padding: 15px; border-radius: 15px; margin-bottom: 15px; }
  .message { background: #222; padding: 12px; border-radius: 10px; margin-bottom: 10px; max-width: 80%; }
  .message.moi { background: #00aaff; margin-left: auto; }
  .message .pseudo { font-size: 3vw; color: #00ff88; font-weight: bold; margin-bottom: 5px; }
  .message .texte { font-size: 4vw; }
  .chat-input { display: flex; gap: 10px; }
  .chat-input input { flex: 1; padding: 4vw; border-radius: 15px; border: 2px solid #555; background: #222; color: #fff; font-size: 4vw; }
  .chat-input button { padding: 4vw 6vw; background: #25D366; border: none; border-radius: 15px; color: #fff; font-weight: bold; font-size: 4vw; cursor: pointer; }
  
  .cta { background: #0f3460; padding: 30px; border-radius: 20px; text-align: center; margin: 40px 0; }
  .cta h2 { font-size: 6vw; color: #00ff88; margin-bottom: 15px; }
  .cta p { font-size: 4vw; margin-bottom: 20px; }
  
  .btn-group { display: flex; flex-direction: column; gap: 15px; max-width: 500px; margin: 0 auto; }
  .btn { padding: 4vw; border-radius: 15px; font-size: 4.5vw; font-weight: bold; text-decoration: none; color: #fff; border: none; cursor: pointer; transition: 0.3s; display: flex; align-items: center; justify-content: center; gap: 10px; }
  .btn-whatsapp { background: #25D366; }
  .btn-whatsapp:hover { background: #1ebe5b; transform: scale(1.05); }
  .btn-share { background: #00aaff; }
  .btn-share:hover { background: #0088cc; transform: scale(1.05); }
  
  footer { background: #000; padding: 30px 20px; text-align: center; font-size: 3.5vw; opacity: 0.7; }
  .toast { position: fixed; top: 10%; left: 50%; transform: translateX(-50%); background: #00ff88; color: #000; padding: 3vw 6vw; border-radius: 15px; font-size: 4vw; display: none; z-index: 100; font-weight: bold; }
</style>
</head>
<body>

<header>
  <h1>TU N'ES PAS SEUL</h1>
  <div class="slogan">
    << Tu as été harcelé ? Tu ne sais pas quoi faire pour que ça s'arrête ? 
    <span>J'ai des conseils à te donner pour que ça s'arrête.</span>
    Contact moi via WhatsApp au : +225 0700267107 >>
  </div>
</header>

<div class="container">
  
  <div class="alerte">
    ⚠️ Si tu es en danger immédiat, parle à un adulte de confiance ou appelle 111
  </div>
  
  <!-- CHAT ANONYME -->
  <div class="chat-box">
    <h2>💬 CHAT ANONYME D'ENTRAIDE</h2>
    <p class="chat-info">Parle librement. Pas de jugement ici. Pseudo auto-généré pour ta sécurité.</p>
    
    <div class="chat-messages" id="chatMessages">
      <div class="message">
        <div class="pseudo">Modo</div>
        <div class="texte">Bienvenue. Ici on s'écoute et on s'entraide. Tu n'es pas seul.</div>
      </div>
    </div>
    
    <div class="chat-input">
      <input type="text" id="chatInput" placeholder="Écris ton message..." onkeypress="if(event.key==='Enter') envoyerMessage()">
      <button onclick="envoyerMessage()">Envoyer</button>
    </div>
  </div>
  
  <div class="conseils">
    <div class="card">
      <h3>1. N'ENCAISSE PAS EN SILENCE</h3>
      <p>Parle. À un parent, un prof, un ami. Le harcèlement meurt quand on le dénonce.</p>
    </div>
    <div class="card">
      <h3>2. GARDES LES PREUVES</h3>
      <p>Messages, photos, vidéos. Ne supprime rien. Ça servira si tu dois voir le proviseur.</p>
    </div>
    <div class="card">
      <h3>3. BLOQUE ET SIGNALE</h3>
      <p>Sur les réseaux : bloque, signale, mets ton compte en privé.</p>
    </div>
  </div>
  
  <div class="cta">
    <h2>Besoin de parler en privé ?</h2>
    <p>Je réponds à tous les messages WhatsApp personnellement.</p>
    <div class="btn-group">
      <a href="https://wa.me/2250700267107?text=Bonjour, j'ai besoin d'aide concernant du harcèlement." class="btn btn-whatsapp" target="_blank">
        💬 M'ÉCRIRE SUR WHATSAPP
      </a>
      <button class="btn btn-share" id="btnShare">
        🔗 PARTAGER CE SITE
      </button>
    </div>
  </div>
  
</div>

<footer>
  <p>Site créé pour aider. Tu mérites le respect.</p>
  <p>⚠️ Le chat est public. Ne donne jamais d'infos perso: nom, école, adresse.</p>
</footer>

<div class="toast" id="toast">LIEN COPIÉ ! Partage-le pour aider quelqu'un</div>

<script>
// PSEUDO ANONYME
const pseudos = ["Écoute", "Courage", "Espoir", "Force", "Lumière", "Paix", "Soutien"];
const monPseudo = pseudos[Math.floor(Math.random() * pseudos.length)];

// CHAT AVEC SAUVEGARDE
const chat = document.getElementById('chatMessages');
let savedMessages = JSON.parse(localStorage.getItem('chatAntiHarcelement')) || [];

// Charger les messages sauvegardés
savedMessages.forEach(m => {
  const msg = document.createElement('div');
  msg.className = m.classe;
  msg.innerHTML = `<div class="pseudo">${m.pseudo}</div><div class="texte">${m.texte}</div>`;
  chat.appendChild(msg);
});

function envoyerMessage() {
  const input = document.getElementById('chatInput');
  const texte = input.value.trim();
  if(texte === '') return;
  
  const msg = document.createElement('div');
  msg.className = 'message moi';
  msg.innerHTML = `<div class="pseudo">${monPseudo}</div><div class="texte">${texte}</div>`;
  chat.appendChild(msg);
  chat.scrollTop = chat.scrollHeight;
  
  // Sauvegarder
  savedMessages.push({pseudo: monPseudo, texte: texte, classe: 'message moi'});
  localStorage.setItem('chatAntiHarcelement', JSON.stringify(savedMessages));
  
  input.value = '';
  
  // Réponse auto du modo
  setTimeout(() => {
    const rep = document.createElement('div');
    rep.className = 'message';
    rep.innerHTML = `<div class="pseudo">Modo</div><div class="texte">Merci pour ton message. N'hésite pas à parler en privé WhatsApp si tu veux.</div>`;
    chat.appendChild(rep);
    chat.scrollTop = chat.scrollHeight;
  }, 1000);
}

// PARTAGE
const btnShare = document.getElementById('btnShare');
const toast = document.getElementById('toast');
btnShare.onclick = () => {
  const lien = window.location.href;
  navigator.clipboard.writeText(lien);
  toast.style.display = 'block';
  setTimeout(()=>toast.style.display='none', 3000);
}
</script>

</body>
</html># GitHub Copilot CLI

The power of GitHub Copilot, now in your terminal.

GitHub Copilot CLI brings AI-powered coding assistance directly to your command line, enabling you to build, debug, and understand code through natural language conversations. Powered by the same agentic harness as GitHub's Copilot coding agent, it provides intelligent assistance while staying deeply integrated with your GitHub workflow.

See [our official documentation](https://docs.github.com/copilot/concepts/agents/about-copilot-cli) for more information.

![Image of the splash screen for the Copilot CLI](https://github.com/user-attachments/assets/f40aa23d-09dd-499e-9457-1d57d3368887)


## 🚀 Introduction and Overview

We're bringing the power of GitHub Copilot coding agent directly to your terminal. With GitHub Copilot CLI, you can work locally and synchronously with an AI agent that understands your code and GitHub context.

- **Terminal-native development:** Work with Copilot coding agent directly in your command line — no context switching required.
- **GitHub integration out of the box:** Access your repositories, issues, and pull requests using natural language, all authenticated with your existing GitHub account.
- **Agentic capabilities:** Build, edit, debug, and refactor code with an AI collaborator that can plan and execute complex tasks.
- **MCP-powered extensibility:** Take advantage of the fact that the coding agent ships with GitHub's MCP server by default and supports custom MCP servers to extend capabilities.
- **Full control:** Preview every action before execution — nothing happens without your explicit approval.

We're still early in our journey, but with your feedback, we're rapidly iterating to make the GitHub Copilot CLI the best possible companion in your terminal.

## 📦 Getting Started

### Supported Platforms

- **Linux**
- **macOS**
- **Windows**

### Prerequisites

- (On Windows) **PowerShell** v6 or higher
- An **active Copilot subscription**. See [Copilot plans](https://github.com/features/copilot/plans?ref_cta=Copilot+plans+signup&ref_loc=install-copilot-cli&ref_page=docs).

If you have access to GitHub Copilot via your organization or enterprise, you cannot use GitHub Copilot CLI if your organization owner or enterprise administrator has disabled it in the organization or enterprise settings. See [Managing policies and features for GitHub Copilot in your organization](http://docs.github.com/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-github-copilot-features-in-your-organization/managing-policies-for-copilot-in-your-organization) for more information.

### Installation

Install with the install script (macOS and Linux):

```bash
curl -fsSL https://gh.io/copilot-install | bash
```

Or

```bash
wget -qO- https://gh.io/copilot-install | bash
```

Use `| sudo bash` to run as root and install to `/usr/local/bin`.

Set `PREFIX` to install to `$PREFIX/bin/` directory. Defaults to `/usr/local`
when run as root or `$HOME/.local` when run as a non-root user.

Set `VERSION` to install a specific version. Defaults to the latest version.

For example, to install version `v0.0.369` to a custom directory:

```bash
curl -fsSL https://gh.io/copilot-install | VERSION="v0.0.369" PREFIX="$HOME/custom" bash
```

Install with [Homebrew](https://formulae.brew.sh/cask/copilot-cli) (macOS and Linux):

```bash
brew install copilot-cli
```

```bash
brew install copilot-cli@prerelease
```


Install with [WinGet](https://github.com/microsoft/winget-cli) (Windows):

```bash
winget install GitHub.Copilot
```

```bash
winget install GitHub.Copilot.Prerelease
```


Install with [npm](https://www.npmjs.com/package/@github/copilot) (macOS, Linux, and Windows):

```bash
npm install -g @github/copilot
```

```bash
npm install -g @github/copilot@prerelease
```


### Launching the CLI

```bash
copilot
```

On first launch, you'll be greeted with our adorable animated banner! If you'd like to see this banner again, launch `copilot` with the `--banner` flag.

If you're not currently logged in to GitHub, you'll be prompted to use the `/login` slash command. Enter this command and follow the on-screen instructions to authenticate.

#### Authenticate with a Personal Access Token (PAT)

You can also authenticate using a fine-grained PAT with the "Copilot Requests" permission enabled.

1. Visit https://github.com/settings/personal-access-tokens/new
2. Under "Permissions," click "add permissions" and select "Copilot Requests"
3. Generate your token
4. Add the token to your environment via the environment variable `GH_TOKEN` or `GITHUB_TOKEN` (in order of precedence)

### Using the CLI

Launch `copilot` in a folder that contains code you want to work with.

By default, `copilot` utilizes Claude Sonnet 4.5. Run the `/model` slash command to choose from other available models, including Claude Sonnet 4 and GPT-5.

### Experimental Mode

Experimental mode enables access to new features that are still in development. You can activate experimental mode by:

- Launching with the `--experimental` flag: `copilot --experimental`
- Using the `/experimental` slash command from within the CLI

Once activated, the setting is persisted in your config, so the `--experimental` flag is no longer needed on subsequent launches.

#### Experimental Features

- **Autopilot mode:** Autopilot is a new mode (press `Shift+Tab` to cycle through modes), which encourages the agent to continue working until a task is completed.

Each time you submit a prompt to GitHub Copilot CLI, your monthly quota of premium requests is reduced by one. For information about premium requests, see [About premium requests](https://docs.github.com/copilot/managing-copilot/monitoring-usage-and-entitlements/about-premium-requests).

For more information about how to use the GitHub Copilot CLI, see [our official documentation](https://docs.github.com/copilot/concepts/agents/about-copilot-cli).

## 🔧 Configuring LSP Servers

GitHub Copilot CLI supports Language Server Protocol (LSP) for enhanced code intelligence. This feature provides intelligent code features like go-to-definition, hover information, and diagnostics.

### Installing Language Servers

Copilot CLI does not bundle LSP servers. You need to install them separately. For example, to set up TypeScript support:

```bash
npm install -g typescript-language-server
```

For other languages, install the corresponding LSP server and configure it following the same pattern shown below.

### Configuring LSP Servers

LSP servers are configured through a dedicated LSP configuration file. You can configure LSP servers at the user level or repository level:

**User-level configuration** (applies to all projects):
Edit `~/.copilot/lsp-config.json`

**Repository-level configuration** (applies to specific project):
Create `.github/lsp.json` in your repository root

Example configuration:

```json
{
  "lspServers": {
    "typescript": {
      "command": "typescript-language-server",
      "args": ["--stdio"],
      "fileExtensions": {
        ".ts": "typescript",
        ".tsx": "typescript"
      }
    }
  }
}
```

### Viewing LSP Server Status

Check configured LSP servers using the `/lsp` command in an interactive session, or view your configuration files directly.

For more information, see the [changelog](./changelog.md).

## 📢 Feedback and Participation

We're excited to have you join us early in the Copilot CLI journey.

We're building quickly. Expect frequent updates--please keep your client up to date for the latest features and fixes!

Your insights are invaluable! Open an issue in this repo, join Discussions, and run `/feedback` from the CLI to submit a confidential feedback survey!
