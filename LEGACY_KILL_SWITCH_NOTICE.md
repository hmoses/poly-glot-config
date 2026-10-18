# Legacy in-app update switch (retired)

This repository's `min-version.json` was used by earlier native Poly-Glot
binaries as a **blocking** forced-update switch. Some of those binaries
**hardcoded obsolete App Store IDs** rather than using this file's store URLs.

Keep `force: false`. Raising the minimum build number and setting `force:
true` could strand existing customers on a blocking modal pointing to an
incorrect app listing. This cannot be repaired by changing the URL values in
the JSON, since those older binaries ignore the URL values entirely.

The current app versions use a separate **nonblocking** published-version
manifest managed at:
https://github.com/hmoses/poly-glot-ai-workspace/blob/main/public-app-versions.json

Only versions in App Store Connect state `READY_FOR_SALE` are eligible to
appear in that public update manifest. Apple continues to manage downloads
and installations. Older binaries lacking the nonblocking checker must
receive an App Store update before they can use it.
