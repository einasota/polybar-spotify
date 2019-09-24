# Controlador de Musica para Spotify

Um simples controlador e exibidor de música para spotify no polybar. 


## Screenshot:

![exemplo:](https://i.ibb.co/c6cYFD5/2019-09-24-04-39.png"Exemplo")

## Dependências:
- playerctl
- ttf-font-awesome


### Arch Linux (Testado):
- 
    - [playerctl](https://www.archlinux.org/packages/community/x86_64/playerctl/)
    - [ttf-font-awesome](https://aur.archlinux.org/packages/ttf-font-awesome-4) [AUR]
    
## Scripts

Adicione os scripts **spotify** e **spotifypp** ao caminho ***~/.config/polybar/scripts***

## Código

#### **Módulos**
Adicione esse códigos nos arquivos **user_modules.ini** ou **config.ini** dependendo de como o seu polybar está configurado.

```;; SPOTIFY
[module/previous]
type = custom/script
format-padding = 2
exec = echo ""
line-size = 1
click-left = "playerctl --player=spotify previous"

[module/next]
type = custom/script
format-padding = 2
exec = echo ""
line-size = 1
click-left = "playerctl --player=spotify next"

[module/playpause]
type = custom/script
format-padding = 2
exec = ~/.config/polybar/scripts/spotifypp
interval = 0.1
click-left = "playerctl --player=spotify play-pause"

[module/spotify]
type = custom/script
format-prefix = " "
exec = ~/.config/polybar/scripts/spotify
interval = 0.1
;;[Apenas i3wm] - Remova o comentário da linha abaixo para focar no Spotify ao clicar no nome da música
;click-left = i3-msg '[class="Spotify"] focus'
```
#### Configuração

Adicione os seguintes modulos ao arquivo **config.ini**:

```
module-¹align = ... spotify previous playpause next ...
enable-ipc = true
;;¹align = procure o modules com alinhamento que deseja adicionar os modulos.
;left = para alinhar a esquerda 
;center = para alinhar ao centro
;right = para alinhar a direita

```




