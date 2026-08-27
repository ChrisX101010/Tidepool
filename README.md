# zk-demo — Rust simulacije za prezentaciju "Pregled ZK rollupova"

Bez ijedne spoljne zavisnosti (SHA-256 je implementiran u `src/sha256.rs`),
pa radi i bez interneta.

## Pokretanje u WSL-u

```bash
cd zk-demo
cargo run              # sve tri simulacije redom
cargo run -- 1         # mini ZK rollup: batch, dokaz, L1 verifier
cargo run -- 2         # Taiko bridge exploit: ranjivi vs popravljeni bridge
cargo run -- 3         # Lighter: exit hatch i instant upgrade
cargo test             # provera SHA-256 protiv poznatih vektora
```

Ako nemaš Rust u WSL-u:
```bash
sudo apt update && sudo apt install -y cargo rustc
```

## Struktura

| Fajl | Šta radi |
|---|---|
| `src/rollup.rs` | Merkle state root, batch izvršavanja, L1 verifier koji odbija lažnu tranziciju |
| `src/bridge.rs` | Bug iz Taiko incidenta: root dolazi od pozivaoca i nikad se ne proverava |
| `src/lighter.rs` | Forced tx, exit hatch posle 14 dana, pa instant upgrade koji sve poništi |
| `src/sha256.rs` | SHA-256, ~100 linija, bez `crates.io` |

Solidity verziju istog bug-a (`03_Bridge.sol`) možeš prikazati u Remix-u
(remix.ethereum.org) ili prevesti u WSL-u ako imaš Foundry:
```bash
forge build
```
