# Contextator

**Self-hosted, multi-tenant MCP documentation server.** Give a project its document sources — a mounted
folder, a git repository, an uploaded archive, an Obsidian vault, a Notion workspace — and it becomes its
own [Model Context Protocol](https://modelcontextprotocol.io) endpoint that AI agents (Claude Code, Claude
Desktop, Cursor, …) can search semantically:

```
http://localhost:3444/mcp/<project-name>
```

[![Licence: AGPL-3.0-or-later](https://img.shields.io/badge/licence-AGPL--3.0--or--later-4c1)](https://github.com/Contextator/Contextator/blob/main/LICENSE)
[![Self-hosted](https://img.shields.io/badge/deployment-one%20Docker%20container-2496ed)](https://github.com/Contextator/Contextator#quick-start-docker)
[![MCP](https://img.shields.io/badge/MCP-Streamable%20HTTP%20%2B%20SSE-6e56cf)](https://modelcontextprotocol.io)

One organisation, one product: **[Contextator/Contextator](https://github.com/Contextator/Contextator)** —
the server, its dashboard, and the documentation that comes with it.

---

## What it does

- **One URL per project, fully isolated.** Each project keeps its own documents and vector embeddings in
  PostgreSQL + [pgvector](https://github.com/pgvector/pgvector). A client connected to `/mcp/billing`
  never sees `/mcp/mobile`.
- **Many sources per project.** A local directory, a git repository (or one subdirectory of it), an upload
  of files, folders or archives (`.zip`, `.tar.gz`, `.rar`), an Obsidian vault, a Notion workspace — all
  combined into one searchable endpoint, each source mounted under its own name.
- **100 % local by default.** Embeddings are generated on the CPU with
  [transformers.js](https://huggingface.co/docs/transformers.js) using a multilingual retrieval model.
  Nothing leaves the machine unless you switch to a hosted embedding provider yourself.
- **Both MCP transports on the same URL.** Streamable HTTP for current clients, legacy HTTP+SSE for older
  ones.
- **An admin dashboard.** Add a repository, drop a folder or an archive on the page, test a connection,
  trigger re-indexing and watch the progress.
- **Accounts and roles.** `root` and `admin` manage everything; a `member` sees only the projects it is
  assigned to, as a read-only `viewer` or an `editor`. Each MCP endpoint can be left open or closed behind
  a per-project bearer token.
- **Incremental indexing.** Files are hashed; only what changed is re-embedded, and what was removed is
  deleted.

Stack: TypeScript · Node.js 20+ · Fastify 5 · PostgreSQL 16 + pgvector · Drizzle ORM ·
`@modelcontextprotocol/sdk` · `@huggingface/transformers`. It ships as **one Docker container** holding
both the database and the app.

## Try it

```bash
git clone https://github.com/Contextator/Contextator.git contextator && cd contextator
cp .env.example .env
docker compose up -d
docker compose logs -f            # wait for "embedding model ready"
```

Then create the first account at **http://localhost:3444/setup**, add a project pointing at a folder of
Markdown, and connect an agent to `http://localhost:3444/mcp/<project-name>`. The
[Quick Start](https://github.com/Contextator/Contextator/wiki/Quick-Start) walks through it in full.

## Where things are

| | |
|---|---|
| **Source code** | [github.com/Contextator/Contextator](https://github.com/Contextator/Contextator) |
| **Documentation** | [the project wiki](https://github.com/Contextator/Contextator/wiki) — installation, configuration, document sources, MCP tools, troubleshooting |
| **Website** | [contextator.com](https://contextator.com) |
| **Questions and bugs** | [issues](https://github.com/Contextator/Contextator/issues) |
| **Contributing** | [how to contribute](https://github.com/Contextator/Contextator/contribute) |
| **Security** | [the security policy](https://github.com/Contextator/Contextator/security/policy) — a vulnerability never goes in a public issue |

## Status

Contextator is **pre-release**. `0.1.0` lives on `main`, no tag has been published yet, and upgrading
means pulling and rebuilding. It is used and it works; treat the interfaces as still able to move.

## Who builds it

Contextator is a [Tunedness](https://tunedness.com) project, developed by
[Muhammet Şafak](https://www.muhammetsafak.com.tr/en/).

## Licence

Free software under the **AGPL-3.0-or-later** — run it, read it, change it, share it, and if you offer a
modified version to others over a network, they get its source too. A commercial licence is available for
anyone who needs different terms. See
[`LICENSE`](https://github.com/Contextator/Contextator/blob/main/LICENSE).
