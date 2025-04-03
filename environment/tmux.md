### Tmux

```bash
tmux ls // список сессий
tmux new -s <s> // создать сессию
tmux a -t <s> // подключиться к сессии
CTRL+B then c // новое окон
CTRL+B then w // список окон
CTRL+B then 0 // переключиться на первое окно
CTRL+B then стрелка/n/p // переключиться на соседнее окно
CTRL+B then D // выйти из сессии, не закрываю сессию
CTRL-B then , (tmux rename-window)
:kill-session // выйти из сессии
CTRL-B then [ // scroll mode: Arrows, PgDn/PgUp, q to quit scorll mode
```
