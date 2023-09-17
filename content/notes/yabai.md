+++
title = "yabai"
author = ["liangGTY"]
draft = false
+++

mac下的平铺窗口管理软件. 可以与 [karabiner]({{< relref "karabiner.md" >}}) / [skhd](https://github.com/koekeishiya/skhd) 等工具集成. 通过自定义快捷键即可完全控制 Window / Desktop / Display.

个人认为是 mac 平台下最适合喜欢折腾和有完全客制化需求的程序员的窗口管理软件.


## notes {#notes}

最好禁用 mac 的 [桌面自动排序功能]({{< relref "my_mac.md#mac-rearrange-automatically" >}}). 否则会让你感到很混乱


## yabairc {#yabairc}

```sh
#!/usr/bin/env sh
sudo yabai --load-sa
yabai -m signal --add event=dock_did_restart action="sudo yabai --load-sa"

yabai -m config mouse_follows_focus off
yabai -m config focus_follows_mouse off
yabai -m config window_placement second_child
yabai -m config window_topmost off
yabai -m config window_shadow on
yabai -m config window_opacity off
yabai -m config window_opacity_duration 0.0
yabai -m config active_window_opacity 1.0
yabai -m config normal_window_opacity 0.90
yabai -m config window_border off
yabai -m config window_border_width 6
yabai -m config active_window_border_color 0xff775759
yabai -m config normal_window_border_color 0xff555555
yabai -m config insert_feedback_color 0xffd75f5f
yabai -m config split_ratio 0.50
yabai -m config auto_balance off
yabai -m config mouse_modifier fn
yabai -m config mouse_action1 move
yabai -m config mouse_action2 resize
yabai -m config mouse_drop_action swap

# general space settings
yabai -m config layout bsp
yabai -m config top_padding 10
yabai -m config bottom_padding 10
yabai -m config left_padding 10
yabai -m config right_padding 10
yabai -m config window_gap 10

# mission-control desktop labels
yabai -m space 1 --label code
yabai -m space 2 --label web
yabai -m space 3 --label mail
yabai -m space 4 --label emacs
yabai -m space 5 --label shell
yabai -m space 6 --label social

yabai -m signal --add event=window_destroyed active=yes action="yabai -m query --windows --window &> /dev/null || yabai -m window --focus mouse &> /dev/null || yabai -m window --focus \$(yabai -m query --windows --space | jq .[0].id) &> /dev/null"
yabai -m signal --add event=application_terminated action="yabai -m query --windows --window &> /dev/null || yabai -m window --focus mouse"
yabai -m signal --add event=application_hidden action="yabai -m query --windows --window &> /dev/null || yabai -m window --focus mouse"
yabai -m signal --add event=window_minimized action="yabai -m query --windows --window &> /dev/null || yabai -m window --focus mouse"
yabai -m signal --add event=space_changed action="yabai -m window --focus \$(yabai -m query --windows --space | jq .[0].id)"
yabai -m signal --add event=space_changed action="yabai -m query --windows --window &> /dev/null || yabai -m window --focus mouse"

echo "yabai configuration loaded.."

```
