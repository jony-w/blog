1. 生成SSH Key【主账户、附账户】

 ```cmd
    $ cd .ssh
    $ ssh-keygen -t rsa -C "xx@email.com"
       
    $Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa): github //可以重命名为github，方便区分
       
    $ ssh-keygen -t rsa -C "workemail@email.com"
       
    $Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa): work
    
        ... 后续直接回车到完成。
        
 ```
> github 经常用的设置为主账户
> work 不常用的设置为附账户


2. 配置config文件
    
    ```cmd
        
    cd ~/.ssh   // 进入ssh目录
    ls           //查看文件
    touch config  //且添加如下下内容【如果有省略】
    ```
    
    config 内容如下
    
    ```cmd
    
    Host github.com       //这个我就保持与HostName一致了
    HostName github.com   //对应仓库的站点
    User name               //用户名
    IdentityFile  ~/.ssh/github  //对应的ssh key 文件
       
    Host work.com
    HostName work.com
    User name
    IdentityFile  ~/.ssh/work 
            
    ```
3. clone 使用
    
    ```cmd
    
    当我们正常去clone代码的时候，给出的地址会是
    
    git clone git@github.com:xx/project1.git
     
    git clone git@work.com:xx/project2.git
      
    eg:
    github clone地址如:
    git@github.com:JonyShiw/react-native-webstrom.git
    
    1、主账户直接使用地址即可。
    2、附账户
    git@work.com:JonyShiw/react-native-webstrom.git
    
    
    ```cmd


