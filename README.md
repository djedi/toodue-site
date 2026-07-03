# toodue-site

Marketing site for [TooDue](https://github.com/djedi/toodue), served at https://toodue.com.
SvelteKit + `adapter-static`; the whole site prerenders to plain HTML/CSS/JS.

## Develop

```sh
npm install
npm run dev
```

## Build

```sh
npm run build   # output in build/
```

## Deploy

The site is static files behind Caddy on the `cheap` server:

```sh
npm run build
rsync -av --delete build/ dustin@108.181.221.120:~/sites/toodue-marketing/
```

Caddy serves `~/sites/toodue-marketing` (mounted at `/home/sites/toodue-marketing`
in the caddy container) for `toodue.com` / `www.toodue.com`.
