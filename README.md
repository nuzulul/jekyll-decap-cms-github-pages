# jekyll-decap-cms-github-pages

Jekyll + Decap CMS hosted on Github Pages

Demo : [https://nuzulul.github.io/jekyll-decap-cms-github-pages/admin](https://nuzulul.github.io/jekyll-decap-cms-github-pages/admin)

## Decap CMS Installation

### 1. Create OAuth application at Github

- Go to [https://github.com/settings/developers](https://github.com/settings/developers)
- Create `New OAuth app`
- Set `Application name` to anything you like
- Set `Homepage URL` to your Github Pages URL
- Set `Authorization callback URL` to `https://api.netlify.com/auth/done`
- Clik `Register application`
- Generate a `Client Secret`
- Copy the `Client ID` and `Client Secret`

### 2. Setup Netlify OAuth Provider

- Create Netlify new dummy site or existing one
- Go to `Site configuration` > `Access & security` > `OAuth`
- Under `Authentication Providers`, select `Install Provider`
- Select `GitHub` and enter the `Client ID` and `Client Secret` from earlier, then save
- Copy the site domain

### 3. Configure Decap CMS

- Update your Decap CMS `config.yml`
```yaml
backend:
  name: github # backend to use
  repo: nuzulul/jekyll-decap-cms-github-pages # your username and repo
  branch: main # branch to use
  site_domain: jekyll-decap-cms-github-pages.netlify.app # netlify site domain
  base_url: https://api.netlify.com # required
  auth_endpoint: /auth # required
```