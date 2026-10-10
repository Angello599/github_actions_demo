# github_actions_demo

![CI](https://github.com/Angello599/github_actions_demo/actions/workflows/devops.yml/badge.svg)
![Release](https://img.shields.io/github/v/release/Angello599/github_actions_demo)

Laboratorio 7.1 — CI/CD con GitHub Actions y Python (UTEC, DevOps).

## Pipeline

| Workflow | Disparador | Jobs |
|---|---|---|
| `devops.yml` | push a `main`, PR, manual | `test` → `package` → `docs` / `deploy` (Pages, con aprobación) |
| `release.yml` | tag `v*` | tests + ZIP + GitHub Release con notas generadas |

- **Quality gate:** cobertura mínima 80% (`.coveragerc`); si baja, `test` falla y no se despliega.
- **Página:** https://Angello599.github.io/github_actions_demo/

## Ejecutar en local

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
PYTHONPATH=. pytest -q --cov=hello --cov-report=term-missing
python hello.py
```

## Publicar una versión

```bash
git tag -a v1.0.0 -m "Primera versión estable"
git push origin v1.0.0
```
