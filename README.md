# 🩺 **mi-primer-proyecto-ci**

> *Deep‑learning pipeline to prep medical chest‑X‑ray data, fine‑tune SOTA CNNs for COVID‑19 detection and launch an interactive **Streamlit** dashboard—all inside one notebook.*

<p align="center">
  <img src="assets/demo.gif" alt="Demo GIF" width="750">
</p>

<p align="center">
  <a href="https://github.com/<USER>/mi-primer-proyecto-ci/actions"><img src="https://img.shields.io/github/actions/workflow/status/<USER>/mi-primer-proyecto-ci/ci.yml?branch=main&label=CI" /></a>
  <img src="https://img.shields.io/github/last-commit/<USER>/mi-primer-proyecto-ci" />
  <img src="https://img.shields.io/github/license/<USER>/mi-primer-proyecto-ci" />
  <img src="https://img.shields.io/badge/python-3.10%20|%203.11-blue" />
</p>

---

## 📚 Tabla de contenido

* [Sneak‑peek](#sneak%E2%80%91peek)
* [Características](#características)
* [Instalación rápida](#instalación-rápida)
* [Estructura del proyecto](#estructura-del-proyecto)
* [Uso del notebook](#uso-del-notebook)
* [Dashboard interactivo](#dashboard-interactivo)
* [CI & CD](#ci--cd)
* [Roadmap](#roadmap)
* [Contribuir](#contribuir)
* [Licencia](#licencia)

---

## Sneak‑peek

| Dashboard 📊                                   | Grad‑CAM 🔍                                  |
| ---------------------------------------------- | -------------------------------------------- |
| <img src="assets/dashboard.png" width="360" /> | <img src="assets/gradcam.png" width="360" /> |

> Sube una radiografía ➜ predicción al instante, probabilidad y mapa de calor explicativo.

---

## Características

* ⚡ **End‑to‑end**: *download → clean → train → deploy* con un click.
* 🤖 **Modelos**: EfficientNetB0 / MobileNetV2 / DenseNet121 (transfer + fine‑tune).
* 🏆 **Métricas**: Precisión, Recall, F1, AUC con *cosine scheduler + warm‑up*.
* 🌐 **Dashboard Streamlit**: upload, Grad‑CAM, métricas en vivo y descarga del modelo.
* 🧪 **Tests & Lint**: `pytest`, `pytest‑nb`, `ruff`, `black`.
* 💻 **CI/CD**: GitHub Actions — tests, docs (MkDocs), release artefactos.

---

## Instalación rápida

```bash
# ▶️ Google Colab (GPU)
# Haz clic en el badge "Open in Colab" del repo y ejecuta todo.

# 💻 Local (Linux/MacOS)
git clone https://github.com/<USER>/mi-primer-proyecto-ci.git
cd mi-primer-proyecto-ci
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab Copia_de_Final_proyecto.ipynb
```

> **Requisitos mínimos**: Python 3.10, TensorFlow ≥ 2.16, OpenCV ≥ 4.10, Streamlit ≥ 1.35.

---

## Estructura del proyecto

```text
mi-primer-proyecto-ci/
├── Copia_de_Final_proyecto.ipynb   ← Notebook principal
├── src/                           ← Utils extraídos (próximo paso)
├── data/                          ← Creados en Fase 1
├── models/                        ← Pesos entrenados (Fase 2)
├── dashboard/                     ← Streamlit app
├── docs/                          ← MkDocs site
└── .github/workflows/             ← CI config
```

---

## Uso del notebook

1. **Fase 1 📦 Dataset** – descarga y limpieza,
2. **Fase 2 🧠 Entrenamiento** – fine‑tuning + callbacks,
3. **Fase 3 📊 Dashboard** – lanza `streamlit run dashboard/app.py` (ngrok en Colab),
4. **Fase 4 💾 Export** – empaqueta modelo + data.

Cada fase está marcada en el notebook con títulos grandes y emojis 👍.

---

## Dashboard interactivo

```bash
# Lanza localmente
ython -m streamlit run dashboard/app.py
```

* **Upload** – Sube imagen
* **Predicción** – Etiqueta + probabilidad
* **Grad‑CAM** – Explicabilidad
* **Metrics** – Curvas, matriz de confusión

Puedes exponer públicamente con **ngrok** (lo hacemos automáticamente en Colab).

---

## CI & CD

| Job             | Acción                               |
| --------------- | ------------------------------------ |
| **Test & Lint** | `pytest`, `pytest‑nb`, `ruff`        |
| **Build Docs**  | MkDocs Material ➜ GitHub Pages       |
| **Release**     | ZIP con modelo + data como artefacto |

Mira el workflow [`ci.yml`](.github/workflows/ci.yml).

---

## Roadmap

* [ ] Extraer utilidades a `src/` + docstrings
* [ ] Cobertura de tests ≥ 80 %
* [ ] Publicar dataset pre‑procesado en Kaggle/Zenodo
* [ ] Añadir Dockerfile
* [ ] Demo permanente en Hugging Face Spaces

---

## Contribuir

> ¡Las PRs son bienvenidas! Lee primero [`CONTRIBUTING.md`](CONTRIBUTING.md).

```bash
git checkout -b feat/mi-feature
# Haz tu magia 🚀
git commit -m "feat: mi feature"
git push origin feat/mi-feature
```

---

## Licencia

Distribuido bajo licencia **MIT**. Ver [`LICENSE`](LICENSE).

---

<p align="center">Hecho con ❤️ y ☕ por <FRANK MILLER ALIPIO></p>
