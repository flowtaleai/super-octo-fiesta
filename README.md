# super-octo-fiesta

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://flowtaleai.github.io/super-octo-fiesta/lab/index.html?path=test_tasks.ipynb)

A JupyterLite deployment with xeus-python kernel for running Python notebooks entirely in the browser.

## 🚀 Try it out

Click the badge above to launch JupyterLite in your browser! No installation required.

## 📝 About

This repository uses [JupyterLite](https://jupyterlite.readthedocs.io/) with the [xeus-python](https://github.com/jupyter-xeus/xeus-python) kernel to provide a fully client-side Jupyter environment. The notebook runs entirely in your browser using WebAssembly.

### Features

- ✨ No server required - runs completely in your browser
- 🐍 Full Python kernel via xeus-python
- 📦 Pre-installed packages: pandas, numpy
- 🔄 Automatic deployment via GitHub Actions

## 🛠️ Setup

This repository is configured to automatically deploy to GitHub Pages when you push to the main branch.

### Prerequisites

1. Enable GitHub Pages for your repository:
   - Go to Settings → Pages
   - Under "Source", select "GitHub Actions"

2. Ensure GitHub Actions has write permissions:
   - Go to Settings → Actions → General
   - Under "Workflow permissions", select "Read and write permissions"

### Adding Packages

To add more packages to the JupyterLite environment, edit `environment.yml` and add them under `dependencies`:

```yaml
dependencies:
  - xeus-python
  - pandas
  - numpy
  - your-package-here  # Add your package
```

See the [xeus-python documentation](https://jupyterlite-xeus.readthedocs.io/en/latest/environment.html) for more information on available packages.

### Adding Notebooks

Place your `.ipynb` files in the `content/` directory. They will be automatically included in the JupyterLite deployment.

## 🏗️ Local Development

To build and preview the site locally:

```bash
# Install dependencies
mamba env create -f environment.yml
conda activate xeus-python-kernel

# Build the site
jupyter lite build --contents content --output-dir dist

# Serve locally (requires a web server)
python -m http.server -d dist
```

Then open http://localhost:8000 in your browser.

## 📚 Resources

- [JupyterLite Documentation](https://jupyterlite.readthedocs.io/)
- [xeus-python Documentation](https://github.com/jupyter-xeus/xeus-python)
- [xeus-lite Demo](https://github.com/jupyterlite/xeus-lite-demo)

## 📄 License

This repository template is based on [jupyterlite/xeus-lite-demo](https://github.com/jupyterlite/xeus-lite-demo).
