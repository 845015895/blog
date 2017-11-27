# md-http

## example
[blog.yizicheng.cn](blog.yizicheng.cn)

## install
    npm install

## use

    node index.js --path="your md path" --port [yourport]

## in linux server

可以用pm2守护后台运行，先安装pm2

use:

    pm2 start index.js -- --path="your md path" --port [yourport]

##tips
- 静态文件如图片都放在md文件下
- 因为存在对于md文件的时间判断，在list.ejs里面需要根据服务器windows系统和linux系统做一下修改:
    
    1.  在linux中需要用着一段代码判断时间格式：
        
             if (date.substring(6,10) === thisItem) {
                      date = date.substring(0,2) + "-" + date.substring(3,4);
             
           然后注释第二段用于windows系统的代码
    2.   在windows中需要用到这一段代码判断时间格式：
    
             if (date.substring(0,4) === thisItem) {
                       date = date.substring(5,9);
                       
         然后注释第一段用于windows系统的代码
         


## options

- path  
markdown文件路径 默认当前目录
- port  
端口号 默认3000



