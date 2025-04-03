# A Beamer Template for NumPEx Presentations

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15113190.svg)](https://doi.org/10.5281/zenodo.15113190)
[![GitHub Release](https://img.shields.io/github/v/release/numpex/presentation.template)](https://github.com/numpex/presentation.template/releases/latest)
[![Slack](https://img.shields.io/badge/slack-presentation-brightgreen.svg?logo=slack)](https://numpex.slack.com/archives/C08L4KHUTFX)
[![Slack](https://img.shields.io/badge/slack-notifications-blue.svg?logo=slack)](https://numpex.slack.com/archives/C08KRJF3B55)


## Getting Started

Just clone the repository, add the path to your `TEXINPUTS` environment variable, and you are ready to use the theme in your presentation by adding:

```latex
\usetheme{numpex}
```

### Slides template

Checkout `presentation.template.tex`:

```shell
bash a.cli build presentation.template.tex
```

### Poster template

Checkout `poster.template.tex`:

```shell
bash a.cli build poster.template.tex
```

## Fonts

For a better result, you should install the [Marianne font](https://www.systeme-de-design.gouv.fr/elements-d-interface/fondamentaux-de-l-identite-de-l-etat/typographie/) and compile with XeTeX.

### Installing Marianne Fonts

1. **Download the Fonts:**
   - You can download the Marianne fonts using the provided `a.cli` script. Run the following command:
     ```bash
     bash a.cli installfonts
     ```
   - This will download and extract the Marianne fonts into the `fonts/` directory within your project.

2. **Configure LaTeX:**
   - Ensure your LaTeX configuration points to the `fonts/` directory. The provided `beamerfontthemenumpex` package is already configured to use the relative path `fonts/`.

## CI/CD Pipeline

This repository includes a GitHub Actions workflow to compile the LaTeX document and release the PDF artifact. The workflow is triggered on pushes to branches and tags.

### Workflow Steps

1. **Workflow Setup:**
   - Determines the appropriate runner (`ubuntu-latest` or `self-texlive`) based on the availability of a self-hosted runner with the `self-texlive` label.

2. **Build LaTeX:**
   - Compiles the LaTeX document using `latexmk` and `xelatex`.
   - Renames the generated PDF to include the branch or tag name.

3. **Check:**
   - Downloads the artifact and verifies that the LaTeX document compiles correctly from the artifact.

4. **Release:**
   - Creates a GitHub release for tagged commits (e.g., `v1.0.0`).
   - Uploads the PDF and other relevant files as release assets.

## Usage

- **Setup Hooks:**
  ```bash
  bash a.cli setup
  ```

- **Create a Release:**
  ```bash
  bash a.cli create v1.0.0
  ```

- **List Releases:**
  ```bash
  bash a.cli list
  ```

- **Compile the Document:**
  ```bash
  bash a.cli build your_document.tex
  ```

## Contributing

Feel free to open issues or submit pull requests for improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

