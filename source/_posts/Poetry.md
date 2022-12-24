---
title: Python 套件管理器 — Poetry
date: 2022-12-24 23:37:12
tags: 筆記
---
Poetry 類似 pip，能協助你進行套件管理（dependency management），但又比 pip 強大得多，因為它還包含了 pip 所未有的下列功能：

1. 虛擬環境管理
1. 套件相依性管理
1. 套件的打包與發布
1. 其中最為關鍵的是「套件的相依性管理.

# Python 套件管理器 --- Poetry 

## 安裝 Poetry

##### macOS / Linux / WSL

``` bash
$ curl -sSL https://install.python-poetry.org | python3 -
```
##### Windows

``` bash
$ (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
```

## 設定 PATH

``` bash
export PATH=$PATH:$HOME/.local/bin
```

## 建置 Poetry 專案

##### 1.初始化 Poetry專案

``` bash
mkdir poetry-demo
cd poetry-demo
poetry init
```

##### 2.管理 Poetry 虛擬環境

###### 建立 Poetry 虛擬環境

``` bash
poetry env use python
```

###### 啟動與退出虛擬環境

``` bash
poetry shell
```

``` bash
exit
```

###### 兩種虛擬環境建置位置
1. 全域
1. 專案內


###### 修改 `config` 來設置虛擬環境建置位置
``` bash
poetry config virtualenvs.in-project true
```

## Poetry 常用指令

##### 1. Poetry 新增套件

``` bash
poetry add
```

##### 2. 更新 poetry.lock

``` bash
poetry lock
```

##### 3. 安裝套件至 dev-dependencies

``` bash
poetry add black -D
```
或
``` bash
poetry add black --dev
```

##### 4. 列出全部套件清單

``` bash
poetry show
```

##### 5. 「樹狀」顯示套件依賴層級

``` bash
poetry show --tree
```

##### 6. Poetry 移除套件

``` bash
poetry remove
```

##### 7. 輸出等價 `requirements.txt` 的文件

``` bash
poetry export -f requirements.txt -o requirements.txt

```
##### 8. 輸出 dev-dependencies

``` bash
poetry export -f requirements.txt -o requirements.txt --dev
```


