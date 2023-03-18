If you are using oh-my-zsh, you can use it directly, and there is no problem.
But if you feel that oh-my-zsh is slow in our daily use, you can use zinit.
There are several things to pay attention to in the use of zinit:
  ```
  # This is my zshrc
  
  # zinit script
  zinit snippet OMZ::plugins/sudo/sudo.plugin.zsh
  zinit snippet OMZ::lib/clipboard.zsh
  zinit snippet OMZ::lib/completion.zsh
  zinit snippet OMZ::lib/history.zsh
  zinit snippet OMZ::lib/key-bindings.zsh
  zinit snippet OMZ::lib/git.zsh
  zinit snippet OMZ::lib/theme-and-appearance.zsh

  # these are common zsh plugins 
  zinit load zsh-users/zsh-autosuggestions
  zinit light zdharma/fast-syntax-highlighting

  # this is the pure theme
  zinit ice pick"async.zsh" src"pure.zsh"
  zinit light sindresorhus/pure

  # setopt autolist
  # unsetopt menucomplete

  # This is very important for the automatic completion of the tab key
  autoload -U compinit
  compinit
  
  # Disable zsh's built-in regular expression matching
  setopt nonomatch
  ```
And the next is the config of anaconda
```shell
function init_conda(){
        # echo "func enter"
        unalias conda
        origin_str="string"
        conda_exist="`command -v conda` $origin_str"
        if [ "$conda_exist" == "conda string" ] ; then
                echo "conda exist: true"
                conda $*
        else
                echo "conda does not exist"
                source /opt/anaconda/bin/activate root
                conda $*
        fi
}

alias conda="init_conda"
```
  
