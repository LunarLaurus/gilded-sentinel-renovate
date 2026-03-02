# Gilded Sentinel Renovate

> _"Supply chain integrity is non-negotiable."_

Gilded Sentinel is the fleet's dependency security advisor. This repository contains the shared Renovate configuration used across all fleet projects to automate dependency neutralisation — keeping the supply chain clean, current, and auditable.

---

## Usage

### Full fleet coverage

Extend the default config to receive coverage for all supported ecosystems:

```json
{
  "extends": ["github>LunarLaurus/gilded-sentinel-renovate"]
}
```

### Selective preset coverage

Projects with a narrower stack can extend individual presets directly:

```json
{
  "extends": [
    "github>LunarLaurus/gilded-sentinel-renovate//presets/base",
    "github>LunarLaurus/gilded-sentinel-renovate//presets/java",
    "github>LunarLaurus/gilded-sentinel-renovate//presets/docker"
  ]
}
```

---

## Presets

| Preset | Managers covered |
|--------|-----------------|
| `base` | Global config — branch naming, PR limits, stability tiers, Gilded Sentinel persona |
| `java` | Maven, Gradle, Gradle Wrapper |
| `go` | gomod (modules + toolchain) |
| `rust` | Cargo, rust-toolchain.toml |
| `python` | pip_requirements, pyproject, poetry, pipenv, pip-compile |
| `node` | npm (engines included) |
| `dotnet` | NuGet |
| `docker` | Dockerfile, docker-compose |
| `actions` | GitHub Actions |

---

## Stability tiers

| Update type | Minimum age before PR | Automerge |
|-------------|----------------------|-----------|
| Patch | 3 days | Yes |
| Minor | 7 days | Yes |
| Major | 14 days | No — manual review required |
| Toolchain | 14 days | No — manual review required |

---

## Fleet conventions

- **Branch prefix:** `Gilded-Sentinel/`
- **Commit prefix:** `Gilded-Sentinel: Neutralise`
- **PR limit:** 15 concurrent, 4 per hour
- **Dashboard:** Dependency threat assessment dashboard enabled per repo
- **Timezone:** Europe/London
