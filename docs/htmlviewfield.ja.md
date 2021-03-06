# HTML ビューとフィールドの表示

Teamstudio Exportはアーカイブから静的なHTMLサイトを生成することを可能にしています。デフォルトでは、HTMLサイトはオリジナルアプリケーションの全ての非表示でないビューとエクスポートされた文書にある全てのフィールドを表示します。いくつかのNotesアプリケーションには、アプリケーション ロジックで使用される多数のビューとフィールドが含まれています。時折これらのビューおよびフィールドは、エンドユーザーに有用な情報を提供せず、さらには関連情報を見つけることを妨げてしまいます。

Teamstudio ExportはエクスポートされたHTMLサイトに対して以下の設定をサポートしています:

* どのビューが表示されるかを制御する
* どのフィールドが表示されているか、表示の順番などを制御し、オプションでフィールドラベルを設定する

!!! note
    HTMLサイトの設定は、サイトのHTMLフォルダ(.tseフォルダ)のatconfig/config.js内にあります。ビューとフィールドを表示させるためのドキュメンテーションとサンプルは、サイトの作成時に生成されるデフォルトのconfig.jsにあります。

## 設定ファイル
設定ファイル(config.js)は本質的には、多くの最新のWeb技術で使用されているプロパティファイルと似た形式でJavaScript/JSONによる設定ファイルになります。Webサーバーを使用せずにHTMLサイトを自前でブラウズができるようにするために、設定プロパティを表すJavaScriptオブジェクトは、config.jsが読み込まれる時に呼ばれる関数(“tmsData”)を通すことでアプリケーションに登録されます。デフォルトのconfig,jsファイルには、この関数について記述した説明とコメントを外して利用できるコードの設定例が含まれています。

JavaScriptに関する構文とJSONの基本的な理解はこのファイルを編集する際に役立ちます。

Config.jsファイルの変更を有効にするには、Webアプリケーションをブラウザに再ロードする必要があります。

## ビューのフィルタリング
この設定は、どのビューを表示するかを制御することができます:

* 明示的に表示するビューの指定
* 使用可能なビュー名の配列を受け取り、表示するビューの配列を返すJavaScript関数の提供
* ()で始まるビューのデフォルトの非表示を無効化 

!!! note
    「(」で始まるビューのフィルタリングは、エクスポート2.0以降の標準機能です。

A simple config.js filtering views
``` javascript
window.tmsData('config.js', {
   views: { filter: [ 'all', 'by date', 'by author'] }
});
```

ビューのフィルタリングの詳細な例については、標準のconfig.jsファイルを参照してください。

## フィールドのフィルタリング
この設定では、特定のフォームに対してどのフィールドを表示するか制御することができます:

* 明示的に順番通りに表示するフィールドの指定
* フィールドに表示するラベルと共に、表示するフィールドを明示的に一覧表示する
* フィールド名の配列を受け取り、上記のいずれかの形式で表示するフィールドの配列を返すJavaScript関数の提供

A simple config.js filtering fields
``` javascript
window.tmsData('config.js', {
    forms: 
        {
        'Main Topic':
            {
                'fields': [
                    {name: 'Created', label: 'Date of publication'},
                    {name: 'Subject', label: 'Topic'}
                ]
            }
        }
});
```

フィールドのフィルタリングの詳細な例については、標準のconfig.jsファイルを参照してください。

## UIでのフィルタリングの一時的な無効化
ビューとフィールドのフィルターの開発を支援するために、ビューのメインリストと文書上の両方のフィルターにおいて、メインのエクスポートヘッダーバーでShiftキーを押しながらダブルクリックすると、オン/オフのトグル設定が可能です。この機能はconfig.jsの保存やアプリケーションを再ロードせずに、フィルターを変更するときに使用できる全てのフィールドの一覧をリスト表示させるのに役立ちます。
