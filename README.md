# glibren — PS5 payload releases

Signed releases of **glibren**, the PS5 payload of Game Library Renamer: it renames your game files on the
console from their Title ID and adds a file manager, batch copy / move / delete, a temperature and fan
monitor, and drive and internet speed tests. The page opens on the PS5 (Media tab icon) or on a PC or
phone at `http://PS5-IP:8765`.

> **Test versions.** Use at your own risk on a jailbroken PS5.

## Install

Send `glibren.elf` to your ELF loader (port 9021), for example `nc -q0 PS5-IP 9021 < glibren.elf`.
On the first run it creates the **Game Library Renamer** icon in the Media tab.

## Updates from the PS5

When a newer version is published here, an **Update** button appears on the payload's Games page. The PS5
downloads `glibren.elf` and `glibren.elf.sig` from this repository, **checks the Ed25519 signature** against
the public key built into the payload, and only then installs and restarts it. A file that was changed or
signed by anyone else is refused.

Public key (Ed25519, hex):

```
ce2767604727310aa1b2a5713fe7b76774b7ecd8c68240fef789819a473847c0
```

## Files

| File | What it is |
|---|---|
| `glibren.elf` | latest payload |
| `glibren.elf.sig` | Ed25519 signature of `glibren.elf` (64 bytes) |
| `versao.json` | latest version number, notes, size and SHA-256 |
| `fonte/glibren-VERSION-source.zip` | complete source code of each version |

Every version is also listed under [Releases](../../releases).

## License

[GPL-3.0-or-later](LICENSE). The source code of every published version is in `fonte/` and attached to its
release. Built with [ps5-payload-dev/sdk](https://github.com/ps5-payload-dev/sdk) (GPL-3.0) and
[TweetNaCl](https://tweetnacl.cr.yp.to/) (public domain). Developed by **PristMC**.
