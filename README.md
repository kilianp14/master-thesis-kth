# Master's Thesis

Source for my KTH master's thesis: "Optimistic Consensus under Conformal Risk Control"

The associated implementation and project code is available here: [conformal-consensus](https://github.com/kilianp14/conformal-consensus)

Final thesis is under [`thesis.pdf`](thesis.pdf). Can be built using docker as well:

```bash
docker run --rm \
  -v "$PWD:/work" \
  -w /work \
  texlive/texlive:latest \
  bash -lc '
    apt-get update &&
    apt-get install -y fonts-noto-core fonts-noto-cjk fonts-liberation &&
    mkdir -p /tmp/latexbuild &&
    latexmk -xelatex -outdir=/tmp/latexbuild thesis.tex &&
    makeglossaries -d /tmp/latexbuild thesis &&
    latexmk -g -xelatex -outdir=/tmp/latexbuild thesis.tex &&
    cp /tmp/latexbuild/thesis.pdf /work/thesis.pdf
  '
```

