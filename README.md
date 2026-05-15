# dotfiles

[chezmoi](https://www.chezmoi.io/) 기반 dotfile 관리 레포지토리.

## 관리 파일

| 파일 | 설명 |
|------|------|
| `~/.zshrc` | zsh + oh-my-zsh 설정 |
| `~/.zprofile` | macOS 전용 환경변수 (Homebrew, OrbStack, Obsidian) |
| `~/.p10k.zsh` | Powerlevel10k 테마 |
| `~/.gitconfig` | Git 전역 설정 |
| `~/.config/git/ignore` | Git 전역 gitignore |
| `~/.ssh/config` | SSH 호스트 설정 |
| `~/.claude/CLAUDE.md` | Claude Code 전역 설정 |
| `~/.claude/settings.json` | Claude Code 설정 |
| `~/.codex/AGENTS.md` | Codex 전역 instruction |
| `~/.codex/config.toml` | Codex 정적 설정 (modify script로 런타임 state 보존) |
| `~/.config/gh/config.yml` | gh CLI 설정 |
| `~/.config/mise/config.toml` | mise 툴체인 설정 |

macOS 전용 항목(Homebrew, OrbStack, Android SDK, GCM credential helper 등)은 Linux에서 자동으로 제외됩니다.

## 새 머신 세팅

```sh
# chezmoi 설치
sh -c "$(curl -fsLS get.chezmoi.io)"

# dotfiles 적용
chezmoi init --apply https://github.com/hw0k/dotfiles.git
```

## 로컬에서 편집

```sh
# 파일 수정 후 chezmoi에 반영
chezmoi re-add ~/.zshrc

# 홈 디렉토리에 적용
chezmoi apply

# 변경 사항 확인
chezmoi diff
```
