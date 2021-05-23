# dwm

yang的Arch的dwm文件   

依赖解决项：  

    xorg  
    xorg-server  
    xorg-apps  
    xorg-xinit  
    
      ps：因为没有用登陆管理器，所以要安装xinit
  
安装的字体：  
  
    noto-fonts-cjk、fontawesome    
      ps:noto-fonts-cjk：不安装的话，中文无法正常显示，fontawesome：字符字体

需要编辑的文件：   
    
    ～/.xinitrc
    ----    
    #语言设置
    export LANG=zh_CN.UTF-8    
    export LANGUAGE=zh_CN:en_US    
    
    #feh    
    ~/.fehbg &

    #picom
    picom &

    #fcitx5
    fcitx5 &

    exec dwm
      
      ps：dianl和shij是状态栏显示的内容，while是循环输出  
          acpi是电量显示，需要自己安装，如果不是笔记本，就没必要了     
      
     
      
    ～/.bash_profile
    ----
    if [[ ! $DISPLAY && $XDG_VTNR -eq 1 ]]; then
    exec startx
    fi
    
      ps：如果使用的是zsh，则编辑～/.zprofile，也可以不编辑～/.bash_profile，输完密码之后执行startx即可
      
      
    ～/.pam——environment    
    GTK_IM_MODULE DEFAULT=fcitx
    QT_IM_MODULE  DEFAULT=fcitx
    XMODIFIERS    DEFAULT=\@im=fcitx
    SDL_IM_MODULE DEFAULT=fcitx
  
  使用的软件  
      
      fcitx5-im、fcitx5-rime、feh、chromium、dwm、dmenu、st、openvpn、picom、slstatus    
      fcitx5-im和fcitx5-rime：中文输入法    
      feh：看图、设置壁纸    
      chromium：浏览器
      dwm：窗口管理器
      dmenu：软件启动器
      st：终端模拟器
      openvpn：上网
      picom：透明窗口
      slstatus：设置状态栏
