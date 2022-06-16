# Goで自作パッケージを使うときのimportのしかた

## ファイル構造

```txt
go_module
├── README.md
├── a
│   ├── c.go
│   └── go.mod
├── go.mod
└── main.go
```

ファイル名とパッケージ名は適当です。見ずらいと思いますがすいません。

main.goとa/c.goを書いたら以下コマンド実行

`cd a`

` go mod init go_module/b`

`cd ..`

`go mod init go_module`

`go mod edit -replace=b=./a`

`go get b`

これでフォルダaに入っていてファイル名c.goのパッケージbがインポートできる

実行すると完☆成