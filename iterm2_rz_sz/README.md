# iTerm 如何使用rz 和sz (Mac)


1. 安装lrzsz
```brew install lrzsz```

2. 将两个脚本放到目录: /usr/local/bin/, 本给予权限chmod +x 
	- iterm2-recv-zmodem.sh
	- iterm2-send-zmodem.sh


3. 配置iTerm 的trigger
一次打开 iTerm > Preperences > Profiles > Default > Advanced.
点击Edit，配置以下两个规则：

```
Regular expression: rz waiting to receive.\*\*B0100
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-send-zmodem.sh
```
 
```
Regular expression: \*\*B00000000000000
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
```

4. 重启下iTerm2 后，输入rz/sz命令看, 可以弹出文件选择窗口了
