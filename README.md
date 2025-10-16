# Rushan Gaming Website

A modern gaming website with automated deployment via GitHub Actions.

## 🚀 Deployment Setup

This repository automatically deploys to your aaPanel server at `rushan.run.place` whenever you push to the main branch.

### GitHub Secrets Configuration

Add these secrets to your GitHub repository:

1. Go to **Settings → Secrets and variables → Actions → New repository secret**

2. Add the following secrets:

| Secret Name | Value |
|-------------|-------|
| `SSH_HOST` | `13.229.36.76` |
| `SSH_USERNAME` | Your SSH username (usually `root`) |
| `SSH_PRIVATE_KEY` | Your private SSH key (see below) |
| `SSH_PORT` | `22` (or your custom SSH port) |

### Getting Your SSH Private Key

On your local machine, run:
```bash
cat ~/.ssh/id_rsa
```

Copy the **entire output** including:
- `-----BEGIN RSA PRIVATE KEY-----`
- All the lines in between
- `-----END RSA PRIVATE KEY-----`

Paste this as the `SSH_PRIVATE_KEY` secret value.

### How It Works

1. Push changes to the `main` branch
2. GitHub Actions automatically triggers
3. Files are copied to `/www/wwwroot/rushan.run.place/` on your server
4. Correct permissions are set (`www:www` owner, `644` permissions)
5. Your website is live!

### Manual Deployment

You can also trigger deployment manually:
1. Go to **Actions** tab
2. Select **Deploy to Server via SSH**
3. Click **Run workflow**

## 📁 Project Structure

```
.
├── index.html              # Main website file
├── .github/
│   └── workflows/
│       ├── deploy-ssh.yml  # SSH deployment workflow
│       └── static.yml      # GitHub Pages deployment
└── README.md              # This file
```

## 🌐 Live URLs

- **Production Server**: https://rushan.run.place
- **GitHub Pages**: (if enabled)

## 🛠️ Local Development

Simply open `index.html` in your browser to preview changes locally.

## 📝 License

© 2026 Rushan Gaming. All rights reserved.
