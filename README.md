# Chrome - Traefik Docker Template

This is a docker template for Browserelees chrome with traefik proxy configuration.

![Visitor](https://visitor-badge.laobi.icu/badge?page_id=manh21.chrome-traefik)

## Usage

Change Host url to your domain in `docker-compose.yml` file.

```yaml
Host(`chrome.local.example.com`)
```

Configure your envoriment in `docker-compose.yml` file. You can find more information about envoriment variable in [here](https://www.browserless.io/docs/docker).

```yaml
- DEFAULT_BLOCK_ADS=true
- ENABLE_CORS=true
- TOKEN=CHANGE_ME # Leave blank to disable | You can generate token with `openssl rand -hex 16`
- DEMO_MODE=false
- MAX_CONCURRENT_SESSIONS=10
- CONNECTION_TIMEOUT=60000
```

if you use token then your connection url will be like this

```js
const browser = await puppeteer.connect({
  browserWSEndpoint: 'ws://localhost:3000?token=YOUR_TOKEN',
});
```

## More Info

[Chrome image](https://github.com/browserless/chrome)