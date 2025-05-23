# タスク概要

あなたが行うべきタスクは大きく以下の二つに分かれます。  
それぞれのタスクについて、詳細な手順を記載していますので、指示に従って作業を進めてください。

1. 論文要約: 「サーベイ開始」または「start survey」と言われたら、`incoming/`ディレクトリ内の論文それぞれに対して、順に[1. 論文サーベイの作業手順](#1-論文要約の作業手順)に従って作業を進めてください。論文が複数保存されている場合、1つの論文に対して作業を進めたら、次の論文に進んでください。
2. トピック要約: 「トピック要約開始 topics/{topic-name}」または「start summarize」と言われたら、`topics/`ディレクトリ内の指定されたトピックに対して、[2. トピック要約の作業手順](#2-トピック要約の作業手順)の指示に従って作業を進めてください。

## 1. 論文要約の作業手順

論文が複数保存されている場合、以降の手順を1つの論文ごとに順に進めてください。

### 1.1 初期セットアップ

1. `README.md`を確認し、リポジトリのスコープとディレクトリ構造を理解
2. `incoming/`ディレクトリ内の全ファイルの内容を確認する
3. 論文を分析し、適切なトピックを判断
4. トピックディレクトリが存在しない場合は新規作成. 適切なトピックディレクトリが既に存在する場合はそのまま次に進む.
   ```sh
   npx scaffdog generate slides \
     --force \
     --output "topic-name" \
   ```

### 1.2 ファイル変換と管理

1. 図表をPNG形式に変換 (※図がpngでない場合)
   - デフォルトシェルを確認 (bash/fish/pwsh?) し、適切なコマンド構文を使用
   - 解像度: 300 DPI
   - 使用ツール:
     - macOS: sips
     - その他: magick (ImageMagick)
2. 変換した画像ファイルを `topics/{topic-name}/{yyyy-author}/public/` ディレクトリに保存

### 1.3 スライド作成プロセス

1. 論文要約スライドの生成
   - 論文タイトルは完全な形で記載（省略禁止）
   - 引用情報のbibファイルから抽出した論文へのURLまたはDOIを記載
   ```sh
   npx scaffdog generate paper \
     --force \
     --output "topic-name" \
     --answer "year:yyyy" \
     --answer "journal:journal-name" \
     --answer "author:author-name" \
     --answer "title:paper-title" \
     --answer "url:paper-url"
   ```
2. 論文全体を精読し、内容を分析・解釈
3. 以下の6つの質問に基づくフォーマットで要約スライドを作成
   1. どんなもの？
   2. 先行研究と比べてどこがすごいの？
   3. 技術や手法のキモはどこにある？
   4. どうやって有効だと検証した？
   5. 議論はあるか？
   6. 次に読むべき論文はあるか？
      - bibファイルからURL情報を抽出
      - Markdown形式でリンクを作成: [論文タイトル](URL)
      - タイトルは完全な形で記載
      - 著者名は _et al._ 形式を使用
4. 図表の配置
   - 作成した要約スライドのページごとの内容を解釈し、ページごとの内容と関連性のある図表を、根拠を示して選択
   - 各ページに選択した図表を配置 (パス指定形式: `figureUrl: ./yyyy-author/public/figure.png`)
   - 図のキャプションを図の下に記載
   - 図表と本文の関連性を批判的に検証。図表が不適切な場合は図表の再選択を実施。
5. 要約スライドのレビュー
   - 作成したスライドを客観的にレビューし、内容の正確性と整合性、品質を確認
     - タイトルの完全記載
     - 著者情報の正確な記載
     - bibファイルのURL情報の確実な反映
     - 各ページの本文内容と配置された図表の関連性を再度確認し自分で関連性の説明を試みる。できなければ図の配置について再考。
   - 修正が必要な場合は適宜修正
6. トピック要約の開始
   - `incoming/`内の全ての論文に対して要約が完了したら、[2. トピック要約の作業手順](#2-トピック要約の作業手順)に進む

# 2. トピック要約の作業手順

1. トピック内の`paper.md`をすべて精読しこのトピックの研究の流れと発展の過程、トレンドを把握
2. それぞれの研究の関係性をメタ的にとらえ、`slides.md`にまとめる
3. `slides.md`の内容を客観的にレビューし、内容の正確性と整合性、品質を確認
4. `npm run dev --topic=topic-name`を実行し、スライドのプレビューを確認
