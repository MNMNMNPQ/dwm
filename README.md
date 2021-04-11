# dwm

yang的Arch的dwm文件   

依赖解决项：  

    xorg  
    xorg-server  
    xorg-apps  
    xorg-xinit  
    
      ps：因为没有用登陆管理器，所以要安装xinit
  
安装的字体：  
  
    noto-fonts-cjk

需要编辑的文件：   
    
    ～/.xinitrc
    ----
    while true
    do

    dianl=`acpi | cut -d" " -f4 | cut -d% -f1`
    shij=`date +"%m/%d %H:%M"`
    xsetroot -name "${shij}|${dianl}"
    sleep 1
    done &

    exec dwm
      
      ps：dianl和shij是状态栏显示的内容，while是循环输出  
      
      
    ～/.bash_profile
    ----
    if [[ ! $DISPLAY && $XDG_VTNR -eq 1 ]]; then
    exec startx
    fi
    
      ps：如果使用的是zsh，则编辑～/.zprofile，也可以不编辑～/.bash_profile，输完密码之后执行startx即可
