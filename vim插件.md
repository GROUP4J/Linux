##显示树形目录插件NERDTree安装和使用
安装：直接按照 https://github.com/scrooloose/nerdtree安装会导致无法使用，需要先安装pathogen,pathogen是管理插件的插件  
pathogen项目地址：项目地址 https://github.com/tpope/vim-pathogen  
在.vim文件夹下建立autoload和bundle目录 
从下载地址获取pathogen.vim文件，将其复制到autoload目录下 
在.vimrc文件中增加如下代码： 
call pathogen#infect() 
		——其实就是把pathogen.vim cp到～/.vim/autoload里就好了  


NERDTre安装：
项目地址：https://github.com/scrooloose/nerdtree
按照github安装方法1安装即可


参考文件：[vim 树形目录插件NERDTree安装](https://blog.csdn.net/gatieme/article/details/43889489)
