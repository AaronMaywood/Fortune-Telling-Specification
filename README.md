# 占いの仕様書

## 仕様一覧

- 誕生数に基づいた占い（占い結果は⑨種類）

## 素材

- HTML/CSS/画像等
  - TODO
- 占い原稿
  - TODO

## 誕生数の算出アルゴリズム

```
// 誕生数(birthNumber)を計算する
static function calcBirthNumber($year, $month, $day){
    // Step1. 誕生日の各桁を足す 例) 1970220 = 1 + 9 + 0 + 2 + 2 + 0 =  14
    $ymd = str_split($year . $month . $day);
    $ymd2 = 0;
    foreach($ymd as $number){
        $ymd2 += $number;
    }
    // Step2. 9 で割った余りが誕生数、ただし0の場合は9とする
    $birthNumber = $ymd2 % 9;
    if ($birthNumber === 0) {
        $birthNumber = 9;
    }
    return $birthNumber;
}
```

## 各種設定
- フォルダ名
  - `fortune1`
- データベース名
  - `academy-php_fortune`
- テーブル名
  - `career_fortunes`
- モデル名
  - `CareerFortune`
- バリデーション
　- バリデーション仕様
    - 年 … 整数型で４桁
    - ボーナス目標：エラー時の画面でエラーになった入力値を初期値として表示すること
- デプロイ先サーバー情報
  - FTP(SFTP)情報
    - ホスト名
      - `www1746.sakura.ne.jp`
    - ユーザー名
      - `academy-php`
    - パスワード
      - ※担当者から別途指示を仰いで下さい。
  - 設置フォルダ名
    - `CareerFortune`
  - .env記載事項
    - APP_NAME=CareerFortune
    - APP_URL=https://academy-php.sakura.ne.jp/CareerFortune
    - DB_HOST=mysql3102.db.sakura.ne.jp
    - DB_DATABASE=academy-php_fortune
    - DB_USERNAME=academy-php_fortune
    - DB_PASSWORD=担当者から別途指示を仰いで下さい。

## 検証

- 検証表作り
  - Google Spreadsheet で作成して下さい。
  - 参考になる検証表：
    - https://docs.google.com/spreadsheets/d/17TXD_PuUTtwvY98QDEjhXULP0JKKe5FiEMuyvfRioY4/edit?gid=0#gid=0
- 検証作業

## 提出

指定された連絡方法で、以下の情報を担当者に送って下さい。

- ソースコード一式をZIPファイルにまとめたもの
- 本番環境URL
  - https://academy-php.sakura.ne.jp/CareerFortune
- 検証作業済みの検証表URL(Google Spreadsheet)
  - 担当者が閲覧できるように適切な共有設定をお願いします。
    - ※担当者のメールアドレスは php@adjust.ne.jp です。

## メモ

- PHPやLaravelの不明点はGoogle 検索やChatGPTなどで調べながら進めましょう。調べることも大切なスキルの一つです。

