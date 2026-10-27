# gha-python-demo

Proyecto mínimo en Python para probar workflows de GitHub Actions.

## Uso local

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements-dev.txt
pip install -e .
ruff check .
pytest --cov=demo
```

## Probar el workflow

1. Sube el contenido a un repositorio de GitHub (rama `main`).
2. Ve a la pestaña **Actions**: el workflow `CI` se ejecuta con cada push o PR.
3. También puedes lanzarlo a mano con **Run workflow** (`workflow_dispatch`).

## Experimentos útiles

- Rompe un test (p. ej. cambia `sumar` para que reste) y comprueba que el job `test` falla.
- Añade una importación sin usar para ver fallar el job `lint`.
- Añade una versión de Python a la matriz y observa los jobs en paralelo.
