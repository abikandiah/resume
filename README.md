# Resume

Resume content as YAML, rendered to PDF with [RenderCV](https://docs.rendercv.com).
Content lives in the YAML files; look and layout live under `design:` in each file.

## One-time setup (Linux Mint)

Install `uv` (a Python tool installer; it can also fetch Python itself if needed):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
# open a new terminal so `uv` is on your PATH
uv tool install "rendercv[full]"
```

Alternative using apt-provided pipx:

```bash
sudo apt install pipx
pipx ensurepath
pipx install "rendercv[full]"
```

RenderCV requires Python 3.12+. Check the docs for the current install command if either
of these fails.

## Render

```bash
rendercv render cv_software.yaml
```

Output (PDF, and by default other formats) is written to `rendercv_output/`.

## Live editing

```bash
rendercv render cv_software.yaml --watch
```

Re-renders on every save (check `rendercv render --help` for the exact flag in your version).

## Variants

One YAML file per target role, e.g.:

- `cv_software.yaml` — software roles (current baseline)
- `cv_embedded.yaml` — copy of the above, then rewrite the summary, add the MEng entry,
  and reorder or trim projects (e.g. for the ECE2500Y capstone application)

## Pinning the version

To keep output layout stable, pin a version and upgrade deliberately:

```bash
uv tool install "rendercv[full]==X.Y.Z"
```
