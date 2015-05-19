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
change file mode bits

ファイルやディレクトリのアクセス権を変更する

### 構文

        chmod [OPTION]... MODE[,MODE]... FILE...
        chmod [OPTION]... OCTAL-MODE FILE...

### オプション

-r, -R, --recursive  
ディレクトリ内を再帰的に変更する

#### 記号によるモードの記述
権限はカンマで区切ることによりいくつでも記述できる。
また，最初のユーザーの設定項目を省略したときはすべてのユーザーと同等の意味になる

        [ugoa][+-=][rwx],...

u : 所有者  
g : グループ  
o : その他のユーザ  
a : すべて

+ : 後述の権限を付加する  
- : 後述の権限を削除する
= : 後述の権限にする  

r : 読み込み権限  
w : 書き込み権限  
x : 実行権限  

#### 数字によるモードの記述
3桁の8進数を使用して権限を指定できる。
左から順に所有者，グループ，その他のユーザの権限を表す。

例

777 : rwxrwxrwx  
644 : rw_r__r__

## ps  ono
~説明~
### 構文
### オプション

## less
opposite of more

ファイルの内容をページ単位で自由に閲覧できる。

### 構文

        less [filename]...

### オプション

**-N, --LINE-NUMBERS**  
行番号を表示する。
遅くなる。

**\+**  
起動時に実行するコマンドを指定できる。

    +G  
    起動時に最終行へ移動する。  
    +F  
    起動時にtailモードにする。  

### 備考
カラー表示に対応させる。  
http://qiita.com/makisyu/items/a8c4231a95d92f02b73a

## grep
searching plain-text data sets for lines matching a regular expression.  
Its name comes from the ed command g/re/p (globally search a regular expression and print).

テキストファイル中から、検索パターンに一致する行を検索。  
検索パターンには、正規表現も使用可能。

### 構文

        grep [OPTION] PATTERN [FILE]

### オプション

**-c**, **--count**  
検索にヒットする行数を取得。

**-i**, **--ignore-case**  
大文字小文字を区別しない。

**-l**, **--files-with-matches**  
マッチしたファイルのファイル名のみを出力する。

**-L**, **--files-without-match**  
マッチしなかったファイルのファイル名を出力する。

**-n**, **--line-number**  
行番号を追加。

**-r**, **--recursive**  
ディレクトリを再帰的にたどって検索する。

**-v**, **--invert-match**  
特定の文字列を持つ行を除外する。

## head
output the first part of files

ファイルの先頭部分を表示する

### 構文

        head [OPTION]... [FILE]...

### オプション

-c, --bytes=K  
ファイルの先頭から K バイトを表示する

-n, --lines=K  
ファイルの先頭から K 行を表示する

## tail
output the last part of files

ファイルの末尾部分を表示する

### 構文

        tail [OPTION]... [FILE]...

### オプション

-c, --bytes=K  
ファイルの末尾から K バイトを表示する

-n, --lines=K  
ファイルの末尾から K 行を表示する

-f, --follow  
ファイルの内容を監視し、表示を更新する  
ログの監視に便利

## cat  ono
~説明~
### 構文
### オプション

## top
display and update information about the top cpu processes

稼働中のシステムの 動的なリアルタイムの概要を報告する。  
Linux カーネルが現在管理しているタスクの一覧だけでなく、 システムの概要情報も表示できる。

### 構文

        top -hv | -bcisS -d delay -n iterations -p pid [, pid ...]

### オプション

**-b**  
バッチモード  
このモードでは、top は入力を受け付けず、 '-n' コマンドラインオプションで設定された繰り返し回数に達するか、 kill されるまで実行を続ける。

**-d**  
遅延時間 間隔  
スクリーンを更新する間隔を指定する。

**-n**  
繰り返し回数 制限

### 対話コマンド

**< Enter > または < Space >**  
表示の再描画

**'q'**  
終了

**'n'**  
表示するプロセス数を変更する。  
プロンプトが出るので表示する数を入れる。

### 表示の見かた

##### 基本情報  
    top - 20:49:53 up 7 min,  1 user,  load average: 0.03, 0.36, 0.23
          1------- 2-------   3-----   4-----------------------------
    1 : 現在時刻
    2 : 起動してからの時間
    3 : ログインしているユーザー数
    4 : 数字の最初から1、5、15分間の実行待ちプロセス数の平均

----

##### プロセスの情報
    Tasks:  79 total,   2 running,  77 sleeping,   0 stopped,   0 zombie

    total : プロセスの総数
    running : 実行中のプロセス数
    sleeping : スリープ状態のプロセス数
    stopped : 停止状態のプロセス数
    zonbie : ゾンビ状態のプロセス数

----

##### CPU関連情報
    Cpu(s):  0.0% us,  0.3% sy,  0.0% ni, 99.7% id,  0.0% wa,  0.0% hi,  0.0% si

    us : ユーザーモードの状態にある時間の割合
    sy : システムモードの状態にある時間の割合
    ni : niceされたタスクの実行中の状態にある時間の割合
    id : アイドル状態にある時間の割合
    wa : IOの終了待ちの状態にある時間の割合
    hi : ハードウェア割り込み要求の状態にある時間の割合
    si : ソフトウェア割り込みの状態にある時間の割合

----

##### メモリ関連情報
    Mem:   1035556k total,   453728k used,   581828k free,    13820k buffers
    Swap:  2096472k total,        0k used,  2096472k free,   329060k cached

    total : トータルのメモリ量
    used : 使用中のメモリ量
    free : 使用していないメモリ量
    buffers : バッファとして使用されているメモリ量
    cached : キャッシュとして使用されているメモリ量

