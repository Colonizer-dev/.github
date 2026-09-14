<p align="center">
  <img src="https://raw.githubusercontent.com/Colonizer-dev/.github/main/assets/org-banner.png" alt="Colonizer. Colonize your backlog. Coding agents in private microVMs, linked home, returning pull requests." width="100%">
</p>

<p align="center">
  <a href="https://github.com/Colonizer-dev/harness"><img src="https://img.shields.io/badge/HARNESS-SHIPPING-EDEBE6?style=for-the-badge&labelColor=0A0A0B" alt="Harness: shipping"></a>
  <img src="https://img.shields.io/badge/COLONIZER.DEV-PLANNED-8A8A8E?style=for-the-badge&labelColor=0A0A0B" alt="colonizer.dev: planned">
  <img src="https://img.shields.io/badge/LICENSE-MIT-FF6B35?style=for-the-badge&labelColor=0A0A0B" alt="License: MIT">
</p>

<p align="center">
  <sub>
    <a href="https://github.com/Colonizer-dev/harness">Harness</a> &nbsp;·&nbsp;
    <a href="https://github.com/Colonizer-dev/harness/blob/main/docs/vision.md">Vision</a> &nbsp;·&nbsp;
    <a href="https://github.com/Colonizer-dev/harness/blob/main/docs/architecture.md">Architecture</a> &nbsp;·&nbsp;
    <a href="https://github.com/Colonizer-dev/harness/blob/main/docs/protocol.md">Protocol</a> &nbsp;·&nbsp;
    <a href="https://github.com/Colonizer-dev/harness#what-this-does-not-do">What it does not do</a>
  </sub>
</p>

---

## Colonize your backlog.

Every issue gets a colony: a private microVM with a fresh worktree and a coding agent inside. Colonies
stay linked to your machine over a private mesh, ask you questions as choices, and come home as pull
requests.

Your machine is the mothership. It holds the credentials, and no colony ever does. The code is MIT.

---

## Two things, and which is which

This matters more than anything else on this page, so it is first.

| | What it is | Status |
| :--- | :--- | :--- |
| **Harness** | The open-source core, MIT, in [`Colonizer-dev/harness`](https://github.com/Colonizer-dev/harness). Runs on one Linux machine today. | `SHIPPING` |
| **Colonizer** | Everything beyond one machine: remote outposts, a fleet view, and anything hosted at colonizer.dev. | `PLANNED` |

Nothing beyond the harness is built. [colonizer.dev](https://colonizer.dev) is a name, not a product,
and there is no price, published or estimated.

Two labels are used everywhere, and they govern the tense of the sentence around them:

- `SHIPPING`: merged, in a public repository, and exercised on a real machine.
- `PLANNED`: named, unspecified. Nothing written.

---

## A colony, as the mothership logged it

Real, from the mothership's log for one colony on 14 September 2026, before the repository moved to
this organisation. Unedited.

```text
13:19:38 cloning https://github.com/ParallelEntrepreneur/colonizer.git (first session for this repository)
13:19:40 fetching origin
13:19:41 creating worktree on branch colonizer/session-79fabc85 from origin/main
13:19:41 starting the private mesh
13:19:41 booting microVM colonizer-79fabc85 (node:24-bookworm, 4 vCPU, 8G)
13:19:41 waiting for the microVM to join the private mesh
13:19:44 colonizer-79fabc85 joined the mesh at 100.64.0.2
13:19:50 agent daemon is ready
13:19:50 connected to the agent
```

Twelve seconds from nothing to an agent in its own machine, on its own branch, one WireGuard hop
away. Seven seconds later it asked its first question, as a card with two options.

---

## The argument, in five points

**1. A colony is a machine, not a container.** Each task runs in a KVM microVM with its own kernel. The
agent works without permission prompts, because there is nothing worth protecting on the other side of
the wall.

**2. Secrets stay home.** The GitHub token never enters a colony. The agent's API credential is a
placeholder, swapped in by a host-side TLS proxy for exactly one host. The mothership commits and opens
the pull request after the colony is gone, and treats what the colony left behind as untrusted.

**3. Every colony is one hop away.** A private mesh (bundled Headscale and WireGuard) links each colony
to the mothership, separate from any network you already use. Chat and a real terminal ride on it.
Colonies can't reach each other.

**4. Decisions, not prose.** When an agent needs you, it asks with concrete choices and an "Other"
answer. If it slips into a plain-text question, it is asked to try again as a card.

**5. Everything is a module.** Source, sandbox, mesh, agent, interfaces and publish are swappable
providers behind small contracts. The agent contract is JSON Lines on stdio, so a module can be written
in anything.

---

## The six module kinds

| Kind | Today | Next |
| :--- | :--- | :--- |
| `source` | GitHub issues and repositories | GitLab, Linear, Jira `PLANNED` |
| `sandbox` | microsandbox KVM microVMs | other VMMs `PLANNED` |
| `mesh` | Private mesh, or a loopback port | remote outposts `PLANNED` |
| `agent` | Claude Code | more agents on the same protocol `PLANNED` |
| `interfaces` | Chat with choice cards, terminal | dev-server previews `PLANNED` |
| `publish` | GitHub pull request | review comments as follow-ups `PLANNED` |

---

## What this does not do

Stated here rather than buried, because trust is the whole point.

- **One machine, Linux x86_64 with KVM.** No macOS, no remote hosts yet.
- **One agent, one forge.** Claude Code and GitHub.
- **No login on the web UI.** It binds to loopback and should stay there.
- **Not yet run end to end:** opening a pull request from a colony, and the installed-app mode of the
  installer. Both are implemented.
- **No CI, no releases, nothing on crates.io or npm.**

---

## Roadmap, in public

| Capability | Status | Where |
| :--- | :--- | :--- |
| Colonies, private mesh, choice cards, terminal, Claude Code module, GitHub source and publish | `SHIPPING` | [harness](https://github.com/Colonizer-dev/harness) |
| CI for the Rust, runner and UI suites | `PLANNED` | not started |
| More agent modules | `PLANNED` | not started |
| GitLab, Linear and Jira sources | `PLANNED` | not started |
| Remote outposts joining the mesh | `PLANNED` | not started |
| Fleet view, budgets and network policies per colony | `PLANNED` | not started |

The roadmap is the issue tracker. There is no private version of it.

---

## Repositories

| Repo | What it is |
| :--- | :--- |
| [**harness**](https://github.com/Colonizer-dev/harness) | The open-source core: mothership, in-VM daemon, agent module, web UI, bundled mesh. MIT |
| **.github** | This page and the mark |

<p align="center">
  <br>
  <a href="https://github.com/Colonizer-dev/harness"><b>github.com/Colonizer-dev/harness</b></a>
  &nbsp;·&nbsp;
  <a href="https://colonizer.dev">colonizer.dev</a>
</p>

<p align="center">
  <sub>MIT license · Colonize your backlog.</sub>
</p>
