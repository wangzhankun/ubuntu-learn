# alias，unalias
alias 命令的作用时间是命令运行之后到 shell 会话结束，经常使用的别名可在 shell 的配置文件比如 C Shell（csh）的 ~/.cshrc 或 Bourne Again Shell 的 ~/.bashrc 里定义，如此当相应的 shell 会话启动后就可以使用这些自定义的别名了。      
# 终端机环境设置：stty,set
stty -a    
会显示出stty的设置内容，tty终端内的热键设置可以执行下列命令。    
stty erase ^h    
上述命令的意思就是，将erase（向前删除）的热键设置为【Ctrl+h】。如果想用【backspace】作为热键，就执行命令：               
stty erase ^?     
很多按键设置可以在文件/etc/inputrc找到。      
# 数据流重定向
*1.标准输入：（stdin）：代码为0，使用<或者<<;
2.标准输出：（stdout）：代码为1，使用>或者>>;
3.标准错误输出：（stderr）：代码为2，使用2>或者2>>。*

