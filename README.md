# PAMI — TapMeMo (C1–C3 revision) LaTeX source

IEEE TPAMI 稿件（`bare_jrnl_new_sample4_c123rev`）的完整 LaTeX 源码，可直接在 Overleaf 编译。

## 目录内容

- `bare_jrnl_new_sample4_c123rev.tex` — 主文件（唯一入口，单文件正文）
- `bare_jrnl_new_sample4_c123rev.bib` — 参考文献库（biblatex / biber）
- `figure/` — 正文插图（PDF，含方法图、结果图、实验图）
- `biofig/` — 作者简介照片（JPG）
- `IEEEtran.cls` — IEEE 模板文件（随仓库固定，保证与本地编译一致）

## Overleaf 使用

1. Overleaf → **New Project → Import from GitHub** → 选择 `fengyixuani/PAMI`。
2. 主文件设为 `bare_jrnl_new_sample4_c123rev.tex`（Overleaf 一般会自动识别）。
3. 编译器选 **pdfLaTeX**；参考文献由 **biber** 处理，Overleaf 默认的 `latexmk` 会自动跑 biber，无需手动设置。
4. 直接点 Recompile 即可出 PDF。

若 Overleaf 报 `babel`/`biber` 相关错误，在 Menu → Settings 里确认 Compiler = pdfLaTeX、TeX Live 版本为最新即可。

## 本地编译

```bash
export PATH=/path/to/texlive/2026/bin/x86_64-linux:$PATH
pdflatex -interaction=nonstopmode bare_jrnl_new_sample4_c123rev.tex
biber bare_jrnl_new_sample4_c123rev
pdflatex -interaction=nonstopmode bare_jrnl_new_sample4_c123rev.tex
pdflatex -interaction=nonstopmode bare_jrnl_new_sample4_c123rev.tex
```

（若装了 `latexmk`，一条 `latexmk -pdf bare_jrnl_new_sample4_c123rev.tex` 即可。）

## 说明

- 仓库只保留源码与图片，编译中间产物（`.aux/.log/.bbl/.bcf/.out/.run.xml` 等）已在 `.gitignore` 中忽略。
- 源文件中的红/蓝颜色标注为修订标记，不影响编译。
- 本地已验证：TeX Live 2026 + pdfLaTeX + biber，可编译出 38 页、约 10 MB 的 PDF。
