export PATH="$HOME/.local/bin:$PATH"

# general alias
alias ls='ls --color=auto'
alias ll='ls -lF'
alias la='ls -A'

# chezmoi work hack
alias chezwork='chezmoi -S ~/.local/share/chezmoi_work -c ~/.config/chezmoi_work/chezmoi.toml'

# list brew packages installed but not tracked in any chezmoi Brewfile (this repo + work layer)
brewdrift() {
  local m=$(chezmoi execute-template '{{ .machine }}')
  cat ~/.local/share/chezmoi/Brewfile{,.$m}(N) ~/.local/share/chezmoi_work/Brewfile*(N) \
    | brew bundle cleanup --file=-
}

# zsh autocompletion
autoload -Uz compinit
compinit

# kubectl
alias kk='kubectl'
source <(kubectl completion zsh)

# prompt
eval "$(starship init zsh)"

