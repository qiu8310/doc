# 我的文档集

记录一些我以前没用但非常有用的事，或者一直在用但又记不住的一些事


**其它一些有用的文档：**

* [正则表达式](./REGEXP.md)
* [编码相关的文档](https://https://github.com/qiu8310/ccode/tree/master/docs)
* [ES6](./ES6.md)
* [遇到的一些坑](./BUG.md)
* [Amending a commit guide](./git/amending-a-commit-guide.md) - Copy from [here](https://github.com/RichardLitt/docs/blob/master/amending-a-commit-guide.md)
* 浏览器嗅探
  - 阿里的 [lib-env](https://github.com/amfe/lib-env)
  - 国外的 [bowser](https://github.com/ded/bowser)

## 命令行

```bash
alias ll='ls -al'

e() { open -a Sublime\ Text ${1-'.'}; } # 用指定的编辑器编辑当前文件或者指定的文件
o() { open ${1-'.'}; } # Open anything otherwise open the current directory in Finder
w() { dir="$HOME/Workspace"; while [[ -n $1 ]]; do dir="${dir}/${1}"; shift; done; cd $dir; } # 快速跳到工作目录

alias e='open -a Brackets' # 用指定的编辑器编辑文件
alias s='python -m SimpleHTTPServer'  # 快速在当前目录创建服务器
alias w='cd ~/Workspace' # 快速跳到工作目录

export EDITOR="/usr/bin/vim" # 设置默认编辑器
```


* [git-completion](https://github.com/git/git/blob/master/contrib/completion/git-completion.bash)
* git 提示当前分支

  ```bash
  function git_branch {
      ref=$(git symbolic-ref HEAD 2> /dev/null) || return;
      echo "("${ref#refs/heads/}") ";
  }

  function git_since_last_commit {
      now=`date +%s`;
      last_commit=$(git log --pretty=format:%at -1 2> /dev/null) || return;
      seconds_since_last_commit=$((now-last_commit));
      minutes_since_last_commit=$((seconds_since_last_commit/60));
      hours_since_last_commit=$((minutes_since_last_commit/60));
      minutes_since_last_commit=$((minutes_since_last_commit%60));

      echo "${hours_since_last_commit}h${minutes_since_last_commit}m ";
  }

  PS1="\u:\W \[\033[0m\]\[\033[1;36m\]\$(git_branch)\[\033[0;33m\]\$(git_since_last_commit)\[\033[0m\]\$ "
  ```



* Git tips

  * [A few git tips you didn't know about](http://mislav.uniqpath.com/2010/07/git-tips/)


## 工具

* [hub](https://github.com/github/hub)：Git 的一个扩展，让你能在命令行上操作 Github `(git + hub = github)`

* [Google: Web Starter Kit](https://developers.google.com/web/starter-kit/)：流程工具

* [Codekit](https://incident57.com/codekit/)：流程工具



## Web 开发

* [Docfiles 聚合](http://dotfiles.github.io/)
* [Google: Web 基本法则](https://developers.google.com/web/fundamentals/)
  
  包括四大流程：Set Up Environment、Build Your Site、Developing on Devices、Testing Your Site

### Grunt 上有用的工具

* [Grunt-codekit](https://github.com/fatso83/grunt-codekit): A grunt plugin to compile kit files using the CodeKit Language
