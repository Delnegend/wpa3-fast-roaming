<div align="center">

# wpa3-fast-roaming

**Generate fast-roaming settings for your OpenWrt access points in the browser: paste AP MACs, get ready-to-apply 802.11r/PMF config — nothing leaves your machine.**

[![License](https://img.shields.io/github/license/Delnegend/wpa3-fast-roaming?style=flat-square)](LICENSE)

</div>

> **Archived.** Kept as a working page; the generator runs entirely in your browser and the repo is read-only.

## Quick Start

No install — the page runs client-side:

```text
1. Open https://delnegend.github.io/wpa3-fast-roaming/
2. Paste your AP MAC addresses, one per line
3. Copy the output as config-file snippets or UCI commands
```

## Highlights

- **Private by construction** — everything (including the generated mobility keys) computes in-page; pasted MACs never leave the tab in this two-file, no-backend setup.
- **Two output styles** — `option` lines for `/etc/config/wireless`, or `uci set` commands to paste over SSH.
- **Same keys everywhere it matters** — one mobility domain and one pre-shared R0 key shared across all your APs, per-AP `nasid`/`r1_key_holder` lists generated to match.
- **Opinionated, modern defaults** — 802.11r on, pre-shared keys (no RADIUS needed), PMF required (`ieee80211w 2`) as WPA3 setups expect.

## Layout

| File | Purpose |
|---|---|
| `index.html` | The page: MAC input, format picker, output pane, apply instructions |
| `index.js` | Zero-dependency generator: random mobility domain + R0 key, per-AP 802.11r/PMF settings, `r0kh`/`r1kh` lists |

> Heads-up: pasted lines are used verbatim, so keep the input to real MACs (`tcpdump`, your DHCP lease table, or the label under the AP). Random examples are pre-filled so the page never renders empty.

## License

[MIT](LICENSE)
