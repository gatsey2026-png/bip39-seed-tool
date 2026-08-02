# BIP-39 Seed Tool

A single-file, fully offline BIP-39 recovery phrase generator, with Ethereum
(EVM) and Bitcoin address derivation. No build step, no external libraries,
no CDNs, no network requests of any kind — everything (BIP-39, secp256k1,
Keccak-256, RIPEMD-160, Base58Check, Bech32) is implemented from scratch in
`index.html` and validated against official test vectors.

**Live version:** 
https://github.com/gatsey2026-png/bip39-seed-tool

## Using this safely

This tool generates real cryptocurrency seed phrases. For anything beyond
testing/curiosity:

- **Download `index.html` and open it locally** (double-click it, or drag it
  into a browser tab) rather than relying on the hosted version. That way
  nothing about your session depends on GitHub's availability or the
  integrity of the network path to it.
- Consider disconnecting from the internet after the page loads — it never
  needs to make a request, so this changes nothing about how it works.
- Read the "About & Security Notes" tab in the tool itself before using it
  for anything real.
- This repo, like the tool's own disclaimer, comes with **no warranty of
  any kind** — see the disclaimer shown every time the tool runs.

## Deploying your own copy via GitHub Pages

1. Push this repo to GitHub (public repo — required for free GitHub Pages
   unless you have GitHub Pro/Team/Enterprise).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose `main` and `/ (root)`, then **Save**.
5. Wait a minute or two — your live URL will appear at the top of that same
   Pages settings screen, in the form
   
Randomness source
This phrase is generated using your browser's built-in crypto.getRandomValues() — a cryptographically secure pseudorandom number generator (CSPRNG) provided by your operating system. It's the same class of random number generator that underlies HTTPS/TLS security across the web, and is a well-audited, standard source suitable for generating cryptocurrency keys.

Optional: add physical dice
CSPRNG is already cryptographically secure on its own — dice are entirely optional. Their purpose is independence: if you'd rather not have to trust this specific device's random number generator alone (for example, on a machine you're not sure is clean, or if you just want a second, physically-verifiable source of randomness you control yourself), roll physical dice and enter the results below. They get combined with the CSPRNG output by hashing both together, so the result is never weaker than the CSPRNG alone — only ever stronger.
