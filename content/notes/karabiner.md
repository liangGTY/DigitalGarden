+++
title = "karabiner"
author = ["liangGTY"]
draft = false
+++

macOS 上强大的键盘定制化软件. 不仅可以进行简单的 key mapTo key, 还可以根据复杂规则进行映射, 例如我有两把不同的键盘 我可以根据键盘进行对应的改键.
也可以通过快捷键触发shell命令执行. 我用他运行 [yabai]({{< relref "yabai.md" >}}) command, 控制我的窗口.

karabiner 官方的配置文件使用 Json 格式, 配置文件行数过多, 导致编辑配置文件异常困难 . 可以搭配 [goku]({{< relref "goku.md" >}}) 使用 [edn]({{< relref "edn.md" >}}) 格式配置文件进行编辑


## config {#config}

```edn
{:profiles
 {:goku {:default true
         :sim     30  ;; simultaneous_threshold_milliseconds (def: 50)
                      ;; keys need to be pressed within this threshold to be considered simultaneous
         :delay    0  ;; to_delayed_action_delay_milliseconds (def: 500)
                      ;; time after which the key press is delayed
         :alone   1000  ;; to_if_alone_timeout_milliseconds (def: 1000)
                      ;; hold for .. ms to register single tap
         :held    500 ;; to_if_held_down_threshold_milliseconds (def: 500)
                      ;; key is fired twice when 500ms is elapsed (otherwise seen as a hold command)
         }}

 :tos {:select_abc {:input :abc}}

 :devices {:apple [{:vendor_id 1452 :product_id 832}]
           :hhkb [{:vendor_id 1278 :product_id 33}]
           :filco [{:vendor_id 2652 :product_id 34050}]}
 :applications {:Preview ["^com\\.apple\\.Preview$"]
                :Emacs ["^org\\.gnu\\.Emacs$"]
                :Idea ["com\\.jetbrains\\.intellij"]
                :Chrome ["com\\.google\\.Chrome"]
                :VSCode ["com\\.microsoft\\.VSCode"]
                :Obsidian ["md\\.obsidian"]}

 :input-sources {:abc      {:input_source_id "^com\\.apple\\.keylayout\\.ABC$"}}
 :templates {:open "open \"%s\""}
 :simlayers {;; make w key a simlayer key
             ;; layers works too, but only recommended for none typing keys
             ;; like . , tab
             ;; or keys like z, which used less often
             :launch-mode {:key :o}}
 :layers    {}
 :main [{:des "hhkb simple"
         :rules [:hhkb
                 [:##right_command :caps_lock]]}
        {:des "apple simple"
         :rules [:apple
                 [:##right_command :caps_lock]
                 [:##left_control :caps_lock]
                 [:##caps_lock :left_control]]}
        {:des "filco simple"
         :rules [:filco
                 [:##caps_lock :left_control]
                 [:##left_control :caps_lock]
                 [:##left_command :left_option]
                 [:##left_option :left_command]
                 [:##right_option :caps_lock]
                 [:##right_command :right_option]]}
        {:des "yabai"
         :rules [[:!O1 "/usr/local/bin/yabai -m space --focus 1"]
                 [:!O2 "/usr/local/bin/yabai -m space --focus 2"]
                 [:!O3 "/usr/local/bin/yabai -m space --focus 3"]
                 [:!Oq "/usr/local/bin/yabai -m space --focus 4"]
                 [:!Ow "/usr/local/bin/yabai -m space --focus 5"]
                 [:!Oe "/usr/local/bin/yabai -m space --focus 6"]

                 [:!Oescape "/usr/local/bin/yabai -m space --focus recent"]

                 ;; 窗口移动至特定桌面
                 [:!E1 "/usr/local/bin/yabai -m window --space 1 && /usr/local/bin/yabai -m space --focus 1"]
                 [:!E2 "/usr/local/bin/yabai -m window --space 2 && /usr/local/bin/yabai -m space --focus 2"]
                 [:!E3 "/usr/local/bin/yabai -m window --space 3 && /usr/local/bin/yabai -m space --focus 3"]
                 [:!Eq "/usr/local/bin/yabai -m window --space 4 && /usr/local/bin/yabai -m space --focus 4"]
                 [:!Ew "/usr/local/bin/yabai -m window --space 5 && /usr/local/bin/yabai -m space --focus 5"]
                 [:!Ee "/usr/local/bin/yabai -m window --space 6 && /usr/local/bin/yabai -m space --focus 6"]

                 ;; 窗口交换
                 [:!SCh "/usr/local/bin/yabai -m window --warp west"]
                 [:!SCj "/usr/local/bin/yabai -m window --warp south"]
                 [:!SCk "/usr/local/bin/yabai -m window --warp north"]
                 [:!SCl "/usr/local/bin/yabai -m window --warp east"]
                 [:!SOh "/usr/local/bin/yabai -m window --swap west"]
                 [:!SOj "/usr/local/bin/yabai -m window --swap south"]
                 [:!SOk "/usr/local/bin/yabai -m window --swap north"]
                 [:!SOl "/usr/local/bin/yabai -m window --swap east"]

                 ;; 窗口焦点移动
                 [:!Oh "/usr/local/bin/yabai -m window --focus west"]
                 [:!Oj "/usr/local/bin/yabai -m window --focus south"]
                 [:!Ok "/usr/local/bin/yabai -m window --focus north"]
                 [:!Ol "/usr/local/bin/yabai -m window --focus east"]

                 [:!OEescape "/usr/local/bin/yabai -m window --display recent && /usr/local/bin/yabai -m display --focus recent"]

                 [:!Od "/usr/local/bin/yabai -m window --toggle zoom-parent"]
                 [:!OCreturn_or_enter "/usr/local/bin/yabai -m window --toggle zoom-fullscreen"]
                 ;; x y 轴反转
                 [:!COy "/usr/local/bin/yabai -m space --mirror y-axis"]
                 [:!COx "/usr/local/bin/yabai -m space --mirror x-axis"]

                 ;; 平铺模式与浮动模式切换
                 [:!TOs "/usr/local/bin/yabai -m space --layout $(/usr/local/bin/yabai -m query --spaces --space | /usr/local/bin/jq -r 'if .type == \"bsp\" then \"float\" else \"bsp\" end')"]

                 ;;
                 [:!Oz "/usr/local/bin/yabai -m window --focus stack.prev"]
                 [:!Oc "/usr/local/bin/yabai -m window --focus stack.next"]
                 [:!TOi "/usr/local/bin/yabai -m window --insert stack"]

                 ;; end
                 ]}
        {:des "VIM Preview"
         :rules [:Preview
                 [:j :down_arrow]
                 [:k :up_arrow]
                 ;; end
                 ]}

        {:des "Ctrl - JK"
         :rules [:!Emacs
                 [:!Tj :down_arrow]
                 [:!Tk :up_arrow]
                 [:!Th :left_arrow]
                 [:!Tl :right_arrow]]}
                 ;;
        {:des "Emacs esc to Select ABC"
         :rules [:Emacs
                ;; Emacs App 下 esc切换至ABC模式
                 [:escape :escape nil {:alone :select_abc}]]}
                ;;
        {:des "Idea esc to Select ABC"
         :rules [:Idea
                ;; Idea App 下 esc切换至ABC模式
                 [:escape :escape nil {:alone :select_abc}]]}
                 ;;
        {:des "Chrome esc to Select ABC"
         :rules [:Chrome
                ;; Idea App 下 esc切换至ABC模式
                 [:escape :escape nil {:alone :select_abc}]]}
                 ;;
        {:des "VSCode esc to Select ABC"
         :rules [:VSCode
                ;; Idea App 下 esc切换至ABC模式
                 [:escape :escape nil {:alone :select_abc}]]}
                 ;;
        {:des "Obsidian esc to Select ABC"
         :rules [:Obsidian
                ;; Obsidian App 下 esc切换至ABC模式
                 [:escape :escape nil {:alone :select_abc}]]}
                 ;;
        ]
;; !  | means mandatory -   modifier(s) alone when pressend change behavior
    ;; #  | means optional  -   modifiers are optional (but at least one necessary)

    ;; :!Ca is keycode :a and prefix a with !C

    ;; C  | left_command
    ;; T  | left_control
    ;; O  | left_option
    ;; S  | left_shift
    ;; F  | fn
    ;; Q  | right_command
    ;; W  | right_control
    ;; E  | right_option
    ;; R  | right_shift

    ;; ## | optional any
    ;; !! | command + control + optional + shift (hyper)
 }
```