----

##### プロセス一覧
    PID USER      PR  NI  VIRT  RES  SHR S %CPU %MEM    TIME+  COMMAND

    PID : タスクのプロセスID
    USER : タスクの所有者のユーザー名
    PR : タスクの優先度
    NI : タスクのnice値
         小さい値が優先度が高い
    VIRT : 仮想イメージ
           単位はKB
    RES : タスクの用いている物理メモリの総量
          単位はKB
    SHR : タスクが利用している共有メモリ
    S : プロセスの状態
    %CPU : 最後にスクリーンが更新されて以降、タスクがCPUを占有していた割合
           プロセッサ一つあたりの時間に対するパーセンテージで表示される
    %MEM : タスクの物理メモリの占有
    TIME+ : タスクが起動してから利用したCPU時間の総量
    COMMAND : タスクのコマンド名

    Sのプロセスの状態は、以下のいずれかとなる。
        S : スリープ状態
        D : 割り込み不可能なスリープ状態
        R : 実行中
        Z : ゾンビ
        T : 停止中
          : 負のnice値を持つプロセス
        N : 正のnice値を持つプロセス
        W : スワップアウトされたプロセス

## find
searches through one or more directory trees of a file system, locates files based on some user-specified criteria and applies a user-specified action on each matched file.

指定されたディレクトリ以下の階層から、与えられた条件に適合するファイルを検索

### 構文

        find [PATH] [OPTION] [EXPRESSION]

### オプション

**-atime** n  
最終アクセス時刻がn日前。

**-anewer** file  
指定されたファイルの更新時刻よりも後にアクセスされたファイル。

**-ctime** n  
ファイル名、ファイルサイズ、パーミッション、リンク数、オーナー、グループなどの最終変更時刻がn日前。

**-cnewer** file  
指定されたファイルの更新時刻よりも後に変更されたファイル。

**-empty**  
ファイルまたはディレクトリが空。

**-mtime** n  
最終更新時刻がn日前。

**-newer** file  
指定されたファイルの最終更新時刻よりも後に変更されたファイル。

**-name** pattern  
ファイル名が指定されたパターンに一致。

**-perm** mode  
許可属性がmodeであるファイル。

**-size** n[ck]  
ファイルサイズがn。nの後にcを付加するとバイト単位、kを付加するとキロバイト単位。

**-type** filetype  
指定されたタイプのファイル。指定可能なタイプ種別は以下。

    b  ブロック型特殊ファイル（バッファ付き）
    c  キャラクタ型特殊ファイル（バッファなし）
    d  ディレクトリ
    p  名前付きパイプ（FIFO）
    f  通常のファイル
    l  シンボリック・リンク
    s  ソケット

**-user** uname  
指定されたユーザーが所有者ならば真を返します。

### アクション

**-exec** command {} \;  
検索後，commandを実行する。commandの後に{}を指定すると，検索したファイル名に置き換わり、command引数となる。

**-fprint** file  
検索結果をfileに書き出す。同名のファイルがある場合は上書きをする。

**-ls**  
検索結果を "ls -dils" と同様な書式で表示。

**-ok** command \;  
-execと同様に検索後commandを実行するが、都度、ユーザーに問い合わせる。

**-print**  
検索結果をフルパスで標準出力する。

## df
report file system disk space usage

ファイルシステムディスク容量を表示する

### 構文

        df [OPTION]... [FILE]...

### オプション

-a, --all  
ダミーを含む全てのファイルシステムを表示する

-B, --block-size=SIZE  
指定したブロックサイズで表示する  
  -BM : 1Mbyte 単位で表示  
  --block-size=1024 : 1Kbyte 単位で表示

-h, --human-readable  
サイズを読みやすいフォーマットで表示する

-l, --local  
ローカルのファイルシステムのみを表示する

-t, --type=TYPE  
指定したタイプのファイルシステムのみを表示する（例：ext3 ext4）

### 表示の見かた
```
    $ df -h
```
```
    Filesystem               Size  Used Avail Use% Mounted on
    /dev/mapper/centos-root   39G   12G   28G  30% /
    devtmpfs                 220M     0  220M   0% /dev
    tmpfs                    229M     0  229M   0% /dev/shm
    tmpfs                    229M  4.3M  225M   2% /run
    tmpfs                    229M     0  229M   0% /sys/fs/cgroup
    /dev/sda1                497M  184M  314M  37% /boot
    
    Filesystem : ファイルシステム
    Size : サイズ
    Used : 使用量
    Avail : 使用可能量
    Mounted on : マウント位置
```

## | パイプ  ono
~説明~
### 構文
### オプション

## diff  iida
~説明~
### 構文
### オプション

## sed
sed (stream editor) is a Unix utility that parses and transforms text, using a simple, compact programming language.

文字列フィルタリング、変換用のストリームエディタ

### 構文

        sed [OPTION] [FILE]

### オプション

**-e** script, **--expression**=script  
指定されたコマンドを適用。

**-f** script-file, **--file**=script-file  
指定されたファイルに記述されたコマンド列を適用。


### コマンド

**s/ regexp / replacement /[g]**  
regexp（置換条件）でreplacement（対象文字列）を置換する。  
gを付加した場合、regexpに該当する、すべてのreplacementを置換する。

1,n **d**  
1行目からn行目を削除する。

## awk  ikeda
~説明~
### 構文
### オプション

