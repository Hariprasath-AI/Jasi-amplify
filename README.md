# Hello World — AWS Amplify + GitHub

A minimal static site (HTML/CSS/JS, no build tools) ready to deploy on AWS Amplify Hosting via a GitHub repo.

## Files

- `index.html` — the page
- `style.css` — styling
- `script.js` — tiny script that stamps the load time
- `amplify.yml` — build spec telling Amplify this is a static site (no build step)

## 1. Push this to GitHub

```bash
cd hello-world-amplify
git init
git add .
git commit -m "Initial commit: Hello World for Amplify"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

(Create the empty repo on GitHub first, via the website or `gh repo create`.)

## 2. Connect the repo in AWS Amplify

1. Go to the [AWS Amplify Console](https://console.aws.amazon.com/amplify/).
2. Click **New app** → **Host web app**.
3. Choose **GitHub** as the source, authorize AWS Amplify to access your GitHub account if prompted.
4. Select the repository and the `main` branch.
5. Amplify will auto-detect `amplify.yml` in the repo root — confirm the build settings shown match the one in this project (no install/build commands needed).
6. Click **Save and deploy**.

Amplify will pull the repo, run the (empty) build, and deploy `index.html` and friends to a generated `https://main.<app-id>.amplifyapp.com` URL. Every future push to `main` auto-deploys.

## Optional: custom domain

In the Amplify console, go to your app → **Domain management** → **Add domain**, and follow the steps to point a custom domain at your Amplify app.
