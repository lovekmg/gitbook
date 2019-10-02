---
description: plugin 관리 및 추천 플러그인 설치
---

# \[memo\] Vim plugin 설치

## 1. Vundle 설치

Vundle 말고도 몇개 더 있지만\(pathogen, vim-plug\) 여기선 Vundle 로 plugin 관리한다.

```
$ mkdir -p ~/.vim/bundle
$ chmod -R 755 ~/.vim
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

{% hint style="info" %}
 본인 home 디렉토리에 설치하는거라 그냥 붙여넣기 하면 된다.
{% endhint %}

## 2. ~/.vimrc에 아래 내용 추가

1. 본인 홈 디렉토리의 vim 설정파일을 연다

```text
$ vim ~/.vimrc
```

   2. 아래 내용을 복사&붙여넣기 한다.

```
map <C-n> :NERDTreeToggle<CR> " [ctrl + n] 하면 nerdtree 실행됨

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" 여기에 vim plugin을 작성하고 :PluginInstall 하면 됨.
Plugin 'VundleVim/Vundle.vim'
Plugin 'scrooloose/nerdtree'

call vundle#end()
```

{% hint style="info" %}
vim에서 더블쿼터\(쌍따옴표 =&gt; "\)는 주석이다.
{% endhint %}

