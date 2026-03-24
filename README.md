# MotaDSLUM — Complete Project Package

Everything from the DSL development journey: documentation, knowledge graph, tutorial videos, scripts, generated code, and build tools.

## Contents

```
package/
|-- 01-documents/          Compiled documentation (4 formats)
|   |-- html/              Self-contained HTML with embedded images
|   |-- pdf/               Print-ready PDFs
|   |-- meeting-presentation.md
|   |-- blog-post.md
|   +-- onboarding-guide.md
|
|-- 02-knowledge-graph/    Source of truth (30 nodes, 92 edges)
|   |-- _index.json        Graph structure with nodes, edges, categories
|   |-- build_index.py     Rebuilds index from markdown nodes
|   |-- images/            9 MPS editor screenshots
|   +-- categories/        12 categories of knowledge nodes
|       |-- architecture/  Plugin vs IDE, JSON/Jinja idea, Rust macros
|       |-- textgen/       Walled garden, debugging, parse_textgen bridge
|       |-- hooks/         4 signatures, priority, customer extensibility
|       |-- mps-gotchas/   1:1 constraint, scoping, holder pattern
|       |-- projects/      v1 UMAN, v2 UserManagement, v3 UserManagmentMps
|       |-- experiments/   pcrd, learning projects, DLS/toys
|       |-- tooling/       merge_hooks.py, sync pipeline
|       |-- sdk/           Module path patching
|       |-- deployment/    Docker + NATS setup
|       |-- testing/       demo.sh e2e approach
|       |-- dsl-evolution/ Field types evolution
|       |-- post-success/  Future improvements
|       +-- cross-cutting/ SQL schema generation
|
|-- 03-tutorial-videos/    6 MPS tutorial screencasts
|   |-- 01-creating-a-new-mps-project.mp4           (266MB, stored locally)
|   |-- 02-textgen-template-authoring.mp4            (26MB, stored locally)
|   |-- 03-custom-behaviour-methods.mp4              (59MB, stored locally)
|   |-- 04-packaging-dsl-as-plugin.mp4               (8.5MB, in repo)
|   |-- 05-installing-and-using-plugin.mp4           (24MB, stored locally)
|   +-- 06-bonus-splitting-one-file-into-many.mp4    (7.8MB, in repo)
|
|-- 04-scripts/            All pipeline and tooling scripts
|   |-- sync.sh            MPS output -> project (copy, patch SDK, Docker)
|   |-- merge_hooks.py     Extract hooks from generated files -> userDefinedHooks.go
|   |-- parse_textgen.py   Reverse-engineered MPS TextGen bridge (md -> .mps XML)
|   |-- demo.sh            21 e2e tests via nats CLI
|   +-- demo-interactive.sh Interactive version of demo
|
|-- 05-generated-code/     DSL-generated Go + SQL
|   |-- main.go            NATS microservice entry point
|   |-- user.go            User entity handler
|   |-- roles.go           Roles entity handler
|   |-- permissions.go     Permissions entity handler
|   |-- userDefinedHooks.go Hook implementations (only safe-to-edit file)
|   +-- sqlPrem_init_sql.sql Generated PostgreSQL schema
|
|-- 06-docker/             Container configuration
|   |-- Dockerfile         Multi-stage Go build
|   +-- docker-compose.yml NATS + app service
|
|-- 07-build-tools/        Documentation build pipeline
|   |-- build.py           Markdown/AsciiDoc -> HTML/PDF with embedded images
|   |-- style.css          Custom stylesheet for HTML outputs
|   +-- *.adoc             Feynman guide AsciiDoc source (7 sections)
|
|-- 08-bonus/              Future plans
|   +-- file-splitting-plan.md  BEGIN_FILE comment splitter idea
|
+-- 09-screenshots/        MPS editor screenshots (9 images)
    |-- entity-user-definition-1.png    User entity fields + types
    |-- entity-user-definition-2.png    User entity hooks
    |-- roles-entity-with-relation.png  Roles + Permission_pivot
    |-- permissions-entity-hooks.png    Permissions hooks
    |-- sandbox-overview.png            All 5 root concepts
    |-- structure-tree-all-concepts.png All 19 DSL concepts
    |-- entity-concept-definition.png   Entity concept structure
    |-- main-concept-definition.png     Main config properties
    +-- behavior-tree.png               Behavior definitions
```

## Quick Start

**Read the docs:**
- New to the project? Open `01-documents/html/onboarding.html`
- Want the full technical story? Open `01-documents/html/feynman-guide.html`
- Presenting to the team? Open `01-documents/html/meeting.html`
- Writing about it? Start from `01-documents/html/blog.html`

**Watch the tutorials:** Play videos in `03-tutorial-videos/` in order (parts 1-5)

**Explore the knowledge graph:** Open `02-knowledge-graph/_index.json` or browse `categories/`

**Rebuild docs:** `cd 07-build-tools && python3 build.py`

## Stats

| Metric | Count |
|--------|-------|
| Knowledge nodes | 30 |
| Graph edges | 92 |
| Categories | 12 |
| Screenshots | 9 |
| Tutorial videos | 6 (1 in repo, 5 stored locally) |
| Scripts | 5 |
| Generated Go files | 5 |
| Document formats | 4 (meeting, blog, Feynman, onboarding) |
| Output formats | 3 (markdown, HTML, PDF) |
| Total documentation words | ~18,600 |
