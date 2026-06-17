# ONE Multiverse — Canonical Hierarchy

> The definitive reference for the ONE Multiverse layer structure.
> All architecture decisions, manifests, and scaffolds must conform to this hierarchy.

---

## The Five Layers

```
Layer 0:  ONE Multiverse
Layer 1:  Universe
Layer 2:  Container Layer (ONE Ecology)
Layer 3:  Ecosystem
Layer 4:  MVP / Product / Deployment
```

Each layer has a manifest, a governance contract, and a SCAFFOLD.md documenting its inheritance chain.
No layer may exist without a parent layer manifest that declares it.

---

## Layer 0 — ONE Multiverse

The meta-architecture. Governs all universes. Contains shared templates and tooling.

- **Manifest:** `multiverse.yaml`
- **Governance:** HASEOS (`github.com/noahnemo1/haseos-spiral-swarm`)
- **Owner:** `noahnemo1`
- **Status:** scaffolded

**Children (Universes):**
| Universe ID | Name | Role | Maturity |
|-------------|------|------|----------|
| one-universe | ONE Universe | reference_implementation | scaffolded |
| one-in-fun-net-universe | ONE In-Fun.net Universe | child_universe | placeholder |
| one-hyper-dimensional-universe | ONE Hyper-dimensional Universe | child_universe | placeholder |

---

## Layer 1 — Universes

Self-contained expressions of the ONE philosophy. Each universe has its own identity,
focus, and cadence, but shares HASEOS governance and SCAFFOLD inheritance law.

### ONE Universe (Reference Implementation)

- **Repo:** `github.com/noahnemo1/ONE-`
- **Manifest:** `one-universe/universe.yaml`
- **Scaffold:** `one-universe/SCAFFOLD.md`
- **Maturity:** scaffolded
- **Governance:** HASEOS

### ONE In-Fun.net Universe (Placeholder)

- **Repo:** not yet created (`github.com/noahnemo1/one-in-fun-net-universe`)
- **Manifest:** `one-in-fun-net-universe/universe.yaml`
- **Maturity:** placeholder
- **Governance:** HASEOS (not yet wired)

### ONE Hyper-dimensional Universe (Placeholder)

- **Repo:** not yet created (`github.com/noahnemo1/one-hyper-dimensional-universe`)
- **Manifest:** `one-hyper-dimensional-universe/universe.yaml`
- **Maturity:** placeholder
- **Governance:** HASEOS (not yet wired)

---

## Layer 2 — Container Layers (ONE Ecology)

Container layers group related ecosystems within a universe. The canonical container layer
in ONE Universe is **ONE Ecology**.

### ONE Ecology (within ONE Universe)

- **Path:** `containers/one-ecology/` within `github.com/noahnemo1/ONE-`
- **Role:** container_layer
- **Maturity:** scaffolded (partially)
- **Governance:** HASEOS

ONE Ecology is the structural envelope for all living ecosystems in ONE Universe.
Every ecosystem must be declared in `universe.yaml` under the ONE Ecology container.

---

## Layer 3 — Ecosystems

Ecosystems are the primary operational units within ONE Universe. Each ecosystem
has its own GitHub repo, governance constitution, and development cadence.

| Ecosystem ID | Name | Repo | Visibility | Maturity |
|-------------|------|------|------------|----------|
| one-church | OurNewEra ONE Church | OurNewEra-ONE-Church | private | in_progress |
| oceanus | Oceanus | Oceanus | private | in_progress |
| one-mesoflex-ai | MesoFlex | MesoFlex | private | in_progress |
| hpm | Human Potential Movement | Human-Potential-Movement | public | scaffolded |
| one-seedfeast-ai | SeedFeast | SeedFeast | private | in_progress |
| one-urban-mines | ONE Urban Mines | one-urban-mines | unknown | placeholder |

All ecosystem repos are owned by `noahnemo1` on GitHub.

---

## Layer 4 — MVPs / Products / Deployments

The leaf nodes of the hierarchy. Deployable software, experiments, programs, and products
that live within an ecosystem.

| MVP ID | Name | Parent Ecosystem | Maturity |
|--------|------|-----------------|----------|
| mesoflex-ai-core | MesoFlex AI Core | one-mesoflex-ai | in_progress |
| seedfeast-ai | SeedFeast AI | one-seedfeast-ai | in_progress |

Additional MVPs are expected to emerge from all ecosystems as they reach `active` maturity.

---

## Governance Across All Layers

```
HASEOS (github.com/noahnemo1/haseos-spiral-swarm)
    │
    ├── Layer 0: ONE Multiverse governance contract
    ├── Layer 1: Universe-level constitutions
    ├── Layer 2: Container layer governance
    ├── Layer 3: Ecosystem-level constitutions
    └── Layer 4: MVP governance (lightweight, inherits from ecosystem)
```

Every layer must have a `governance/constitution.yaml` that:
1. Declares its `governed_by: HASEOS`
2. Defines layer-specific roles and decision protocols
3. References the parent layer's constitution

---

## Naming Conventions

| Convention | Rule |
|------------|------|
| Directory names | lowercase-hyphenated |
| YAML keys | snake_case |
| GitHub repo names | May use mixed case (e.g. `OurNewEra-ONE-Church`) — canonical mapping in `universe.yaml` |
| Architecture IDs | Always lowercase-hyphenated (e.g. `one-church`, not `OurNewEra-ONE-Church`) |
| Owner | Always `noahnemo1` |

---

## Inheritance Chain (Full)

```
multiverse.yaml
    └── one-universe/universe.yaml  (Layer 1 — reference implementation)
            └── containers/one-ecology/  (Layer 2 — container layer)
                    ├── OurNewEra-ONE-Church  (Layer 3 — ecosystem)
                    │       └── [MVPs]  (Layer 4)
                    ├── Oceanus  (Layer 3 — ecosystem)
                    │       └── [MVPs]  (Layer 4)
                    ├── MesoFlex  (Layer 3 — ecosystem)
                    │       └── mesoflex-ai-core  (Layer 4 — MVP)
                    ├── Human-Potential-Movement  (Layer 3 — ecosystem)
                    │       └── [MVPs]  (Layer 4)
                    ├── SeedFeast  (Layer 3 — ecosystem)
                    │       └── seedfeast-ai  (Layer 4 — MVP)
                    └── one-urban-mines  (Layer 3 — ecosystem, placeholder)
                            └── [MVPs]  (Layer 4)
```

---

## What Does NOT Belong Here

The canonical hierarchy governs architecture and governance structure only.
The following are NOT canonical hierarchy concerns:

- Business logic or product features
- Individual code files or functions
- CI/CD pipeline internals
- Infrastructure configs (unless tied to ecosystem governance)
- Marketing or branding assets (unless tied to a manifest)

---

> Generated by [repo-mapper-live](https://github.com/noahnemo1/repo-mapper-live)
> Owner: [noahnemo1](https://github.com/noahnemo1)
> Last updated: 2026-06-17
