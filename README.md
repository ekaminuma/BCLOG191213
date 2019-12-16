# Blockchain入門(実習の補足情報)

### 補足概要
- **Hyperledger Composerを利用したBlockchainの体験実習**
- 19/12/13に実習実施
- 講師（IBM株式会社 紫関様、西下様）
- [MDDSCデータ人材育成プログラム](https://md-dsc.com/curriculum31.php)の応用編
- **Hyperledger Composer(HC)は、2019年12月時点で非推奨(Deprecated)状態**です。
    - [非推奨の理由](https://stackoverflow.com/questions/57423380/what-are-reasons-for-the-deprecation-of-hyperledger-composer)がネットに掲載されています。
    - 幾つかのHCの機能がHyperledge fabric本体に吸収されました。
    - 使い易い他のソフトウェア候補が少ない事から、現在もデモ目的で使用されています。
- 本来はデフォルトとして存在していたプログラムコードが、Deprecatedにより一部消去されました。
　　- 実習時に入力する必要があった部分が消去されています。該当コード部分を、下記に掲載いたします。
---

### 実習手順[1]　Embty-Business-Networkの準備

詳しい実習手順は講義中に紫関講師により解説されています。講義ビデオは、データ人材育成プログラムの[e-Learning教材](https://md-dsc.learning-ware.jp/
)で御確認下さい。

1. **Hyperledger Composerの起動**
   - https://hyperledger.github.io/composer/latest/ から「Try It Online」をクリックします。
2. **Let's Blockchainを選択** 
   - Welcome to Hyperledger Composer Playground!とポップアップ画面が出るので、「Let's Blockchain」ボタンを押下します。
3. **Deploy a new business networkを選択**
   - こんにちは、Hello, Composer!の右側の点線で囲まれている「Deploy a new business network」を選択します。
4. **empty-business-networkを選択, Deployを押下**
   - 「Deploy a new business network」の画面が現れます。
   - (1.BASIC INFORMATION)では、何もせずデフォルトのままにします。
   - (2.Model Network Starter Template)で真ん中の「Empty-business-network」を選択して、右側の「Deploy」ボタンを押下します。
   - <img src="./MODEL_TEMPLATE.png" alt="empty-business-network-sel2" title="sel2選択画面" width="400" border="1" />
5. **Connect nowを選択**
   - 左に「admin@empty-business-network」でUSER ID: adminのempty-business-networkが生成されるので、LINK状態になっている「Connect now」を押下します。
6. **Marble.zipデータファイルをダウンロードして解凍**する。
    - Marble.zipをe-Learningサイトからダウンロードして下さい。
    - Marble.zipを解凍して下さい。
    - Marbleディレクトリに「Marble.cto, Marble.js, permissions.acl」の3ファイルがある事を確認して下さい。
7. **Marble.ctoモデルファイルを追加**する。
    - 左画面の「UPDATE NETWORK」直上の「Ade a file」を選択する。
    - ポップアップ画面にModel File(Marble.cto)を流し込み「Add」ボタンを押下する。
8. **Marble.jsスクリプトファイルを追加**する。
    - 左画面の「UPDATE NETWORK」直上の「Ade a file」を選択する。
    - ポップアップ画面にScript File(Marble.js)を流し込む。
9. **permissions.aclアクセスコントロールファイルを追加**する。
    - 左画面の「UPDATE NETWORK」直上の「Ade a file」を選択する。
    - ポップアップ画面にアクセスコントロールファイル(permissions.acl)を流し込み、置き換えなら「Replace」ボタンを押下する。
10. 余分なModelファイルを削除する。 
　　　- Marble.cto以外の「model.cto」ファイル等を、左画面から選択してごみ箱マークを押下して削除（Delete）する。
     - 左画面は「About(README.md,package.json)」「models/Marble.cto」「lib/Marble.js」「permissions.acl」だけにする。
11. **左画面の下の「Deploy changes」ボタンを押下**する。
     - ボタンは灰色非選択状態になるが、そのままで大丈夫です。

---

### 実習手順[2]　Marbleのハンズオン基礎編

- 構築したBlockchain上で、AbeさんとTrumpさんの間でMarbleのやりとり(=Assetの移転)をします。

1. **作業内容の確認**します。
   - 1. (Defineタブ)Model Fileの確認(Participantクラスの定義,Assetクラスの定義,Transactionクラスの定義)
   - 2. (Defineタブ)Script Fileの確認(Transaction Processor Functionの定義)
   - 3. (Defineタブ)Access Controlの確認
   - 4. (Testタブ)テスト用インスタンスの作成(Participantインスタンスの作成,Assetインスタンスの作成)
   - 5. (Testタブ)Transactionの実行
   - 6. (Testタブ)実行結果の確認(Assetインスタンスの確認)
2. Testタブを選択した画面を開き、**右上の「Create New Participant」ボタンを押下**してAbeさんとTrumpさんを追加します。
   - デフォルトは下記になっています。
```
{
  "$class": "org.hyperledger_composer.marbles.Player",
  "email": "8169",
  "firstName": "",
  "lastName": ""
}
```
   - 1つ目のParticipantは下記の様に追記します。
```
{
  "$class": "org.hyperledger_composer.marbles.Player",
  "email": "Shinzo.Abe@mail.jp",
  "firstName": "Shinzo",
  "lastName": "Abe"
}
```
   - 2つ目のParticipantは下記の様に追記します。
```
{
  "$class": "org.hyperledger_composer.marbles.Player",
  "email": "Donald.Trump@mail.us",
  "firstName": "Donald",
  "lastName": "Trump"
}
```

3. 
---


