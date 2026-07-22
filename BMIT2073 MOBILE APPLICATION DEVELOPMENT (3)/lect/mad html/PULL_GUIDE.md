# Pull MAD HTML Study Guides

## Prerequisites

- Git installed

## Steps

```bash
git clone --depth 1 --branch MAD --single-branch https://github.com/FjingXR/y3s1-note.git y3s1-mad
cd y3s1-mad
git sparse-checkout init --cone
git sparse-checkout set "BMIT2073 MOBILE APPLICATION DEVELOPMENT (3)/lect/mad html"
cd "BMIT2073 MOBILE APPLICATION DEVELOPMENT (3)/lect/mad html"
```

Open `index.html` in your browser.

## Get updates

```bash
git pull
```

That's it.
