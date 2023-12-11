# Console / Terminal Cheatsheet

On github: https://github.com/patopitaluga/patooverflow/blob/master/iterm-zsh.md

Also useful:
* [Node / javascript cheatsheet](https://github.com/patopitaluga/patooverflow/blob/master/console-terminal.md)

Index:
* [Edit .zshrc](#edit-zshrc)

------
## <a name="edit-zshrc"></a> Edit .zshrc
`code ~/.zshrc`

PROMPT='${ret_status} %{$fg[cyan]%}%~%{$reset_color%} $(git_prompt_info)'

------
Ignore the rest code. Is styling for local display of this file using https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
<style>
  .markdown-body {
    position: relative;
  }
  .cpy-btns {
    background: transparent;
    border: 0;
    cursor: pointer;
    display: block;
    font-family: monospace;
    font-size: 11px;
    margin-top: -4px;
    position: absolute;
    right: 45px;
    width: auto;
  }
  .cpy-btns::before {
    content: 'COPY'
  }
</style>
