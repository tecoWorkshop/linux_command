# linux_command
リナックスコマンドについて


## ls
list directory contents

ファイルやディレクトリの情報を表示する

### 構文

    ls [OPTION]... [FILE]...

### オプション
-a, --all  
ドットファイルを含む全てのファイルを表示する

-l  
詳細を表示する

--color[=when]  
色付けして表示する  
when には 'never', 'auto', 'always'(default) が入る

-t, --sort=time  
タイムスタンプの新しい順にソートして表示する

-S, --sort=size  
サイズ順にソートして表示する

-r, --reverse  
ソート順を逆にする

-h, --human-readable  
-l オプションを使用したときに、サイズを読みやすいフォーマットで表示する


## cd
Change  the current directory to dir.

ディレクトリを移動する

### 構文

        cd [dir]

### Tips

ルートディレクトリ

        $ cd /

親ディレクトリ

        $ cd ../

ホームディレクトリ

        $ cd ~/
        $ cd

ひとつ前にいたディレクトリ

        $ cd -


## mkdir
make directories

ディレクトリを作成する

### 構文

        mkdir [OPTION]... DIRECTORY...

### オプション

-m, --mode  
ディレクトリのパーミッションを設定する

-p, --parents  
必要に応じて親ディレクトリも作成する  
ツリー状に作成できる

## cp
copy files and directories

ファイルやディレクトリをコピーする

### 構文

        cp [OPTION]... [-T] SOURCE DEST
        cp [OPTION]... SOURCE... DIRECTORY
        cp [OPTION]... -t DIRECTORY SOURCE...

### オプション

-b, --backup  
上書きされるファイルのバックアップを作成する

-f, --force  
強制的に上書きする

-i, --interactive  
上書きするかを問い合わせる

-l, --link  
コピーする代わりにハードリンクを作る

-s, --symbolic-link  
コピーする代わりにシンボリックリンクを作る

-p, --preserve  
パーミッション、オーナー情報、タイムスタンプを保持したままコピーする

-r, --recursive  
ディレクトリを再帰的にコピーする

## mv
move files

ファイルやディレクトリを移動する

### 構文

        mv [OPTION] SOURCE TARGET
        mv [OPTION] SOURCE ... DIRECTORY
     
### オプション

-b, --backup  
上書きされるファイルのバックアップを作成する

-f, --force  
強制的に上書きする

-i, --interactive  
上書きするかを問い合わせる

-u, --update
同名のファイルの場合，タイム・スタンプを比較し同じまたは新しいときには移動を行わない

-v, --verbose
移動の前にファイル名を表示する
    
## rm
remove directory entries

ファイルやディレクトリを削除する

### 構文

        rm [-OPTION] FILE

### オプション

-d, --directory
ディレクトリごと削除できる。スーパーユーザーのみ使用が可能
    
-f, --force
警告メッセージを表示しない
      
-i, --interactive
ファイルを削除してよいかを問い合わせる
  
-r, -R, --recursive
ディレクトリ内を再帰的に削除する
  
-v, --verbose
ファイルを削除する前にファイル名を表示する

## chmod
~説明~
### 構文
### オプション

## ps
~説明~
### 構文
### オプション

## less
~説明~
### 構文
### オプション

## grep
~説明~
### 構文
### オプション

## tail head
~説明~
### 構文
### オプション

## cat
~説明~
### 構文
### オプション

## top
~説明~
### 構文
### オプション

## find
~説明~
### 構文
### オプション

## df
~説明~
### 構文
### オプション

## | パイプ
~説明~
### 構文
### オプション

## diff
~説明~
### 構文
### オプション

## sed
~説明~
### 構文
### オプション

## awk
~説明~
### 構文
### オプション

