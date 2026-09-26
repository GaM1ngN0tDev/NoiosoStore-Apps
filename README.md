# NoiosoStore Repo

Catalog and app releases powering **NoiosoStore**, the app store client for [NoiosoOS](https://github.com/GaM1ngN0tDev/NoiosoOS).

No server, no account, no tracking — this repo *is* the backend. `catalog.json` lists the available apps, GitHub Releases host the actual APKs, and NoiosoStore just reads both.

---

## What's in here

- **`catalog.json`** — the list NoiosoStore fetches to know which apps exist, their latest version, and where to download them.
- **Releases** *(on the individual app repos, not here)* — each app's actual `.apk` file, published as a GitHub Release.

If you're looking for the source code of the apps themselves, or of NoiosoStore, head to the [main NoiosoOS repo](https://github.com/GaM1ngN0tDev/NoiosoOS).

---

## Apps in the catalog

| App | Status |
|---|---|
| **NoiosoHome** | Ready to install |
| **NoiosoPhone** | Listed, but **not installable yet** — the app isn't finished. It'll show up in NoiosoStore, but installing it will fail until a working release is published. |

More apps will be added here as they reach a usable state. Nothing is listed before it can actually be installed and used — NoiosoPhone above is a temporary exception while it's finished up.

---

## How the catalog works

Each entry in `catalog.json` looks like this:

```json
{
  "id": "com.noioso.home",
  "name": "NoiosoHome",
  "description": "Short one-line description.",
  "longDescription": "Longer description shown on the app's detail page.",
  "developer": "NoiosoOS",
  "version": "1.0",
  "versionCode": 1,
  "downloadUrl": "https://github.com/<repo>/releases/download/<tag>/<file>.apk"
}
```

`versionCode` is what NoiosoStore compares against what's already installed on the phone, to know whether to show **get**, **update**, or **open**.
