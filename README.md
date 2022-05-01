# Workaround for Byobu auto-rename issue for window 0

## What's this? | これは何？
[Byobu](https://www.byobu.org), a famous wrapper for terminal multiplexers, has a [bug](https://bugs.launchpad.net/byobu/+bug/1066626) that automatic window renaming function does not work properly only on window 0.
This simple script avoids the issue by renaming the window to blank and enabling automatic-rename function again.

[Byobu](https://www.byobu.org)（ターミナルマルチプレクサーのラッパーとして有名なアプリ）には、window 0のみautomatic renameが動作しない[バグ](https://bugs.launchpad.net/byobu/+bug/1066626)があります。
Window名を空にして再度automatic-renameを有効化するシンプルなシェルスクリプトでこの問題を回避します。

### Without workaround | Workaround未適用
It shows like `0:-*`, not `0:bash*` for window 0.
Window 0のみ`0:bash*`のような表示になりません。
![Without workaround](https://github.com/figmentum/byobu-autorename-fix/raw/resources/images/byobu_original_behavior.png)

### With workaround | Workaround適用後
Name of window 0 shows like other windows.
Window 0も他のwindowと同様の表示になっています。
![With workaround](https://github.com/figmentum/byobu-autorename-fix/raw/resources/images/byobu_behavior_after_fix.png)

## Target environments | 動作環境
* byobu (tested on byobu version 5.133 on Ubuntu 20.04)
* tmux (tested on tmux version 3.0a on Ubuntu 20.04)
* bash (tested on bash version 5.0.17 on Ubuntu 20.04) or zsh (tested on zsh 5.8 on Ubuntu 20.04)

## Usage | 使用方法

### Method 1
Add lines like following into your `.bashrc` or `.zshrc` to include `.byobu_autorename_fix`.
下記のような内容を`.bashrc`または`.zshrc`に追記して`.byobu_autorename_fix`を読み込むようにする。

```
# Include byobu_autorename_fix if exists
if [ -f ~/.byobu_autorename_fix ]; then
    . ~/.byobu_autorename_fix
fi
```

### Method 2
Copy & paste content of `.byobu_autorename_fix` into your `.bashrc` or `.zshrc`.
`.byobu_autorename_fix`の内容を`.bashrc`もしくは`.zshrc`に書き込む。

## Notes | 補足
This workaround may cause another problem. It is not sufficiently evaluated.
このworkaround適用で他の問題が発生する可能性があります。十分なテストは行われていません。

