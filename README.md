# IoT学習管理支援システム

![DEMO](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/20241028_020601.jpg)

## 製品概要
現在、学習における課題として、デジタルデバイスによる通知や誘惑によって集中力が持続しにくいこと、勉強の意義や達成感が感じにくいためにモチベーションが低下しやすいこと、さらには保護者や教師が子供の学習状況を把握しづらいことが挙げられます。
このような背景を踏まえ、学習管理支援システムは、学習者の集中力やモチベーションの向上を図り、保護者や教師との連携を強化するためのツールとして開発しました。

### 製品説明（具体的な製品の説明）
この学習管理システムは、学習者の集中度をリアルタイムで測定し、学習時間や進捗状況を可視化する機能を備えた学習支援ツールです。

ハードウェア面では、ロックケースにスマホを設置するとケースがロックされ、ポモドーロタイマーとカメラによる顔認識が作動して集中度スコアを計測します。タイマーが終了すると、ディスプレイにランダムに生成された4桁のパスワードが表示され、正しいパスワードを入力するとケースのロックが解除される仕組みです。

ソフトウェア面では、日ごとの集中度スコアや学習レポートなどのフィードバックが提供されます。さらに、LINEによる通知機能により親や教師も、学習状況をリアルタイムで確認し、適切なサポートを提供できるように設計されています。

### 特長・注力したこと（こだわり等）
#### 1. ハードウェアの活用
* ソフトウェアのみでは解決できないことに注目しました。
* 外部とのケーブルの接続は電源のみとしました。
* コンパクトで大きな面積をとらないタテ型を採用しました。
* 配線を綺麗にしました。
* モーターの不安定な信号の制御のため外部電源を採用しました。

#### 2. データベースとの連携
SQlite3を用いて、ダッシュボードとデータベースを連携しました。

#### 3. データの可視化
ダッシュボードに学習者の集中度、学習時間を管理できるようにしました。学習履歴をわかりやすく表示し、学習意欲を促進することを意識しました。

### 解決出来ること
#### 現状の課題点
* 現代人の悩みとして、すぐにスマホを触ってしまい集中力が続かない現状があります。
* スマホを触ることを禁止するアプリもあるが、スマホの中にあるためスマホ禁止起動終了前後に
スマホをさわってしまいあっというまに時間がたっているということがあります。
* 親や教師はこどもが勉強しているといっても勉強しているかわからない。

### システムを用いて解決できること
このデバイスでは以下のような人に利用してもらいたいと想定しています。
1. 子供がひとりのとき部屋で勉強しているか不安な保護者
2. スマホをすぐ触ってしまい勉強に対する集中力が続かない人
3. 勉強のモチベーションが低い人
4. 自身の勉強時間や集中度を管理したい人

* 集中力の持続を支援し、学習習慣の定着をサポートします。
* 学習者が自らの学習進捗を把握し、目標設定や達成感を感じることができます。
* 子供の学習を親や教師が管理することによりサポートできます。

### 今後の展望
* より高度な集中度測定アルゴリズムの開発により、学習者の状態をより正確に把握できるようにします。
* 他の教育プラットフォームや学習アプリとの連携を検討し、学習管理の効率化を図ります。
* 学習者の意見を反映し、さらなる使いやすさと機能向上を目指します。
* ゲーミフィケーションの機能を追加します。具体的にはポイント制度(集中度スコア×学習時間)を用いてバッジをOpenAIのDELL
によって作成しダッシュボードの集めたバッジとして表示します。
* 教科ごとに学習時間を管理できるようにします。
* 収集したDBをもとにmatplotlibを用いて(i)週の日ごとの勉強時間, (ii)週の日ごとの集中度スコア, (iii) 科目ごとの勉強時間の割合を
ダッシュボードに表示します。
* また収集したDBをもとにOpenAIのAPIを活用し, その人に特化したフィードバック, 学習計画の立案を策定します。
* UIのスマホ版を追加します。
* Google calenderを連携し, 学習計画を作成します。
* ユーザーの学習状況から, 教員によるアドバイスをコメントとしてダッシュボードに表示します。


### 実行手順
#### 1.ログインまたは新規登録
ログインまたは新規登録を行います。
![ログイン](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/rogin.png)

![新規登録](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/touroku.png)
#### 2.ハード側でユーザーIDを入力
ログインまたは新規登録で取得したユーザーIDをハード側のKeypadに入力します。
![ユーザーID](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/userID.jpg)
#### 3.スマートフォンをロック機構に格納
ユーザーIDを入力後、スマートフォンをロックケースに格納します。格納したことを感知するとケースにロックがかかります。
![スマホin](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/phonein.png)
#### 4.顔認識が作動
USBカメラによる顔認識が作動し、独自の数理モデルに基づいて学習中の集中度を測定します。
![顔認証](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/facecam.png)
#### 5.　ポモドーロタイマーが作動
顔認識が作動すると同時にポモドーロタイマーが作動します。ポモドーロタイマーは一般的には25分のサイクルですが、今回は時間短縮のため15秒に設定してあります。
![ボロモード](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/boromode.jpg)
#### 6.　ハード側でロック解除パスワードを入力
ポモドーロタイマーが停止後、ランダムに生成された４桁のパスワードがディスプレイ（LCD）に表示させる。そのパスワードをKeypadで入力し、パスワードが一致していればケースのロックが解除される。
![ロック解除パス](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/password.jpg)
#### 7.　ダッシュボードにフィードバックの可視化
ダッシュボードには日付, 検出時間, 学習時間, 集中度スコアを表形式で表示。ログアウトボタンからログアウトする。
![ダッシュボード](https://github.com/Shotaro-Akehi/Shotaro-Akehi/blob/main/7E4C8880-7C57-4D77-9DCB-708E660C2F1E.png)


## 開発技術

### 活用した技術

#### フレームワーク・ライブラリ・モジュール
- gpiozero
- RPLCD
- face_recognition
- cv2 (OpenCV)
- random
- sqlite3
- datetime
- time

- HTML
- CSS

- database/sql
- html/template
- net/http
- time
- github.com/mattn/go-sqlite3

- go
- github.com/mattn/go-sqlit

- database/sql
- html/template
- log
- net/http
- time
- github.com/mattn/go-sqlite3e3

#### デバイス
* Raspberry Pi 5 - 集中度測定用デバイス
* カメラモジュール - 顔認識および集中度のリアルタイム監視
* I2C LCD 1602 - ディスプレイ表示
* 9G Servo - ロックケースのロック部分
* Keypad - IDおよびパスワードの入力キーパッド
* Switch - スマホがロックケースにセットされたことを確認

### 独自技術
#### ハッカソンで開発した独自機能・技術
* 集中度スコア算出 - 独自の数式に基づいて算出されている。学習中の集中度を自動的に評価し、リアルタイムで集中力を可視化します。
* サーボの制御　- パルス信号によってサーボモータは制御されており、以下の二点で解決に至った。(i)不安定なサーボの挙動を外部電源(リチウムバッテリー)とコンデンサーの使用により問題を解決した。 (ii)インスタンスの生成によっておこる
サーボの不具合を、受け入れるという立場でハードウェアを設計した。
* switchボタンによるスマホの検知 - スマホを入れたときの負荷を検知できるようにハードウェアを設計した。
