## 1.5    SSH

SSH是一种网络协议，用于计算机之间的加密登录。

SSH只是一种协议，存在多种实现，既有商业实现，也有开源实现。本文针对的是[OpenSSH](http://www.openssh.com/)，它是自由软件，应用非常广泛。

如果要在Windows系统中使用SSH，会用到另一种软件[PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty)，我们后面用到的Git客户也集成了SSH

> putty使用后也会总结相关文档

格式：ssh user@host

user 代表真实存在的用户host代表要登录的远程计算机

常见有两种加密技术，分别是对称性加密和非对称性加密，SSH属于后者。

对称加密[算法](http://baike.baidu.com/view/7420.htm)在加密和解密时使用的是同一个密钥；而[非对称加密算法](http://baike.baidu.com/view/1490349.htm)需要两个[密钥](http://baike.baidu.com/view/934.htm)来进行加密和解密，这两个秘钥分别是[公开密钥](http://baike.baidu.com/view/1145160.htm)（public key，简称公钥）和私有密钥（private key，简称私钥）。

**工作原理**

公钥和私钥是成对出现，可以通过ssh-keygen -t rsa来创建，既可以通过密钥来加密数据，也可以通过私钥来加密数据，如果是以公钥进行的数据加密，只能与之相对应的私钥才可以解密，相反如果以私钥进行的数据加密，则只能与之对应的公钥才可以将数据进行解密，这样就可以提高信息传递的安全性。

**免密码登录**

我们可以将本地机器上的公钥保存到特定的远程计算机上，这样当我们再次登录访问这台远程计算机时就可以实现免密码登录了。

1、ssh-keygen -t rsa会创建公钥和密钥（默认在用户目录/.ssh目录下）

2、ssh-copy-id user@host添加到对应远程主机的用户目录/.ssh目录下

3、也可以登录远程主机，进入到用户目录/.ssh目录下手动创建authorized_keys文件，并将自已的公钥粘入该文件。
