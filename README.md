# trifecta

The CompTIA practice site for Western Tech, served by GitHub Pages from this repo.

**This repo holds one built, sealed file and nothing else.** The application source and
the question banks live in a separate private repo. Do not add them here: this repo is
public, and GitHub code search indexes everything in it.

`index.html` is the whole site. The question banks inside it are encrypted
(PBKDF2-SHA256 x310,000 -> AES-256-GCM); it asks for the class passphrase before it opens.
Rotating the passphrase means rebuilding and pushing a new `index.html`.

Rebuild from the source repo:

    python3 tools/build.py --passphrase 'THE-PASSPHRASE' --pages
    # then copy dist/pages/* into this repo and push
