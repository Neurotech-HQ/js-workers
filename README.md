# Converting a GitHub Raw File URL to a jsDelivr CDN URL

## Original URL

The original file was hosted on GitHub using the raw content URL format:

```
https://raw.githubusercontent.com/Neurotech-HQ/js-workers/refs/heads/main/build/pdf.worker.5.1.91.mjs
```

This format directly fetches the raw file from the GitHub repository. However, it is **not optimized for CDN delivery** and may suffer from slower performance or rate limits under heavy traffic.

---

## Goal

Convert the GitHub raw link into a CDN-compatible URL using [jsDelivr](https://www.jsdelivr.com/), which provides:

* Global CDN delivery
* Better performance
* Version locking support
* Easy integration with web apps

---

## jsDelivr CDN URL Format

The general format for jsDelivr GitHub CDN links is:

```
https://cdn.jsdelivr.net/gh/{USER}/{REPO}@{TAG_OR_BRANCH}/{FILE_PATH}
```

---

## Conversion Steps

### Step 1: Extract Components

From the original URL:

* **User:** `Neurotech-HQ`
* **Repo:** `js-workers`
* **Branch:** `main`
* **File path:** `build/pdf.worker.5.1.91.mjs`

### Step 2: Construct jsDelivr URL

Combine the components using jsDelivr format:

```
https://cdn.jsdelivr.net/gh/Neurotech-HQ/js-workers@main/build/pdf.worker.5.1.91.mjs
```

> ✅ `refs/heads/main` becomes `@main`

---

## Final CDN URL

```
https://cdn.jsdelivr.net/gh/Neurotech-HQ/js-workers@main/build/pdf.worker.5.1.91.mjs
```

---

## Notes

* You can replace `@main` with a specific **tag** or **commit SHA** to lock the version and ensure stability.
* jsDelivr automatically caches files for better performance, but this may delay updates after a push.
* Consider adding a fallback strategy in production for better reliability.
