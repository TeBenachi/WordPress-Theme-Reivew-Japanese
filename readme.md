
## ワードプレステーマリビュー 必須事項

テーマ審査チームとしてワードプレスにコントリビュートしています。ワールドプレスのテーマレビューの審査項目が更新されたので日本語でまとめました。WordPress.orgのダイレクトリーに公式テーマとして登録するには、３箇所以上のエラーがあると失格となり, 全ての必須項目を満たす事が必要です。審査員として気づいた点など、[必須項目](https://make.wordpress.org/themes/handbook/review/required/) (英語)を基にまとめました。直訳ではありませんのでご了承ください。不明な点、タイプミスなどあれば Github Issueにてお知らせください。
(Last update: 6/24/22)

### 1. Licensing & copyright 

テーマは [GPLライセンス](https://www.gnu.org/licenses/licenses.html)、またはGPLに適合したライセンスであることが必要です。WordPressと同様「GPLv2 or later」のライセンスが推奨されます。テーマをGPLにする事によって、ユーザーがテーマを制限なく自由に使えるようになる他、次の事が可能になります。

- 個人、商業目的に拘らず幾つものサイト、ドメインにインストールする事ができる。
- コードを見て学んだり、自由に変更したり、また再配布する事ができる。

サードパーティのリソースのライセンス :
Bootstrap, Google fonts等のサードパーティのリソース使用した場合、それらのライセンスもGPLに適合している事が必要です。各リソースのライセンスとコピーライトを Readme.txt などを使って、一箇所にまとめて記載します。　

```
== Resources ==
Google font Inter
License: Open Font License https://fonts.google.com/specimen/Inter#license
Source: https://fonts.google.com/specimen/Inter
```

#### よく記載漏れのあるリソース
スクリーンショットに使った写真や画像、JavaScript (Slider, Swiper), CSSフレームワーク (Bootstrap)、フォント (Google fonts)、アイコン (fontawesome).

#### テーマを販売している方への注意点　
自分のサイトやテーマショップ等で GPLライセンスに適合しないテーマを販売している場合、審査の失格対象となります。GPLに適合しているテーマを販売している場合は、利用規約やFAQページ等にライセンス情報を明確に表示すると、審査過程がスムーズに進みます。

#### 他に注意する点

- コードやデザインは法的に自分のものである事。他の人のデザインをコピーしたテーマは禁止。
- テーマ自体のコピーライトを Readme.txt に記載する。
- 自作画像の著作権も Readme.txt に記載する。
- Public Domainの画像は著作権の表示が不要ですが、画像へのリンク等を記載すると審査時間や審査員とのやりとりが省ける。
- フッターによくあるコピーライトの表示は、テーマを利用するユーザーのためであり、テーマ制作者のコピーライトは表示しない。

```
悪い例 Copyright by ABC theme 
```

### 2. Privacy

トラッカーを使ってユーザー情報の収集をする事は、ユーザーが同意した場合のみで、初期設定では無効にする。ユーザーから取得する情報とその収集方法、利用目的について Readme.txt かプライバシーポリシーと共に記載する。

### 3. Accessibility

スキップリンク (Skip Links) : スキップリンクとは、［Tab］キーを使ってメニューを読み飛ばして本文へジャンプできる機能。通常［Tab］キーを押すと、画面の左上に Skip to Content リンクが表示されます。

##### スキップリンクの必須事項 

- 各ページの先頭に設置して、スクリーンリーダーが一番はじめに読めるようにし、キーボード操作で一番はじめにフォーカスを受けれるようにする。
- ページを読み込んだ時は画面外に配置しても問題ないが、キーボード操作でフォーカスを受けた時に表示するようにする。

**Note:** ヘッダー、メニュー、ウィジェット等がなく、メインコンテンツにジャンプする必要がない場合はスキップリンクの必要なし。

##### Keyboard navigation

メニュー、フォーム、送信ボタンなどのキーボード操作が可能なユーザインタフェースにフォーカスインジケータが見える。

- キーボードを使ってでコントロールやリンクが操作できる。
- マウスで操作できる機能は、キーボードでも操作できるようにする。スマートフォンやタブレット端末の表示にしてもキーボードで操作できる事が必須。

##### よくあるエラー

- スマートフォンやタブレット端末の表示にしても、キーボードでハンバーガーメニューボタンが開閉したり、各リンク開く等メニューの操作ができる。マウスでできる操作がキーボードのみでもできる。
- レスポンシブ メニューが開いている間は、メニューを閉じない限り、フォーカスがメニュー内を循環する。フォーカスはメニュー外の本文に飛んでしまわない。

##### リンクの可視化

- メインコンテント、コメント、テキストウィジット、カスタムオプション内にあるリンクにはアンダーラインを付ける。太文字、イタリック、色違いを使ったリンクのインジケーターは許容範囲外。
- ナビゲーションリンクにはアンダーラインの必要なし。

`accessibility-ready` タグが付いているテーマは、テーマ審査後さらにアクセシビリティの審査を受けます。

### 4. Code

PHP, JavaScriptのエラー、警告、通知メッセージはないようにし、テーマのセキュリティ保護をする。

##### サニタイズ処理 ( Sanitization ) 
入力フォームに対してサニタイズ処理して入力制限や入力チェックする。サニタイズについての詳しい説明（英語）

`<?php echo esc_html( $title ); ?>`

##### エスケープ処理 

テーマを他の言語に翻訳する際に、翻訳者にどこを訳すのかわかりやすいようにエスケープ処理する。テーマに直接日本語を入れる場合は、必ずエスケープする。

```
良い例  <p><php esc_html_e('お問合せ', 'mytheme'); ?></p>

悪い例  <p>お問合せ</p>
```

ブロックテーマのHTMLファイルにはエスケープなしで日本語を直接記入しても問題なし。ブロックテーマ構成についてのチュートリアル（日本語）

非推奨の関数や定数は使用しない。[非推奨リスト](https://codex.wordpress.org/Category:Deprecated_Functions)（英語）

##### Prefix 

Functions, global variables, constants, meta, enque にユニークな prefix をつける。これはプラグイン等との競合を避けるため。ほとんどの場合、テーマの text domain (slug) を prefix として使う。

```
function yoneko_content_width() {
   $GLOBALS['content_width'] = apply_filters( 'yoneko_content_width', 640 );
}
add_action( 'after_setup_theme', 'yoneko_content_width', 0 );
```

Bootstrap, Google fonts等のサードパーティスクリプトを wp_enqueue_script & wp_enqueue_style に使う場合は、prefix をつける必要無し。

### 5. Functionality and Features

WordPress.orgでのプレビューを小細工する事は禁止。違反した場合アカウントの停止、または削除の可能性があり。

##### 管理画面上での通知

- admin_notices API を使って生成する
- ワードプレスコアのUIデザインに従う。

##### 違反行為

- ワードプレスの基本機能を有料化する。
- Admin bar (管理バー)を隠したり、削除したり、ユーザーのアクセスを阻止しない。
- テーマを有効化する際、リダイレクトしたり、有効化過程を変更しない。
- non-presentational hooksを削除しない。[Non-presentinal hooks](https://make.wordpress.org/themes/handbook/review/required/#5-functionality-and-features) のリスト

テーマに組み込みしてはいけない機能 – Custom post types, Custom blocks, Custom roles, Custom user contact methods, Custom mime types, shortcodes, Functionality that is not related to design and presentation

### 6. Plugins

WordPress.orgに登録されているプラグインを推奨することは問題なし。テーマにプラグインを組み込み、ユーザーの承諾無しに自動的にインストールする事は禁止。

##### 禁止事項

- テーマにZipファイルや、プラグインを添付したり、ユーザーの承諾無しにダウンロードしない。
- プラグインの機能をテーマに取り込まない。

##### プラグインの機能の例

- アナリティックスやトラッキング操作
- SEO機能
- お問合せフォーム
- デザインに関しない meta boxes
- リソースキャッシュ
- ソーシャルメディアのLike、フォロー、シェアボタン
- セッション改ざん

テーマを変えた時にユーザーの入力したデータ（ソーシャルメディアへのリンク、スライダー等）が消えてしまう機能は不可。テーマの機能内なのか、プラグインの機能なのか不明な時はテーマ審査チームにメールで確認するか 、[Slack](https://wordpress.slack.com/?redir=%2Fmessages%2Fthemereview) （アカウント必要）で問い合わせる。Slackの方が返答が早い。[Slack](https://ja.wordpress.org/support/article/slack/) への参加方法（日本語）

### 7. Naming, spelling, and trademarks

テーマの名前が不適当であったり、他のテーマや他社ブランドに類似している場合、テーマの拒否、または名前の変更を要請する場合があります。

- 名前にWordPress, Theme, Twentyを使うのは禁止。
- WordPress の W と P は大文字で綴る。
- 商標法違反はしない。

### 8. Language & internationalization　

Edit, Next, Previous など基本機能を日本語に変えて記入しても問題なし。その際、英語と日本語をミックスしない。テーマに直接使えるのは１言語のみ。もし多国語が混じっていると、語翻訳者が翻訳しにくくなるため。

テーマに直接文字列 ( text strings ) を使う場合は, e() か _() と text domain (slug) を一緒に使う。文字列に e() か _() をつけることによって、翻訳者がどこを翻訳するのかわかりやすくなる。

```
<php _e( '編集する', 'mytheme' ); ?>
<php _e( 'Previous', 'mytheme' ); ?>
```

ほとんどの場合、 e() や _() はを使う場合は、セキュリティのためにサニタイズと一緒に使う。esc_htmlをつけることにより、セキュリティのためWordPressがユーザー入力からHTMLタグを除外し、文字のみ表示する。

```
<php esc_html_e( 'メニュー', 'mytheme' ); ?>
```
[翻訳、国際化についての詳しい説明](https://developer.wordpress.org/apis/handbook/internationalization/)（英語）

### 9. Files

[ ファイル ]
テーマをサブミット(submit)する際の注意事項

- 完了していない中途半端なテーマはサブミットしない
- プロバージョン（有料テーマ）でしか使えない機能のコードを入れない。
- .git, .svn, .hg, and .bzr.等のダイレクトリーを含めない。
- DOS やUNIX の改行コードが入っていると、テーマをサブミット、アップデートする際にSVN（ワードプレスのサブミットシステム）に支障が出てしまうので使わない。
- アンダースコアの_S などのスターターテーマ(白紙状態の骨組みテーマ）等を使った場合、text domain、スタイルシートのヘッダー情報が変更してある。

##### よく間違って入っているファイル 
Thumbs.db, desktop.ini, php.ini, error_log, web.config, __MACOSX , favicon.ico, .xml, .sh

##### 許容範囲内のファイル 
wpml-config.xml, loco.xml, phpcs.xml

##### リモート共有リソース 
GDPR（General Data Protection Regulation）EU一般データ保護規則やプライバシーポリシーに従うために、リモート共有リソースは使用は禁止。

- CDNを使ったリモート共有リソースは使わない。
- Google フォントは許容範囲内。
- ファイルやデータをリモートリソースから呼び込み ( fetch ) はしない。

##### スタイルシート 
ワードプレスのガイドラインに沿ってヘッダー部分に必須事項を記入する。スタイルシートの例。

 ```
 /*
Theme Name: Twenty Twenty
Theme URI: https://wordpress.org/themes/twentytwenty/
Author: the WordPress team　
Author URI: https://wordpress.org/　
Description: This is a blog style theme that is suitable for personal blog or portfolio websites. 
Tags: blog, one-column, custom-background, custom-colors, custom-logo, custom-menu, editor-style,  translation-ready, block-styles, wide-blocks, accessibility-ready　
Version: 1.3　
Requires at least: 5.0　
Tested up to: 5.4　
Requires PHP: 7.0　
License: GNU General Public License v2 or later　
License URI: http://www.gnu.org/licenses/gpl-2.0.html　
Text Domain: twentytwenty　
This theme, like WordPress, is licensed under the GPL.
Use it to make something cool, have fun, and share what you've learned with others.
*/
```

 Theme URI （テーマリンク）と Author URL (テーマ制作者のリンク）以外は全て必須項目です。

- Theme Name – テーマ名。
- Theme URI – テーマへのリンク先。テーマに関したデモや説明のページのみ。テーマの宣伝、販売ページはNG。
- Author – WordPress.orgのアカウント名。１名のみ。
- Author URI – オプショナル テーマ制作者のウエブサイト。
- Description – テーマの説明。
- Tags – タグのリスト
- Version – テーマのバージョン。
- Requires at least – テーマが使える最低限必要なワードプレスのバージョン。
- Tested up to – テーマをテストした最新ワードプレスのバージョン。
- Requires PHP – 最低限必要なPHPバージョン。
- License – テーマのライセンス。
- Lisence URI – テーマのライセンスへのリンク。
- Text Domain – テキストドメイン。

##### テキストドメインとは 
テキストドメイン ( Text Domain )とは Slug とも呼び、テーマの名前を使った独自の文字列。テキストドメインは全て小文字でスペースは 「 – 」ハイフンを使う。

```
例：もしテーマの名前が Green Apple なら、テキストドメインは green-apple
```

##### Readme.txt
readme.txtファイルに下記の必要事項を記入する。]Readme バリデータ ( validator )](https://wordpress.org/plugins/developers/readme-validator/) で記入漏れやエラーを確認する。

```
=== Theme Name ===　
Contributors: (Should only contain one WordPress.org username.)
Requires at least: 5.0
Tested up to: 5.2　
Requires PHP: 5.6　
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Short description. No more than 150 chars.　

== Description ==
テーマの簡単な説明をする。

== Changelog ==
リリースノート。変更履歴を記録する。
1.2
* Added new option

1.1
* Security bug addressed
* Changed thumbnail size
```

- Theme Name – テーマ名。
- Contributors – WordPress.orgのアカウント名。１名のみ。
- Requires at least – テーマが使える最低限必要なワードプレスのバージョン。
- Tested up to – テーマをテストした最新ワードプレスのバージョン。
- Requires PHP – 低限必要なPHPバージョン。
- License – テーマのライセンス。
- License URI – テーマのライセンスへのリンク。

##### Resources
リーソスの部分にサードパーティのスクリプト、フォントのライセンス、コピーライトの表示をする。

```
== Resources ==
Google font Inter
License: Open Font License https://fonts.google.com/specimen/Inter#license
Source: https://fonts.google.com/specimen/Inter

Underscores _S starter theme
Copyright (C) 2012-2020 Automattic, Inc.,
License: GPLv2 or later, https://www.gnu.org/licenses/gpl-2.0.html
Source:  https://underscores.me/
```

##### 画像、写真についての禁止事項
嫌悪や暴力助長する画像は使用禁止。子供の顔や身体的特徴がはっきり見分けがつく写真の使用も禁止。

##### スクリーンショット（Screenshot)

- 広告のようなスクリーンショットは禁止。ユーザーから不適当だと苦情があった場合、スクリーンショットの変更を要請する場合がある。
- スクリーンショットの最大サイズは 1200 x 900px まで。
- スクリーンショットのサイズの割合は 4:3 にする


### 10. Classic themes

DOCTYPE declaration (文書型宣言) とlanguage_attributes()を使って言語宣言する。

##### 注意
<html lang=”ja“>とハードコードせず、どの言語でも使えるように<html <?php language_attributes(); ?>>を使う。

```
<!doctype html>
<html <?php language_attributes(); ?>>
```

- カスタムテンプレートを使う場合は、get_template_part( ) or locate_template( ) を使って呼び込む。
- ユーザーが設定するフロントページに沿ってコンテントを正しく表示する

##### オプションと設定 (Options and Settings)
ユーザーパーミッション（権限）は、edit_theme_options を使って権限を判定する。
edit_themes, manage_optionsは使用しない

##### テンプレート 
テーマにテンプレート使われている場合、下記のテンプレートは決まったファイル名を使う。
- header.php
- footer.php
- sidebar.php
- searchform.php

[カスタマイザー (Customizer) を使ったテーマオプションについてのガイドライン](https://make.wordpress.org/themes/2015/04/22/details-on-the-new-theme-settings-customizer-guideline/)


＃＃＃11. Block themes

テーマサブミット時のエラーチャックが、ブロックテーマ、およびFSE (Full Site Editor) テーマに対応していないので、エラーチャックを通過するだけのために、ブロックテーマに不必要なファイルやタグを追加する必要があります。ブロックテーマをサブミットする際はあらかじめ Slack でテーマチームに連絡することお勧めします。（９月２８日現在）

##### 最低限必要事項

- Index.php, style.css, readme.txt, theme.json, and index.html は必ず必要。
- Index.html は block-templates ダイレクトリーの中に入れる。
- ミスマッチや終了タグ (Closing tag)が落ちてないか注意する。

[ブロックテーマ構成についてのチュートリアル](https://ja.wordpress.org/team/handbook/block-editor/how-to-guides/themes/block-theme-overview/)（日本語）

### 12. Selling, credits, links, and spam

[ テーマの販売、クレジット、リンクとスパム ]
フロントエンド、またはクライアント側ウエブサイトにて、テーマ制作者のウエブサイトへのリンクかテーマを説明するページへのリンクをつけても問題ありません。ただリンクは１つのみ。

```
<?php
  printf( esc_html__( '%1$s theme made by %2$s', 'kiyono' ), 'Kiyono',
  '<a href=" ' . esc_url( 'https://www.benachi.com/kiyono-wordpress-theme/' ) . ' ">' . esc_html( 'Benachi',     'kiyono')  . '</a>' );
?>
```


テーマ制作者のウエブサイトリンク以外にWordPress.orgへのリンクも許容範囲内。

```
<a href="<?php echo esc_url( __( 'https://wordpress.org/', 'kiyono' ) ); ?>">
  <?php
    /* translators: %s: CMS name, i.e. WordPress. */
    printf( esc_html__( 'Proudly powered by %s', 'kiyono' ), 'WordPress' );
  ?>
</a>
```

##### その他の注意事項

- アフィリエイトに参加している場合、明確に表示する。
- 不快なクロスセル（upselling）はしない。
- クライアント側のウエブページやフロントエンドでクロスセルはしない。

クライアント側のウエブページやフロントエンド ( public-facing pages )、テーマ、テーマの記述 ( description ), readme.txt ファイル、スターターコンテント、翻訳ファイルなどを使って、ブラックハットSEOやキーワードを詰め込んだりするような、スパム迷惑な行為しない。

### 13. Theme author and theme upload restrictions

テーマ制作者は一度に１つ以上のテーマをサブミットしない。１つテーマをサブミットしたら、審査が終わるまで他のテーマをサブミットしない。１つ以上サブミットした場合は、全てのテーマが却下されます。

- サブミット予定のテーマに確保するためにテーマをサブミットするのは禁止。
- ガイドラインの抜け穴を探して意図的に違反行為することは禁止。

##### WordPress.orgのダイレクトリー以外で配付しているテーマのライセンスについて
ダイレクトリーでテーマを登録するには、ダイレクトリー以外で配付しているテーマのライセンスもGPLかGPLに適合したライセンスであることが必要です。GPL以外のライセンスで配布している場合は、ダイレクトリーには登録できません。

例えば Themeforest でテーマを販売している場合、販売している全てのテーマがGPLかGPLに適合したライセンスでないとWordPress.orgのダイレクトリーには登録できない。 ライセンスについての詳しい説明（英語）

##### よくあるGPLライセンスに反する行為

- テーマをインストールできるドメインを１件に限る
- Key codeなどを配布してインストールの回数を１回に制限する

GPL適合ライセンスのテーマを販売したり、インストールやアップデート等のカスタマーサポートのサービスを売る事には問題ありません。

##### WordPress.orgの複数のアカウント
複数のアカウントを持つ事には問題ありません、ただ、いくつかのアカウントを使って複数のテーマを同時にサブミットすることは違反です。複数のアカウントを所有する場合は、審査前に予めテーマチームにメールで連絡する。Email：themes＠wordpress.org

上記のガイドラインに反する意図的な行為に対し、審査中の全てのテーマ、及びすでに登録してある全てのテーマが停止され、今後のテーマのサブミッションも制限されます。違反したテーマ一つにつき１ヶ月の停止の可能性がある。また違反行為の深刻度により、すべてのアカウントを永久に禁止になる可能性があります。











