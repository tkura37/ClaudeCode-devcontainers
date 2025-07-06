# Claude Code セットアップ手順(Dev Containers)

## 概要
- 前提：WindowsのVSCode上で操作
- Dev ContainersでClaude Codeを動かすためのセットアップ手順

## 事前インストール
- Dockerデスクトップアプリ
  [Docker Desktop](https://www.docker.com/ja-jp/products/docker-desktop/)
- VSCode もしくは Cursor
- VSCode拡張機能
  [Dev Containers](https://marketplace.cursorapi.com/items?itemName=ms-vscode-remote.remote-containers)

## Dev Containersの設定
.devcontainer/devcontainer.jsonに記載
1. `image`で使用するLinuxを指定 
   - Claude CodeはLinux上のみで動作するため
   - 今回はUbuntu 22.04を指定
   - 別のものを使用したい場合は、[Docker Hub](https://hub.docker.com/r/microsoft/devcontainers-base)で検索
2. `features`でNode.jsのバージョンを指定
   - Claude Codeをnpmでインストールするため
3. `features`でClaude Codeのバージョンを指定
   - 今回は最新バージョンを指定
4. `mounts`でマウントしたいホスト(Windows)側のファイルを指定
   - 今回はC:\Users\user\devcontainer\claude内のディレクトリとファイルを指定

## コンテナのビルド・接続手順
1. VSCode左下の`><`ボタンから、「コンテナーで再度開く」をクリック
2. 開発コンテナーへの接続が開始されるので、しばらく待つ
3. VSCode左下が`><開発コンテナー @ desktop-linux`に変われば接続完了

## 接続解除
VSCode左下の`><開発コンテナー @ desktop-linux`から、「リモート接続を終了する」をクリック

## 注意事項
- プロジェクトを`.code-workspace`で開いていると、devcontainer.jsonが認識されない場合がある
   - プロジェクトディレクトリを直接開くと、問題なくコンテナに入れる
