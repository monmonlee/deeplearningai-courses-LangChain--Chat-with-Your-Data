#### 問題背景：為什麼需要安裝 homebrew?
* homebrew 可用於管理 mac 套件，輸入`brew`後就可以安裝、管理、搜尋套件。
* 在第一章 document loader 中，因為我是從地端開始練習「音檔轉譯成文字」，因此需要下載ffmpeg套件，需要執行`brew install ffmpeg`

#### 安裝 homebrew 方法

第一步：把homebrew程式檔安裝到路徑中，但目前系統還不知道`brew`這個指令在哪裡

```bash 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

第二步：執行以下三行，目的為「設定 shell 環境 (brew shellenv) 把路徑加到 PATH，讓shell認識homebrew」

```bash 
echo >> /Users/mangtinglee/.zprofile
```


```bash 
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/mangtinglee/.zprofile 
```

```bash 
eval "$(/opt/homebrew/bin/brew shellenv)"
```
第三步：安裝自己需要的套件，例如：

```bash 
install ffmpeg
```

#### 備註

一、其他語法

1. 搜尋套件

``` bash 
brew search [text]
```

2. 更新套件

``` bash
brew install <fomula>
```

二、小檔案

* homebrew 是用 ruby 寫的，因為適合寫腳本，而且相較於c語言，ruby開發速度較快。