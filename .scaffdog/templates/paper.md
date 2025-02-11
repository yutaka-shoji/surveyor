---
layout: default
title: "{{ inputs.title }}"
---

# {{ inputs.title }}

{{ inputs.journal }}, {{ inputs.year }}

{{ inputs.url }}

- 1st author name (affiliation)
- 2nd author name (affiliation)
- ...

---
level: 2
layout: figure-side
figureUrl: ./{{ inputs.year }}-{{ inputs.author | lower }}/public/figure.png
figureCaption: Caption for figure N.
---

::header::

## どんなもの？

::content::

- 論文の主要な貢献
- 提案手法の概要
- 解決しようとしている問題

---
level: 2
layout: figure-side
figureUrl: ./{{ inputs.year }}-{{ inputs.author | lower }}/public/figure.png
figureCaption: Caption for figure N.
---

::header::

## 先行研究と比べてどこがすごいの？

::content::

- 先行研究の課題
- 提案手法の新規性
- 技術的なブレークスルー

---
level: 2
layout: figure-side
figureUrl: ./{{ inputs.year }}-{{ inputs.author | lower }}/public/figure.png
figureCaption: Caption for figure N.
---

::header::

## 技術や手法の"キモ"はどこにある？

::content::

- 提案手法の詳細
- アーキテクチャや実装の工夫
- 重要なアルゴリズムや数式

---
level: 2
layout: figure-side
figureUrl: ./{{ inputs.year }}-{{ inputs.author | lower }}/public/figure.png
figureCaption: Caption for figure N.
---

::header::

## どうやって有効だと検証した？

::content::

- 実験設定
- ベースライン手法
- 評価指標
- 結果と考察

---
level: 2
layout: figure-side
figureUrl: ./{{ inputs.year }}-{{ inputs.author | lower }}/public/figure.png
figureCaption: Caption for figure N.
---

::header::

## 議論はあるか？

::content::

- 手法の限界
- 未解決の課題
- 将来の展望
- 実用化への課題

---
level: 2
layout: default
---

## 次に読むべき論文はあるか？

<!-- 論文中で引用されている参考文献からピックアップ -->

1. Author Name et al. (Year). [Title](https://doi.org/xxxxxx). Journal Name.
   - Summary of the paper.
2. ...
