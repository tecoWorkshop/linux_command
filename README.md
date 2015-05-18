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

## chmod  ikeda
~説明~
### 構文
### オプション

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

-r  
ディレクトリを再帰的にたどって検索する。

-c  
検索にヒットする行数を取得。

-n  
行番号を追加。

-i  
大文字小文字を区別しない。

-v  
特定の文字列を持つ行を除外する。

-l  
マッチしたファイルのファイル名のみを出力する。

-L  
マッチしなかったファイルのファイル名を出力する。

## tail head  ikeda
~説明~
### 構文
### オプション

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

## find  uraki
~説明~
### 構文
### オプション

## df  ikeda
~説明~
### 構文
### オプション

## | パイプ  ono
~説明~
### 構文
### オプション

## diff  iida
~説明~
### 構文
### オプション

## sed  uraki
~説明~
### 構文
### オプション

## awk  ikeda
~説明~
### 構文
### オプション

