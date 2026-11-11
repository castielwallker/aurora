<div align="center">

<img src="https://i.imgur.com/49Uet4M.png" alt="Aurora Logo" width="180"/>

# ⚡ Aurora — Why External

**Cliente externo para MTA:SA (GTA San Andreas) com ESP, aimbot, silent aim e escrita em memória via driver de kernel.**

[![Versão](https://img.shields.io/badge/vers%C3%A3o-1.0.0-8a5acc?style=for-the-badge)](https://github.com/castielwallker/aurora/blob/main/manifest/version.json)
[![Plataforma](https://img.shields.io/badge/plataforma-Windows%2010%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/castielwallker/aurora)
[![MTA:SA](https://img.shields.io/badge/MTA%3ASA-compatible-4ade80?style=for-the-badge)](https://multitheftauto.com/)
[![Licença](https://img.shields.io/badge/licen%C3%A7a-Privada-ef4444?style=for-the-badge)](./LICENSE)

</div>

---

> ⚠️ **AVISO LEGAL**
> Usar em servidor online **viola as regras do MTA** e pode resultar em **ban permanente** da conta.
> Use **apenas em jogo local** ou em um **servidor seu**.
> O autor não se responsabiliza pelo uso indevido.

---

## 📸 Preview

<div align="center">

<img src="https://i.imgur.com/VfViaDv.png" alt="Aurora Preview" width="800"/>

</div>

---

## 📌 Sobre este repositório

Este repositório **NÃO contém o código-fonte nem o executável** do Aurora.

Ele existe **exclusivamente** para hospedar o manifesto de atualização automática:

Ele existe **exclusivamente** para hospedar o manifesto de atualização automática:
📁 manifest/
└── version.json



O cliente Aurora consulta esse arquivo periodicamente. Quando encontra uma versão maior que a instalada, baixa o novo `.exe` (a URL vem do próprio manifesto), valida o **SHA-256** e se atualiza sozinho.

---

## ⚙️ Estrutura do manifesto

O `version.json` deve conter:

| Campo | Obrigatório | Descrição |
|:-:|:-:|---|
| `version` | ✅ | Versão nova (ex.: `1.0.1`) |
| `url` | ✅ | Link direto para o `.exe` |
| `sha256` | ✅ | Hash SHA-256 real do executável |
| `notes` | ✅ | Notas da versão |
| `player_ped` | ❌ | Offset opcional |
| `ped_pool` | ❌ | Offset opcional |
| `vehicle_pool` | ❌ | Offset opcional |
| `view_matrix` | ❌ | Offset opcional |

> ⚠️ Se o `sha256` **não bater** com o executável baixado, o cliente **aborta a instalação** (`hash mismatch`).

---

## 🚀 Como publicar uma atualização

### 1. Gerar o hash do executável

```powershell
certutil -hashfile build\Release\Aurora.exe SHA256
