---
type: quick-start
hide_in_page_nav: true
category_id: tooling
subcategory_id: tooling/cli
is_index: false
id: tooling/cli/quick-start/create-oauth-app
rank: 1
total_steps: 5
sibling_id: tooling/cli/quick-start
parent_id: tooling/cli/quick-start
next_page_id: tooling/cli/quick-start/install-and-configure
previous_page_id: tooling/cli/quick-start
source_url: >-
  https://github.com/box/developer.box.com/blob/main/content/guides/tooling/cli/quick-start/1-create-oauth-app.md
fullyTranslated: true
---
# Boxアプリの設定

To use the **Box CLI** you will need to create a **Box App**. A Box App is an application that can be used for making API calls. When using the Box CLI you can choose to either set up your own Box App or use our preconfigured one. The key benefit of setting up your own Box App is that you won't need to go through login every hour, but it does require a few extra steps to set up.

## 使用するBoxアプリの選択

<Grid columns="2">

<Choose option="cli.app_type" value="create_new" color="blue">

# 新しいBoxアプリを作成する

We can set up a Box App for you right here from the documentation. With a few clicks you will be ready to go!

</Choose>

<Choose option="cli.app_type" value="use_existing" color="red">

# Use existing Box App

使用したいBoxアプリをすでに作成済みの場合は、そのアプリケーションの資格情報を使用できます。

</Choose>

</Grid>

<Choice option="cli.app_type" value="create_new,clicked" color="blue">

# Create a Box App

To use your own **Box App** you will need to create a new Box App in the **Box Developer Console**. Click the button below and we will set it up for you. At the end you will have a **Client ID** and **Client Secret**.

<Trigger option="cli.app_type" value="clicked">

<AppButton id="cli" name="Box CLI" scopes="root_readonly,root_readwrite,manage_managed_users,manage_app_users,manage_groups,manage_webhook,manage_enterprise_properties,manage_data_retention,item_execute_integration" can_act_as_user authentication_type="auth_code_grant" redirect_url="http://localhost:3000/callback" cors_origins>

アプリの作成

</AppButton>

</Trigger>

<Observe option="cli.app_type" value="clicked">

We will use these credentials to authenticate the Box CLI in the next step.

</Observe>

</Choice>

<Choice option="cli.app_type" value="use_existing" color="red">

# Use existing Box App

事前にBoxアプリをすでに作成済みの場合は、そのアプリも使用できます。そのアプリを使用するには、いくつかの設定が必要です。

1. [開発者コンソール][devconsole]に移動します。
2. アプリケーションを選択します。
3. Go to the application’s **Configuration** section 
4. アプリケーションが認証方法として**標準OAuth 2.0**を使用することを確認します。
5. \[**OAuth 2.0リダイレクトURI**] の設定まで下にスクロールし、\[**リダイレクトURI**] に値`http://localhost:3000/callback`を設定します。
6. Scroll down to the **Application Scopes** section to select your desired [permissions][scopes]. **Your application must have at least one or more** **of the following scopes:** read all files and folders stored in Box, read and write all files and folders in Box.
7. ページ上部にある \[**変更を保存**] ボタンをクリックします。

次に、クライアントIDとクライアントシークレットの値を以下の2つのフィールドにコピーします。

<Store id="cli_credentials.client_id" placeholder="zECq2EkYBjZ..." pattern="\w{32}">

クライアントID

</Store>

<Store id="cli_credentials.client_secret" placeholder="913td9hr6jo..." pattern="\w{32}">

クライアントシークレット

</Store>

We will use these credentials to authenticate the Box CLI in the next step.

</Choice>

<Choice option="cli.app_type" value="create_new,use_existing,clicked" color="none">

<Message danger>

# セキュリティに関する注意

API資格情報は、ブラウザキャッシュに保存されています。このガイドで後から出てくる**リセット**ボタンをクリックして、この情報を消去することを強くお勧めします。

</Message>

</Choice>

<Choice option="cli.app_type" value="create_new,use_existing,clicked" color="none">

## まとめ

* 新しい**Boxアプリ**の作成を選択しました。
  * Developerアカウントにサインアップ (必要な場合)
  * Had us create a **Custom App** for you that uses **OAuth 2.0** authentication
  * アプリケーションの**リダイレクトURL**を設定
* または、**既存のBoxアプリ**の使用を選択しました。

</Choice>

<Observe option="cli.app_type" value="create_new,use_existing,clicked">

<Next>

Boxアプリの設定が完了しました

</Next>

</Observe>

[devconsole]: https://account.box.com/developers/services

[signup]: https://account.box.com/signup/n/developer

[scopes]: https://developer.box.com/guides/api-calls/permissions-and-errors/scopes/