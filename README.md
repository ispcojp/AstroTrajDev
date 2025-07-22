# 軌道計算クラウドサービス AstroTraj (試験運用中)

- **AstroTraj** : Astrodynamics Trajectory Optimization
    - AstroTraj は、宇宙機の軌道最適化やミッション設計のための、強力かつ柔軟なツールを提供するクラウドネイティブなサービスです。

## プロジェクト概要

- このサービスは、DDP（Differential Dynamic Programming）を用いた軌道最適化・軌道計算をクラウド上で提供するものです。主に低・中推力の宇宙機を用い、多周回での軌道最適化を必要とする以下のようなユーザーを対象としています :
    - 民間のオービットトランスファー事業者（例：LEO to LEO、GTO to GEO）
    - 宇宙工学・航空宇宙分野の研究者
    - 大学院レベルの学生
    - 軌道力学に関心のある技術者・開発者

- 現在は **試験運用中（トライアル期間）** につき、無償でご利用いただけます。

## AstroTraj を使う

- クラウド版はこちら : [AstroTraj](https://d3ckxaulmhak11.cloudfront.net/)
- GitHubリポジトリ（ローカルPC向けインストール版）：近日公開予定

### クイックスタート

1. サービスのリンク先にウェブブラウザでアクセス
    - [AstroTraj](https://d3ckxaulmhak11.cloudfront.net/)
2. 右上の`Start trajectory calculation`ボタンを押下
3. `Settings`画面で、`TrialName`に任意の実行名を入力
4. `Preset`からコンフィグを指定
    - コンフィグは以下のプリセットの中から選べます。
        - `DDP (Earth to Mars)`
        - `DDP (GTO to GEO)`
        - `Multishoot (Multiflyby)`
        - `Multishoot (NRHO)`
5. 実行ボタンを押下
    - 数分～最大120分ほど待つ。 
        - Initial Guessとtarget次第ですが、
            - プリセット`DDP(Earth to Mars)`だと5分程度
            - プリセット`DDP(GTO to GEO)`だと120分程度

## 機能一覧

- DDPを用いた軌道遷移最適化（地球周回軌道、ランデブー、多軌道など）
- 入力形式：軌道要素（位置・速度・時刻）
    - Keplerian要素 : **将来対応予定**
- 出力形式：
    - CSV : 遷移軌道、推力時系列、消費燃料
    - 画像 (UIでのみ表示) : 3D軌道表示と推力変化 (初期値、最適化過程、最終値) 
- 対応フォーマット：JSON, CSV

---


## ライセンス・利用条件
- T.B.D. 

## 禁止事項
- T.B.D. 

## 無断での商用利用
- T.B.D. 

## サービスの再配布
- T.B.D. 

## 他者のAPIキーの不正使用
- T.B.D. 

## 現在の制限事項

- 一度の計算で実行可能なイテレーション数に制限あり (詳細は近日公開予定)
- 同時実行は最大20リクエストまで（並列実行は最大16件）
    - 並列実行は16件までで、17リクエスト以降は処理待ち状態となり、21リクエスト以降は受け付けません。
- 軌道離脱（escape trajectory）は現時点で未対応

※上記予定は変更になる可能性がございます。

## 今後のロードマップ

|フェーズ|予定内容|時期|
|--------|--------|----|
|クラウド版試験運用公開|期間/機能限定で無料公開(ISTSにて)|2025年Q3|
|クラウド版user feedback収集/対応|試験運用によるfeedbackを通じた機能改善・追加|2025年Q4|
|クラウド版正式リリース|ログイン機能、利用料導入（無料枠あり）、その他|2026年Q1|
|ローカルPC向けインストール版試験運用公開|機能限定で公開(詳細はT.B.D.)|2026年Q2|
|ローカルPC向けインストール版user feedback収集/対応|試験運用によるfeedbackを通じた機能改善・追加|2026年Q3|
|ローカルPC向けインストール版正式リリース|GitHub上でOSSとして公開(詳細はT.B.D.)|2026年Q4|



※上記予定は変更になる可能性がございます。

## セキュリティ・プライバシー

- 現在トライアル利用のため、ユーザーの計算データは保存され、現時点では全員参照可能です。
- 今後は、ログイン機能を搭載し、有償版では自身のみが参照可能となる予定です。
    - キーはユーザーまたは組織ごとに個別発行予定です。

## 応用例・ユースケース

- 宇宙機の軌道遷移計画
    - LEO to LEO
    - GTO to GEO

- 小型衛星の燃料最適化
- 多機体協調制御（Swarm Control）研究

## 論文・参考文献

- Naoya Ozaki : Tube Stochastic Differential Dynamic Programming and Application to Robust-Optimal Spacecraft Trajectory Design, Ph.D. Thesis, The University of Tokyo, 2018.

- Gregory Lantoine and Ryan P. Russell : A Hybrid Differential Dynamic Programming Algorithm for Constrained Optimal Control Problems. Part 1: Theory, Journal of Optimization Theory and Applications, Vol. 154, No. 2, pp. 382-417, 2012.

- Gregory Lantoine and Ryan P. Russell : A Hybrid Differential Dynamic Programming Algorithm for Constrained Optimal Control Problems. Part 2: Application, Journal of Optimization Theory and Applications, Vol. 154, No. 2, pp. 418-442, 2012.

- Jonathan David Aziz : Low-Thrust Many-Revolution Trajectory Optimization, Ph.D. Thesis, The University of Colorado, 2018.

- Shun Kodama, Naoya Ozaki, Toshiro Shimizu, Kazuaki Someno, Takashi Shimizu and Satoshi Ikari : A study of GPU acceleration of trajectory design software using DDP, the 64th Space Sciences and Technology Conference (2020).

- Shun Kodama, Naoya Ozaki, Toshiro Shimizu, Ken Nishioka, Yohei Kubo, Kazuaki Someno, Takashi Shimizu and Takuya Chikazawa : Development Status of Trajectory Design Software Using DDP - A Case Study of Trajectory Transfer from NRHO to LLO -, the 67th Space Sciences and Technology Conference (2023).

- Shun Kodama, Naoya Ozaki, Toshiro Shimizu, Ken Nishioka, Yohei Kubo, Kazuaki Someno and Takashi Shimizu : Development Status of Trajectory Design Software Using DDP – Application study to Trajectory Transfer from Earth Orbit to the Lunar Gravity Field -, the 68th Space Sciences and Technology Conference (2024).

## お問い合わせ・フィードバック
- メール : 
    - 児玉 s-kodama@isp.co.jp
    - 清水(敏) t-shimizu@isp.co.jp

- Issue投稿（準備中）

## フィードバックフォーム（準備中）

- 本プロジェクトは現在試験運用中であり、内容は予告なく変更される可能性があります。ご理解のほどよろしくお願いいたします。

## 確認されている不具合・挙動の違和感


### "Home" 画面

- `Start Time (JST)`でソートした際、昇順・降順が指定通りに動作しない場合があります。  
- 画面右下部のページネーション（`1...2,3,4...5`）において、折りたたむ必要がないケースでも `...` が表示されることがあります。  (Windows/MacOS, chrome環境で確認)
- `Running` の状態が長時間続いた際に、 `View` をクリックして、`No Data` と表示され、その後 `Go to Home` を押して戻ると `Status: SUCCEEDED` となり、再度 `View` をクリックすると正常に表示されるケースがあります。(MacOS, chrome環境で確認)

### "Result" 画面

- 画面の拡大・縮小や移動はマウスホイールやドラッグで操作可能です (操作方法として明示することを検討中です)
    - マウスホイールによる拡大・縮小を行った際、操作が繰り返され、安定しない現象が確認されています。(MacOS, chrome環境で確認)
- `Intermediate Result` の `step` を変更した際、画像表示後にモデルが回転する挙動が見られ、不自然に感じられる場合があります。(Windows/MacOS, chrome環境で確認)
